<script>
import SubList from './SubList.vue';

export default {
  data() {
    return {
      show: false
    }
  },

  props: ['title', 'actorDisplayName', 'objectType', 'published'],

  methods: {
    clickedHandler(message, e){
      if (e) {
        e.preventDefault()
      }
      console.log(message);
    }
  },

  components: {
    SubList
  }
};
</script>

<template>
  <div @click="(e) => clickedHandler('Clicked', e)"  class="card text-center m-3">
    <div class="card-body">Title of Event: {{title}}</div>
    <div class="card-body">Display Name: {{actorDisplayName}}</div>
  </div>
  <SubList :title="`${title}`" :actorDisplayName="`${actorDisplayName}`" :objectType="`${objectType}`" :published="`${published}`"/>
</template>
