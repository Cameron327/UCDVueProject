<script>
import { ref, toRefs } from "vue";
import SubList from "./SubList.vue";

export default {
  props: ["title", "actorDisplayName", "objectType", "published"],
  components: {SubList},
  setup(props) {
    // like useState
    let show = ref(false);
    let { title, actorDisplayName, objectType, published } = toRefs(props);

    let clickedHandler = (e) => {
      if (e) {
        e.preventDefault();
      }
      show.value = !show.value;
      console.log(show.value);
    }

    // this is where you return everything for the html to use (states, props, methods)
    return {
      show,
      title,
      actorDisplayName,
      objectType,
      published,
      clickedHandler
    }
  }
};
</script>

<template>
  <div @click="(e) => clickedHandler(e)" class="listItem">
    <div class="text">Title of Event: {{ title }}</div>
    <div class="text">Display Name: {{ actorDisplayName }}</div>
  </div>
  <SubList
    v-if="show"
    :title="`${title}`"
    :actorDisplayName="`${actorDisplayName}`"
    :objectType="`${objectType}`"
    :published="`${published}`"
  />
</template>

<style scoped>
.listItem {
  padding-bottom: 15px;
}
.text {
  font-weight: 600;
  font-size: 20px;
}
</style>
