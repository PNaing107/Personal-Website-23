<template>
  <TheHeader></TheHeader>
  <main>
  </main>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';

export default {
  components: {
    TheHeader
  }
}

</script>

<style>
#app {
  background-color: var(--background-color-primary);
  color: var(--text-primary-color);
}

a {
  color: var(--text-primary-color);
}
</style>
