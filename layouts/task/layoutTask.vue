<template>
  <div>
    <div class="tabs">
      <ul>
        <NuxtLink to="/task/paraMim">
          <b-icon pack="fas" icon="people-arrows"></b-icon
          ><span>Para mim</span></NuxtLink
        >
        <NuxtLink to="/task/porMim">
          <b-icon pack="fas" icon="user"></b-icon><span>Por mim</span></NuxtLink
        >
        <NuxtLink to="/task/task">
          <b-icon pack="fas" icon="plus"></b-icon
          ><span>Nova task</span></NuxtLink
        >
      </ul>
    </div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },

  methods: {},
}
</script>

<style>
</style>