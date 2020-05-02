 <template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row> 
        <v-chip
          class="ma-2"
        >การทำงาน (ระบุประสบการณืในการทำงานโดยเริ่มจากที่ล่าสุดก่อน) / Employment record (List from present to last)</v-chip>
        </v-row>
        <v-radio-group>
          <v-col>
            <v-row>
              <v-checkbox
                v-model="datain.experience"
                label="ไม่มีประสบการณ์การทำงาน"
                value="ไม่มีประสบการณ์การทำงาน"
              ></v-checkbox>
            </v-row>
          </v-col>
        </v-radio-group>
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
              v-model="datain.company_add1"
              :rules="rules.company_add1"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.from1"
              :rules="rules.from1"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.to1"
              :rules="rules.to1"
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
              v-model="datain.position1"
              :rules="rules.position1"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.s_last1"
              :rules="rules.s_last1"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.note1"
              :rules="rules.note1"
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
              v-model="datain.company_add2"
              :rules="rules.company_add2"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.from2"
              :rules="rules.from2"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.to2"
              :rules="rules.to2"
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
              v-model="datain.position2"
              :rules="rules.position2"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.s_last2"
              :rules="rules.s_last2"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.note2"
              :rules="rules.note2"
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
              v-model="datain.company_add3"
              :rules="rules.company_add3"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ระยะเวลา/Period</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.from3"
              :rules="rules.from3"
              label="จาก เดือน/ปี (From month/year)"
              placeholder="Details"
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.to3"
              :rules="rules.to3"
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
              v-model="datain.position3"
              :rules="rules.position3"
              label="Details"
              hint="Details"
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">เงินเดือน/Salary</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.s_last3"
              :rules="rules.s_last3"
              label="ค่าจ้าง/เงินเดือน (Wage/salary) "
              placeholder="Details"
            ></v-text-field>
          </v-col>
           <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.note3"
              :rules="rules.note3"
              label="  สาเหตุที่ลาออก/Reason for Leaving"
              placeholder="Details"
            ></v-text-field>
          </v-col>
        </v-row>
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
              v-model="datain.applicant_s_signature"
              :rules="rules.applicant_s_signature"
              label="Details"
              hint="Details"
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
                  :return-value.sync="datain.date3"
                  transition="scale-transition"
                  offset-y
                  min-width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field
                      v-model="datain.date3"
                      label="วันที่ /Date"
                      prepend-icon="mdi-calendar-multiple"
                      readonly
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker v-model="datain.date3" no-title scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="menu = false">Cancel</v-btn>
                    <v-btn text color="primary" @click="$refs.menu.save(datain.date3)">OK</v-btn>
                  </v-date-picker>
                </v-menu>
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
export default {
  props: ["thisid"],
  data() {
    return {
      data: null,
      valid: false,
      rules: {
        applicant_s_signature: [v => !!v || "applicant_s_signature is required"]
      },
      datain: {
        experience1: "",
        company_add1: "",
        form1: "",
        to1: "",
        position1: "",
        s_last1: "",
        note1: "",
        company_add2: "",
        form2: "",
        to2: "",
        position2: "",
        s_last2: "",
        note2: "",
        company_add3: "",
        form3: "",
        to3: "",
        position3: "",
        s_last3: "",
        note3: "",
        applicant_s_signature: "",
        date: ""
      }
    };
  },
  methods: {
    async init() {},
    back() {
      this.$parent.$parent.$parent.e6 = 1;
    },
    async save() {
      let urldata = process.env.VUE_APP_DATA;
      // console.log(urldata + "/" + this.thisid);
      let res = await axios({
        method: "get",
        url: urldata + "/" + this.thisid
      });
      this.data = res.data;
      this.$parent.$parent.$parent.e6 = 4;
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


