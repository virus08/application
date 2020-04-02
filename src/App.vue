<template>
  <v-app id="inspire">
    

    <v-app-bar
      app
      color="indigo"
      dark
    >
      <v-toolbar-title>Application</v-toolbar-title>
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