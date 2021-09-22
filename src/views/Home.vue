<template>
  <v-row class="">
    <v-col cols="12" class="height-100 d-flex align-center" id="home">
      <v-container :class="$vuetify.breakpoint.smAndDown ? 'px-6' : ''">
        <v-row>
          <v-col cols="12" sm="5">
            <h1 class="display-2 font-weight-bold green--text">
              0% Interest rate
            </h1>
            <h4 class="title mb-0 font-weight-light">
              For the first loan if paid back in due time
            </h4>

            <loan-form></loan-form>
          </v-col>
          <v-col cols="12" sm="7">
            <v-img height="500" contain src="../assets/intro.png" alt="" />
          </v-col>
        </v-row>
      </v-container>
    </v-col>

    <v-col cols="12" class="page-section about white--text text-center">
      <v-container>
        <h2 class="display-1 font-weight-bold">About Us</h2>
        <div class="divider my-8"></div>
        <h6 class="title font-weight-normal">
          Aspire Credit and Lending Corp is committed to becoming the leading
          institution in providing a quality, affordable, trustworthy and easier
          financing scheme to bridge the gap between you and your aspirations in
          life.
        </h6>

        <v-btn
          rounded
          color="default"
          x-large
          depressed
          dark
          class="mt-6"
          href="#contact"
        >
          Apply for a Loan
        </v-btn>
      </v-container>
    </v-col>

    <v-col cols="12" class="page-section steps text-center" id="services">
      <v-container>
        <h2 class="display-1 font-weight-bold mb-6">
          4 Easy Steps to get a Cash Loan
        </h2>
        <div class="divider my-10 green"></div>
        <v-row>
          <v-col cols="12" sm="3">
            <v-icon color="green" size="40">
              mdi-clipboard-edit-outline
            </v-icon>

            <h4 class="title">1.Apply for Loan</h4>
            <p>
              Let us know more about you. Complete the application process in 3
              minutes
            </p>
          </v-col>
          <v-col cols="12" sm="3">
            <v-icon color="green" size="40"> mdi-clock-check-outline </v-icon>

            <h4 class="title">2.Wait for approval</h4>
            <p>
              In a few minutes you will receive our decision thru SMS or call
            </p>
          </v-col>
          <v-col cols="12" sm="3">
            <v-icon color="green" size="40"> mdi-cash-multiple </v-icon>

            <h4 class="title">3.Receive your money and enjoy</h4>
            <p>You'll receive money in less than 5 minutes (using InstaPay)</p>
          </v-col>
          <v-col cols="12" sm="3">
            <v-icon color="green" size="40">
              mdi-calendar-check-outline
            </v-icon>

            <h4 class="title">4.Make repayment</h4>
            <p>
              Pay via Gcash, at 7-11, via online banking or via 5000+ branches
              nationwide.
            </p>
          </v-col>
        </v-row>
      </v-container>
    </v-col>

    <v-col
      cols="12"
      class="page-section eligible blue-grey darken-4 white--text"
    >
      <v-container :class="$vuetify.breakpoint.smAndDown ? 'px-8' : ''">
        <h2 class="display-1 font-weight-bold mb-6">
          Who is eligible to apply?
        </h2>

        <v-row no-gutters>
          <v-col cols="12" sm="3" class="d-flex align-center">
            <v-icon large color="green"> mdi-check-decagram </v-icon>
            <p class="mb-0 subtitle-1 ml-2">You are age 22 - 70 years old</p>
          </v-col>
          <v-col cols="12" sm="3" class="d-flex align-center">
            <v-icon large color="green"> mdi-check-decagram </v-icon>
            <p class="mb-0 subtitle-1 ml-2">
              Located in the Philippinas (nationwide)
            </p>
          </v-col>
          <v-col cols="12" sm="3" class="d-flex align-center">
            <v-icon large color="green"> mdi-check-decagram </v-icon>
            <p class="mb-0 subtitle-1 ml-2">
              Employed individuals or selected professionals
            </p>
          </v-col>
          <v-col cols="12" sm="3" class="d-flex align-center">
            <v-icon large color="green"> mdi-check-decagram </v-icon>
            <p class="mb-0 subtitle-1 ml-2">
              Have a valid bank or e-wallet account
            </p>
          </v-col>
        </v-row>
      </v-container>
    </v-col>
    <!-- Contact Section -->
    <contact-form id="contact"></contact-form>
    <v-col cols="12" class="footer text-center grey lighten-5 py-6">
      <p class="mb-0 body-1 grey--text text-darken-4">
        Copyright © 2021 - Aspire Credit and Lending Corporation
      </p>
    </v-col>
  </v-row>
</template>
<script>
import LoanForm from "@/components/LoanForm.vue";
import ContactForm from "@/components/ContactForm.vue";

export default {
  data: () => ({}),
  components: {
    LoanForm,
    ContactForm,
  },
};
</script>
