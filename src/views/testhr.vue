<template>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1"
  >
    <template v-slot:item.calories="{ item }">
      <v-chip :color="getColor(item.calories)" dark>{{ item.calories }}</v-chip>
    </template>
<template v-slot:item.Name="{ item }">{{item.nt+' '+ item.namet+' ' + item.surnamet}}</template>
    <template v-slot:item.actions="{ item }">
      <v-icon small class="mr-2" @click="editItem(item)">mdi-pencil</v-icon>
      <v-icon small @click="deleteItem(item)">mdi-delete</v-icon>
      
    </template>
    <template v-slot:no-data>
      <v-btn color="primary" @click="initialize">Reset</v-btn>
    </template>
  </v-data-table>
</template>
<script>
  export default {
  data: () => ({
    dialog: false,
    headers: [
      {
        text: "Empolyee ID",
        value: "id"
      },
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
      getColor (calories) {
        if (calories > 400) return 'red'
        else if (calories > 200) return 'orange'
        else return 'green'
      },

         async initialize() {
      let dataurl = process.env.VUE_APP_DATA;
      let res = await axios({
        method: "get",
        url: dataurl
      });
      this.desserts = res.data;
      },
      editItem(item) {
      this.editedIndex = this.desserts.indexOf(item);
      this.editedItem = Object.assign({}, item);
      this.dialog = true;
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