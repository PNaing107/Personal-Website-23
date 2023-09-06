<template>
  <div class="modal-backdrop">
    <div class="modal">
      <header class="modal-header">
        <slot name="header">
        </slot>
        <button type="button" class="btn-close" @click="close">X</button>
      </header>
      <section class="modal-body">
        <slot name="body">
        </slot>
      </section>
      <footer class="modal-footer">
        <slot name="footer">
        </slot>
        <button type="button" class="btn-green" @click="close">Close Modal</button>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    close() {
      this.$emit('close');
    },
  },
};
</script>

<style scoped>
.modal-backdrop {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-color: rgba(116, 113, 113, 0.377);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  background-color: var(--background-color-primary);
  color: var(--text-primary-color);
  overflow-x: auto;
  display: flex;
  flex-direction: column;
}

.modal-header,
.modal-footer {
  padding: 15px;
  display: flex;
  justify-content: center;
}

.modal-header {
  position: relative;
  border-bottom: 1px solid #eeeeee;
  justify-content: space-between;
}

.modal-footer {
  border-top: 1px solid #eeeeee;
  flex-direction: column;
  justify-content: flex-end;
}

.modal-body {
  position: relative;
  margin-top: 0;
  padding: 1rem 2rem;
  max-height: 60vh;
  max-width: 90vw;
  overflow-y: auto;
}

.btn-close {
  position: absolute;
  top: 0;
  right: 0;
  border: none;
  font-size: 1.2rem;
  padding: 0.5rem;
  cursor: pointer;
  font-weight: bold;
  background: transparent;
  width: fit-content;
}

.btn-close:hover {
  background-color: var(--background-color-primary);
}

.btn-green {
  /* color: var(--modal-text-color); */
  /* background: var(--modal-background-color); */
  /* border: 1px solid var(--modal-text-color); */
  border-radius: 0.2rem;
  padding: 0.5rem;
  width: fit-content;
}
</style>