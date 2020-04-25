<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row>
          <v-chip class="ma-5">ระดับการศึกษา/ Education level</v-chip>
        </v-row>

        <v-row>
          <v-chip class="ma-5">ประถมศึกษา/Primary School</v-chip>

          <v-col cols="4">
            <v-text-field
              v-model="datain.institute1"
              label="ชื่อสถานศึกษาและที่ตั้ง"
              prepend-inner-icon="mdi-city"
              hint="Name of Institution/Location"
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-text-field
             v-model="datain.country1" 
             label="ประเทศ" hint="Country" dense outlined
             ></v-text-field>
          </v-col>

          <v-subheader>ปีที่ศึกษา<br />Period</v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yIn1" 
             label="จาก (ค.ศ.)" hint="From (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yout1" 
             label="ถึง (ค.ศ.)" hint="To (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>
            คะแนนเฉลี่ย
            <br />G.P.A
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.grade1" label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            วุฒิการศึกษา
            <br />Degree/Cert.
          </v-subheader>
          <v-col cols="2">
            <v-text-field
              v-model="datain.degree1"
              label="วุฒิการศึกษา"
              hint="Degree/Cert."
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major1" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept1" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">มัธยมศึกษา/Secondary School</v-chip>

          <v-col cols="4">
            <v-text-field
              v-model="datain.institute2"
              label="ชื่อสถานศึกษาและที่ตั้ง"
              prepend-inner-icon="mdi-city"
              hint="Name of Institution/Location"
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-text-field
             v-model="datain.country2" 
             label="ประเทศ" hint="Country" dense outlined
             ></v-text-field>
          </v-col>

          <v-subheader>ปีที่ศึกษา<br />Period</v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yIn2" 
             label="จาก (ค.ศ.)" hint="From (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yout2" 
             label="ถึง (ค.ศ.)" hint="To (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>


        <v-row>
          <v-subheader>
            คะแนนเฉลี่ย
            <br />G.P.A
          </v-subheader>
          <v-col cols="2">
            <v-text-field 
            v-model="datain.grade2" 
            label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วุฒิการศึกษา
            <br />Degree/Cert.
          </v-subheader>
          <v-col cols="2">
            <v-text-field
              v-model="datain.degree2"
              label="วุฒิการศึกษา"
              hint="Degree/Cert."
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major2" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept2" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">ปริญญาตรี/Bachelor's Degree</v-chip>

          <v-col cols="4">
            <v-text-field
              v-model="datain.institute3"
              label="ชื่อสถานศึกษาและที่ตั้ง"
              prepend-inner-icon="mdi-city"
              hint="Name of Institution/Location"
              dense
              outlined
            ></v-text-field>
          </v-col>

         <v-col cols="2">
            <v-text-field
             v-model="datain.country3" 
             label="ประเทศ" hint="Country" dense outlined
             ></v-text-field>
          </v-col>

           <v-subheader>ปีที่ศึกษา<br />Period</v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yIn3" 
             label="จาก (ค.ศ.)" hint="From (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yout3" 
             label="ถึง (ค.ศ.)" hint="To (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>
            คะแนนเฉลี่ย
            <br />G.P.A
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.grade3" label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            วุฒิการศึกษา
            <br />Degree/Cert.
          </v-subheader>
          <v-col cols="2">
            <v-text-field
              v-model="datain.degree3"
              label="วุฒิการศึกษา"
              hint="Degree/Cert."
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major3" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept3" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">ปริญญาโท/Master's Degree</v-chip>

          <v-col cols="4">
            <v-text-field
              v-model="datain.institute4"
              label="ชื่อสถานศึกษาและที่ตั้ง"
              prepend-inner-icon="mdi-city"
              hint="Name of Institution/Location"
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-text-field
             v-model="datain.country4" 
             label="ประเทศ" hint="Country" dense outlined
             ></v-text-field>
          </v-col>

          <v-subheader>ปีที่ศึกษา<br />Period</v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yIn4" 
             label="จาก (ค.ศ.)" hint="From (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yout4" 
             label="ถึง (ค.ศ.)" hint="To (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>


        <v-row>
          <v-subheader>
            คะแนนเฉลี่ย
            <br />G.P.A
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.grade4" label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            วุฒิการศึกษา
            <br />Degree/Cert.
          </v-subheader>
          <v-col cols="2">
            <v-text-field
              v-model="datain.degree4"
              label="วุฒิการศึกษา"
              hint="Degree/Cert."
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major4" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept4" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">อื่นๆ/Others</v-chip>

          <v-col cols="2">
            <v-text-field
              v-model="datain.name_Level5"
              label="ระดับการศึกษา"
              hint="Level"
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-col cols="3">
            <v-text-field
              v-model="datain.institute5"
              label="ชื่อสถานศึกษาและที่ตั้ง"
              prepend-inner-icon="mdi-city"
              hint="Name of Institution/Location"
              dense
              outlined
            ></v-text-field>
          </v-col>

         <v-col cols="2">
            <v-text-field
             v-model="datain.country5" 
             label="ประเทศ" hint="Country" dense outlined
             ></v-text-field>
          </v-col>

           <v-subheader>ปีที่ศึกษา<br />Period</v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yIn5" 
             label="จาก (ค.ศ.)" hint="From (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="1">
            <v-text-field
             v-model="datain.yout5" 
             label="ถึง (ค.ศ.)" hint="To (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>
            คะแนนเฉลี่ย
            <br />G.P.A
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.grade5" label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            วุฒิการศึกษา
            <br />Degree/Cert.
          </v-subheader>
          <v-col cols="2">
            <v-text-field
              v-model="datain.degree5"
              label="วุฒิการศึกษา"
              hint="Degree/Cert."
              dense
              outlined
            ></v-text-field>
          </v-col>

          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major5" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept5" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-col cols="4">
            <v-checkbox v-model="datain.name_studying" label="ปัจจุบันศึกษาต่อ/ Studying"></v-checkbox>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>
            ระดับการศึกษา
            <br />Level
          </v-subheader>
          <v-col cols="4">
            <v-autocomplete
              v-model="datain.name_Level6"
              :items="lists[0].data"
              outlined
              dense
              chips
              small-chips
              label="ระดับการศึกษา"
              hint=" Level"
              
            ></v-autocomplete>
          </v-col>

          <v-subheader>
            ศึกษาต่ออยู่ที่
            <br />Institute
          </v-subheader>
          <v-col cols="4">
            <v-text-field
              v-model="datain.institute6"
              label="ศึกษาต่ออยู่ที่"
              hint="Institute"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>
            วิชาเอก
            <br />Major
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.major6" label="วิชาเอก" hint="Major" dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            คณะ
            <br />Dept.
          </v-subheader>
          <v-col cols="2">
            <v-text-field v-model="datain.name_dept6" label="คณะ" hint="Dept." dense outlined></v-text-field>
          </v-col>

          <v-subheader>
            ปีที่จบ
            <br />Year to Graduate
          </v-subheader>
          <v-col cols="2">
            <v-text-field
             v-model="datain.yIn6" 
             label="ปีที่เริ่มการศึกษา (ค.ศ.)" hint="Start Year (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
          <v-subheader> _ </v-subheader>
           <v-col cols="2">
            <v-text-field
             v-model="datain.yout6" 
             label="ปีที่คาดว่าจะจบ (ค.ศ.) " hint="Expected year (A.D.)" dense outlined
             ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">งานอดิเรก/ Hobbies</v-chip>
        </v-row>

        <v-row>
          <v-col cols="2" sm="6" md="6">
            <v-container fluid>
              <hobbies />
            </v-container>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">กีฬา/ Sports</v-chip>
        </v-row>

        <v-row>
          <v-col cols="2" sm="6" md="6">
            <v-container fluid>
              <sports />
            </v-container>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">มียานพาหนะเป็นของตัวเอง / Vehicle</v-chip>
        </v-row>

        <v-row>
          <v-col cols="12" sm="2">
            <v-checkbox v-model="datain.name_car" label="รถยนต์/Car" value="รถยนต์/Car"></v-checkbox>
          </v-col>
          <v-col cols="12" sm="3">
            <v-checkbox
              v-model="datain.name_motorcycle"
              label="รถจักรยานยนต์ / Motorcycle"
              value="รถจักรยานยนต์ / Motorcycle"
            ></v-checkbox>
          </v-col>
          <v-col cols="12" sm="3">
            <v-checkbox
              v-model="datain.name_have"
              label="ไม่มี / Don't have"
              value="ไม่มี / Don't have"
            ></v-checkbox>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">ความสามารถพิเศษ/ Special Ability</v-chip>
        </v-row>

        <v-row>
          <v-subheader>ด้านความสามารถพิเศษ/ Skill</v-subheader>
        </v-row>

        <v-row>
        <v-col cols="2" sm="6" md="6">
            <v-container fluid>
              <skill />
            </v-container>
          </v-col>
        </v-row>

        <v-row>
          <v-subheader>ด้านคอมพิวเตอร์/ Computer Skill</v-subheader>
        </v-row>

        <v-row>
          <v-col cols="1" sm="3" md="3">
            <v-container fluid>
              <software />
            </v-container>
          </v-col>
          <v-col cols="1" sm="3" md="3">
            <v-container fluid>
              <hardware />
            </v-container>
          </v-col>
          <v-col cols="1" sm="3" md="3">
            <v-container fluid>
              <certificate />
            </v-container>
          </v-col>
          <v-col cols="1" sm="3" md="3">
            <v-container fluid>
              <others />
            </v-container>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">ด้านภาษาต่างประเทศ/ Proficiency in language</v-chip>
        </v-row>
        <v-row>
          <v-subheader>อังกฤษ / English</v-subheader>
          <v-col cols="2.5">
            <v-autocomplete
              v-model="datain.name_understanding1"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="เข้าใจ"
              prepend-inner-icon="mdi-lightbulb-on"
              hint=" Understanding"
            ></v-autocomplete>
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="datain.name_speaking1"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="พูด"
              prepend-inner-icon="mdi-comment-processing"
              hint="Speaking"
            ></v-autocomplete>
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="datain.name_reading1"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="อ่าน"
              prepend-inner-icon="mdi-book-open-variant"
              hint="Reading"
            ></v-autocomplete>
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="datain.name_writing1"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="เขียน"
              prepend-inner-icon="mdi-lead-pencil"
              hint="Writing"
            ></v-autocomplete>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">อื่นๆ / Others</v-chip>
        </v-row>

        <v-row>
          <v-subheader>ภาษา/ Language</v-subheader>
          
           <v-col cols="2.5">
            <v-text-field v-model="datain.name_dept2" 
            label="ภาษา" hint="Language" dense outlined></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_understanding2"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="เข้าใจ"
              prepend-inner-icon="mdi-lightbulb-on"
              hint="Understanding"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_speaking2"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="พูด"
              prepend-inner-icon="mdi-comment-processing"
              hint="Speaking"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_reading2"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="อ่าน"
              prepend-inner-icon="mdi-book-open-variant"
              hint="Reading"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_writing2"
              :items="lists[1].data"
              outlined
              dense
              chips
              small-chips
              label="เขียน"
              prepend-inner-icon="mdi-lead-pencil"
              hint="Writing"
            ></v-autocomplete>
          </v-col>
        </v-row>
      </v-form>
      <v-row>
        <v-spacer />
        <v-col>
          <v-btn color="primary" :disabled="!valid" @click="save()">Continue</v-btn>
        </v-col>
        <v-col>
          <v-btn color="primary" @click="back()">Back</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>


<script>
//import HelloWorld from '@/components/HelloWorld.vue'
import hobbies from "@/components/hobbies.vue";
import sports from "@/components/sports.vue";
import software from "@/components/software.vue";
import hardware from "@/components/hardware.vue";
import certificate from "@/components/certificate.vue";
import others from "@/components/others.vue";
import skill from "@/components/skill.vue";
export default {
  props: ["thisid"],
  components: {
    hobbies,
    sports,
    software,
    hardware,
    certificate,
    skill,
    others
  },
  data: () => ({
    datain: {
      institute1: "",
      country1: "",
      yIn1: "",
      yout1: "",
      grade1: "",
      degree1: "",
      major1: "",
      name_dept1: "",
      institute2: "",
      country2: "",
      yIn2: "",
      yout2: "",
      grade2: "",
      degree2: "",
      major2: "",
      name_dept2: "",
      institute3: "",
      country3: "",
      yIn3: "",
      yout3: "",
      grade3: "",
      degree3: "",
      major3: "",
      name_dept3: "",
      institute4: "",
      country4: "",
      yIn4: "",
      yout4: "",
      grade4: "",
      degree4: "",
      major4: "",
      name_dept4: "",
      name_Level5: "",
      institute5: "",
      country5: "",
      yIn5: "",
      yout5: "",
      grade5: "",
      degree5: "",
      major5: "",
      name_dept5: "",
      name_level6: "",
      institute6: "",
      major6: "",
      name_dept6: "",
      yIn6: "",
      yout6: "",
      name_studying: "",
      name_car: "",
      name_motorcycle: "",
      name_have: "",
      name_understanding1: "",
      name_speaking1: "",
      name_reading1: "",
      name_writing1: "",
      name_language2: "",
      name_understanding2: "",
      name_speaking2: "",
      name_reading2: "",
      name_writing2: ""
    },
    data: null,
    lists: [],
    valid: false
  }),
  mounted() {
    this.getLists();
  },
  methods: {
    getLists: async function() {
      let listurl = process.env.VUE_APP_LIST;
      console.log(listurl);
      let res = await axios({
        method: "get",
        url: listurl
      });
      this.lists = res.data;
      console.log(this.lists);
    },
    back() {
      this.$parent.$parent.$parent.e6 = 1;
    },
    async save() {
      let urldata = process.env.VUE_APP_DATA;
      let res = await axios({
        method: "get",
        url: urldata + "/" + this.thisid
      });
      this.data = res.data;
      console.log(this.data);
      this.$parent.$parent.$parent.e6 = 3;
      let obj = Object.assign(this.data, this.datain);
      console.log(obj);
      res = await axios({
        method: "put",
        url: urldata + "/" + this.thisid,
        data: obj
      });
    }
  },
  mounted() {
    this.getLists();
  }
};
</script>
 


