<template>
  <header>
    <div>
      <h1>Phone Naing</h1>
      <h2>Software Developer</h2>
    </div>
    <div class="control">
      <img id="logo" src="../../assets/light-green-icon.png" alt="phone naing logo">
      <ToggleSwitch id="color-theme" :switch-toggle-state="toggleState" @toggle="toggleTheme">
      <template #on>
        <span>🌙</span>
      </template>
      <template #off>
        <span>☀️</span>
      </template>
    </ToggleSwitch>
    </div>
    <div>
      <p>Connect with me:</p>
      <div class="social">
        <a href="https://github.com/PNaing107" target="_blank">
          <i class="fa-brands fa-square-github fa-2x"></i>
        </a>
        <a href="https://www.linkedin.com/in/phone-naing-92423a133" target="_blank">
          <i class="fa-brands fa-linkedin fa-2x"></i>
        </a>
      </div>
    </div>
  </header>
</template>

<script>
import ToggleSwitch from '../UI/ToggleSwitch.vue';

export default {
  components: { ToggleSwitch },
  data() {
    return {
      userTheme: "dark-theme",
    };
  },
  mounted() {
    const initUserTheme = this.getMediaPreference();
    this.setTheme(initUserTheme);
  },
  methods: {
    setTheme(theme) {
      localStorage.setItem("user-theme", theme);
      this.userTheme = theme;
      document.documentElement.className = theme;
    },
    toggleTheme() {
      const activeTheme = localStorage.getItem("user-theme");
      if (activeTheme === "light-theme") {
        this.setTheme("dark-theme");
      } else {
        this.setTheme("light-theme");
      }
    },
    getMediaPreference() {
      const hasDarkPreference = window.matchMedia(
        "(prefers-color-scheme: dark)"
      ).matches;
      if (hasDarkPreference) {
        return "dark-theme";
      } else {
        return "light-theme";
      }
    },
  },
  computed: {
    toggleState() {
      return this.userTheme === 'light-theme';

    }
  }
}
</script>

<style scoped>
#color-theme {
  align-self: center;
}

a:hover {
  color: var(--text-secondary-color);
}

header {
  display: flex;
  justify-content: space-between;
  width: 100%;
  border-bottom: 4px solid var(--text-secondary-color);
}

h2 {
  font-weight: 400;
}

.social {
  display: flex;
  justify-content: space-around;
}

#logo {
  width: 4rem;
  height: auto;
  margin-bottom: 0.5rem;
}

.control {
  display: flex;
  flex-direction: column;
  align-items: center;
}

@media (max-width: 768px) {
  header {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .control {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 30%;
  }

  .social {
    margin-bottom: 0.5rem;
  }
}
</style>