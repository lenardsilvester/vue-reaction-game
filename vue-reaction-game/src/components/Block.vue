<template>

  <div class="block" v-if="showBlock" @click="stopTimer">
    <b>
        (Click me!)
    </b>
  </div>

</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0
        }
    },

    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
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
            this.$emit('end', this.reactionTime)
        }
    }
}
</script>
