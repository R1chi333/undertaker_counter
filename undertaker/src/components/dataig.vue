<script>
import container from './container.vue'

export default {
  components: {
    container
  },
  data() {
    return {
      play: true
    }
  },
  methods: {
    togglePlay() {
      this.play = !this.play
    }
  }
}
</script>
<style scoped>
div {
  /* overflow-y: hidden; */
}
</style>
