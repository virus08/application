<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row>
          <v-col cols="10">
            <v-row>
              <v-col cols="6" sm="2" md="4">
                <v-text-field
                  v-model="data.positionnew"
                  :rules="rules.req"
                  label="*ตำแหน่ง /Position*"
                  required
                />
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="6" sm="2" md="2">
                <v-text-field
                  v-model="data.titlename"
                  :rules="rules.req"
                  label="*คำนำหน้า/Titel*"
                  required
                />
              </v-col>
              <v-col cols="4" sm="6" md="4">
                <v-text-field v-model="data.name" :rules="rules.name" label="*ชื่อ/Name*" required />
              </v-col>
              <v-col cols="4" sm="6" md="4">
                <v-text-field
                  v-model="data.surname" :rules="rules.name" label="*นามสกุล/Surname*" required
                />
              </v-col>
              <v-col cols="4" sm="1" md="2">
                <v-text-field
                  v-model="data.nickt"
                  label="ชื่อเล่น/Nickname"
                />
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-cellphone-iphone"
                  v-model="data.tel"
                  :rules="rules.reqm2"
                  label="*เบอร์มือถือ/Mobile*"
                  required
                />
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-email"
                  v-model="data.email"
                  :rules="rules.email"
                  label="*อีเมล/Email*"
                  hint="example@gmail.com"
                  required
                />
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field v-model="data.reqm2" label="ID Line" required />
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
            />
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
                  v-model="Brith_Date_Model"
                  :return-value.sync="thisdate"
                  persistent
                  width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field :rules="rules.req" v-model="tbd_format" label="วัน/เดือน/ปี*" readonly v-on="on"></v-text-field>
                  </template>
                  <v-date-picker v-model="data.BrithDate" scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="Brith_Date_Model = false">Cancel</v-btn>
                    <v-btn text color="primary" @click="$refs.dialog.save(data.BrithDate)">OK</v-btn>
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
                  v-model="data.sex"
                  :rules="rules.req"
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
                <v-text-field
                  disabled
                  v-model="comp_age"
                  :rules="rules.req"
                  label="อายุ/Age"
                  hint="Age"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-col>
          <v-col cols="3">
            <v-row>
              <v-col cols="5">
                <v-text-field
                  v-model="data.height"
                  :rules="rules.reqm2"
                  label="ส่วนสูง"
                  hint="Height"
                ></v-text-field>
              </v-col>
              <v-col cols="5">
                <v-text-field
                  v-model="data.weight"
                  :rules="rules.reqm2"
                  label="น้ำหนัก"
                  hint="Weight"
                ></v-text-field>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
        <br />
        <v-divider />
        <br />
        <v-chip class="ma-2">** ที่อยู่ปัจจุบัน/ Pressent **</v-chip>
        <v-row>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_add"
              :rules="rules.reqm2"
              label="บ้านเลขที่ / หมู่"
              hint="House number"
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.pr_addhh"
              label="หมู่บ้าน/อาคาร Village/building"
              hint="Village/building"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_soi"
              label="ซอย/Alley"
              hint="Alley"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_street"
              label="ถนน/Street"
              hint="Street"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_district"
              :rules="rules.reqm2"
              label="แขวง/ตำบล  District"
              hint="District"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_aumphur"
              :rules="rules.reqm2"
              label="เขต/อำเภอ  Canton"
              hint="Canton"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_proince"
              :rules="rules.reqm2"
              label="จังหวัด/Province"
              hint="Province"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_country"
              :rules="rules.reqm2"
              label="ประเทศ"
              hint="County"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.pr_postaicode"
              :rules="rules.reqeq5"
              label="รหัสไปรษณีย์"
              hint="Postal code"
            ></v-text-field>
          </v-col>
        </v-row>
        <br />
        <v-divider />
        <br />
        <v-row>
          <v-col cols="3">
            <v-text-field
              v-model="data.certificate"
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
              v-model="data.name_Level1"
              :rules="rules.req"
              :items="lists.find(e => e.name =='edu').data"
              label="ระดับการศึกษา"
              hint=" Level"
            ></v-autocomplete>
          </v-col>

          <v-col cols="3">
            <v-text-field
              v-model="data.institute1"
              :rules="rules.req"
              label="จากสถาบัน/มหาวิทยาลัย"
              prepend-inner-icon="mdi-city"
              hint="From institutions / Universities"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="data.name_subject1"
              :rules="rules.req"
              label="สาขาวิชา"
              hint="Subject"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="data.name_graduation1"
              :rules="rules.req"
              label="ปีที่สำเร็จการศึกษา"
              hint="Graduation year"
            ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-5">อื่นๆ/Others</v-chip>
          <v-col cols="2">
            <v-autocomplete
              :items="lists.find(e => e.name =='other').data"
              v-model="data.name_Level3"
              hint=" Level"
              label="ระดับการศึกษา"
            ></v-autocomplete>
          </v-col>
          <v-col cols="3">
            <v-text-field
              v-model="data.institute3"
              label="จากสถาบัน/มหาวิทยาลัย"
              prepend-inner-icon="mdi-city"
              hint="From institutions / Universities"
            ></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field v-model="data.name_subject3" label="สาขาวิชา" hint="Subject"></v-text-field>
          </v-col>

          <v-col cols="1.5">
            <v-text-field
              v-model="data.name_graduation3"
              label="ปีที่สำเร็จการศึกษา"
              hint="Graduation year"
            ></v-text-field>
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">**ภาษาอังกฤษ / English language**</v-chip>
          <v-col cols="2.5">
            <v-autocomplete
              v-model="data.name_understanding1"
              label="เข้าใจ"
              :rules="rules.req"
              hint=" Understanding"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-lightbulb-on"
            />
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="data.name_speaking1"
              label="พูด"
              :rules="rules.req"
              hint="Speaking"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-comment-processing"
            />
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="data.name_reading1"
              :rules="rules.req"
              :items="lists.find(e => e.name =='gfb').data"
              label="อ่าน"
              prepend-inner-icon="mdi-book-open-variant"
              hint="Reading"
            />
          </v-col>

          <v-col cols="2.5">
            <v-autocomplete
              v-model="data.name_writing1"
              label="เขียน"
              :rules="rules.req"
              hint="Writing"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-lead-pencil"
            />
          </v-col>
        </v-row>

        <v-row>
          <v-chip class="ma-2">ภาษาอื่นๆ / Others</v-chip>

          <v-col cols="2.5">
            <v-text-field v-model="data.name_language2" label="ภาษา" hint="Language"></v-text-field>
          </v-col>

          <v-col cols="2">
            <v-autocomplete
              v-model="data.name_understanding2"
              label="เข้าใจ"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-lightbulb-on"
              hint="Understanding"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="data.name_speaking2"
              label="พูด"
              hint="Speaking"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-comment-processing"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="data.name_reading2"
              label="อ่าน"
              hint="Reading"
              :items="lists.find(e => e.name =='gfb').data"
              prepend-inner-icon="mdi-book-open-variant"
            ></v-autocomplete>
          </v-col>
          <v-col cols="2">
            <v-autocomplete
              v-model="data.name_writing2"
              :items="lists.find(e => e.name =='gfb').data"
              label="เขียน"
              prepend-inner-icon="mdi-lead-pencil"
              hint="Writing"
            ></v-autocomplete>
          </v-col>
        </v-row>
        <br />
        <v-divider />
        <br />
        <v-chip>การทำงาน (ระบุประสบการณืในการทำงานโดยเริ่มจากที่ล่าสุดก่อน) / Employment record (List from present to last)</v-chip>
        <v-checkbox
          v-model="data.experience"
          label="ไม่มีประสบการณ์การทำงาน"
          value="ไม่มีประสบการณ์การทำงาน"
        />
        <v-divider />
        <div v-if="!data.experience">
        <v-chip class="ma-2">อันดับที่ 1/ No.1</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                บริษัท/หน่วยงาน
                <br />Company / Department
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.company_add1"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.from1"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.to1"
              label="ถึง เดือน/ปี (To month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ตำแหน่งงานสุดท้าย
                <br />Last Position
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.position1"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.s_last1"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.note1"
              label="  สาเหตุที่ลาออก/Reason for Leaving"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">อันดับที่ 2/ No.2</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                บริษัท/หน่วยงาน
                <br />Company / Department
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.company_add2"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.from2"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.to2"
              label="ถึง เดือน/ปี (To month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ตำแหน่งงานสุดท้าย
                <br />Last Position
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.position2"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.s_last2"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.note2"
              label="  สาเหตุที่ลาออก/Reason for Leaving"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">อันดับที่ 3/ No.3</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                บริษัท/หน่วยงาน
                <br />Company / Department
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.company_add3"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.from3"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.to3"
              label="ถึง เดือน/ปี (To month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ตำแหน่งงานสุดท้าย
                <br />Last Position
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="data.position3"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.s_last3"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="data.note3"
              label="  สาเหตุที่ลาออก/Reason for Leaving"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
        </div>
        <br />
        <br />
        <v-row>
          <v-spacer />
          <v-spacer />
          <v-list-item-content>
            <v-col cols="10">
              <v-subheader>
                <p class="font-weight-black">
                  ข้าพเจ้าขอรับรองว่าข้อความทั้งหมด
                  <br />ในใบสมัครเป็นความจริงทุกประการ
                  <br />
                  <br />I certify that all statements in the application are true.
                </p>
              </v-subheader>
            </v-col>
          </v-list-item-content>
        </v-row>
        <br />
        <v-row>
          <v-spacer />
          <v-col cols="12" sm="6" md="4">
            <v-subheader>
              <p class="font-weight-black">
                ลงชื่อผู้สมัคร
                <br />Applicant's signature *
              </p>
            </v-subheader>
            <v-text-field
              v-model="data.applicant_s_signature"
              :rules="rules.req"
              label="Signature"
              hint="Signature"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-spacer />
          <v-col cols="12" sm="6" md="4">
            <v-menu
              ref="menu"
              v-model="menu3"
              :close-on-content-click="false"
              :return-value.sync="data.date3"
              transition="scale-transition"
              offset-y
              min-width="290px"
            >
              <template v-slot:activator="{ on }">
                <v-text-field
                  v-model="tdate3_format"
                  label="วันที่ /Date"
                  prepend-icon="mdi-calendar-multiple"
                  readonly
                  v-on="on"
                ></v-text-field>
              </template>
              <v-date-picker v-model="data.date3" no-title scrollable>
                <v-spacer></v-spacer>
                <v-btn text color="primary" @click="menu3 = false">Cancel</v-btn>
                <v-btn text color="primary" @click="$refs.menu.save(data.date3)">OK</v-btn>
              </v-date-picker>
            </v-menu>
          </v-col>
        </v-row>
      </v-form>
      <v-row>
        <v-spacer /> 
        <v-col cols="2"> 
          <v-btn color="warning" v-if="!valid" @click="validate"> Validate </v-btn> 
          <v-btn color="success" v-else @click="save"> Save</v-btn> 
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
import PictureInput from "vue-picture-input";
var moment = require("moment");
//for edu

export default {
  props: ["data", "rules"],
  components: {
    PictureInput
  },
  data() {
    return {
      Brith_Date_Model: false,
      thisdate: new Date().toISOString().substr(0, 10),
      valid: false,
      // edu
      lists: [
        {
          id: 1,
          name: "edu",
          data: ["ม.ปลาย", "ปวช.", "ปวส.", "ปริญญาตรี", "ปริญญาโท", "อื่น ๆ"]
        },
        { id: 2, name: "gfb", data: ["ดี/Good", "พอใช้/Ok", "ไม่ดี/Not Good"] },
        { id: 3, name: "other", data: ["ปริญญาโท", "ปริญญาเอก", "อื่น ๆ"] }
      ],
      //
      menu3:false
    };
  },
  mounted() {
    // this.init();
  },
  methods: {
    async init() {
      let listurl = process.env.VUE_APP_LIST;
      let res = await axios({
        method: "get",
        url: listurl
      });
      this.lists = res.data;
    },
    validate(){
      this.$refs.form.validate();
    },
    save(){
      console.log(this.data)
    },
    onChange(image) {
      if (image) {
        this.data.img = image;
      }
    }
  },
  computed: {
    tdate3_format : function(){
        if(!this.data.date3) this.data.date3 = this.thisdate;
            return moment(this.data.date3).format('D MMM YYYY') 
    },
    tbd_format : function(){
        if(this.data.BrithDate)
            return moment(this.data.BrithDate).format('D MMM YYYY') 
    },
    comp_age: function() {
      
      let yy = moment().diff(this.data.BrithDate, "years", false);
      let mo = moment().diff(this.data.BrithDate, "months", false);
      let xx = mo - yy * 12;
      this.age = yy;
      return yy + "ปี(" + xx + "ด.)";
    }
  }
};
</script>