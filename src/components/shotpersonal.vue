<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row>
          <v-col cols="10">
            <v-row>
              <v-col cols="6" sm="2" md="4">
                <v-text-field
                  v-model="datain.positionnew"
                  :rules="rules.positionnew"
                  label="*ตำแหน่ง /Position*"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="6" sm="2" md="2">
                <v-text-field
                  v-model="datain.titlename"
                  :rules="rules.titlename"
                  label="*คำนำหน้า/Titel*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="4" sm="6" md="4">
                <v-text-field
                  v-model="datain.name"
                  :rules="rules.name"
                  label="*ชื่อ/Name*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="4" sm="6" md="4">
                <v-text-field
                  v-model="datain.surname"
                  :rules="rules.surname"
                  label="*นามสกุล/Surname*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="4" sm="1" md="2">
                <v-text-field
                  v-model="datain.nickt"
                  :rules="rules.nickt"
                  label="*ชื่อเล่น/Nickname*"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-cellphone-iphone"
                  v-model="datain.tel"
                  :rules="rules.tel"
                  label="*เบอร์มือถือ/Mobile*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-email"
                  v-model="datain.email"
                  :rules="rules.email"
                  label="*อีเมล/Email*"
                  hint="example@gmail.com"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="datain.line" label="ID Line" required></v-text-field>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="2">
            <picture-input
              ref="pictureInput"
              width="300"
              height="300"
              margin="16"
              accept="image/jpeg, image/png"
              size="10"
              button-class="btn"
              :custom-strings="{
                upload: '<h1>Bummer!</h1>',
                drag: 'Drag a jpeg or png'
              }"
              @change="onChange"
            ></picture-input>
          </v-col>
        </v-row>
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
                  v-model="modal3"
                  :return-value.sync="date"
                  persistent
                  width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field v-model="date4" label="วัน/เดือน/ปี*" readonly v-on="on"></v-text-field>
                  </template>
                  <v-date-picker v-model="date4" scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="modal4 = false">Cancel</v-btn>
                    <v-btn text color="primary" @click="$refs.dialog.save(date)">OK</v-btn>
                  </v-date-picker>
                </v-dialog>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="2">
            <v-row>
              <v-col cols="3">
                <v-subheader>
                  เพศ
                  <br />Sex
                </v-subheader>
              </v-col>
              <v-col cols="9">
                <v-select
                  v-model="datain.sex"
                  :rules="rules.sex"
                  :items="['Male','Female']"
                  label="Male/Female"
                ></v-select>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="2">
            <v-row>
              <v-col cols="3"></v-col>
              <v-col cols="7">
                <v-text-field v-model="datain.age" :rules="rules.age" label="อายุ/Age" hint="Age"></v-text-field>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="3">
            <v-row>
              <v-col cols="5">
                <v-text-field
                  v-model="datain.height"
                  :rules="rules.height"
                  label="ส่วนสูง"
                  hint="Height"
                ></v-text-field>
              </v-col>
              <v-col cols="5">
                <v-text-field
                  v-model="datain.weight"
                  :rules="rules.weight"
                  label="น้ำหนัก"
                  hint="Weight"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-col>
          
        </v-row>
        <v-chip class="ma-2">** ที่อยู่ปัจจุบัน/ Pressent **</v-chip>
        <v-row>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_add"
              :rules="rules.pr_add"
              label="บ้านเลขที่ / หมู่"
              hint="House number"
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field v-model="datain.pr_addhh" label="หมู่บ้าน/อาคาร Village/building" hint="Village/building"></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field v-model="datain.pr_soi" :rules="rules.pr_soi" label="ซอย/Alley" hint="Alley"></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_street"
              :rules="rules.pr_street"
              label="ถนน/Street"
              hint="Street"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_district"
              :rules="rules.pr_district"
              label="แขวง/ตำบล  District"
              hint="District"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_aumphur"
              :rules="rules.pr_aumphur"
              label="เขต/อำเภอ  Canton"
              hint="Canton"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_proince"
              :rules="rules.pr_proince"
              label="จังหวัด/Province"
              hint="Province"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_country"
              :rules="rules.pr_country"
              label="ประเทศ"
              hint="County"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_postaicode"
              :rules="rules.pr_postaicode"
              label="รหัสไปรษณีย์"
              hint="Postal code"
            ></v-text-field>
          </v-col>
        </v-row>
      </v-form>
      <v-row>
        <v-spacer />
        <v-btn color="primary" :disabled="!valid" @click="save()">Continue</v-btn>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
import nameprefix from "@/components/nameprefix.vue";
import nameprefixeng from "@/components/nameprefixeng.vue";
import bloodgroup from "@/components/nameprefixeng.vue";
import PictureInput from "vue-picture-input";
import citizen from "@/components/citizen.vue";

// import
export default {
  props: ["thisid"],
  components: {
    PictureInput,
    nameprefix,
    nameprefixeng,
    bloodgroup,
    citizen
  },

  data() {
    return {
      lists: [],
      address_is_same: false,
      date4: new Date().toISOString().substr(0, 10),
      date3: new Date().toISOString().substr(0, 10),
      date: new Date().toISOString().substr(0, 10),
      menu: false,
      modal: false,
      menu2: false,
      modal3: false,
      modal4: false,
      menu3: false,
      menu4: false,
      data4: null,
      data3: null,
      data: null,
      valid: false,

      rules: {
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
        nationality: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        citizen: [
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
        ],
        n_service: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ]
      },
      datain: {
        date3: new Date().toISOString().substr(0, 10),
        date4: new Date().toISOString().substr(0, 10),
        date: new Date().toISOString().substr(0, 10),
        data4: "",
        img: null,
        pofb: "",
        date: "",
        positionnew: "",
        stratingdate: "",
        news: "",
        nt: "",
        namet: "",
        surnamet: "",
        nickt: "",
        ne: "",
        namee: "",
        surnamee: "",
        nicke: "",
        dofb: "",
        sex: "",
        age: "",
        citizen: "",
        nationality: "",
        religion: "",
        height: "",
        weight: "",
        blood: "",
        pr_add: "",
        pr_soi: "",
        pr_street: "",
        pr_district: "",
        pr_aumphur: "",
        pr_proince: "",
        pr_country: "",
        pr_postaicode: "",
        pr_map: "",
        father_n: "",
        father_age: "",
        father_wp: "",
        father_oc: "",
        mather_n: "",
        mather_age: "",
        mather_wp: "",
        mather_oc: "",
        bs_name: "",
        bs_age: "",
        bs_wp: "",
        bs_oc: "",
        bs2_name: "",
        bs2_age: "",
        bs2_wp: "",
        bs2_oc: "",
        bs3_name: "",
        bs3_age: "",
        bs3_wp: "",
        bs3_oc: "",
        bs4_name: "",
        bs4_age: "",
        bs4_wp: "",
        bs4_oc: "",
        bs5_name: "",
        bs5_age: "",
        bs5_wp: "",
        bs5_oc: "",
        not_service: "",
        dm_service: "",
        past_service: "",
        except_service: "",
        single: "",
        divorce: "",
        widow: "",
        marriage_certificate: "",
        marriage_not_registered: ""
      }
    };
  },

  methods: {
    async init() {
      let listurl = process.env.VUE_APP_LIST;
      //console.log(listurl);
      let res = await axios({
        method: "get",
        url: listurl
      });
      this.lists = res.data;
      // console.log(this.lists);
    },
    onChange(image) {
      console.log("New picture selected!");
      if (image) {
        console.log("Picture loaded.");
        this.datain.img = image;
      } else {
        console.log("FileReader API not supported: use the <form>, Luke!");
      }
    },
    async save() {
      let urldata = process.env.VUE_APP_DATA;
      let res = await axios({
        method: "get",
        url: urldata + "/" + this.thisid
      });
      this.data = res.data;
      this.$parent.$parent.$parent.e1 = 2;
      let obj = Object.assign(this.data, this.datain);
      res = await axios({
        method: "put",
        url: urldata + "/" + this.thisid,
        data: obj
      });
    }
  },
  mounted() {
    this.init();
  }
};
</script>