<template>
  <TheHeader></TheHeader>
  <main>
    <WelcomeBanner :show-banner="showWelcome"></WelcomeBanner>
    <NavigationBar @navigation="updateContent"></NavigationBar>
    <About v-if="content === 'About Me'"></About>
    <PersonalProjects v-if="content === 'Projects'"></PersonalProjects>
    <TheBlog v-if="content === 'Blog'"></TheBlog>
  </main>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import NavigationBar from './components/UI/NavigationBar.vue';
import About from './components/pages/AboutMe.vue';
import PersonalProjects from './components/pages/PersonalProjects.vue';
import TheBlog from './components/pages/TheBlog.vue';
import WelcomeBanner from './components/layout/WelcomeBanner.vue';

export default {
  components: {
    TheHeader,
    NavigationBar,
    About,
    PersonalProjects,
    TheBlog,
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
