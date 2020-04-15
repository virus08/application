<template>
  <v-card>
    <v-container fluid>
    <v-form ref="form" v-model="valid">
     
      <v-row>
        <v-chip class="ma-5">ระดับการศึกษา/ Education level</v-chip>
      </v-row>
      
      <v-row>
         <v-chip class="ma-5">ประถมศึกษา/Primary School</v-chip>
              
  
        <v-col cols="3">
          <v-text-field
          
            label="ชื่อสถานศึกษาและที่ตั้ง"
            prepend-inner-icon="mdi-city"
            hint="Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="1">
          <v-text-field label="ประเทศ" hint="Country" dense outlined>
          </v-text-field>
        </v-col>
        
        <v-subheader>
                ปีที่ศึกษา/Period 
              </v-subheader>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="year" class="px-2" 
          label="จาก (ค.ศ.) / From (A.D.)" type="number"></v-text-field>
        </v-col>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="yea" class="px-2" label="ถึง (ค.ศ.) / To (A.D.)" type="number">
          </v-text-field>
        </v-col> 
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย<br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>
      <v-row>
         <v-chip class="ma-5">มัธยมศึกษา/Secondary School</v-chip>
              
  
        <v-col cols="3">
          <v-text-field
            label="ชื่อสถานศึกษาและที่ตั้ง"
            prepend-inner-icon="mdi-city"
            hint="Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="1">
          <v-text-field label="ประเทศ" hint="Country" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                ปีที่ศึกษา/Period
              </v-subheader>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="year" class="px-2" 
          label="จาก (ค.ศ.) / From (A.D.)" type="number"></v-text-field>
        </v-col>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="yea" class="px-2" label="ถึง (ค.ศ.) / To (A.D.)" type="number">
          </v-text-field>
        </v-col> 
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย<br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>

      <v-row>
          <v-chip class="ma-5">ปริญญาตรี/Bachelor's Degree</v-chip>
  
        <v-col cols="3">
          <v-text-field
            label="ชื่อสถานศึกษาและที่ตั้ง"
            prepend-inner-icon="mdi-city"
            hint="Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="1">
          <v-text-field label="ประเทศ" hint="Country" dense outlined>
          </v-text-field>
        </v-col>

        <v-subheader>
                ปีที่ศึกษา/Period
              </v-subheader>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="year" class="px-2" 
          label="จาก (ค.ศ.) / From (A.D.)" type="number"></v-text-field>
        </v-col>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="yea" class="px-2" label="ถึง (ค.ศ.) / To (A.D.)" type="number">
          </v-text-field>
        </v-col> 
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย<br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>

      <v-row>
         <v-chip class="ma-5">ปริญญาโท/Master's Degree</v-chip>
  
        <v-col cols="3">
          <v-text-field
            label="ชื่อสถานศึกษาและที่ตั้ง"
            prepend-inner-icon="mdi-city"
            hint="Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="1">
          <v-text-field label="ประเทศ" hint="Country" dense outlined>
          </v-text-field>
        </v-col>
        
        <v-subheader>
                ปีที่ศึกษา/Period
              </v-subheader>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="year" class="px-2" 
          label="จาก (ค.ศ.) / From (A.D.)" type="number"></v-text-field>
        </v-col>
        <v-col cols="6" sm="2">
          <v-text-field v-model.number="yea" class="px-2" label="ถึง (ค.ศ.) / To (A.D.)" type="number">
          </v-text-field>
        </v-col> 
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย<br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>
      <v-row>
         <v-chip class="ma-5">อื่นๆ/Others</v-chip>
  
        
        <v-col cols="2">
          <v-text-field label="ระดับการศึกษา" hint="Level" dense outlined>
          </v-text-field>
        </v-col>
       

        <v-col cols="3">
          <v-text-field
            label="ชื่อสถานศึกษาและที่ตั้ง"
            prepend-inner-icon="mdi-city"
            hint="Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="2">
          <v-text-field label="ประเทศ" hint="Country" dense outlined>
          </v-text-field>
        </v-col>
        
        <v-subheader>
                ปีที่จบ
                <br />Period
              </v-subheader>
        <v-col cols="6" sm="1">
          <v-text-field v-model.number="year" class="px-2" 
          label="จาก (ค.ศ.) / From (A.D.)" type="number"></v-text-field>
        </v-col>
        <v-col cols="6" sm="1">
          <v-text-field v-model.number="yea" class="px-2" label="ถึง (ค.ศ.) / To (A.D.)" type="number">
          </v-text-field>
        </v-col> 
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย<br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย" hint="G.P.A" dense outlined>
          </v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="4">
          <v-checkbox v-model="checkbox" :label="`ปัจจุบันศึกษาต่อ/ Studying `"></v-checkbox>
        </v-col>
      </v-row>
      <v-row>
        <v-subheader>
                ระดับการศึกษา
                <br />Level
              </v-subheader>
        <v-col cols="4">
          <v-autocomplete
            v-model="v"
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
          <v-text-field label="วิชาเอก" hint="Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ" hint="Dept." dense outlined></v-text-field>
        </v-col>
        
        <v-subheader>
                ปีที่จบ
                <br />Year to Graduate
              </v-subheader>
        <v-col cols="3" sm="2">
          <v-text-field
            v-model.number="ye"
            class="px-2"
            label="ปีที่เริ่มการศึกษา (ค.ศ.) / Start Year (A.D.)"
            type="number" 
          ></v-text-field>
        </v-col>
         <v-col cols="3" sm="2">
          <v-text-field
            v-model.number="yi"
            class="px-2"
            label="ปีที่คาดว่าจะจบ (ค.ศ.) / Expected year (A.D.)"
            type="number"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-5">กิจกรรมพิเศษ/ Activities</v-chip>
      </v-row>
      <v-row>
      <v-col cols="2" sm="6" md="6">
        <v-container fluid>
          <activities />
        </v-container>
        </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-5">งานอดิเรก/กีฬา / Hobbies/Sports</v-chip>
      </v-row>
      <v-row>
      <v-col cols="2" sm="6" md="6">
        <v-container fluid>
         <hobbies />
        </v-container>
        </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-2">มียานพาหนะเป็นของตัวเอง / Vehicle</v-chip>
      </v-row>
      <v-row>
        <v-col cols="12" sm="2">
            <v-checkbox
              v-model="x"
              label="รถยนต์/Car"
              value="รถยนต์/Car"
            ></v-checkbox>
          </v-col>
           <v-col cols="12" sm="3">
            <v-checkbox
              v-model="j"
              label="รถจักรยานยนต์ / Motorcycle"
              value="รถจักรยานยนต์ / Motorcycle"
            ></v-checkbox>
          </v-col>
          <v-col cols="12" sm="3">
            <v-checkbox
              v-model="j"
              label="ไม่มี / Don't have"
              value="ไม่มี / Don't have"
            ></v-checkbox>
          </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-2">ความสามารถพิเศษ/ Special Ability</v-chip>
      </v-row>
      <v-row>
       <v-subheader>
                ด้านคอมพิวเตอร์/ Computer Skill
              </v-subheader>
              </v-row>
        <v-row>
        <v-col cols="1" sm="3" md="3">
        <v-container fluid>
         <ifbox />
        </v-container>
        </v-col>
        <v-col cols="1" sm="3" md="3">
        <v-container fluid>
         <ijbox />
        </v-container>
        </v-col>
         <v-col cols="1" sm="3" md="3">
        <v-container fluid>
         <iabox />
        </v-container>
        </v-col>
         <v-col cols="1" sm="3" md="3">
        <v-container fluid>
         <ipbox />
        </v-container>
        </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-2">ด้านภาษาต่างประเทศ/ Proficiency in language</v-chip>
      </v-row>
      <v-row>
               <v-subheader>
                อังกฤษ / English
              </v-subheader>
        <v-col cols="2">
          <v-autocomplete
            v-model="v" :items="items" outlined dense chips small-chips
            label="เข้าใจ"
            prepend-inner-icon="mdi-lightbulb-on"
            hint=" Understanding"
          ></v-autocomplete>
        </v-col>
        <v-col cols="2">
          <v-autocomplete
            v-model="a"
            :items="items"
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
            v-model="l"
            :items="items"
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
            v-model="u"
            :items="items"
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
       <v-subheader>
                ภาษา/ Language
              </v-subheader>
        <v-col cols="1">
          <v-text-field label="ภาษา" 
          hint="Language" dense outlined></v-text-field>
        </v-col>
        <v-col cols="2">
          <v-autocomplete
            v-model="k"
            :items="items"
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
            v-model="n"
            :items="items"
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
            v-model="o"
            :items="items"
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
            v-model="p"
            :items="items"
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
        <v-btn color="primary" :disabled="!valid" @click="save()">Continue</v-btn>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
//import HelloWorld from '@/components/HelloWorld.vue'
import hobbies from "@/components/hobbies.vue";
import activities from "@/components/activities.vue";
import software from "@/components/software.vue";
import hardware from "@/components/hardware.vue";
import certificate from "@/components/certificate.vue";
import others from "@/components/others.vue";
export default {
   props: ["thisid"],
  components: {
    hobbies,
    activities,
    software,
    hardware,
    certificate,
    others
  },
  data: () => ({
    datain: {
      hobbies: []
    },
    data:null,
    lists:[],
     valid: false,
    checkbox: false,
    i: ["ม.ปลาย", "ปวช.", "ปวส.", "ปริญญาตรี","ปริญญาโท","อื่น ๆ"],
    v: ["ม.ปลาย", "ปวช.", "ปวส.", "ปริญญาตรี","ปริญญาโท","อื่น ๆ"],
    value: null,
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    year: 2000,
    x: null,
    y: "top",
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    yea: 2000,
    x: null,
    y: "top",
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    ye: 2000,
    x: null,
    y: "top",
    text: "Hello, I'm a snackbar",
    yea: 2000,
    x: null,
    y: "top",
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    yi: 2000,
    x: null,
    y: "top",
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    v: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    a: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    l: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    values: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    u: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    k: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    n: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    o: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    value: null,
    checkbox: false,
    items: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
    p: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"],
   
    }),
  mounted(){
    this.getLists();
  },
  methods:{
    getLists: async function(){
      let listurl = process.env.VUE_APP_LIST;
      console.log(listurl);
      let res = await axios({
        method: "get",
        url: listurl
      });
      this.lists = res.data
      console.log(this.lists);
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
 


