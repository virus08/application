 <template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-chip
          class="ma-2"
        >ประวัติการทำงาน จากปัจจุบันไปหาอดีต / Employment record (List from present to last)</v-chip>
       <v-radio-group >
          <v-col>
          <v-row>
            <v-checkbox v-model="datain.experience" label="ไม่มีประสบการณ์การทำงาน" value="ไม่มีประสบการณ์การทำงาน"></v-checkbox>         
          </v-row>
          <v-row>
            <v-checkbox v-model="datain.experience" label="มีประสบการณ์การทำงาน(โปรดระบุ)" value="Iมีประสบการณ์การทำงาน(โปรดระบุ)"></v-checkbox>       
          </v-row>
          </v-col>
        </v-radio-group>
        <v-chip class="ma-2">อันดับที่ 1/ No.1</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-ที่อยู่บริษัท
                <br />Name
                <br />Address Employer
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.company_add1"
              :rules="rules.company_add1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ประเภทธุรกิจ
                <br />Type of Business
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.type_of_business1"
              :rules="rules.type_of_business1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ระยะเวลา
                <br />Period
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.since1"
              :rules="rules.since1"
              label="เริ่ม/Since"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.until1"
              :rules="rules.until1"
              label="ถึง/Until"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.total1"
              :rules="rules.total1"
              label="รวม/Total"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                เงินเดือน
                <br />Salary
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.start1"
              :rules="rules.start1"
              label="เริ่ม/Start"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.s_last1"
              :rules="rules._s_last1"
              label="สุดท้าย/Final"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                รายได้อื่นนอกเหนือ
                <br />จากเงินเดือน
                <br />(เฉลี่ยต่อเดือน)
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.travelling_expenses1"
              :rules="rules.travelling_expenses1"
              label="ค่าพาหนะ/ Travelling expenses "
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mobile1"
              :rules="rules.mobile1"
              label="ค่าโทรศัพท์/ Mobile"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.commission1"
              :rules="rules.commission1"
              label="ค่าคอมมิชชัน/ Commission"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.ot1"
              :rules="rules.ot1"
              label="โอที/OT"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.bonus1"
              :rules="rules.bonus1"
              label="โบนัส/Bonus"
              placeholder="Details"
              dense
              outlined
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
          <v-col cols="4" md="5">
            <v-text-field
              v-model="datain.position1"
              :rules="rules.position1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                หน้าที่ความรับผิดชอบ
                <br />Type of Work
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-textarea
              outlined
              name="input-8-5"
              v-model="datain.job_Discription1"
              :rules="rules.job_Discription1"
              label="Details"
              hint="Details"
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-สกุล ผู้บังคับบัญชา/โทรศัพท์
                <br />Name-surname of contractor / telephone
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.tel1"
              :rules="rules.tel1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                สาเหตุที่ลาออก
                <br />Reason for Leaving
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.note1"
              :rules="rules.note1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">อันดับที่ 2/ No.2</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-ที่อยู่บริษัท
                <br />Name-
                <br />Address Employer
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.company_add2"
              :rules="rules.company_add2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ประเภทธุรกิจ
                <br />Type of Business
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.type_of_business2"
              :rules="rules.type_of_business2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ระยะเวลา
                <br />Period
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.since2"
              :rules="rules.since2"
              label="เริ่ม/Since"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.until2"
              :rules="rules.until2"
              label="ถึง/Until"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.total2"
              :rules="rules.total2"
              label="รวม/Total"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                เงินเดือน
                <br />Salary
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.start2"
              :rules="rules.start2"
              label="เริ่ม/Start"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.s_last2"
              :rules="rules.s_last2"
              label="สุดท้าย/Final"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                รายได้อื่นนอกเหนือ
                <br />จากเงินเดือน
                <br />(เฉลี่ยต่อเดือน)
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.travelling_expenses2"
              :rules="rules.travelling_expenses2"
              label="ค่าพาหนะ/ Travelling expenses "
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mobile2"
              :rules="rules.mobile2"
              label="ค่าโทรศัพท์/ Mobile"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.commission2"
              :rules="rules.commission2"
              label="ค่าคอมมิชชัน/ Commission"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.ot1"
              :rules="rules.ot1"
              label="โอที/OT"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.bonus2"
              :rules="rules.bonus2"
              label="โบนัส/Bonus"
              placeholder="Details"
              dense
              outlined
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
          <v-col cols="4" md="5">
            <v-text-field
              v-model="datain.position2"
              :rules="rules.position2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                หน้าที่ความรับผิดชอบ
                <br />Type of Work
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-textarea
              outlined
              name="input-8-5"
              v-model="datain.job_discription2"
              :rules="rules.job_discription2"
              label="Details"
              hint="Details"
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-สกุล ผู้บังคับบัญชา/โทรศัพท์
                <br />Name-surname of contractor / telephone
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.tel2"
              :rules="rules.tel2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                สาเหตุที่ลาออก
                <br />Reason for Leaving
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.note2"
              :rules="rules.note2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">อันดับที่ 3/ No.3</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-ที่อยู่บริษัท
                <br />Name-
                <br />Address Employer
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.company_add3"
              :rules="rules.company_add3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ประเภทธุรกิจ
                <br />Type of Business
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.type_of_business3"
              :rules="rules.type_of_business3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ระยะเวลา
                <br />Period
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.since3"
              :rules="rules.since3"
              label="เริ่ม/Since"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.until3"
              :rules="rules.until3"
              label="ถึง/Until"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.total3"
              :rules="rules.total3"
              label="รวม/Total"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                เงินเดือน
                <br />Salary
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.start3"
              :rules="rules.start3"
              label="เริ่ม/Start"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.s_last3"
              :rules="rules.s_last3"
              label="สุดท้าย/Final"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                รายได้อื่นนอกเหนือ
                <br />จากเงินเดือน
                <br />(เฉลี่ยต่อเดือน)
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.travelling_expenses3"
              :rules="rules.travelling_expenses3"
              label="ค่าพาหนะ/ Travelling expenses "
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mobile3"
              :rules="rules.mobile3"
              label="ค่าโทรศัพท์/ Mobile"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.commission3"
              :rules="rules.commission3"
              label="ค่าคอมมิชชัน/ Commission"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.ot3"
              :rules="rules.ot3"
              label="โอที/OT"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.bonus3"
              :rules="rules.bonus3"
              label="โบนัส/Bonus"
              placeholder="Details"
              dense
              outlined
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
          <v-col cols="4" md="5">
            <v-text-field
              v-model="datain.position3"
              :rules="rules.position3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                หน้าที่ความรับผิดชอบ
                <br />Type of Work
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-textarea
              outlined
              name="input-8-5"
              v-model="datain.job_discription3"
              :rules="rules.job_discription3"
              label="Details"
              hint="Details"
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-สกุล ผู้บังคับบัญชา/โทรศัพท์
                <br />Name-surname of contractor / telephone
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.tel3"
              :rules="rules.tel3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                สาเหตุที่ลาออก
                <br />Reason for Leaving
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.note3"
              :rules="rules.note3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">อันดับที่ 4/ No.4</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-ที่อยู่บริษัท
                <br />Name-
                <br />Address Employer
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.company_add4"
              :rules="rules.company_add4"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ประเภทธุรกิจ
                <br />Type of Business
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.type_of_business4"
              :rules="rules.type_of_business4"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ระยะเวลา
                <br />Period
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.since4"
              :rules="rules.since4"
              label="เริ่ม/Since"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.until4"
              :rules="rules.until4"
              label="ถึง/Until"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.total4"
              :rules="rules.total4"
              label="รวม/Total"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                เงินเดือน
                <br />Salary
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.start4"
              :rules="rules.start4"
              label="เริ่ม/Start"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.s_last4"
              :rules="rules.s_last4"
              label="สุดท้าย/Final"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                รายได้อื่นนอกเหนือ
                <br />จากเงินเดือน
                <br />(เฉลี่ยต่อเดือน)
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.travelling_expenses4"
              :rules="rules.travelling_expenses4"
              label="ค่าพาหนะ/ Travelling expenses "
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.mobile4"
              :rules="rules.mobile4"
              label="ค่าโทรศัพท์/ Mobile"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.commission4"
              :rules="rules.commission4"
              label="ค่าคอมมิชชัน/ Commission"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.ot4"
              :rules="rules.ot4"
              label="โอที/OT"
              placeholder="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.bonus4"
              :rules="rules.bonus4"
              label="โบนัส/Bonus"
              placeholder="Details"
              dense
              outlined
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
          <v-col cols="4" md="5">
            <v-text-field
              v-model="datain.position4"
              :rules="rules.position4"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                หน้าที่ความรับผิดชอบ
                <br />Type of Work
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-textarea
              outlined
              name="input-8-5"
              v-model="datain.job_discription4"
              :rules="rules.job_discription4"
              label="Details"
              hint="Details"
            ></v-textarea>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-สกุล ผู้บังคับบัญชา/โทรศัพท์
                <br />Name-surname of contractor / telephone
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.tel4"
              :rules="rules.tel4"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                สาเหตุที่ลาออก
                <br />Reason for Leaving
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="12" md="6">
            <v-text-field
              v-model="datain.note4"
              :rules="rules.note4"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">ประวัติการฝึกอบรม-สัมมนา / Training Course - Seminar</v-chip>
        <v-col cols="2">
          <v-row>
            <v-chip class="ma-2">ลำดับที่ 1</v-chip>
          </v-row>
        </v-col>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ชื่อสถาบัน/Institute</p>
            </v-subheader>
          </v-col>
          <v-col cols="4" md="4">
            <v-text-field
              v-model="datain.institute1"
              :rules="rules.institute1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">หัวข้อการฝึกอบรม/Course</p>
          </v-subheader>
          <v-col cols="2" md="3">
            <v-text-field
              v-model="datain.course1"
              :rules="rules.course1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ปีที่อบรม</p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.trainingyear1"
              :rules="rules.trainingyear1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">จำนวนเวลาที่อบรม</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.traininghours1"
              :rules="rules.traininghours11"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>

        <v-chip class="ma-2">ลำดับที่ 2</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ชื่อสถาบัน/Institute</p>
            </v-subheader>
          </v-col>
          <v-col cols="4" md="4">
            <v-text-field
              v-model="datain.institute2"
              :rules="rules.institute2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">หัวข้อการฝึกอบรม/Course</p>
          </v-subheader>
          <v-col cols="2" md="3">
            <v-text-field
              v-model="datain.course2"
              :rules="rules.course2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ปีที่อบรม</p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.trainingyear2"
              :rules="rules.trainingyear2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">จำนวนเวลาที่อบรม</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.traininghours2"
              :rules="rules.traininghours2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">ลำดับที่ 3</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ชื่อสถาบัน/Institute</p>
            </v-subheader>
          </v-col>
          <v-col cols="4" md="4">
            <v-text-field
              v-model="datain.institute3"
              :rules="rules.institute3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">หัวข้อการฝึกอบรม/Course</p>
          </v-subheader>
          <v-col cols="2" md="3">
            <v-text-field
              v-model="datain.course3"
              :rules="rules.course3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ปีที่อบรม</p>
            </v-subheader>
          </v-col>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.trainingyear3"
              :rules="rules.trainingyear3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">จำนวนเวลาที่อบรม</p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.traininghours3"
              :rules="rules.traininghours3"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip
          class="ma-2"
        >บุคคลที่สามารถติดต่อได้ ในกรณีฉุกเฉิน / Who should we contact in an emergency ?</v-chip>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ชื่อ-สกุล/Name-Surname *</p>
            </v-subheader>
          </v-col>
          <v-col cols="5" md="5">
            <v-text-field
              v-model="datain.name_surname"
              :rules="rules.name_surname"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">ความสัมพันธ์/Relation *</p>
          </v-subheader>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.relation1"
              :rules="rules.relation1"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">ที่อยู่/Address</p>
            </v-subheader>
          </v-col>
          <v-col cols="5" md="5">
            <v-text-field
              v-model="datain.address"
              :rules="rules.address"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">โทรศัพท์มือถือ<br />Mobile*</p>
          </v-subheader>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.mobile"
              :rules="rules.mobile"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">
            <v-subheader>
              <p class="font-weight-black">
                ที่ทำงำน
                <br />Office *
              </p>
            </v-subheader>
          </v-col>
          <v-col cols="3" md="3">
            <v-text-field
              v-model="datain.office"
              :rules="rules.office"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">
              ตำแหน่ง
              <br />Position
            </p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.position"
              :rules="rules.position"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-subheader>
            <p class="font-weight-black">
              โทรศัพท์
              <br />Telephone *
            </p>
          </v-subheader>
          <v-col cols="2" md="2">
            <v-text-field
              v-model="datain.telephone"
              :rules="rules.telephone"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-chip class="ma-2">ข้อมูลเพิ่มเติม / Miscellaneous</v-chip>
        <v-row>
          <v-col cols="5">
            <v-subheader>
              <p class="font-weight-black">
                คุณเคยต้องโทษทางอาญาหรือไม่
                <br />Do you have any criminal or civil record?
              </p>
            </v-subheader>
          </v-col>
          <v-checkbox v-model="datain.no1" label="ไม่เคย/NO" value="ไม่เคย/NO"></v-checkbox>
          <v-checkbox v-model="datain.yes1" label="เคย/Yes" value="เคย/Yes"></v-checkbox>
          <v-subheader>ระบุ/Explain</v-subheader>
          <v-text-field
            v-model="datain.explain1"
            :rules="rules.explain1"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-row>
        <v-row>
          <v-col cols="5">
            <v-subheader>
              <p class="font-weight-black">
                คุณเคยสมัครงานหรือทำงานกับบริษัทมาก่อนหรือไม่
                <br />Have you ever applied to this company?
              </p>
            </v-subheader>
          </v-col>
          <v-checkbox v-model="datain.no2" label="ไม่เคย/NO" value="ไม่เคย/NO"></v-checkbox>
          <v-checkbox v-model="datain.yes2" label="เคย/Yes" value="เคย/Yes"></v-checkbox>
          <v-subheader>ระบุ/Explain</v-subheader>
          <v-text-field
            v-model="datain.explain2"
            :rules="rules.explain2"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-row>
        <v-row>
          <v-col cols="5">
            <v-subheader>
              <p class="font-weight-black">
                คุณเคยป่วยหนักหรือเป็นโรคติดต่อร้ายแรงหรือไม่
                <br />Have you ever been seriously ill or contracted with contagious disease?
              </p>
            </v-subheader>
          </v-col>
          <v-checkbox v-model="datain.no3" label="ไม่เคย/NO" value="ไม่เคย/NO"></v-checkbox>
          <v-checkbox v-model="datain.yes3" label="เคย/Yes" value="เคย/Yes"></v-checkbox>
          <v-subheader>ระบุ/Explain</v-subheader>
          <v-text-field
            v-model="datain.explain3"
            :rules="rules.explain3"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-row>
        <v-row>
          <v-col cols="5">
            <v-subheader>
              <p class="font-weight-black">
                บริษัทสามารถพูดคุยกับนายจ้างเดิมของคุณได้หรือไม่
                <br />Can we contact your past employer?
              </p>
            </v-subheader>
          </v-col>
          <v-checkbox v-model="datain.no4" label="ไม่ได้/NO" value="ไม่ได้/NO"></v-checkbox>
          <v-checkbox v-model="datain.yes4" label="ได้/Yes" value="ได้/Yes"></v-checkbox>
          <v-subheader>เพราะ/ Because</v-subheader>
          <v-text-field
            v-model="datain.because"
            :rules="rules.because"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-row>
        <v-subheader>
          <p
            class="font-weight-black"
          >บุคคลในบริษัทที่คุณรู้จัก/Relatives or friends working in this company</p>
        </v-subheader>
        <v-row>
          <v-col cols="4" md="4">
            <v-subheader>
              <p class="font-weight-black">
                ชื่อ-สกุล
                <br />Name-Surname
              </p>
            </v-subheader>
            <v-text-field
              v-model="datain.name"
              :rules="rules.name"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="3" md="3">
            <v-subheader>
              <p class="font-weight-black">แผนก/Department</p>
            </v-subheader>
            <v-text-field
              v-model="datain.department"
              :rules="rules.department"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
          <v-col cols="2" md="2">
            <v-subheader>
              <p class="font-weight-black">ความสัมพันธ์/Relation</p>
            </v-subheader>
            <v-text-field
              v-model="datain.relation2"
              :rules="rules.relation2"
              label="Details"
              hint="Details"
              dense
              outlined
            ></v-text-field>
          </v-col>
        </v-row>
        <v-list-item-content>
          <v-col cols="9">
            <v-subheader>
              <p class="font-weight-black">
                ข้าพเจ้าขอรับรองว่ารายละเอียดทั้งหมดเป็นความจริงทุกประการ หากปรากฏว่าหลักฐาน และ / หรือ ข้อความที่ให้ไว้ไม่เป็นความจริง ข้าพเจ้าขอให้บริษัทฯ
                เลิกจ้างข้าพเจ้า โดยข้ำพเจ้าไม่ขอรับค่าชดเชยใดๆทั้งสิ้น
                <br />
                <br />The statement made by me in this application are true, a false statement or dishonest answer to any question may be ground for my immediate
                discharge from employment with the company.
              </p>
            </v-subheader>
          </v-col>
        </v-list-item-content>

        <v-col cols="4" md="4">
          <v-text-field
            v-model="datain.salary_expectation"
            :rules="rules.salary_expectation"
            label="เงินเดือนที่ต้องการ/Salary Expectation "
            placeholder="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-col cols="4" md="4">
          <v-text-field
            v-model="datain.other_income_expected"
            :rules="rules.other_income_expected"
            label="รายได้อื่นที่คาดหวัง
              /Other income expected"
            placeholder="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>

        <v-col cols="4" md="4">
          <v-text-field
            v-model="datain.applicant_s_signature"
            :rules="rules.applicant_s_signature"
            label="ลงชื่อผู้สมัคร/Applicant's signature "
            placeholder="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
      </v-form>
      <v-row>
        <v-btn color="primary" :disabled="!valid" @click="save()">Save</v-btn>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
export default {
  props: ["datain"],
  data() {
    return {
      data: null,
      valid: false,
      rules: {
       
      }
      // datain:this.sdata,
    };
  },
   methods: {
    async init() {
      //  console.log(this.datain)
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
      this.$parent.$parent.$parent.$parent.$parent.$parent.$parent.$parent.dialog = false;
      await axios({
        method: "put",
        url: urldata + "/" + this.datain.id,
        data: this.datain
      });
    }
  },
  mounted() {
    this.init();
  }
};
</script>

