<template>
  <v-snackbar
    class="main-snackbar"
    :color="snackbar.color"
    v-model="snackbar.show"
    :bottom="snackbar.position == 'bottom'"
    :centered="snackbar.position == 'centered'"
    :left="snackbar.position == 'left'"
    :right="snackbar.position == 'right'"
    :top="snackbar.position == 'top'"
    :timeout="snackbar.timeout"
    @input="$store.dispatch('snackbarHide')"
    dark
    content-class="overflow-auto"
  >
    {{ snackbar.message }}
    <template v-slot:action="{ attrs }">
      <v-btn icon @click="$store.dispatch('snackbarHide')">
        <v-icon small v-bind="attrs">mdi-close</v-icon>
      </v-btn>
    </template>
  </v-snackbar>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      snackbar: "getSnackbar",
    }),
  },
};
</script>
