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
        <slot></slot>
      </v-container>
    </v-content>
    <v-footer
      color="indigo"
      app
    >
      <span class="white--text">&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    name: 'inspire',
    props: {
      source: String,
    },
    data: () => ({
    }),
  }
</script>