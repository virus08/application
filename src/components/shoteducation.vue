<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row>
          <v-col cols="3">
            <v-text-field
              v-model="datain.institute1"
              :rules="rules.institute1"
              label="ประกาศนียบัตร"
              prepend-inner-icon="mdi-certificate"
              hint="Certificate"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-chip class="ma-5">**ระดับการศึกษา/ Education level**</v-chip>

          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_Level1"
              :rules="rules.name_Level1"
              :items="lists[6].data"
              chips
              small-chips
              label="ระดับการศึกษา"
              hint=" Level"
            ></v-autocomplete>
          </v-col>

          <v-col cols="3">
            <v-text-field
              v-model="datain.institute1"
              :rules="rules.institute1"
              label="จากสถาบัน/มหาวิทยาลัย"
              prepend-inner-icon="mdi-city"
              hint="From institutions / Universities"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="datain.name_subject1"
              :rules="rules.name_subject1"
              label="สาขาวิชา"
              hint="Subject"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="datain.name_graduation1"
              :rules="rules.name_graduation1"
              label="ปีที่สำเร็จการศึกษา"
              hint="Graduation year"
            ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">อื่นๆ/Others</v-chip>

          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_Level3"
              :items="lists[5].data"
              chips
              small-chips
              label="ระดับการศึกษา"
              hint=" Level"
            ></v-autocomplete>
          </v-col>

          <v-col cols="3">
            <v-text-field
              v-model="datain.institute3"
              label="จากสถาบัน/มหาวิทยาลัย"
              prepend-inner-icon="mdi-city"
              hint="From institutions / Universities"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field v-model="datain.name_subject3" label="สาขาวิชา" hint="Subject"></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="datain.name_graduation3"
              label="ปีที่สำเร็จการศึกษา"
              hint="Graduation year"
            ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">**ภาษาอังกฤษ / English language**</v-chip>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="datain.name_understanding1"
              :rules="rules.name_understanding1"
              :items="lists[1].data"
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
              :rules="rules.name_speaking1"
              :items="lists[1].data"
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
              :rules="rules.name_reading1"
              :items="lists[1].data"
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
              :rules="rules.name_writing1"
              :items="lists[1].data"
              chips
              small-chips
              label="เขียน"
              prepend-inner-icon="mdi-lead-pencil"
              hint="Writing"
            ></v-autocomplete>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">ภาษาอื่นๆ / Others</v-chip>

          <v-col cols="2.5">
            <v-text-field v-model="datain.name_language2" label="ภาษา" hint="Language"></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_understanding2"
              :items="lists[1].data"
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
              label="พูด"
              prepend-inner-icon="mdi-comment-processing"
              hint="Speaking"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="datain.name_reading2"
              :items="lists[1].data"
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
      name_Level1: "",
      institute1: "",
      name_subject1: "",
      name_graduation1: "",
      institute2: "",
      name_subject2: "",
      name_graduation2: "",
      name_Level3: "",
      institute3: "",
      name_subject3: "",
      name_graduation3: "",
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
    rules: {
      name_Level1: [v => !!v || "Item is required"],
      institute1: [v => !!v || "Item is required"],
      name_subject1: [v => !!v || "Item is required"],
      name_graduation1: [v => !!v || "Item is required"],
      name_understanding1: [v => !!v || "Item is required"],
      name_speaking1: [v => !!v || "Item is required"],
      name_reading1: [v => !!v || "Item is required"],
      name_writing1: [v => !!v || "Item is required"]
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
      this.$parent.$parent.$parent.e1 = 1;
    },
    async save() {
      let urldata = process.env.VUE_APP_DATA;
      let res = await axios({
        method: "get",
        url: urldata + "/" + this.thisid
      });
      this.data = res.data;
      console.log(this.data);
      this.$parent.$parent.$parent.e1 = 3;
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

