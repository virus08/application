<template>
  <v-stepper v-model="e6" vertical>
    <v-stepper-step :complete="e6 > 1" step="1">
      Personal data
      <small>ประวัติส่วนบุคคล</small>
    </v-stepper-step>

    <v-stepper-content step="1">
      <neung :thisid="thisid" />
      <v-divider />
    </v-stepper-content>

    <v-stepper-step :complete="e6 > 2" step="2">Education background
         <small>ประวัติการศึกษา</small>
    </v-stepper-step>
    <v-stepper-content step="2">
      <iaeo/>
      <v-btn color="green accent-1" @click="$refs.menu.save(editedItem.date)">Confirmed</v-btn>
      <v-btn color="primary" @click="e6 = 3">Continue</v-btn>
      <v-btn text>Cancel</v-btn>
    </v-stepper-content>

    <v-stepper-step :complete="e6 > 3" step="3">Employment Record
        <small>ประวัติการทำงาน</small>
    </v-stepper-step>
    <v-stepper-content step="3">
      <ipat1/>
      <v-btn color="green accent-1" @click="$refs.menu.save(editedItem.date)">Confirmed</v-btn>
      <v-btn color="primary" @click="e6 = 4">Continue</v-btn>
      <v-btn text>Cancel</v-btn>
    </v-stepper-content>

    <v-stepper-step step="4">คำถามจากบริษัท VSTECS
        <small>กรุณาตอบคำถามตามความคิดเห็นอย่างตรงไปตรงมาที่สุด</small>
    </v-stepper-step>
    <v-stepper-content step="4">
      <ipat2/>
      <v-btn color="green accent-1" @click="$refs.menu.save(editedItem.date)">Confirmed</v-btn>
      <v-btn color="primary" @click="e6 = 1">Continue</v-btn>
      <v-btn text>Cancel</v-btn>
    </v-stepper-content>
  </v-stepper>
</template>
<script>
import neung from "@/components/neung.vue";
import iaeo from "@/components/iaeo.vue";
import ipat1 from "@/components/ipat1.vue";
import ipat2 from "@/components/ipat2.vue";
export default {
  components: {
    neung,
    iaeo,
    ipat1,
    ipat2
  },
  data() {
    return {
      e6: 1,
      thisid: null
    };
  },
  methods: {
    async init() {
      let urldata = process.env.VUE_APP_DATA
      let res = await axios({
        method: "post",
        url: urldata,
        data:{}
      });
      this.thisid=res.data.id
    }
  },
  mounted() {
    this.init();
  }
};
</script>