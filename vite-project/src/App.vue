<script>
import Item from "./components/Item.vue";
import axios from "axios";
import { ref, onMounted } from "vue";

export default {
  components: {
    Item
  },

	setup() {
    let returned = ref([]);

    let created = async () => {
      const response = await axios.get(
        "https://aggiefeed.ucdavis.edu/api/v1/activity/public?l=25"        
      );
      console.log("Response Data: ", response.data);      
      returned.value = [...response.data]
      console.log("returned.value: ", returned.value);
    }

    onMounted(async () => await created());

    return {
      returned
    }

  }
};
</script>

<template>
  <ul>
    <!-- Each list item needs a key -->
    <li v-for="UCDevent in returned" :key="UCDevent.title" class="width">
      <Item
        :title="`${UCDevent.title}`"
        :actorDisplayName="`${UCDevent.actor.displayName}`"
        :objectType="`${UCDevent.object.objectType}`"
        :published="`${UCDevent.published}`"
      />
    </li>
  </ul>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 31%;
  content: none;
}
.width {
  width: 50%
}

</style>

// Endpoint: https://aggiefeed.ucdavis.edu/api/v1/activity/public?l=25
