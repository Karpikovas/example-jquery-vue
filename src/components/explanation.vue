<template>
    <input type="text" ref="input" :value="value">
</template>

<script>

  export default {
    name: 'mask-wrapper',
    props: {
      value: String,
      mask: String
    },
    watch: {
      value(newValue, oldValue) {
        if (newValue !== oldValue) {
          this.jMask.val(newValue);
        }
      },
      mask(newValue) {
        this.jMask....
      }
    },

    date() {
      return {
        jMask: null
      }
    },
    mounted() {
      this.jMask = $.mask(...this.refs.input.... this.mask );
      this.jMask.on('input', onInput);
    },
    beforeDestroy() {
      // deattach mask
    },
    methods: {
      onInput(ev) {
        this.$emit('input', ev.value);
      }
    }
  }

</script>


obj = {...}
obj.foo() { /* this = obj */ }
obj.foo = function() { /* this = obj */ }

obj.foo = () => { /* this = ? */ }
