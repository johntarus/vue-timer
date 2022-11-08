<template>
    <div class="w-80 rounded-md bg-green-500 text-white text-center py-24 m-8" v-if="showBlock" @click="stopTimer">
        click me
    </div>
</template>

<script>
export default {
    data() {
        return{
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },
    props: ['delay'],
    mounted() {
        setTimeout(() => {
            this.showBlock = true; 
            this.startTimer();
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            console.log(this.reactionTime)
            this.$emit('end', this.reactionTime)
        }
    }
    }
</script>