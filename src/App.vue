<template>
  <div id="app">
    <div class="container">
      <VuePhoneNumberInput
        id="phoneNumber1"
        v-model="phoneNumber"
        color="dodgerblue"
        :dark="dark"
        :disabled="disabled"
        :ignored-countries="countriesIgnored"
        :preferred-countries="countriesList"
        :loader="hasLoaderActive"
        clearable
        :error="hasErrorActive"
        class="mb-2"
        @update="onUpdate"
      />
      <b>v-model</b> : {{ phoneNumber }}
    </div>
  </div>
</template>

<script>
import VuePhoneNumberInput from "vue-phone-number-input";
export default {
  name: "App",
  components: {
    VuePhoneNumberInput,
  },
  data() {
    return {
      phoneNumber: null,
      defaultCountry: "FR",
      countriesList: ["FR", "BE", "DE"],
      countriesIgnored: ["AF", "AD", "AL"],
      dark: false,
      disabled: false,
      hasLoaderActive: false,
      hasErrorActive: false,
    };
  },
  methods: {
    onUpdate(payload) {
      this.results = payload;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
