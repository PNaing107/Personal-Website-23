<template>
    <div class="style-64">
      <div>
        <button v-for="tab in tablist" :key="tab" @click="$emit('navigation',tab)">{{ tab }}</button>
      </div>
    </div>
</template>

<script>
export default {
    data() {
    return {
      tablist: ['About Me', 'Projects', 'Blog']
    };
  }
}
</script>

<style scoped>

.style-64 {
  align-items: center;
  background-image: linear-gradient(144deg, #AF40FF, #5B42F3 50%, #00DDEB);
  border: 0;
  border-radius: var(--border-radius-default);
  box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
  color: #FFFFFF;
  margin: 2rem auto;
  justify-content: center;
  line-height: 1em;
  width: clamp(120px,60vw,1024px);
  padding: 3px;
  text-decoration: none;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.style-64 div {
  background-color: var(--background-color-secondary);
  padding: 1rem;
  border-radius: calc(var(--border-radius-default)*0.8);
  display: flex;
  justify-content: space-between;
}

@media (max-width: 660px) {
  .style-64 div {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .style-64 div > button:nth-child(2) {
    margin: 0.5rem 0;
  }

  button {
    width: 90%;
    justify-content: space-between;
  }
}
</style>