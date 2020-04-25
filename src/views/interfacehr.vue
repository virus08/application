<template>
  <div>
    <v-dialog v-model="dialog" max-width="1080px">
      <v-card>
        <v-toolbar flat color="primary" dark>
          <v-toolbar-title>User Profile</v-toolbar-title>
        </v-toolbar>
        <v-tabs vertical>
          <v-tab>
            <v-icon left>mdi-account-edit</v-icon>Personal Data
          </v-tab>
          <v-tab>
            <v-icon left>mdi-school</v-icon>Education Data
          </v-tab>
          <v-tab>
            <v-icon left>mdi-treasure-chest</v-icon>Employment
          </v-tab>
          <v-tab>
            <v-icon left>mdi-access-point</v-icon>popsu
          </v-tab>

          <v-tab-item>
            <v-card flat>
              <v-card-text>
                <editpersonal :datain="sitem" />
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab-item>
            <v-card flat>
              <v-card-text>
                <editeducation :datain="sitem" />
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab-item>
            <v-card flat>
              <v-card-text>
                <editemployment :datain="sitem" />
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab-item>
            <v-card flat>
              <v-card-text>
                <editpopsu :datain="sitem" />
              </v-card-text>
            </v-card>
          </v-tab-item>
        </v-tabs>
      </v-card>
    </v-dialog>
    <v-data-table :headers="headers" :items="desserts" sort-by="calories" class="elevation-1">
      <template v-slot:top>
        <v-toolbar flat color="white">
          <v-toolbar-title>My CRUD</v-toolbar-title>
          <v-divider class="mx-4" inset vertical></v-divider>
          <v-spacer></v-spacer>
        </v-toolbar>
      </template>
      <template v-slot:item.Name="{ item }">{{item.nt+' '+ item.namet+' ' + item.surnamet}}</template>
      <template v-slot:item.actions="{ item }">
        <v-icon small class="mr-2" @click="editItem(item)">mdi-pencil</v-icon>
        <v-icon small class="mr-2" @click="deleteItem(item)">mdi-delete</v-icon>
        <v-icon small class="mr-2" @click="printpdf(item)">mdi-file-pdf</v-icon>
      </template>
      <template v-slot:no-data>
        <v-btn color="primary" @click="initialize">Reset</v-btn>
      </template>
    </v-data-table>
    <v-dialog v-model="printa" max-width="800px">
      <div ref="document">
        <fromview :data="editedItem" />
      </div>
      <v-row>
        <v-spacer />
        <v-btn color="primary" @click="exportToPDF">Print</v-btn>
      </v-row>
    </v-dialog>
  </div>
</template>
<script>
import fromview from "@/views/appform.vue";
import html2pdf from "html2pdf.js";
import editpersonal from "@/components/editpersonal.vue";
import editeducation from "@/components/editeducation.vue";
import editemployment from "@/components/editemployment.vue";
import editpopsu from "@/components/editpopsu.vue";
export default {
  components: {
    editpersonal,
    editeducation,
    editemployment,
    editpopsu,
    fromview
  },
  data: () => ({
    sitem: null,
    dialog: false,
    printa: false,
    thisid: null,
    headers: [
      {
        text: "Empolyee ID",
        value: "id"
      },
      { text: "calories", value: "calories" },
      { text: "Name", align: "start", value: "Name" },

      { text: "Position", value: "p_level" },
      { text: "Actions", value: "actions", sortable: false }
    ],
    desserts: [],
    editedIndex: -1,
    editedItem: {
      name: "",
      calories: 0,
      fat: 0,
      carbs: 0,
      protein: 0
    },
    defaultItem: {
      name: "",
      calories: 0,
      fat: 0,
      carbs: 0,
      protein: 0
    }
  }),

  computed: {
    formTitle() {
      return this.editedIndex === -1 ? "New Item" : "Edit Item";
    }
  },

  watch: {
    dialog(val) {
      val || this.close();
    }
  },

  created() {
    this.initialize();
  },

  methods: {
    async initialize() {
      let dataurl = process.env.VUE_APP_DATA;
      let res = await axios({
        method: "get",
        url: dataurl
      });
      this.desserts = res.data;
    },
    async printpdf(item) {
      // this.editedIndex = this.desserts.indexOf(item);
      let dataurl = process.env.VUE_APP_DATA + "/" + item.id;
      // console.log(dataurl);
      let res = await axios({
        method: "get",
        url: dataurl
      });
      this.editedItem = res.data;
      this.printa = true;
    },
    exportToPDF() {
      html2pdf(this.$refs.document, {
        margin: 0,
        filename: "myfile.pdf",
        image: { type: "jpeg", quality: 0.98 },
        html2canvas: { dpi: 200, letterRendering: true },
        jsPDF: { unit: "mm", format: "a4", orientation: "portrait" }
      });
    },
    editItem(item) {
      //  console.log (item)
      this.sitem = item;
      this.dialog = true;
      //this.getitem();
    },

    async deleteItem(item) {
      const index = this.desserts.indexOf(item);

      let xurl = process.env.VUE_APP_DATA + "/" + item.id;
      confirm("Are you sure you want to delete this item?") &&
        (await axios({ method: "delete", url: xurl }));
      this.initialize();
    },

    close() {
      this.dialog = false;
      setTimeout(() => {
        this.editedItem = Object.assign({}, this.defaultItem);
        this.editedIndex = -1;
      }, 300);
    },

    save() {
      if (this.editedIndex > -1) {
        Object.assign(this.desserts[this.editedIndex], this.editedItem);
      } else {
        this.desserts.push(this.editedItem);
      }
      this.close();
    }
  }
};
</script>