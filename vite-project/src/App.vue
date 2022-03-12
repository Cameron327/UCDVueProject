<script>
import Item from './components/Item.vue'
import axios from 'axios';

export default {
  data() {
    return {
      returned: null
    };
  },
  async created() {
    // Simple GET request using axios
    const response = await axios.get("https://aggiefeed.ucdavis.edu/api/v1/activity/public?l=25");

    console.log("Response Data: ", response.data)
    this.returned = response.data;
  },
  
  components: {
    Item
  }
};
</script>

<template>
  <Item v-for="UCDevent in returned" :title="`${UCDevent.title}`" :actorDisplayName="`${UCDevent.actor.displayName}`"/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>


// Endpoint: https://aggiefeed.ucdavis.edu/api/v1/activity/public?l=25