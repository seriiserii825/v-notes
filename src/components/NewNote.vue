<template>
  <div class="new-note">
    <input type="text" v-model="note.title">
    <textarea v-model="note.description"></textarea>
    <button @click="addNote">Add note</button>
  </div>
</template>

<script>
export default {
  props: ['note'],
  methods: {
    addNote () {
      this.$emit('add-note', this.note)
    }
  }
}
</script>

<style scoped>

</style>
