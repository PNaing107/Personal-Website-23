<template>
    <section class="content">
        <p>Below you will find a range of projects I've worked on to apply my Web Development knowledge.<br> Feel free to
            test
            out the live apps and explore the code on GitHub.
        </p>
        <div class="container">
            <div v-for="project in projects" :key="project.id">
                <h3>{{ project.title }}</h3>
                <TagList :tags="project.tags"></TagList>
                <p>{{ project.description }}</p>
                <div>
                    <p>Objective:</p>
                    <p>{{ project.objective }}</p>
                </div>
                <div class="social">
                    <a href="project.links.github" target="_blank">
                        <i class="fa-brands fa-square-github fa-2x"></i>
                    </a>
                    <a v-if="project.links.app" href="project.links.app" target="_blank">
                        <i class="fa-solid fa-arrow-up-right-from-square fa-2x"></i>
                    </a>
                </div>
                <hr>
            </div>
        </div>
    </section>
</template>

<script>
import TagList from '../UI/TagList.vue';

export default {
    components: {
        TagList,
    },
    data() {
        return {
            projects: [
                {   id: 1,
                    title: 'Mock Invoicing SPA (v2)',
                    tags: [
                        {
                            name: 'Vue',
                            class: 'text-green'
                        },
                        {
                            name: 'Tailwind CSS',
                            class: 'text-light-blue'
                        },
                        {
                            name: 'Cypress',
                            class: ''
                        }
                    ],
                    description: 'This is a Vue 3 and Tailwind CSS frontend for an Invoicing Application which pulls data from a prebuilt RESTful API.',
                    objective: 'To demonstrate an understanding of Vue 3 fundamentals with both the Options and Composition API aswell as state management (using Vuex).\nTo demonstrate an understanding of front end testing using Cypress.',
                    links: {
                        github: 'https://github.com/PNaing107/invoicing-spa',
                        app: null,
                    }
                },
                {
                    id: 2,
                    title: 'Restaurant Order Tracking API',
                    tags: [
                        {
                            name: 'PHP',
                            class: 'text-purple'
                        },
                        {
                            name: 'Slim',
                            class: 'text-green'
                        },
                        {
                            name: 'MySQL',
                            class: 'text-orange'
                        },
                    ],
                    description: 'A Restful API built with PHP (Slim Framework) and MySQL to track restaurant orders.',
                    objective: 'To demonstrate an understanding of the SOLID principles of OOP while working with a minimalist backend PHP framework.',
                    links: {
                        github: 'https://github.com/PNaing107/2022-aug-restaurant-api',
                        app: null,
                    }
                },
                {
                    id: 3,
                    title: 'Mock Invoicing SPA (v1)',
                    tags: [
                        {
                            name: 'React',
                            class: 'text-light-blue'
                        },
                        {
                            name: 'Bootstrap',
                            class: 'text-purple'
                        },
                    ],
                    description: 'This is a React and Bootstrap frontend for an Invoicing Application which pulls data from a prebuilt RESTful API.',
                    objective: 'To demonstrate an understanding of React fundamentals such as state management, component based design, and JSX; as well as using HTTP requests to retrieve and manipulate data from an API.',
                    links: {
                        github: 'https://github.com/iO-Academy/2022-aug-react-invoice-app',
                        app: 'https://2022-aug-react-invoice-app.dev.io-academy.uk/',
                    }
                },
            ]
        }
    }
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
}
</style>