<template>
    <input id="maskedInput" v-model="localValue" v-on:input="test">
</template>

<script>
  import $ from 'jquery';
  import 'jquery.maskedinput/src/jquery.maskedinput';

  export default {
    name: "mask-input",
    props: ["value", "mask"],
    data() {
      return {
        localValue: null
      }
    },
    mounted: function () {
      let vm = this
      let elem = $(this.$el)
      $(this.$el).val(this.value)
      elem.mask(this.mask,  {
        autoclear: false,
        completed: function() {
          vm.$emit("input", this.val());
        }
      });
      this.localValue = this.value;
      console.log('Velu', $(this.$el).val())
    },
    methods: {
      test: function () {
        console.log($(this.$el).val())
      }
    },
    watch: {
      localValue: function () {
        this.$emit("input", this.localValue);
      },
      value: function () {
        this.localValue = this.value;
      }
    },
  }
</script>

<style scoped>

</style>
