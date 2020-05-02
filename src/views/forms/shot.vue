<template>
  <div>
    <formshot :data="data" :rules="formshot_rules" />
  </div>
</template>
<script>
import formshot from "@/components/forms/form-shot.vue";

export default {
  components: {
    formshot
  },
  data() {
    return {
      data: {},

      formshot_rules: {
        req: [v => !!v || "Item is required"],
        name: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Must be more than 2 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        email: [
          v => !!v || "Item is required",
          v => /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || "E-mail must be valid"
        ],
      reqm2: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Must be more than 2 characters"
        ],
        reqeq5: [
          v => !!v || "Item is required",
          v => (v && v.length == 5) || "Must be 5 Digit"
        ]
      }
    };
  }
};
</script>