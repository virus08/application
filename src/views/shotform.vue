<template>
  <v-stepper v-model="e1">
    <v-stepper-header>
      <v-stepper-step :complete="e1 > 1" step="1">ประวัติส่วนบุคคล/Personal Data</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step :complete="e1 > 2" step="2">ประวัติการศึกษา/Education</v-stepper-step>

      <v-divider></v-divider>

      <v-stepper-step step="3">ประวัติการทำงาน/Employment</v-stepper-step>
    </v-stepper-header>

    <v-stepper-items>
      <v-stepper-content step="1">
          <shotpersonal :thisid="thisid" />
          <shoteducation :thisid="thisid" />
          <shotemployment :thisid="thisid" />
      </v-stepper-content>

      <v-stepper-content step="2">
      </v-stepper-content>

      <v-stepper-content step="3">
      </v-stepper-content>
    </v-stepper-items>
  </v-stepper>
</template>
<script>
import shotpersonal from "@/components/shotpersonal.vue";
import shoteducation from "@/components/shoteducation.vue";
import shotemployment from "@/components/shotemployment.vue";
  export default {
      components: {
          shotpersonal,
          shotemployment,
          shoteducation
      },
    data () {
        components: 
      return {
        e1: 1,
      }
    },
  }
</script>