<template>
  <div class="container mt-5">

    <div class="row justify-content-md-center mb-3">
      <div class="col col-lg-1">
        Date:
      </div>
      <div class="col-md-auto">
        <mask-input v-model="inputDateValue" mask="99/99/9999"></mask-input>
      </div>
      <div class="col col-lg-2">
        {{ inputDateValue }}
      </div>
    </div>
    <div class="row justify-content-md-center mb-3">
      <div class="col col-lg-1">
        Phone:
      </div>
      <div class="col-md-auto">
        <mask-input v-model="inputPhoneValue" mask="(999) 999-9999"></mask-input>
      </div>
      <div class="col col-lg-2">
        {{ inputPhoneValue }}
      </div>
    </div>
    <div class="row justify-content-md-center mb-3">
      <div class="col col-lg-1">
        Tin:
      </div>
      <div class="col-md-auto">
        <mask-input v-model="inputTinValue" mask="99-9999999"></mask-input>
      </div>
      <div class="col col-lg-2">
        {{ inputTinValue }}
      </div>
    </div>
    <div class="row justify-content-md-center mb-3">
      <div class="col col-lg-1">
        Ssn:
      </div>
      <div class="col-md-auto">
        <mask-input v-model="inputSsnValue" mask="999-99-9999"></mask-input>
      </div>
      <div class="col col-lg-2">
        {{ inputSsnValue }}
      </div>
    </div>
  </div>
</template>

<style lang="less">
#app {
  text-align: center;
  color: #2c3e50;
}
</style>
  <script>
  import MaskInput from "./components/mask-input";
  export default {
    data() {
      return {
        inputPhoneValue: 111,
        inputDateValue: 111,
        inputTinValue: 1111,
        inputSsnValue: 111
      }
    },
    mounted() {
      console.log(this.$el)
    },
    components: {MaskInput}
  }
</script>
