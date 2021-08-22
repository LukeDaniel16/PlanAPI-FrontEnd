<template>
  <card-task></card-task>
</template>

<script>
import cardTask from '~/components/cardTask.vue'
export default {
  layout: 'task/layoutTask',
  components: { cardTask },
  data() {
    return {}
  },
}
</script>

<style>
</style>