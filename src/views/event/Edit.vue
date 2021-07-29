<template>
  <p>Edit the event here</p>
  <button @click="edit">Edit</button>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    edit() {
      this.GStore.flashMessageEdit =
        'the data has been updated.'
        setTimeout(() => {
          // After 3 seconds remove it
          this.GStore.flashMessageEdit = ''
        }, 3000)

      this.$router.push({
        name: 'EventDetails',
        params: { id: this.event.id }
      })
    }
  }
}
</script>
