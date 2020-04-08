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
                  <input class="txt" type="text" style="width:10cm" value="27/3/2563" />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">ตำแหน่ง/ Position</v-col>
                <v-col cols="4">
                  <input
                    class="txt"
                    type="text"
                    style="width:10cm"
                    value="Business Development (Sale IT Product)"
                  />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">วันที่เริ่มงาน/ Starting Date</v-col>
                <v-col cols="4">
                  <input class="txt" type="text" style="width:10cm" value="01/04/2563" />
                </v-col>
              </v-row>
              <v-row>
                <v-col cols="3">ทราบข่าวการสมัครจาก</v-col>
                <v-col cols="4">
                  <input class="txt" type="text" style="width:10cm" value="เว็บไซต์" />
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
            <input align="left" class="txt" type="text" style="width:3cm" value="Jo" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">Name - Surname</v-col>
          <v-col cols="10">
            <input
              align="left"
              class="txt"
              type="text"
              style="width:14.5cm"
              :value="data.ne+' '+data.namee+' '+data.surnamee"
            />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">วันเกิด/ Birth Date</v-col>
          <v-col cols="7">
            <input class="txt" type="text" style="width:9.5cm" value="1 มกราคม 2504" />
          </v-col>
          <v-col cols="1">อายุ</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:2.4cm;padding-left:40px;" value="59" /> ปี
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3">สถานที่เกิด/ Place of birth</v-col>
          <v-col cols="7">
            <input class="txt" type="text" style="width:10cm" value />
          </v-col>
          <v-col cols="1">เพศ</v-col>
          <v-col cols="1">
            <input class="txt" type="text" style="width:1.5cm" value="ชาย" />
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
              <input class="txt" type="text" style="width:1cm" value="ไทย" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" value="ไทย" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" value="180" /> cm.
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1cm" value="80" /> kg.
            </td>
          </tr>
        </table>
        <br />
        <v-row>
          <v-col cols="3">
            ที่อยู่ปัจจุบัน
            <br />Present Address
          </v-col>
          <v-col cols="9">
            <input class="txt" type="text" style="width:11.5cm" value="VST ECS" />
            <br />
            <input class="txt" type="text" style="width:11.5cm" value />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="2">Telephone</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:2cm" value="0839239741" />
          </v-col>
          <v-col cols="1">Mobile</v-col>
          <v-col cols="3">
            <input class="txt" type="text" style="width:3.5cm" value="0839239741" />
          </v-col>
          <v-col cols="1">E-mail</v-col>
          <v-col cols="3">
            <input class="txt" type="text" style="width:4cm" value="Panuruk@vstecs.co.th" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="3">
            ที่อยู่ตามทะเบียนบ้าน
            <br />Permanent Address
          </v-col>
          <v-col cols="5">
            <input class="txt" type="text" style="width:6cm" value />
            <br />
            <input class="txt" type="text" style="width:6cm" value />
          </v-col>
          <v-col cols="1" style="padding-right:10px;">
            <br />Telephone
          </v-col>
          <v-col cols="2">
            <br />
            <input class="txt" type="text" style="width:4cm;padding-left:10px;" value />
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
              <v-col cols="4">สถานภาพการสมรส Marital Status</v-col>
              <v-col cols="1">
                <input class="txt" type="text" style="width:1.7cm" value="โสด" />
              </v-col>
            </v-row>
          </v-row>
        </v-row>
      </div>

      <div>
        <br />
        <p style="text-decoration:underline;">ข้อมูลของคู่สมรสและบุตร / Family Information</p>
        <v-row>
          <v-col cols="3">
            ชื่อ-สกุล คู่สมรส
            <br />Name of spouse
          </v-col>
          <v-col cols="6">
            <input class="txt" type="text" style="width:7cm" value />
          </v-col>
          <v-col cols="1">บุตร</v-col>
          <v-col cols="2">
            <input class="txt" type="text" style="width:1cm" value /> คน
          </v-col>
        </v-row>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:2.5cm;">
              สถานที่ทำงาน
              <br />Office Address
            </td>
            <td>
              <input class="txt" type="text" style="width:14cm" value />
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
              <input class="txt" type="text" style="width:3.5cm" value />
            </td>
            <td style="width:2.0cm; text-align:center;">
              อาชีพ
              <br />Occupation
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" value />
            </td>
            <td style="width:2.0cm; text-align:center;">
              ตำแหน่ง
              <br />Position
            </td>
            <td>
              <input class="txt" type="text" style="width:3.25cm" value />
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
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1" style="width:0.8cm;">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1" style="width:2.5cm;">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">มารดา</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 1</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 2</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 3</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 4</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
          </tr>
          <tr>
            <td class="Type1">พี่น้องลำดับที่ 5</td>
            <td class="Type1">
              <input class="txt" type="text" style="width:4cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:0.5cm" value />ปี
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:6.9cm" value=" โทร:" />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
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
              ปวส.
              <br />High Vocational Diploma
            </th>
            <td class="Type1">
              ชื่อสถานศึกษาและที่ตั้ง
              <input class="txt" type="text" style="width:10cm;" value />
              <p>
                วุฒิการศึกษา
                <input class="txt" type="text" style="width:7cm;" value />
                คะแนนเฉลี่ย
                <input class="txt" type="text" style="width:2.5cm;" value />
              </p>
              <p>
                คณะ/ สาขา
                <input class="txt" type="text" style="width:8cm;" value />
                ปีที่ศึกษา
                <input class="txt" type="text" style="width:2cm;" value="-" />
              </p>
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              ปริญญาตรี
              <br />Bachelor's Degree
            </th>
            <td class="Type1">
              ชื่อสถานศึกษาและที่ตั้ง
              <input class="txt" type="text" style="width:10cm;" value />
              <p>
                วุฒิการศึกษา
                <input class="txt" type="text" style="width:7cm;" value />
                คะแนนเฉลี่ย
                <input class="txt" type="text" style="width:2.5cm;" value />
              </p>
              <p>
                คณะ/ สาขา
                <input class="txt" type="text" style="width:8cm;" value />
                ปีที่ศึกษา
                <input class="txt" type="text" style="width:2cm;" value="-" />
              </p>
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              ปริญญาโท
              <br />Master's Degree
            </th>
            <td class="Type1">
              ชื่อสถานศึกษาและที่ตั้ง
              <input class="txt" type="text" style="width:10cm;" value />
              <p>
                วุฒิการศึกษา
                <input class="txt" type="text" style="width:7cm;" value />
                คะแนนเฉลี่ย
                <input class="txt" type="text" style="width:2.5cm;" value />
              </p>
              <p>
                คณะ/ สาขา
                <input class="txt" type="text" style="width:8cm;" value />
                ปีที่ศึกษา
                <input class="txt" type="text" style="width:2cm;" value="-" />
              </p>
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3.5cm;">
              ม.ปลาย/ ปวช./ อื่น ๆ
              <br />Secondary/ Vocational Certificate/ Others
            </th>
            <td class="Type1">
              ชื่อสถานศึกษาและที่ตั้ง
              <input class="txt" type="text" style="width:10cm;" value />
              <p>
                วุฒิการศึกษา
                <input class="txt" type="text" style="width:7cm;" value />
                คะแนนเฉลี่ย
                <input class="txt" type="text" style="width:2.5cm;" value />
              </p>
              <p>
                คณะ/ สาขา
                <input class="txt" type="text" style="width:8cm;" value />
                ปีที่ศึกษา
                <input class="txt" type="text" style="width:2cm;" value="-" />
              </p>
            </td>
          </tr>
        </table>
        <br />
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td>
              ปัจจุบันศึกษาต่อที่/ Present study at
              <input class="txt" type="text" style="width:9.3cm;" value />
              ปีที่จบ
              <input class="txt" type="text" style="width:2cm;" value />
              <br />วุฒิการศึกษา
              <input class="txt" type="text" style="width:5.4cm;" value />
              คณะ/ สาขา
              <input class="txt" type="text" style="width:8cm;" value />
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
              <input class="txt" type="text" style="width:14cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Hardware</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Certificate</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1" style="width:3cm;">Others</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:14cm;" value />
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
            <th class="Type1" rowspan="2">&nbsp;</th>
            <th class="Type1" rowspan="2" style="width:4.5cm;">
              ชื่อสถาบัน
              <br />Institute
            </th>
            <th class="Type1" rowspan="2" style="width:5.5cm;">
              หัวข้อการฝึกอบรม
              <br />Course
            </th>
            <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
          </tr>
          <tr>
            <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
            <th class="Type1" style="width:1.8cm;">ถึง</th>
            <th class="Type1" style="width:2.0cm;">รวม</th>
          </tr>
          <tr>
            <th class="Type1">1.</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:4.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.0cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">2.</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:4.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.0cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">3.</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:4.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:5.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.0cm;" value />
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
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value=" โทร." />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
            <th class="Type1" rowspan="2">
              เงินเดือนล่าสุด
              <br />Salary
            </th>
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
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
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
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value=" โทร." />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
            <th class="Type1" rowspan="2">
              เงินเดือนล่าสุด
              <br />Salary
            </th>
            <th class="Type1" colspan="4">เงินได้พิเศษ/ Special Income</th>
          </tr>
          <tr>
            <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
            <th class="Type1" style="width:1.8cm;">ถึง</th>
            <th class="Type1" style="width:2cm;">รวม</th>
            <th class="Type1" style="width:2cm;">ค่าพาหนะ</th>
            <th class="Type1" style="width:2cm;">ค่าโทรศัพท์</th>
            <th class="Type1" style="width:2cm;">ค่าคอมมิทชัน</th>
            <th class="Type1" style="width:2cm;">อื่นๆ</th>
          </tr>
          <tr>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
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
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ประเภทธุรกิจ
              <br />Type of Business
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">
              ชื่อ-เบอร์โทร ผู้บังคับบัญชา
              <br />Name-Tel of chief
            </th>
            <td class="Type1">
              <input class="txt" type="text" style="width:12.5cm;" value=" โทร." />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" colspan="3">ระยะเวลา/ Period</th>
            <th class="Type1" rowspan="2">
              เงินเดือนล่าสุด
              <br />Salary
            </th>
            <th class="Type1" colspan="4">เงินได้พิเศษ/ Special Income</th>
          </tr>
          <tr>
            <th class="Type1" style="width:1.8cm;">ตั้งแต่</th>
            <th class="Type1" style="width:1.8cm;">ถึง</th>
            <th class="Type1" style="width:2cm;">รวม</th>
            <th class="Type1" style="width:2cm;">ค่าพาหนะ</th>
            <th class="Type1" style="width:2cm;">ค่าโทรศัพท์</th>
            <th class="Type1" style="width:2cm;">ค่าคอมมิทชัน</th>
            <th class="Type1" style="width:2cm;">อื่นๆ</th>
          </tr>
          <tr>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:1.8cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2.5cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td class="Type1">
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
          </tr>
        </table>
        <table class="Type1" cellpadding="0" cellspacing="0">
          <tr>
            <th class="Type1" style="width:6cm;">ตำแหน่งงานสุดท้าย/ Last Position</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">หน้าที่ความรับผิดชอบ / Type of Work</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
            </td>
          </tr>
          <tr>
            <th class="Type1">สาเหตุที่ลาออก / Reason for Leaving</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:10.5cm;" value />
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
              <input class="txt" type="text" style="width:8cm;" value="มีรถยนต์" />
            </td>
          </tr>
          <tr>
            <th class="Type1">จักรยานยนต์/ Motorcycle</th>
            <td class="Type1">
              <input class="txt" type="text" style="width:8cm;" value="ไม่มีรถมอเตอร์ไซต์" />
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
              <input class="txt" type="text" style="width:7cm;" value="คุณสมพร" />
              ความสัมพันธ์/ Relation
              <input
                class="txt"
                type="text"
                style="width:3cm;"
                value="เพื่อน"
              />
            </td>
          </tr>
          <tr>
            <td>ที่อยู่/ Address</td>
            <td>
              <input class="txt" type="text" style="width:13cm;" value />
            </td>
          </tr>
          <tr>
            <td>
              สถานที่ทำงานปัจจุบัน
              <br />Office Address
            </td>
            <td>
              <input class="txt" type="text" style="width:13cm;" value />
            </td>
          </tr>
          <tr>
            <td>โทรศัพท์/ Telephone</td>
            <td>
              <input class="txt" type="text" style="width:5cm;" value="08712457896" />
              โทรศัพท์มือถือ/ Mobile
              <input
                class="txt"
                type="text"
                style="width:5cm;"
                value="08712457896"
              />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <p style="text-decoration:underline;">กิจกรรมพิเศษ - งานอดิเรก/ Activity - Hobbies</p>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:3.5cm;">กิจกรรมพิเศษ/ Activity</td>
            <td>
              <input class="txt" type="text" style="width:13.5cm;" value />
            </td>
          </tr>
          <tr>
            <td style="width:3.5cm;">งานอดิเรก/ Hobbies</td>
            <td>
              <input class="txt" type="text" style="width:13.5cm;" value />
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
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" value />
            </td>
          </tr>
          <tr>
            <td>
              คุณเคยสมัครงานหรือทำงานกับบริษัทมาก่อนหรือไม่
              <br />Have you ever applied to this company?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" value />
            </td>
          </tr>
          <tr>
            <td>
              คุณเคยป่วยหนักหรือเป็นโรคติดต่อร้ายแรงหรือไม่
              <br />Have you ever been seriously ill or contracted
              <br />with contagious disease?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" value />
            </td>
          </tr>
          <tr>
            <td>
              บริษัทสามารถพูดคุยกับนายจ้างเดิมของคุณได้หรือไม่
              <br />Can we contact your past employer?
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;" value />    
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" value />
            </td>
          </tr>
          <tr>
            <td>
              บุคคลในบริษัทที่คุณรู้จัก
              <br />Relatives or friends working in this company
            </td>
            <td>
              <input class="txt" type="text" style="width:2cm;" value />
            </td>
            <td>
              ระบุ/ Explain :
              <input class="txt" type="text" style="width:6.3cm;" value />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:6.5cm;">
              ข้อความเพิ่มเติมอื่น ๆ ที่ประสงค์จะแจ้งให้ทราบ
              <br />Additional information
            </td>
            <td>
              <input class="txt" type="text" style="width:10cm;" value />
            </td>
          </tr>
        </table>
      </div>
      <div>
        <br />
        <br />
        <table cellpadding="0" cellspacing="0">
          <tr>
            <td style="width:12.4cm;">
              เงินเดือนที่ต้องการ
              <br />Salary Expectation
              <input class="txt" type="text" style="width:6cm;" value="60000" />
            </td>
            <td style="width:5.1cm;">&nbsp;</td>
          </tr>
        </table>
      </div>
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
                value
              />
            </td>
          </tr>
        </table>
      </div>
      <div>
        
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["data"]   
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