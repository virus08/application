<template>
  <v-card>
    <v-container fluid>
      <v-form ref="form" v-model="valid">
        <v-subheader>
          <p class="font-weight-black">1). อะไรที่ทำให้คุณอยากเปลี่ยนงานใหม่ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details1"
            :rules="rules.details1"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">2). อะไรที่ทำให้คุณสนใจมาสมัครงานที่นี่ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details2"
            :rules="rules.details2"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">3). คุณคิดว่าตัวคุณเหมาะสมกับตำแหน่งที่คุณสมัครอย่างไรบ้าง *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details3"
            :rules="rules.details3"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p
            class="font-weight-black"
          >4). ในการทำงานที่ผ่านมาคุณได้ตั้งเป้าหมายในการทำงานหรือไม่ และประสบความสำเร็จตามเป้าหมายมากน้อยเพียงใด *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details4"
            :rules="rules.details4"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">5). อธิบายความหมายของ “คิดบวกเชิงสร้างสรรค์” ในความคิดของคุณ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details5"
            :rules="rules.details5"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">6). อธิบายความหมายของ “จริงใจในสิ่งที่ทำ” ในความคิดของคุณ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details6"
            :rules="rules.details6"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">7). อธิบายความหมายของ “ทำงานอย่างมืออาชีพ” ในความคิดของคุณ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details7"
            :rules="rules.details7"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">8). อธิบายความหมายของ “เป็นเจ้าของร่วมกัน” ในความคิดของคุณ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details8"
            :rules="rules.details8"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">9). อธิบายความหมายของ “รวมพลังเป็นหนึ่งเดียว” ในความคิดของคุณ *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details9"
            :rules="rules.details9"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">10).ผลงานใดที่ทำให้คุณภาคภูมิใจมากที่สุด *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details10"
            :rules="rules.details10"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">11). หากคุณเลือกได้คุณอยากมีหัวหน้าแบบใด *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details11"
            :rules="rules.details11"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">12). หากคุณเลือกได้คุณอยากได้ลูกน้องแบบใด *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details12"
            :rules="rules.details12"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p
            class="font-weight-black"
          >13). เมื่อคุณประสบปัญหาในการทำงาน (หรือชีวิต) มากที่สุด จนรู้สึกท้อถอย คุณมีวิธีการแก้ไขสถานการณ์นั้นอย่างไร *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details13"
            :rules="rules.details13"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
          <p class="font-weight-black">14). คุณคิดว่าอยากจะพัฒนาตนเองในเรื่องใดมากที่สุด เพราะอะไร *</p>
        </v-subheader>
        <v-col cols="2" md="10">
          <v-text-field
            v-model="datain.details14"
            :rules="rules.details14"
            label="Details"
            hint="Details"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-chip class="ma-2">English Writing</v-chip>
        <v-subheader>
          <p
            class="font-weight-black"
          >Please choose 1 topic for paragraph writing about 100 words or 10 sentences</p>
        </v-subheader>

        <v-radio-group >
          <v-col>
          <v-row>
            <v-checkbox v-model="datain.english_writing" label="My life in next 5 years" value="My life in next 5 years"></v-checkbox>         
          </v-row>
          <v-row>
            <v-checkbox v-model="datain.english_writing" label="If I could turn back time" value="If I could turn back time"></v-checkbox>       
          </v-row>
          <v-row> 
            <v-checkbox v-model="datain.english_writing" label="My dream boss" value="My dream boss"></v-checkbox>
          </v-row>
          </v-col>
        </v-radio-group>

        <p class="font-weight-medium"></p>
        <v-col cols="2" md="10">
          <v-textarea
            outlined
            name="input-8-5"
            v-model="datain.details15"
            :rules="rules.details15"
            label="Details"
            hint="Details"
          ></v-textarea>
        </v-col>
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
        details1: [v => !!v || " Details is required"],
        details2: [v => !!v || " Details is required"],
        details3: [v => !!v || " Details is required"],
        details4: [v => !!v || " Details is required"],
        details5: [v => !!v || " Details is required"],
        details6: [v => !!v || " Details is required"],
        details7: [v => !!v || " Details is required"],
        details8: [v => !!v || " Details is required"],
        details9: [v => !!v || " Details is required"],
        details10: [v => !!v || " Details is required"],
        details11: [v => !!v || " Details is required"],
        details12: [v => !!v || " Details is required"],
        details13: [v => !!v || " Details is required"],
        details14: [v => !!v || " Details is required"],
        details15: [v => !!v || " Details is required"]
      },
      datain: {
        details1: "",
        details2: "",
        details3: "",
        details4: "",
        details5: "",
        details6: "",
        details7: "",
        details8: "",
        details9: "",
        details10: "",
        details11: "",
        details12: "",
        details13: "",
        details14: "",
        english_writing:"",
        details15: ""
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
      this.$parent.$parent.$parent.e6 = 0;
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

