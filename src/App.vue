<template>
  <TheHeader></TheHeader>
  <main>
    <NavigationBar @navigation="updateContent"></NavigationBar>
    <About v-if="content === 'About Me'"></About>
  </main>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import NavigationBar from './components/UI/NavigationBar.vue';
import About from './components/pages/About.vue';

export default {
  components: {
    TheHeader,
    NavigationBar,
    About,
  },
  data() {
    return {
      content: '',
    }
  },
  methods: {
    updateContent(content) {
      this.content = content;
    },
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
