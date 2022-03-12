<script>
export default {
  data() {
    return {
      text: "This is a test"
    }
  },
  props: ['UCDevent', 'title', 'actorDisplayName']
}
</script>

<template>
  <div class="card text-center m-3">
    <div class="card-body">Title of Event: {{title}}</div>
    <div class="card-body">Display Name: {{actorDisplayName}}</div>
  </div>
</template>
