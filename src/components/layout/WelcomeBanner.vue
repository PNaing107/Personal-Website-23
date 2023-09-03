<template>
    <div v-if="showBanner" id="banner">
        <div>{{ text }}<span :id="showCarat" class="carat">|</span></div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            showCarat: false,
            messages: [
                'Welcome!',
                'Bienvenue!',
                'Willkommen!',
                'Bem-vindos!',
                'ようこそ',
                '欢迎',
                '환영합니다',
            ],
            text: '',
        };
    },
    props: ['showBanner'],
    mounted() {
        // Start the carat animation
        setInterval(() => {
            if (this.showCarat) {
                this.showCarat = false;
            } else {
                this.showCarat = 'carat';
            }
        }, 500)

        // Start the typing animation

        let i = 0;
        let j = 0;
        let direction = 'forward';

        const timer = setInterval(()=> {
            
            if(i < this.messages.length) {
                let message = this.messages[i];

                if(direction === 'forward') {

                    if(j < message.length) {
                        this.text += message.charAt(j);
                        j++
                    } else {
                        direction = 'backward'
                    }

                } else {

                    if(j>0) {
                        this.text = message.substring(0,j);
                        j--;
                    } else {
                        this.text = '';
                        direction = 'forward';
                        i++;
                    }
                }

            } else {
                clearInterval(timer);
            }

        },300);
    },

}

</script>

<style scoped>
#banner {
    font-size: 5rem;
    text-align: center;
    margin: 5rem auto;
}

.carat {
    color: rgb(138, 43, 226, 1);
    /* animation-name: blink; */
    /* animation-duration: 0.5s; */
    /* animation-timing-function: cubic-bezier(0.075, 0.82, 0.165, 1); */
    /* animation: blink 0.5s cubic-bezier(0.075, 0.82, 0.165, 1); */
    
}

#carat {
    color: rgb(138, 43, 226, 0);
}

@keyframes blink {
    from {
        color: rgb(138, 43, 226, 1);
    }

    to {
        color: rgb(138, 43, 226, 0);
    }
}
</style>