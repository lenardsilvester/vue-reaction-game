<template>

  <h3>
      Your time was <span>{{ score }}</span> ms.
  </h3>

  <h4>
      Your rank was <span>{{ rank }}</span>
  </h4>

</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },

    mounted() {
        if (this.score < 250) {
            this.rank = 'Ninja fingers.'
        } else if (this.score < 400) {
            this.rank = 'Rapid reflexes.'
        } else {
            this.rank = 'Turtle man...'
        }
    }
}
</script>