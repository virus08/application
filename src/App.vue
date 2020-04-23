<template>
  <v-app id="inspire">
    

    <v-app-bar
      app
      color="indigo lighten-1"
      dark
    >
      <v-toolbar-title>บริษัทวีเอสที อีซีเอส (ประเทศไทย) จำกัด</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container class="fill-height" fluid>
        <v-layout child-flex>
          <router-view />
        </v-layout>
      </v-container>
    </v-content>
    
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    data: () => ({
      drawer: false,
    }),
  }
</script>