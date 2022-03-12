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
  <div class="card text-center m-3">
    <div class="card-body">Title of Event: {{title}}</div>
    <div class="card-body">Display Name: {{actorDisplayName}}</div>
    <div class="card-body">Object Type: {{objectType}}</div>
    <div class="card-body">Published: {{published}}</div>
  </div>
</template>