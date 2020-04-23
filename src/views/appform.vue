<template>
  <div>
    <div class="Contianner">
      <div style="text-align:center;">
        <h2>บริษัทวีเอสที อีซีเอส (ประเทศไทย) จำกัด</h2>
        <h2>VST ECS (Thailand) Co., Ltd.</h2>
        <br />
        <p style="font-size:8pt;">
          275 ซอยลาดพร้าว 101 (วัดบึงทองหลาง) แขวงคลองเจ้าคุณสิงห์ เขตวังทองหลาง กรุงเทพฯ 10310
          <br />275 Soi Lat Phrao 101 (Wat Bung Thonglang), Khlong Chao Khun Sing, Wang Thonglang, Bangkok 10310, Thailand
          <br />โทร.0-2032-9999 แฟกซ์ 0-2032-9989
        </p>
      </div>
      <div>
        <table class="Type1" style="height:3.5cm;" cellpadding="0" cellspacing="0">
          <tr>
            <td class="Type1">
              <v-row>
                <v-col cols="3">วันที่/ Date</v-col>
                <v-col cols="4">
                  <input class="txt" type="text" style="width:10cm" :value="xdate" />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">ตำแหน่ง/ Position</v-col>
                <v-col cols="4">
                  <input
                    class="txt"
                    type="text"
                    style="width:10cm"
                    :value="data.positionnew"
                  />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">วันที่เริ่มงาน/ Starting Date</v-col>
                <v-col cols="4">
                  <input class="txt" type="text" style="width:10cm" :value="xdate3" />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">ทราบข่าวการสมัครจาก</v-col>
                <v-col cols="4">
                  <input class="txt" type="text" style="width:10cm" :value="data.news" />
                </v-col>
              </v-row>
            </td>
            <td class="Type1" align="center" style="width:3.5cm;">
              <img alt :src="data.img" height="148" width="120" />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p style="text-decoration:underline;">ประวัติส่วนบุคคล / Personnel Data</p>
        <v-row>
          <v-col cols="1">ชื่อ - สกุล</v-col>
          <v-col cols="8">
            <input
              align="left"
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.nt+' '+data.namet+' '+data.surnamet"
            />
          </v-col>
          <v-col cols="1">ชื่อเล่น</v-col>
          <v-col cols="2">
            <input align="left" class="txt" type="text" style="width:3cm" :value="data.nickt" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="1">Name - Surname</v-col>
          <v-col cols="8">
            <input
              align="left"
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.ne+' '+data.namee+' '+data.surnamee"
            />
          </v-col>
          <v-col cols="1">Nickname</v-col>
          <v-col cols="2">
            <input align="left" class="txt" type="text" style="width:3cm" :value="data.nicke" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">วันเกิด/ Birth Date</v-col>
          <v-col cols="7">
            <input class="txt" type="text" style="width:9.5cm" :value="xdate4" />
          </v-col>
          <v-col cols="1">อายุ</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:2.4cm;padding-left:40px;" :value="data.age" /> ปี
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">สถานที่เกิด/ Place of birth</v-col>
          <v-col cols="7">
            <input class="txt" type="text" style="width:10cm" :value="data.pofb" />
          </v-col>
          <v-col cols="1">เพศ</v-col>
          <v-col cols="1">
            <input class="txt" type="text" style="width:2.5cm" :value="data.sex" />
          </v-col>
        </v-row>
        <br />
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1">
              สัญชาติ
              <br />Nationality
            </th>
            <th class="Type1">
              เชื้อชาติ
              <br />Race
            </th>
            <th class="Type1">
              ศาสนา
              <br />Religion
            </th>
            <th class="Type1">
              ส่วนสูง
              <br />Height
            </th>
            <th class="Type1">
              น้ำหนัก
              <br />Weight
            </th>
          </tr>
          <tr align="center">
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" :value="data.nationality" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" :value="data.xcitizen" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm" :value="data.religion" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" :value="data.height" /> cm.
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" :value="data.weigth" /> kg.
            </td>
          </tr>
        </table>

        <v-row>
          <v-col cols="3">
            ที่อยู่ปัจจุบัน
            <br />Present Address
          </v-col>
          <v-col cols="9">
            <input
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.pr_add+' '+data.pr_addhh+' '+data.pr_soi+' '+data.pr_street"
            />
            <br />
            <input
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.pr_district+' '+data.pr_aumphur+' '+data.pr_proince+' '+data.pr_country+' '+data.pr_postaicode"
            />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="1">Telephone</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:2cm" :value="data.tel" />
          </v-col>
          <v-col cols="1">Mobile</v-col>
          <v-col cols="3">
            <input class="txt" type="text" style="width:3.5cm" :value="data.mobile" />
          </v-col>
          <v-col cols="1">E-mail</v-col>
          <v-col cols="3">
            <input class="txt" type="text" style="width:4cm" :value="data.email" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3">
            ที่อยู่ตามทะเบียนบ้าน
            <br />Permanent Address
          </v-col>
          <v-col cols="9">
            <input
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.re_add+' '+data.re_addhh+' '+data.re_soi+' '+data.re_street"
            />
            <br />
            <input
              class="txt"
              type="text"
              style="width:11.5cm"
              :value="data.re_district+' '+data.re_aumphur+' '+data.re_proince+' '+data.re_country+' '+data.re_postaicode"
            />
          </v-col>
          <v-row>
            <v-col cols="3">
              สถานที่ทำงานปัจจุบัน
              <br />Office Address
            </v-col>
            <v-col cols="9">
              <input class="txt" type="text" style="width:11.5cm" value />
              <br />
              <input class="txt" type="text" style="width:11.5cm" value />
            </v-col>
            <v-row>
              <v-col cols="2">Telephone</v-col>
              <v-col cols="3">
                <input class="txt" type="text" style="width:3.5cm" value />
              </v-col>
              <v-col cols="1">Extension</v-col>
              <v-col cols="1">
                <input class="txt" type="text" style="width:1cm" value />
              </v-col>
              <v-col cols="3">สถานภาพการสมรส Marital Status</v-col>
              <v-col cols="1">
                <input class="txt" type="text" style="width:1.5cm" value="โสด" />
              </v-col>
            </v-row>
          </v-row>
        </v-row>
      </div>
      <div>
        <p style="text-decoration:underline;">ข้อมูลของคู่สมรสและบุตร / Family Information</p>
        <v-row>
          <v-col cols="2">
            ชื่อ-สกุล คู่สมรส
            <br />Name of spouse
          </v-col>
          <v-col cols="7.5">
            <input class="txt" type="text" style="width:10cm" :value="data.spouses_n" />
          </v-col>
          <v-col cols="0">บุตร</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:1cm" :value="data.spouses_oder" /> คน
          </v-col>
        </v-row>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:2.5cm;">
              สถานที่ทำงาน
              <br />Office Address
            </td>
            <td>
              <input class="txt" type="text" style="width:14cm" :value="data.spouses_wp" />
            </td>
          </tr>
        </table>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:2.5cm;">
              โทรศัพท์
              <br />Telephone
            </td>
            <td>
              <input class="txt" type="text" style="width:3.5cm" :value="data.spouses_tel" />
            </td>
            <td style="width:2.0cm; text-align:center;">
              อาชีพ
              <br />Occupation
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" :value="data.oc" />
            </td>
            <td style="width:2.0cm; text-align:center;">
              ตำแหน่ง
              <br />Position
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" :value="data.oc" />
            </td>
          </tr>
        </table>
      </div>
    </div>
    <div class="Contianner">
      <div>
        <p
          style="text-decoration:underline;"
        >ประวัติครอบครัว (ประวัติของบิดา/ มารดา/ พี่น้องทุกคน)/ Family background</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1">
              ความสัมพันธ์
              <br />Relation
            </th>
            <th class="Type1">
              ชื่อ-สกุล
              <br />Full Name
            </th>
            <th class="Type1">
              อายุ
              <br />Age
            </th>
            <th class="Type1">
              สถานที่ทำงาน/ โทรศัพท์
              <br />Company/ Telephone
            </th>
            <th class="Type1">
              อาชีพ
              <br />Occupation
            </th>
          </tr>
          <tr>
            <td class="Type1" style="width:2cm;">บิดา</td>
            <td class="Type1" style="width:4cm;">
              <input class="txt" type="text" style="width:4cm;" :value="data.father_n" />
            </td>
            <td class="Type1" style="width:0.8cm;">
              <input class="txt" type="text" style="width:0.5cm" :value="data.father_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.father_wp" />
            </td>
            <td class="Type1" style="width:2.5cm;">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.father_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">มารดา</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.mather_n" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.mather_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.mather_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.mater_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 1</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.bs_name" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.bs_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.bs_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.bs_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 2</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.bs2_name" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.bs2_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.bs2_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.bs2_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 3</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.bs3_name" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.bs3_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.bs3_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.bs3_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 4</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.bs4_name" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.bs4_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.bs4_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.bs4_oc" />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 5</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" :value="data.bs5_name" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" :value="data.bs5_age" />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" :value="data.bs5_wp" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" :value="data.bs5_oc" />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p style="text-decoration:underline;">ประวัติการศึกษา / Educational background</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1">ระดับการศึกษา/ Level</th>
            <th class="Type1">รายละเอียด/ Description</th>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              ประถมศึกษา
              <br />Primary School
            </th>

            <td class="Type1">
              <p>
                ชื่อสถานศึกษาและที่ตั้ง
                <input
                  class="txt"
                  type="text"
                  style="width:6.5cm;"
                  :value="data.institute1"
                />
                ประเทศ
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.country1"
                />
              </p>

              <p>
                วุฒิการศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:7.5cm;"
                  :value="data.degree1"
                />
                คะแนนเฉลี่ย
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.grade1"
                />
              </p>

              <p>
                คณะ
                <input class="txt" type="text" style="width:4cm;" :value="data.name_dept1" />
                สาขา
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.major1"
                />
                ปีที่ศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.yIn1+' - '+data.yout1"
                />
              </p>
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              มัธยมศึกษา
              <br />Secondary School
            </th>
            <td class="Type1">
              <p>
                ชื่อสถานศึกษาและที่ตั้ง
                <input
                  class="txt"
                  type="text"
                  style="width:6.5cm;"
                  :value="data.institute2"
                />
                ประเทศ
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.country2"
                />
              </p>

              <p>
                วุฒิการศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:7.5cm;"
                  :value="data.degree2"
                />
                คะแนนเฉลี่ย
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.grade2"
                />
              </p>

              <p>
                คณะ
                <input class="txt" type="text" style="width:4cm;" :value="data.name_dept2" />
                สาขา
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.major2"
                />
                ปีที่ศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.yIn2+' - '+data.yout2"
                />
              </p>
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              ปริญญาตรี
              <br />Bachelor's Degree
            </th>
            <td class="Type1">
              <p>
                ชื่อสถานศึกษาและที่ตั้ง
                <input
                  class="txt"
                  type="text"
                  style="width:6.5cm;"
                  :value="data.institute3"
                />
                ประเทศ
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.country3"
                />
              </p>

              <p>
                วุฒิการศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:7.5cm;"
                  :value="data.degree3"
                />
                คะแนนเฉลี่ย
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.grade3"
                />
              </p>

              <p>
                คณะ
                <input class="txt" type="text" style="width:4cm;" :value="data.name_dept3" />
                สาขา
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.major3"
                />
                ปีที่ศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.yIn3+' - '+data.yout3"
                />
              </p>
            </td>
          </tr>

          <tr>
            <th class="Type1" style="width:3.5cm;">
              ปริญญาโท
              <br />Master's Degree
            </th>
            <td class="Type1">
              <p>
                ชื่อสถานศึกษาและที่ตั้ง
                <input
                  class="txt"
                  type="text"
                  style="width:6.5cm;"
                  :value="data.institute4"
                />
                ประเทศ
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.country4"
                />
              </p>

              <p>
                วุฒิการศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:7.5cm;"
                  :value="data.degree4"
                />
                คะแนนเฉลี่ย
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.grade4"
                />
              </p>

              <p>
                คณะ
                <input class="txt" type="text" style="width:4cm;" :value="data.name_dept4" />
                สาขา
                <input
                  class="txt"
                  type="text"
                  style="width:4cm;"
                  :value="data.major4"
                />
                ปีที่ศึกษา
                <input
                  class="txt"
                  type="text"
                  style="width:3.5cm;"
                  :value="data.yIn4+' - '+data.yout4"
                />
              </p>
            </td>
          </tr>
        </table>
      </div>

      <div>
        <p style="text-decoration:underline;">ความสามารถพิเศษ/ Special Ability</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" colspan="2">
              <p>ด้านคอมพิวเตอร์/ Computer Skills</p>
            </th>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Software</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" :value="xsoftware"  />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Hardware</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" :value="xhardware" />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Certificate</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" :value="xcertificate" />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Others</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" :value="xothers" />
            </td>
          </tr>
        </table>
      </div>
    </div>
   <div class="Contianner">
      <div>
        <p style="text-decoration:underline;">ประวัติการฝึกอบรม-สัมมนา / Training Course - Seminar</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" rowspan="1">&nbsp;</th>
            <th class="Type1" rowspan="1" style="width:5cm;">
              ชื่อสถาบัน
              <br />Institute
            </th>
            <th class="Type1" rowspan="1" style="width:5cm;">
              หัวข้อการฝึกอบรม
              <br />Course
            </th>
             <th class="Type1" rowspan="1" style="width:3.5m;">
             ปีที่อบรม
            </th>
             <th class="Type1" rowspan="1" style="width:3.5cm;">
              จำนวนเวลาที่อบรม
            </th>
          <tr>
            <th class="Type1" >1.</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.institute1" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.course1" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.trainingyear1" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.traininghours1" />
            </td>
          </tr>
          <tr>
            <th class="Type1">2.</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.institute2" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.course2" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.trainingyear2" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.traininghours2" />
            </td>
          </tr>
          <tr>
            <th class="Type1">3.</th>
             <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.institute3" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5cm;" :value="data.course3" />
            </td>
             <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.trainingyear3" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:3.5cm;" :value="data.traininghours3" />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p
          style="text-decoration:underline;"
        >ประวัติการทำงาน จากปัจจุบันไปหาอดีต/Employment Record (List from present to last)</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:4cm;">
              ชื่อ-ที่อยู่บริษัท
              <br />Name & Address Employer
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.company_add1" />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.type_of_business1" />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.tel1" />
            </td>
          </tr>
        </table>
       <table class="Type1" cellpadding="0" cellspacing="0">
        <tr>
          <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
          <th class="Type1" rowspan="2">เงินเดือนล่าสุด<br />Salary</th>
          <th class="Type1" colspan="4">เงินได้พิเศษ/ Special Income</th>
        </tr>
        <tr>
          <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
          <th class="Type1" style="width:1.8cm;">ถึง</th>
          <th class="Type1" style="width:2cm;">รวม</th>
          <th class="Type1" style="width:2cm;">ค่าพาหนะ</th>
          <th class="Type1" style="width:2cm;">ค่าโทรศัพท์</th>
          <th class="Type1" style="width:2cm;">ค่าคอมมิชชัน</th>
          <th class="Type1" style="width:2cm;">อื่นๆ</th>
        </tr>
        <tr>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.since1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.until1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.total1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2.5cm;" :value="data.travelling_expenses1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.mobile1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.commission1"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input  class="txt" type="text" style="width:10.5cm;" :value="data.position1"   />
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;"  :value="data.job_Discription1" />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" :value="data.note1" />
            </td>
          </tr>
        </table>
        <br />
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:4cm;">
              ชื่อ-ที่อยู่บริษัท
              <br />Name & Address Employer
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.company_add2" />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;"  :value="data.type_of_business2" />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.tel2" />
            </td>
          </tr>
        </table>
       <table class="Type1" cellpadding="0" cellspacing="0">
        <tr>
          <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
          <th class="Type1" rowspan="2">เงินเดือนล่าสุด<br />Salary</th>
          <th class="Type1" colspan="4">เงินได้พิเศษ/ Special Income</th>
        </tr>
        <tr>
          <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
          <th class="Type1" style="width:1.8cm;">ถึง</th>
          <th class="Type1" style="width:2cm;">รวม</th>
          <th class="Type1" style="width:2cm;">ค่าพาหนะ</th>
          <th class="Type1" style="width:2cm;">ค่าโทรศัพท์</th>
          <th class="Type1" style="width:2cm;">ค่าคอมมิชชัน</th>
          <th class="Type1" style="width:2cm;">อื่นๆ</th>
        </tr>
        <tr>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.since2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.until2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.total2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2.5cm;" :value="data.travelling_expenses2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.mobile2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.commission2"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;"  :value="data.position2" />
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;"  :value="data.job_Discription2" />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" :value="data.note2" />
            </td>
          </tr>
        </table>
        <br />
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:4cm;">
              ชื่อ-ที่อยู่บริษัท
              <br />Name & Address Employer
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.company_add3"/>
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.type_of_business3" />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" :value="data.tel3" />
            </td>
          </tr>
        </table>
      <table class="Type1" cellpadding="0" cellspacing="0">
        <tr>
          <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
          <th class="Type1" rowspan="2">เงินเดือนล่าสุด<br />Salary</th>
          <th class="Type1" colspan="4">เงินได้พิเศษ/ Special Income</th>
        </tr>
        <tr>
          <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
          <th class="Type1" style="width:1.8cm;">ถึง</th>
          <th class="Type1" style="width:2cm;">รวม</th>
          <th class="Type1" style="width:2cm;">ค่าพาหนะ</th>
          <th class="Type1" style="width:2cm;">ค่าโทรศัพท์</th>
          <th class="Type1" style="width:2cm;">ค่าคอมมิชชัน</th>
          <th class="Type1" style="width:2cm;">อื่นๆ</th>
        </tr>
        <tr>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.since3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:1.8cm;" :value="data.until3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.total3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2.5cm;" :value="data.travelling_expenses3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.mobile3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" :value="data.commission3"/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          <td class="Type1">
            <input class="txt" type="text" style="width:2cm;" value=""/>
          </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;"  :value="data.position3"/>
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" :value="data.job_Discription3" />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" :value="data.note3" />
            </td>
          </tr>
        </table>
        <br />
      </div>
    </div>
    <div class="Contianner">
      <div>
        <p style="text-decoration:underline;">ยานพาหนะ/ Vehicle</p>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1">
              ประเภท
              <br />Type
            </th>
            <th class="Type1" style="width:8cm;">มีของตนเอง/ Owner</th>
          </tr>
          <tr>
            <th class="Type1">รถยนต์/ Car</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:8cm;" :value="data.name_car" />
            </td>
          </tr>
          <tr>
            <th class="Type1">จักรยานยนต์/ Motorcycle</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:8cm;" :value="data.name_motorcycle" />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p
          style="text-decoration:underline;"
        >บุคคลที่สามารถติดต่อได้ในกรณีฉุกเฉิน / Person to Contact in Case of Emergency</p>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:3.5cm;">ชื่อ-สกุล/ Name-Surname</td>
            <td>
              <input class="txt" type="text" style="width:7cm;" :value="data.name_surname" />
              ความสัมพันธ์/ Relation
              <input
                class="txt"
                type="text"
                style="width:3cm;"
                :value="data.relation1"
              />
            </td>
          </tr>
            <tr>
            <td style="width:3.5cm;">ที่ทำงาน/Office</td>
            <td>
              <input class="txt" type="text" style="width:7cm;" :value="data.office" />
              ตำเเหน่ง/ Position
              <input
                class="txt"
                type="text"
                style="width:3cm;"
                :value="data.position"
              />
            </td>
          </tr>
          <tr>
            <td>โทรศัพท์/ Telephone</td>
            <td>
              <input class="txt" type="text" style="width:5cm;" :value="data.telephone" />
              โทรศัพท์มือถือ/ Mobile
              <input
                class="txt"
                type="text"
                style="width:5cm;"
                :value="data.mobile"
              />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p style="text-decoration:underline;">งานอดิเรก - กีฬา/ Hobbies - Sports</p>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:3.5cm;">งานอดิเรก/ Hobbies</td>
            <td>
              <input class="txt" type="text" style="width:15cm;" :value="xhobbies" />
            </td>
          </tr>
          <tr>
            <td style="width:3.5cm;">กีฬา/ Sports</td>
            <td>
              <input class="txt" type="text" style="width:15cm;" :value="xsports" />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p style="text-decoration:underline;">ข้อมูลเพิ่มเติม / Miscellaneous</p>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:6.5cm;">
              คุณเคยต้องโทษทางอาญาหรือไม่
              <br />Do you have any criminal or civil record?
            </td>
            <td style="width:2cm;">
              <input class="txt" type="text" style="width:2cm;"  :value="data.no1+' '+data.yes1" />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" :value="data.explain1" />
            </td>
          </tr>
          <tr>
            <td>
              คุณเคยสมัครงานหรือทำงานกับบริษัทมาก่อนหรือไม่
              <br />Have you ever applied to this company?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;"  :value="data.no2+' '+data.yes2" />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" :value="data.explain2"/>
            </td>
          </tr>
          <tr>
            <td>
              คุณเคยป่วยหนักหรือเป็นโรคติดต่อร้ายแรงหรือไม่
              <br />Have you ever been seriously ill or contracted
              <br />with contagious disease?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;"  :value="data.no3+' '+data.yes3" />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" :value="data.explain3" />
            </td>
          </tr>
          <tr>
            <td>
              บริษัทสามารถพูดคุยกับนายจ้างเดิมของคุณได้หรือไม่
              <br />Can we contact your past employer?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;"  :value="data.no4+' '+data.yes4" />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" :value="data.because" />
            </td>
          </tr>
        </table>
      </div>
      <div>
          <tr>
            <td style="width:12.4cm;">
              บุคคลในบริษัทที่คุณรู้จักเเละคุ้นเคย<br/>Relatives or friends working in this company
            </td>
          </tr>
         <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:2.5cm;">
                ชื่อ-สกุล
              <br />Name-Surname
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" :value="data.name" />
            </td>
            <td style="width:2.0cm; text-align:center;">
             แผนก <br />Department
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" :value="data.department" />
            </td>
            <td style="width:2.0cm; text-align:center;">
             ความสัมพันธ์<br />Relation
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" :value="data.relation2" />
            </td>
          </tr>
        </table>
      </div>
        <div>
         <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:12.4cm;">
              เงินเดือนที่ต้องการ
              <br />Salary Expectation
              <input class="txt" type="text" style="width:6cm;" :value="data.salary_expectation" />
            </td>
            <td style="width:5.1cm;">&nbsp;</td>
          </tr>
        </table>
      </div>
        <div>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:12.4cm;">
             รายได้อื่นที่คาดหวัง
              <br />Other IncomeExpected
              <input class="txt" type="text" style="width:6cm;" :value="data.other_income_expected" />
            </td>
            <td style="width:5.1cm;">&nbsp;</td>
          </tr>
        </table>
      </div>
      <br />
        <br />
      <div>
        <br />ข้าพเจ้าขอรับรองว่ารายละเอียดทั้งหมดเป็นความจริงทุกประการ หากปรากฏว่าหลักฐาน และ/หรือ ข้อความที่ให้ไว้ไม่เป็นความจริง
        <br />ข้าพเจ้าขอให้บริษัทฯ เลิกจ้างข้าพเจ้า โดยข้าพเจ้าไม่ขอรับค่าชดเชยใดๆ ทั้งสิ้น
        <br />The Statements are made by me in this application are true, complete and correct. A false statement or dishonest
        answer
        <br />to any question may be and for my immediate discharged from employment with the company.
      </div>
      <div>
       <br />
        <br />
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="text-align:right;">
              ลงชื่อผู้สมัคร/ Applicant's Signature
              <input
                class="txt"
                type="text"
                style="width:6cm;"
                :value="data.applicant_s_signature"
              />
            </td>
          </tr>
        </table>
      </div>
      <div></div>
    </div>
  </div>
</template>
<script>
var moment = require('moment');
export default {
  props: ["data"],
  computed: {
    xsoftware:function(){
      if (Array.isArray(this.data.software))
        return this.data.software.map(a => a.text);
      else this.data.software
    },
    xhardware:function(){
      if (Array.isArray(this.data.hardware))
        return this.data.hardware.map(a => a.text);
      else this.data.hardware
    },
    xcertificate:function(){
      if (Array.isArray(this.data.certificate))
        return this.data.certificate.map(a => a.text);
      else this.data.certificate
    },
    xothers:function(){
      if (Array.isArray(this.data.others))
        return this.data.others.map(a => a.text);
      else this.data.others
    },
    xhobbies:function(){
      if (Array.isArray(this.data.hobbies))
        return this.data.hobbies.map(a => a.text);
      else this.data.hobbies
    },
    xsports:function(){
      if (Array.isArray(this.data.sports))
        return this.data.sports.map(a => a.text);
      else this.data.sports
    },
    xcitizen:function(){
      if (Array.isArray(this.data.citizen))
        return this.data.citizen.map(a => a.text);
      else this.data.citizen
    },
     xdate:function(){
      if (this.data.date)
        return moment(this.data.date).format('Do MMMM YYYY');
      else return this.data.date
    },
     xdate4:function(){
      if (this.data.date3)
        return moment(this.data.date4).format('Do MMMM YYYY');
      else return this.data.date4
    },
    xdate3:function(){
      if (this.data.date3)
        return moment(this.data.date3).format('Do MMMM YYYY');
      else return this.data.date3
    }
  }
};
</script>
<style scoped>
html {
  width: 100%;
  height: 100%;
  padding: 1cm;
  margin: 1cm;
}
body {
  background-color: #ffffff;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 9pt;
  width: 100%;
  height: 100%;
  padding: 0cm;
  margin: 0cm;
}
p {
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
  padding: 0cm;
}
div {
  margin: 0cm;
  padding: 0.1cm;
  width: 98%;
}
div.Contianner {
  background-color: #ffffff;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
  margin: 0.5cm;
  padding: 0.5cm;
  width: 19.5cm;
  height: 26.6cm;
}
input.txt {
  border-bottom: dotted 1px #000000;
  border-top-style: none;
  border-left-style: none;
  border-right-style: none;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 9pt;
  padding-left: 5px;
  text-align: left;
}
h1 {
  font-size: 12pt;
  line-height: 0.3cm;
}
table {
  width: 100%;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}
td {
  padding-top: 0.2cm;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}
th {
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}

table.Type1 {
  border-right: solid 1px #000000;
  border-bottom: solid 1px #000000;
  border-top-style: none;
  border-left-style: none;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}
td.Type1 {
  border-left: solid 1px #000000;
  border-top: solid 1px #000000;
  border-bottom-style: none;
  border-right-style: none;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}
th.Type1 {
  border-left: solid 1px #000000;
  border-top: solid 1px #000000;
  border-bottom-style: none;
  border-right-style: none;
  font-family: Tahoma, Garamond, "Times New Roman";
  color: #000000;
  font-size: 8pt;
}
</style>
