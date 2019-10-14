<template>
    <input id="maskedInput" ref="input" :value="value">
</template>

<script>
import $ from 'jquery';
import 'jquery.maskedinput/src/jquery.maskedinput';
import Inputmask from "inputmask";

export default {
    name: "mask-input",
    props: ["value", "mask"],
    data() {
        return {
            jMask: null
        }
    },
    mounted: function () {

        let im = new Inputmask(
            '9999-9999-9999-9999[-99]',
            {greedy: false}
        )

        im.mask(this.$refs.input)
        this.JMask = $(this.$refs.input)
        this.JMask.on('input', (event) => this.$emit('input', event.target.value))
    }
}
</script>

<style scoped>

</style>
