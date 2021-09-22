<template>
  <v-form ref="form" v-model="valid" lazy-validation class="mt-3">
    <h3 class="title">
      How much money do you need?
      <span class="orange--text text--darken-3 font-weight-bold"
        >₱ {{ value }}</span
      >
    </h3>
    <v-slider
      v-model="value"
      class="align-center mb-4"
      color="orange darken-3"
      track-color="grey"
      :step="step"
      :max="max"
      :min="min"
      :rules="rules"
      hint="The amount will increase with repeated borrowing"
      persistent-hint
    >
    </v-slider>
    <v-text-field
      v-model="name"
      :rules="[rules.required]"
      label="Name"
      outlined
      required
    ></v-text-field>

    <v-text-field
      v-model="phone"
      :rules="[rules.phone, rules.required]"
      label="Phone"
      outlined
      required
    >
    </v-text-field>

    <v-btn
      color="success"
      class="mr-4 px-16"
      rounded
      depressed
      x-large
      @click.prevent="submit"
    >
      Apply Now
    </v-btn>
  </v-form>
</template>

<script>
import forms from "@/mixins/forms";
import rules from "@/mixins/rules";

export default {
  mixins: [forms, rules],
  data: () => ({
    valid: true,
    name: "",
    phone: "",
    value: 1000,
    min: 1000,
    max: 20000,
    step: 500,
    rules: [],
  }),

  computed: {
    test() {
      if (this.value <= 5000) {
        return this.rules == "Only for repeated Clients";
      } else {
        return "";
      }
    },
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        this.requestLoan({
          name: this.name,
          phone: this.phone,
          value: this.value,
          // app_code: window.SETTINGS.APP_CODE
        });
      }
    },
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    },
  },
};
</script>
