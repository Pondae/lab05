<template>
  <p>Regstration form here</p>
  <button @click="register">Register Me</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    register() {
      this.GStore.flashMessage =
        'You are successfully registered for ' + this.event.title
        setTimeout(() => {
          // After 3 seconds remove it
          this.GStore.flashMesage = ''
        }, 3000)

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
