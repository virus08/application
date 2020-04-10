<template>
  <v-card>
    <v-container fluid>
      <v-row>
      <v-subheader>
                ระดับการศึกษา/ Level
              </v-subheader>
        <v-col cols="4">
          <v-autocomplete
            v-model="a"
            :items="t"
            outlined
            dense
            chips
            small-chips
            multiple
            label="ระดับการศึกษา/ Level"
            prepend-inner-icon="mdi-human-male"
            hint="ระดับการศึกษา/ Level"
          >></v-autocomplete>
        </v-col>
        <v-subheader>
                ชื่อสถานศึกษาและที่ตั้ง
                <br />Name of Institution/Location
              </v-subheader>
        <v-col cols="4">
          <v-text-field
          v-model="mather_wp"
              :rules="rules.mather_wp"
            label="ชื่อสถานศึกษาและที่ตั้ง/ Name of Institution/Location"
            hint="ชื่อสถานศึกษาและที่ตั้ง/ Name of Institution/Location"
            dense
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-subheader>
                ปีที่ศึกษา/Period
              </v-subheader>
        <v-col cols="12" sm="3">
          <v-text-field v-model.number="year" class="px-4" label="จาก/ From" type="number"></v-text-field>
        </v-col>
        <v-col cols="12" sm="3">
          <v-text-field v-model.number="yea" class="px-4" label="ถึง/ To" type="number"></v-text-field>
        </v-col>
      </v-row>

      <v-row>
      <v-subheader>
                คะแนนเฉลี่ย
                <br />G.P.A
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คะแนนเฉลี่ย/ G.P.A" hint="คะแนนเฉลี่ย/ G.P.A" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                วุฒิการศึกษา
                <br />Degree/Cert.
              </v-subheader>
        <v-col cols="2">
          <v-text-field
            label="วุฒิการศึกษา/ Degree/Cert."
            hint="วุฒิการศึกษา/ Degree/Cert."
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
                วิชาเอก
                <br />Major
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="วิชาเอก/ Major" hint="วิชาเอก/ Major" dense outlined></v-text-field>
        </v-col>
        <v-subheader>
                คณะ
                <br />Dept.
              </v-subheader>
        <v-col cols="2">
          <v-text-field label="คณะ/ Dept." hint="คณะ/ Dept." dense outlined></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-col cols="4">
          <v-checkbox v-model="checkbox" :label="`ปัจจุบันศึกษาต่อ/ Studying `"></v-checkbox>
        </v-col>
      </v-row>
      <v-row>
      <v-subheader>
                ศึกษาต่ออยู่ที่
                <br />Institute
              </v-subheader>
        <v-col cols="4">
          <v-text-field
            label="ศึกษาต่ออยู่ที่/ Institute"
            hint="ศึกษาต่ออยู่ที่/ Institute"
            dense
            outlined
          ></v-text-field>
        </v-col>
        <v-subheader>
                ปีที่จบ
                <br />Year to Graduate
              </v-subheader>
        <v-col cols="3" sm="4">
          <v-text-field
            v-model.number="ye"
            class="px-2"
            label="ปีที่จบ/ Year to Graduate"
            type="number"
          ></v-text-field>
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
            :items="i"
            outlined
            dense
            chips
            small-chips
            label="ระดับการศึกษา/ Level"
            prepend-inner-icon="mdi-human-male"
            hint="ระดับการศึกษา/ Level"
            multiple
          ></v-autocomplete>
        </v-col>
        <v-subheader>
                วิชาเอก/คณะ
                <br />Major/Dept.
              </v-subheader>
        <v-col cols="4">
          <v-text-field
            label="วิชาเอก/คณะ/ Major/Dept."
            hint="วิชาเอก/คณะ/ Major/Dept."
            dense
            outlined
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row>
        <v-chip class="ma-5">กิจกรรมพิเศษ/ Activities</v-chip>
      </v-row>
      <v-row>
        <v-container fluid>
          <v-textarea autocomplete label></v-textarea>
        </v-container>
      </v-row>
      <v-row>
        <v-chip class="ma-5">งานอดิเรก/กีฬา / Hobbies/Sports</v-chip>
      </v-row>
      <v-row>
        <v-container fluid>
          <v-textarea autocomplete label></v-textarea>
        </v-container>
      </v-row>
      <v-row>
        <v-chip class="ma-2">ด้านยานพาหนะ / Vehicle</v-chip>
      </v-row>
      <v-row>
        <v-container fluid>
          <v-checkbox v-model="checkbox1" :label="`รถยนต์/ Car: ${checkbox1.toString()}`"></v-checkbox>
          <v-checkbox
            v-model="checkbox2"
            :label="`รถมอเตอร์ไซต์/ Motorcycle: ${checkbox2.toString()}`"
          ></v-checkbox>
        </v-container>
      </v-row>
      <v-row>
        <v-chip class="ma-2">ความสามารถพิเศษ/ Special Ability</v-chip>
      </v-row>
      <v-row>
       <v-subheader>
                ด้านคอมพิวเตอร์/ Computer Skill
              </v-subheader>
        <v-col cols="4" sm="6" md="2">
          <v-text-field label="Software " placeholder="Software " outlined dense></v-text-field>
        </v-col>
        <v-col cols="4" sm="6" md="2">
          <v-text-field label="Hardware" placeholder="Hardware" outlined dense></v-text-field>
        </v-col>
        <v-col cols="4" sm="6" md="2">
          <v-text-field label="Certificate" placeholder="Certificate" outlined dense></v-text-field>
        </v-col>
        <v-col cols="4" sm="6" md="2">
          <v-text-field label="Others" placeholder="Others" outlined dense></v-text-field>
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
            v-model="v"
            :items="items"
            outlined
            dense
            chips
            small-chips
            label="เข้าใจ/ Understanding"
            prepend-inner-icon="mdi-human-male"
            hint="เข้าใจ/ Understanding"
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
            label="พูด/ Speaking"
            prepend-inner-icon="mdi-human-male"
            hint="พูด/ Speaking"
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
            label="อ่าน/ Reading"
            prepend-inner-icon="mdi-human-male"
            hint="อ่าน/ Reading"
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
            label="เขียน/ Writing"
            prepend-inner-icon="mdi-human-male"
            hint="เขียน/ Writing"
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
          <v-text-field label="ภาษา/ Language" hint="ภาษา/ Language" dense outlined></v-text-field>
        </v-col>
        <v-col cols="2">
          <v-autocomplete
            v-model="k"
            :items="items"
            outlined
            dense
            chips
            small-chips
            label="เข้าใจ/ Understanding"
            prepend-inner-icon="mdi-human-male"
            hint="เข้าใจ/ Understanding"
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
            label="พูด/ Speaking"
            prepend-inner-icon="mdi-human-male"
            hint="พูด/ Speaking"
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
            label="อ่าน/ Reading"
            prepend-inner-icon="mdi-human-male"
            hint="อ่าน/ Reading"
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
            label="เขียน/ Writing"
            prepend-inner-icon="mdi-human-male"
            hint="เขียน/ Writing"
          ></v-autocomplete>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    checkbox: false,
    t: ["ปวส.", "ปริญญาตรี", "ปริญญาโท", "ม.ปลาย/ ปวช./ อื่น ๆ"],
    a: ["ปวส.", "ปริญญาตรี", "ปริญญาโท", "ม.ปลาย/ ปวช./ อื่น ๆ"],
    value: null,
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    year: 2500,
    x: null,
    y: "top",
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    yea: 2500,
    x: null,
    y: "top",
    color: "",
    mode: "",
    snackbar: false,
    text: "Hello, I'm a snackbar",
    ye: 2500,
    x: null,
    y: "top",
    checkbox: false,
    i: ["ปวส.", "ปริญญาตรี", "ปริญญาโท", "ม.ปลาย/ ปวช./ อื่น ๆ"],
    v: ["ปวส.", "ปริญญาตรี", "ปริญญาโท", "ม.ปลาย/ ปวช./ อื่น ๆ"],
    values: null,
    radios: "radio-1",
    checkbox1: true,
    checkbox2: false,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    v: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    a: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    l: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    values: ["ดี", "พอใช้", "ไม่ดี"],
    u: null,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    k: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    n: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    o: ["ดี", "พอใช้", "ไม่ดี"],
    value: null,
    checkbox: false,
    items: ["ดี", "พอใช้", "ไม่ดี"],
    p: ["ดี", "พอใช้", "ไม่ดี"],
    value: null
  })
};
</script>
