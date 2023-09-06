<template>
    <section class="content">
        <p>Welcome to my blog section where I aim to document my developer journey. Feel free to reach out to me via email
            (phone.naing.dev+blog@gmail.com) if
            you want to talk about my posts.</p>
        <div class="container">
            <div v-for="post in posts" :key="post.id">
                <h3>{{ post.title }}</h3>
                <p>{{ post.created_at }}</p>
                <TagList :tags="post.tags"></TagList>
                <p>{{ post.description }}</p>
                <button @click="showModal(post.id)">Read More</button>
                <hr>
            </div>
        </div>
        <Modal v-show="isModalVisable" @close="closeModal">
            <template #header>Blog Post</template>
            <template #body>
                <Post1 v-if="modalBody === 1"></Post1>
            </template>
        </Modal>
    </section>
</template>

<script>
import TagList from '../UI/TagList.vue';
import Modal from '../UI/TheModal.vue';
import Post1 from './blog/Post1.vue';

export default {
    components: {
        TagList,
        Modal,
        Post1,
    },
    data() {
        return {
            isModalVisable: false,
            modalBody: null,
            posts: [
                {
                    id: 1,
                    title: 'Why I decided to become a Software Developer',
                    created_at: '14/12/2022',
                    tags: [
                        {
                            name: 'Career',
                            class: 'text-purple'
                        },
                    ],
                    description: 'I am a career changer and managed to break into software development after completing a bootcamp with iOAcademy. This post might be interesting to you if you are also considering a career as a programmer and considering the bootcamp route.',
                },
            ]
        }
    },
    methods: {
        showModal(id) {
            this.modalBody = id;
            this.isModalVisable = true;
        },
        closeModal() {
            this.isModalVisable = false;
        },
    },
}
</script>

<style scoped>
.container {
    width: clamp(120px, 65vw, 1024px);
    max-height: 14rem;
    overflow-y: auto;
    margin: 0 auto;
    padding: 1rem;
    background-color: var(--background-color-secondary);
    border-radius: var(--border-radius-default);
    text-align: left;
}

a {
    margin-right: 1rem;
}

.social {
    margin-top: 0.5rem;
    margin-bottom: 1rem;
}

a:hover {
    color: var(--text-secondary-color);
}</style>