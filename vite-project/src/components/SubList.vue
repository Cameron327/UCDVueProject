<script lang="ts">
import { ref, toRefs, onMounted } from "vue";

export default {
  props: {
    "title": String, 
    "actorDisplayName": String, 
    "objectType": String, 
    "published": String
  },

  setup(props, context) {
    // Destructure the props here and not in the parameters so that it keeps its reactability
    let { title, actorDisplayName, objectType, published } = toRefs(props);

    onMounted(() => {
      console.log("Mounted");
    });

    return {
      title,
      actorDisplayName,
      objectType,
      published
    };
  }
};
</script>

<template>
  <div class="subListItem">
    <div class="subText">Title of Event: {{title}}</div>
    <div class="subText">Display Name: {{actorDisplayName}}</div>
    <div class="subText">Object Type: {{objectType}}</div>
    <div class="subText">Published: {{published}}</div>
  </div>
</template>

<style scoped>
.subListItem {
  padding-bottom: 15px;
}
</style>