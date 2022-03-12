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
  <div @click="(e) => clickedHandler(e)">
    <div class="card-body">Title of Event: {{ title }}</div>
    <div class="card-body">Display Name: {{ actorDisplayName }}</div>
  </div>
  <SubList
    v-if="show"
    :title="`${title}`"
    :actorDisplayName="`${actorDisplayName}`"
    :objectType="`${objectType}`"
    :published="`${published}`"
  />
</template>


