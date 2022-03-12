<script>
import SubList from "./SubList.vue";

export default {
  data() {
    return {
      show: false,
    };
  },

  props: ["title", "actorDisplayName", "objectType", "published"],

  methods: {
    clickedHandler(e) {
      if (e) {
        e.preventDefault();
      }
      this.show = !this.show;
      console.log(this.show);
    },
  },

  components: {
    SubList,
  },
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
  font-weight: 700;
  font-size: 20px;
}


</style>
