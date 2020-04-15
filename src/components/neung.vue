<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-row>
          <v-col cols="10">
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-menu
                  ref="menu"
                  v-model="menu"
                  :close-on-content-click="false"
                  :return-value.sync="date"
                  transition="scale-transition"
                  offset-y
                  min-width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field
                      v-model="date"
                      label="วันที่สมัคร /Application Date*"
                      prepend-icon="mdi-calendar-multiple"
                      readonly
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker v-model="date" no-title scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="menu = false">Cancel</v-btn>
                    <v-btn text color="primary" @click="$refs.menu.save(date)">OK</v-btn>
                  </v-date-picker>
                </v-menu>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-account-location"
                  v-model="datain.position"
                  :rules="rules.position"
                  label="ตำแหน่ง /Position*"
                  required
                ></v-text-field>
              </v-col>
            </v-row>
            <v-row>
              <v-col cols="12" sm="6" md="4">
                <v-dialog
                  ref="dialog"
                  v-model="modal3"
                  :return-value.sync="date"
                  persistent
                  width="290px"
                >
                  <template v-slot:activator="{ on }">
                    <v-text-field
                      v-model="date3"
                      label="วันเริ่มงาน /Strating Date*"
                      prepend-icon="mdi-calendar-multiple"
                      readonly
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker v-model="date3" scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="modal3 = false">Cancel</v-btn>
                    <v-btn text color="primary" @click="$refs.dialog.save(date)">OK</v-btn>
                  </v-date-picker>
                </v-dialog>
              </v-col>
              <v-col cols="12" sm="6" md="4">
                <v-text-field
                  prepend-icon="mdi-message-text-outline"
                  v-model="datain.news"
                  :rules="rules.news"
                  label="รับทราบข่าวสารจาก*"
                  required
                ></v-text-field>
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
        <v-row align="center">
          <v-col cols="2" md="2">
            <v-container fluid>
              <v-autocomplete
                :items="lists[3].data"
                outlined
                dense
                chips
                small-chips
                label="คำนำหน้าชื่อ"
                hint="อะไรไม่รุ"
              />
            </v-container>
          </v-col>
          <v-row>
            <v-col cols="5" md="3">
              <v-text-field
                v-model="datain.namet"
                :rules="rules.namet"
                label="ชื่อ / (TH)*"
                hint="ระบุเป็นภาษาไทย"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-col cols="5" md="3">
              <v-text-field
                v-model="datain.surnamet"
                :rules="rules.surnamet"
                label="นามสกุล / (TH)*"
                hint="ระบุเป็นภาษาไทย"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.nickt"
                :rules="rules.nt"
                label="ชื่อเล่น / (TH)*"
                hint="ระบุเป็นภาษาไทย"
                dense
                outlined
              ></v-text-field>
            </v-col>
          </v-row>
        </v-row>
        <v-row>
          <v-col cols="2" md="2">
            <v-container fluid>
              <nameprefixeng />
            </v-container>
          </v-col>  
          <v-col cols="5" md="3">
            <v-text-field
              v-model="datain.namee"
              :rules="rules.namee"
              label="Name / (EN)*"
              hint="ระบุเป็นภาษาอังกฤษ"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="5" md="3">
            <v-text-field
              v-model="datain.surnamee"
              :rules="rules.surnamee"
              label="Surname / (EN)*"
              hint="ระบุเป็นภาษาอังกฤษ"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.nicke"
              :rules="rules.nicke"
              label="Nickname / (EN)*"
              hint="ระบุเป็นภาษาอังกฤษ"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <!-- ยังใช้งานไม่ได้ date brihtday -->
          <v-col cols="4">
            <v-row>
            <v-col cols="3">
              <v-subheader>
                วันเกิด
                <br />Brith Date
              </v-subheader>
            </v-col>
            <v-col cols="5">
              <v-dialog
                ref="dialog"
                v-model="modal3"
                :return-value.sync="date"
                persistent
                width="290px"
              >
                <template v-slot:activator="{ on }">
                  <v-text-field
                    v-model="date4"
                    label="วัน/เดือน/ปี*"
                    prepend-icon="mdi-calendar-multiple"
                    readonly
                    v-on="on"
                    dense
                    outlined
                  ></v-text-field>
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
          <v-col>
            <v-subheader>
              เพศ
              <br />Sex
            </v-subheader>
          </v-col>
          <v-col>
            <v-select
              v-model="datain.sex"
              :rules="rules.sex"
              :items="['Male','Female']"
              label="Male/Female"
              dense
              solo
            ></v-select>
          </v-col>
          <v-col>
            <v-subheader>
              อายุ
              <br />Age
            </v-subheader>
          </v-col>
          <v-col>
            <v-text-field
              v-model="datain.age"
              :rules="rules.age"
              label="อายุ/Age"
              hint="Age"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3">
            <v-row>
            <v-col cols="3">
              <v-subheader>
                เชื้อชาติ
                <br />Citizen
              </v-subheader>
            </v-col>
            <v-col cols="9">
              <v-text-field
                v-model="datain.citizen"
                :rules="rules.citizen"
                label="เชื้อชาติ/Race*"
                hint="Race"
                dense
                outlined
              ></v-text-field>
            </v-col>
            </v-row>
          </v-col>
          <v-col cols="3">
            <v-row>
            <v-col cols="3">
              <v-subheader>
                สัญชาติ
                <br />Nationality
              </v-subheader>
            </v-col>
            <v-col cols="9">
              <v-text-field
                v-model="datain.nationality"
                :rules="rules.nationality"
                label="สัญชาติ/Nationality*"
                hint="Nationality"
                dense
                outlined
              ></v-text-field>
            </v-col>
            </v-row>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            ศาสนา
            <br />Religion
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.religion"
              :rules="rules.religion"
              label="ศาสนา/Religion"
              hint="Religion"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ส่วนสูง
            <br />Height*
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field
              v-model="datain.height"
              :rules="rules.height"
              label="ระบุ.."
              hint="Height"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            น้ำหนัก
            <br />Weight*
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field
              v-model="datain.weight"
              :rules="rules.weight"
              label="ระบุ.."
              hint="Weight"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            กรุ๊ปเลือด
            <br />Blood Group
          </v-subheader>
          <v-col cols="2" md="2">
            <v-autocomplete
              :items="lists[4].data"
              outlined
              dense
              chips
              small-chips
              label="คำนำหน้าชื่อ"
              hint="อะไรไม่รุ"
            />
          </v-col>
        </v-row>
        <v-chip class="ma-2">** ที่อยู่ปัจจุบัน/ Pressent **</v-chip>
        <v-row>
          <v-subheader>
            บ้านเลขที่-หมู่ที่
            <br />House number
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field
              v-model="datain.pr_add"
              :rules="rules.pr_add"
              label="บ้านเลขที่ / หมู่"
              hint="House number"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            หมู่บ้าน/อาคาร
            <br />Village/building
          </v-subheader>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.pr_addhh"
              :rules="rules.pr_addhh"
              label="หมู่บ้าน/อาคาร"
              hint="Village/building"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ซอย
            <br />Alley
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_soi"
              :rules="rules.pr_soi"
              label="ซอย"
              hint="Alley"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ถนน
            <br />Street
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_street"
              :rules="rules.pr_street"
              label="ถนน"
              hint="Street"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            แขวง/ตำบล
            <br />District
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_district"
              :rules="rules.pr_district"
              label="แขวง/ตำบล"
              hint="District"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            เขต/อาเภอ
            <br />county
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_aumphur"
              :rules="rules.pr_aumphur"
              label="เขต/อาเภอ"
              hint="county"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            จังหวัด
            <br />county
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_proince"
              :rules="rules.pr_proince"
              label="จังหวัด"
              hint="county"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ประเทศ
            <br />county
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_country"
              :rules="rules.pr_country"
              label="ประเทศ"
              hint="county"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            รหัสไปรษณีย์
            <br />Postal code
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.pr_postaicode"
              :rules="rules.pr_postaicode"
              label="เขต/อาเภอ"
              hint="Postal code"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3" md="3">
            <v-radio-group v-model="datain.house_or" :rules="rules.house_or" row>
              <v-radio label="บ้านตนเอง/Own house " dense outlined></v-radio>
              <v-radio label="ห้องเช่า/Rented room" dense outlined></v-radio>
            </v-radio-group>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            Telephone
            <br />โทรศัพท์บ้าน**
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field v-model="datain.tel" :rules="rules.tel" label="02 .." dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            Mobile
            <br />มือถือ**
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mobile"
              :rules="rules.mobile"
              label="+(66).."
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            Email**
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.email"
              :rules="rules.email"
              label="example@gmail.com"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            Facebook**
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field v-model="datain.facebook" :rules="rules.facebook" label dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ID Line**
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field v-model="datain.line" :rules="rules.line" label dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-switch v-model="address_is_same" label="ที่อยู่ตามทะเบียนบ้านเป็นที่อยู่ปัจจุบัน" />
        </v-row>
        <div v-if="!address_is_same">
          <v-chip class="ma-2">ที่อยู่ตามทะเบียนบ้าน/ Permanent address</v-chip>
          <v-row>
            <v-subheader>
              บ้านเลขที่-หมู่ที่
              <br />House number
            </v-subheader>
            <v-col cols="1" md="1">
              <v-text-field
                v-model="datain.pr_add2"
                :rules="rules.pr_add2"
                label="บ้านเลขที่ / หมู่"
                hint="House number"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              หมู่บ้าน/อาคาร
              <br />Village/building
            </v-subheader>
            <v-col cols="3" md="3">
              <v-text-field
                v-model="datain.pr_add2"
                :rules="rules.pr_add2"
                label="หมู่บ้าน/อาคาร"
                hint="Village/building"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              ซอย
              <br />Alley
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_soi2"
                :rules="rules.pr_soi2"
                label="ซอย"
                hint="Alley"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              ถนน
              <br />Street
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_street2"
                :rules="rules.pr_street2"
                label="ถนน"
                hint="Street"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              แขวง/ตำบล
              <br />District
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_district2"
                :rules="rules.pr_district2"
                label="แขวง/ตำบล"
                hint="District"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              เขต/อาเภอ
              <br />county
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_aumphur2"
                :rules="rules.pr_aumphur2"
                label="เขต/อาเภอ"
                hint="county"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              จังหวัด
              <br />county
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_proince2"
                :rules="rules.pr_proince2"
                label="จังหวัด"
                hint="county"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              ประเทศ
              <br />county
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_country2"
                :rules="rules.pr_country2"
                label="ประเทศ"
                hint="county"
                dense
                outlined
              ></v-text-field>
            </v-col>
            <v-subheader>
              รหัสไปรษณีย์
              <br />Postal code
            </v-subheader>
            <v-col cols="2" md="2">
              <v-text-field
                v-model="datain.pr_postaicode2"
                :rules="rules.pr_postaicode2"
                label="เขต/อาเภอ"
                hint="Postal code"
                dense
                outlined
              ></v-text-field>
            </v-col>
          </v-row>
        </div>
        <v-row>
          <v-chip class="ma-2">การอุปสมบท/ Ordination</v-chip>
          <v-radio-group v-model="datain.ordination" :rules="rules.ordination" row>
            <v-radio label="ไม่เคย/ No" dense outlined></v-radio>
            <v-radio label="บวชเรียนแล้ว-ชื่อวัดและที่ตั้ง/ (Yes / where)" dense outlined></v-radio>
          </v-radio-group>

          <v-col cols="3" md="3">
            <v-text-field label="ระบุรายละเอียด" hint="Details" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-chip class="ma-2">สถานภาพทางทหาร/ Military status</v-chip>
          <br />
          <br />
          <v-radio-group v-model="datain.n_service" :rules="rules.n_service" row>
            <v-radio label="ยังไม่ผ่านการเกณฑ์ทหาร /No Dischrged" dense outlined></v-radio>
            <v-radio label="ผ่านการศึกษาวิชาทหาร /Military Studied" dense outlined></v-radio>
            <v-radio label="ผ่านการเกณฑ์ทหาร /Dischrged" dense outlined></v-radio>
            <v-radio label="ได้รับการยกเว้น /Exempted" dense outlined></v-radio>
          </v-radio-group>
          <v-col cols="3" md="3">
            <v-text-field label="เนื่องจาก /Reason" hint="ระบุรายละเอียด" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-chip class="ma-2">สถานภาพการสมรส/ Marital status</v-chip>
          <v-radio-group v-model="datain.marital" :rules="rules.marital" row>
            <v-radio label="โสด/ Single" dense outlined></v-radio>
            <v-radio label="หย้า/ Divorced" dense outlined></v-radio>
            <v-radio label="หม้าย/ Widowed" dense outlined></v-radio>
            <v-radio label="สมรสจดทะเบียน/ Civil marriage" dense outlined></v-radio>
            <v-radio label="สมรสไม่จดทะเบียน/ Common-law marriage" dense outlined></v-radio>
          </v-radio-group>
        </v-row>
        <v-chip class="ma-2">ข้อมูลของคู่สมรสและบุตร / Family information</v-chip>
        <v-row>
          <v-col cols="2" md="1.5">
            <v-select :items="['นาย','นาง']" label="คำนำหน้า" dense solo></v-select>
          </v-col>
          <v-col cols="7" md="3">
            <v-text-field label="ชื่อ / (TH)" hint="ระบุเป็นภาษาไทย" dense outlined></v-text-field>
          </v-col>
          <v-col cols="5" md="3">
            <v-text-field label="นามสกุล / (TH)" hint="ระบุเป็นภาษาไทย" dense outlined></v-text-field>
          </v-col>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="Age" dense outlined></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field label="อาชีพ/ตำแหน่ง" hint="Occupation / Position" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            สถำนที่ทำงาน
            <br />Office address
          </v-subheader>
          <v-col cols="2" md="3">
            <v-text-field label="สถานที่ทำงาน" hint dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            โทรศัพท์
            <br />Telephone
          </v-subheader>
          <v-col cols="2" md="3">
            <v-text-field label="+66 .." hint dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-chip class="ma-2">จำนวนบุตร / Number of children</v-chip>
          <v-col cols="2" md="2">
            <v-text-field label="จำนวนบุตร" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-chip
          class="ma-2"
        >ประวัติทางครอบครัว (ประวัติของบิดา / มารดา / พี่น้องทุกคน) / Family background</v-chip>
        <br />
        <v-chip class="ma-2">ความสัมพันธ์/ Relation</v-chip>
        <v-row>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.num_b"
              :rules="rules.num_b"
              prepend-icon="mdi-account-multiple"
              label="จำนวนบุตร /No."
              required
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.order_b"
              :rules="rules.order_b"
              prepend-icon="mdi-account-multiple"
              label="คุณเป็นบุตรคนที่ /No.Also"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.num_s"
              :rules="rules.num_s"
              prepend-icon="mdi-gender-male"
              label="ชาย /son"
              required
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.num_d"
              :rules="rules.num_d"
              prepend-icon="mdi-gender-female"
              label="หญิง /daughter"
              required
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            บิดา
            <br />Father
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.father_n"
              :rules="rules.father_n"
              label="ชื่อ/นามสกุล"
              hint="Name"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field
              v-model="datain.father_age"
              :rules="rules.father_age"
              label="อายุ"
              hint="ระบุเป็นตัวเลข"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.father_wp"
              :rules="rules.father_wp"
              label="สถานที่ทำงาน/โทรศัพท์"
              hint="Company/Telephone"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.father_oc"
              :rules="rules.father_oc"
              label="ตำแหน่ง/อาชีพ"
              hint="Position"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            มารดา
            <br />Mather
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mather_n"
              :rules="rules.mather_n"
              label="ชื่อ/นามสกุล"
              hint="Name"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field
              v-model="datain.mather_age"
              :rules="rules.mather_age"
              label="อายุ"
              hint="ระบุเป็นตัวเลข"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mather_wp"
              :rules="rules.mather_wp"
              label="สถานที่ทำงาน/โทรศัพท์"
              hint="Company/Telephone"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mather_oc"
              :rules="rules.mater_oc"
              label="ตำแหน่ง/อาชีพ"
              hint="Position"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            พี่น้องลำดับที่1
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ชื่อ/นามสกุล" hint="Name" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="ระบุเป็นตัวเลข" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="สถานที่ทำงาน/โทรศัพท์" hint="Company/Telephone" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ตำแหน่ง/อาชีพ" hint="Position" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            พี่น้องลำดับที่2
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ชื่อ/นามสกุล" hint="Name" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="ระบุเป็นตัวเลข" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="สถานที่ทำงาน/โทรศัพท์" hint="Company/Telephone" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ตำแหน่ง/อาชีพ" hint="Position" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            พี่น้องลำดับที่3
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ชื่อ/นามสกุล" hint="Name" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="ระบุเป็นตัวเลข" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="สถานที่ทำงาน/โทรศัพท์" hint="Company/Telephone" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ตำแหน่ง/อาชีพ" hint="Position" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            พี่น้องลำดับที่4
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ชื่อ/นามสกุล" hint="Name" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="ระบุเป็นตัวเลข" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="สถานที่ทำงาน/โทรศัพท์" hint="Company/Telephone" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ตำแหน่ง/อาชีพ" hint="Position" dense outlined></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-subheader>
            พี่น้องลำดับที่5
            <br />
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ชื่อ/นามสกุล" hint="Name" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            อายุ
            <br />Age
          </v-subheader>
          <v-col cols="1" md="1">
            <v-text-field label="อายุ" hint="ระบุเป็นตัวเลข" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            สถานที่ทำงาน/โทรศัพท์
            <br />Company/Telephone
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="สถานที่ทำงาน/โทรศัพท์" hint="Company/Telephone" dense outlined></v-text-field>
          </v-col>
          <v-subheader>
            ตำแหน่ง/อาชีพ
            <br />Position
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field label="ตำแหน่ง/อาชีพ" hint="Position" dense outlined></v-text-field>
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
import nameprefix from "@/components/nameprefix.vue";
import nameprefixeng from "@/components/nameprefixeng.vue";
import bloodgroup from "@/components/nameprefixeng.vue";
import PictureInput from "vue-picture-input";
// import
export default {
  props: ["thisid"],
  components: {
    PictureInput,
    nameprefix,
    nameprefixeng,
    bloodgroup
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
        position: [v => !!v || "Item is required"],
        stratingdate: [v => !!v || "Item is required"],
        news: [v => !!v || "Item is required"],
        nt: [v => !!v || "Item is required"],
        namet: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        surnamet: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        nickt: [v => !!v || "Item is required"],
        ne: [v => !!v || "Item is required"],
        namee: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        surnamee: [
          v => !!v || "Name is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters",
          v => (v || "").indexOf(" ") < 0 || "No spaces are allowed"
        ],
        nicke: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        email: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        tel: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        mobile: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        facebook: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        line: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        dofb: [
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
        pr_soi: [
          v => !!v || "Item is required",
          v => (v && v.length >= 2) || "Name must be more than 5 characters"
        ],
        pr_street: [
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
        img: null,
        date: "",
        position: "",
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
        mather_oc: ""
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
      this.$parent.$parent.$parent.e6 = 2;
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