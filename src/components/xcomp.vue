<template>
  <v-container>
    <v-row>
      <!-- ยังใช้งานไม่ได้ date brihtday -->
      <v-col cols="3">
        <v-row>
          <v-col cols="5">
            <v-subheader>
              วันเกิด
              <br />Brith Date
            </v-subheader>
          </v-col>
          <v-col cols="7">
            <v-dialog
              ref="dialog"
              v-model="Brith_Date_Model"
              :return-value.sync="start_date"
              persistent
              width="290px"
            >
              <template v-slot:activator="{ on }">
                <v-text-field v-model="Brith_Date" label="วัน/เดือน/ปี*" readonly v-on="on"></v-text-field>
              </template>
              <v-date-picker v-model="Brith_Date" scrollable>
                <v-spacer></v-spacer>
                <v-btn text color="primary" @click="Brith_Date_Model = false">Cancel</v-btn>
                <v-btn text color="primary" @click="$refs.dialog.save(start_date)">OK</v-btn>
              </v-date-picker>
            </v-dialog>
          </v-col>
        </v-row>
      </v-col>

      <v-col cols="2">
        <v-row>
          <v-col cols="3"></v-col>
          <v-col cols="7">
            <v-text-field disabled v-model="comp_age" label="อายุ/Age" hint="Age"></v-text-field>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
var moment = require('moment');
export default {
  data() {
    return {
      Brith_Date_Model: false,
      start_date: new Date().toISOString().substr(0, 10),
      Brith_Date: new Date().toISOString().substr(0, 10),
      age: null
    };
  },
  computed: {
    comp_age: function() {
      let yy = moment().diff(this.Brith_Date, 'years',false); 
      let mo = moment().diff(this.Brith_Date, 'months',false); 
      let xx = mo-yy*12 
      return yy + '(' + xx + '/12)' ;
    }
  }
};
</script>


