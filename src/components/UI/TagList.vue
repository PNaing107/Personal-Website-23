<template>
    <div class="taglist">
        <div
          v-for="tag in tags"
          :key="tag.name"
          :class="tag.class"
          class="tag"
        >
        {{ tag.name }}
    </div>
    </div>
</template>

<script>
export default {
    props: ['tags'],
}
</script>

<style scoped>
.taglist {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
}

.tag {
    padding: 0.2rem 0.4rem;
    border: 1px solid var(--text-primary-color);
    border-radius: 0.2rem;
}

.text-purple {
    color: #3b14eb;
}

.text-green {
    color: chartreuse;
}

.text-orange {
    color: #df6d22;
}

.text-light-blue {
    color: #0facf5;
}
</style>