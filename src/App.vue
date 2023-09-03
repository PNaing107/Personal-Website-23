<template>
  <TheHeader></TheHeader>
  <main>
    <NavigationBar @navigation="updateContent"></NavigationBar>
    <WelcomeBanner :show-banner="showWelcome"></WelcomeBanner>
    <About v-if="content === 'About Me'"></About>
    <PersonalProjects v-if="content === 'Projects'"></PersonalProjects>
  </main>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import NavigationBar from './components/UI/NavigationBar.vue';
import About from './components/pages/AboutMe.vue';
import PersonalProjects from './components/pages/PersonalProjects.vue';
import WelcomeBanner from './components/layout/WelcomeBanner.vue';

export default {
  components: {
    TheHeader,
    NavigationBar,
    About,
    PersonalProjects,
    WelcomeBanner,
  },
  data() {
    return {
      content: '',
      showWelcome: true,
    }
  },
  methods: {
    updateContent(content) {
      this.content = content;
      this.showWelcome = false;
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
