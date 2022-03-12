<script>

export default {
  data() {
    return {
      show: false
    }
  },
  props: ['title', 'actorDisplayName', 'objectType', 'published'],
}
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