<template>
    <section class="content">
        <h3>Hi 👋, I'm Phone
            <span>(yes that is the correct spelling - my parents were not forgiving 🙈)</span>
        </h3>
        <h4>Welcome to my site!</h4>
        <div class="bio">
            <p>This is me in a nutshell 🥜:</p>
            <ul class="fa-ul">
                <li>
                    <span class="fa-li"><i class="fa-solid fa-meteor"></i></span>
                    Born in Yangon, Myanmar <img id="mm-flag" src="../../assets/myanmar-flag-icon.svg" alt="Myanmar Flag" />
                    but
                    grew
                    up
                    in Cornwall, UK (unfortunately I can't surf <span class="emoji">🏄</span>)
                </li><br>
                <li>
                    <span class="fa-li"><i class="fa-solid fa-meteor"></i></span> Love exploring the outdoors, especially on
                    my
                    bike
                    <span class="emoji">🚴</span> , and tasting new cuisines <span class="emoji">🍲 🥡 🍰 😋</span>
                </li><br>
                <li>
                    <span class="fa-li"><i class="fa-solid fa-meteor"></i></span> I hold a Masters Degree in Mechanical
                    Engineering
                    but my true passion is building things for the Web <span class="emoji">👨‍💻</span>
                </li>
            </ul>
            <div class="controls">
                <button @click="showModal">View My Skills</button>
                <button><a href="https://naingphonecv.tiiny.site" target="_blank">View My CV</a></button>
            </div>
        </div>
        <Modal v-show="isModalVisable" @close="closeModal">
            <template #header><h3 style="margin:0">My Skills</h3></template>
            <template #body>
                <SkillsAboutMe></SkillsAboutMe>
            </template>
            <template #footer></template>
        </Modal>
    </section>
</template>

<script>
import Modal from '../UI/TheModal.vue';
import SkillsAboutMe from './slots/SkillsAboutMe.vue';

export default {
    components: {
        Modal,
        SkillsAboutMe,
    },
    data() {
        return {
            isModalVisable: false,
        };
    },
    methods: {
        showModal() {
            this.isModalVisable = true;
        },
        closeModal() {
            this.isModalVisable = false;
        },
    }
}
</script>

<style>
#mm-flag {
    width: 2em;
}

section {
    text-align: center;
    margin-top: 3rem;
}

.bio {
    display: flex;
    flex-direction: column;
    align-content: center;
    border-radius: var(--border-radius-default);
    width: clamp(260px, 60vw, 1024px);
    margin: 0 auto;
    background-color: var(--background-color-secondary);
}

.fa-ul {
    list-style-type: none;
    padding-left: 0;
    text-align: left;
}

.controls {
    margin: 1rem 0;
    display: flex;
    justify-content: space-evenly;
}

@media (max-width: 660px) {
    .controls {
        display: flex;
        flex-direction: column;
    }

    button {
        width: auto;
        margin: 0.5rem;
    }
}
</style>