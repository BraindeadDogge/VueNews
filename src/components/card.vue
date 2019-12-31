<template> 
<div id="card">
  <v-card
    class="mx-auto"
    max-width="344"
  >
    <v-img
      :src="imglink"
      height="200px"
    ></v-img>

    <v-card-title>
        {{newstitle}}
    </v-card-title>

    <v-card-subtitle>
        {{date}}
    </v-card-subtitle>

    <v-card-actions>
      <v-btn text>Share</v-btn>

      <v-btn
        color="purple"
        text
      >
        Explore
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        icon
        @click="show = !show"
      >
        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
      </v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          {{description}}
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
 </div>
</template>

<script>
  export default {
    name: 'card',
    data: () => ({
      show: false,
    }),
    props: ["imglink", "newstitle", "date", "description"]
  }
</script>

<style>
#card {
    margin-right: 3vw;
    margin-left: 3vw;
    margin-bottom: 5vh;
}
</style>