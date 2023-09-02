<template>
        <div class="card">
            <input @change="$emit('toggle')" id="checkbox" type="checkbox" class="switch-checkbox" />
            <label for="checkbox" class="switch-label">
                <slot name="on"></slot>
                <slot name="off"></slot>
                <div class="switch-toggle" :class="{ 'switch-toggle-checked': switchToggleState }"></div>
            </label>
        </div>
</template>

<script>
export default {
    props: ['switchToggleState']
};
</script>

<style scoped>
p {
  color: var(--text-primary-color);
}

.container-center {
  background-color: var(--background-color-primary);
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}

.switch-checkbox {
  display: none;
}

.switch-label {
  /* for width, use the standard element-size */
  width: var(--element-size); 

  /* for other dimensions, calculate values based on it */
  border-radius: var(--element-size);
  border: calc(var(--element-size) * 0.025) solid var(--accent-color);
  padding: calc(var(--element-size) * 0.1);
  font-size: calc(var(--element-size) * 0.3);
  height: calc(var(--element-size) * 0.35);

  align-items: center;
  background: var(--text-primary-color);
  cursor: pointer;
  display: flex;
  position: relative;
  transition: background 0.5s ease;
  justify-content: space-between;
}

.switch-toggle {
  position: absolute;
  background-color: var(--background-color-primary);
  border-radius: 50%;
  top: calc(var(--element-size) * 0.07);
  left: calc(var(--element-size) * 0.07);
  height: calc(var(--element-size) * 0.4);
  width: calc(var(--element-size) * 0.4);
  transform: translateX(0);
  transition: transform 0.3s ease, background-color 0.5s ease;
}

.switch-toggle-checked {
  transform: translateX(calc(var(--element-size) * 0.6)) !important;
}
</style>

  