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
        positionnew: [v => !!v || "Item is required"],
        stratingdate: [v => !!v || "Item is required"],
        news: [v => !!v || "Item is required"],
        titlename: [v => !!v || "Item is required"],
        name: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        surname: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        nickt: [v => !!v || "Item is required"],
        email: [
          v => !!v || "Item is required",
          v => /.+@.+/.test(v) || "E-mail must be valid"
        ],
        tel: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        date4: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        height: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        weight: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_add: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_district: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_aumphur: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_proince: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_country: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_postaicode: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],// Edu valadate
        name_Level1: [v => !!v || "Item is required"],
        institute1: [v => !!v || "Item is required"],
        name_subject1: [v => !!v || "Item is required"],
        name_graduation1: [v => !!v || "Item is required"],
        name_understanding1: [v => !!v || "Item is required"],
        name_speaking1: [v => !!v || "Item is required"],
        name_reading1: [v => !!v || "Item is required"],
        name_writing1: [v => !!v || "Item is required"]
      }
    };
  }
};
</script>