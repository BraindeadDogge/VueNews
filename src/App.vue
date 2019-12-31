<template>
  <div id="App">
    <inspire id="insp">
      <card v-for="item in text" :key="item.id" :imglink="item.urlToImage" :newstitle="item.title" :date="item.publishedAt" :description="item.description"></card>
    </inspire>
  </div>
</template>

<script>
import inspire from './components/inspire.vue';
import card from './components/card.vue';
import axios from 'axios';

export default {
  name: 'App',

  components: {
    inspire,
    card,
  },

  data(){
    return {
      text: [],
    }
  },
  methods: {

  },
  mounted() {
    axios.get('https://newsapi.org/v2/top-headlines?country=ru&apiKey=d7f41a32c26b4bbfb596d58b1a54c766')
    .then((response) => {
      this.text = response.data.articles
      console.log('rrr', this.text)
    })
    
  }
};
</script>

<style>
card {
  margin: 100px;
}
#insp {
  display: flex;
  justify-content: space-between
}
</style>