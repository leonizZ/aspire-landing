<template>
  <v-col cols="12" class="page-section contact">
    <v-container :class="$vuetify.breakpoint.smAndDown ? 'px-8' : ''">
      <v-row>
        <v-col cols="12" sm="5">
          <h2 class="display-1 font-weight-bold">Let's Get In Touch!</h2>
          <p>Contact us if you have any questions, comments or complaints</p>

          <v-form ref="form" v-model="valid" lazy-validation class="mt-6">
            <v-text-field
              v-model="name"
              :rules="[rules.required]"
              label="Name"
              outlined
            ></v-text-field>
            <v-text-field
              v-model="email"
              :rules="[rules.email, rules.required]"
              label="E-mail"
              outlined
            ></v-text-field>

            <v-text-field
              v-model="phone"
              :rules="[rules.phone, rules.required]"
              label="Phone"
              outlined
            >
            </v-text-field>

            <v-textarea
              v-model="message"
              label="Message"
              :rules="[rules.required]"
              auto-grow
              rows="4"
              outlined
              row-height="20"
            >
            </v-textarea>

            <v-btn
              color="success"
              class="mr-4"
              rounded
              block
              depressed
              x-large
              @click="submit"
            >
              Submit
            </v-btn>
          </v-form>
        </v-col>

        <v-col>
          <div class="d-flex align-center">
            <v-icon>mdi-phone-in-talk-outline</v-icon>
            <p class="mb-0 ml-2">+63-9672151653</p>
          </div>
          <div class="d-flex align-center mb-4">
            <v-icon>mdi-map-outline</v-icon>
            <p class="mb-0 ml-2">
              2F, Unit-9, 2020 Travelers Inn, Accross LP Hypermart Food Court,
              Dumaguete City
            </p>
          </div>
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d921.6095787593279!2d123.2978444876293!3d9.301601245160654!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x33ab6f7e7a4ce797%3A0xb70b98036142ae49!2sAspire%20Credit%20and%20Lending%20Corporation!5e0!3m2!1sen!2sph!4v1627361401729!5m2!1sen!2sph"
            width="100%"
            height="350"
            style="border: 0"
            allowfullscreen="false"
            loading="lazy"
          ></iframe>
        </v-col>
      </v-row>
    </v-container>
  </v-col>
</template>

<script>
import forms from "@/mixins/forms";
import rules from "@/mixins/rules";
export default {
  mixins: [forms, rules],
  data() {
    return {
      valid: true,
      name: "",
      email: "",
      phone: "",
      message: "",
    };
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        this.contactForm({
          name: this.name,
          phone: this.phone,
          email: this.email,
          message: this.message,
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
