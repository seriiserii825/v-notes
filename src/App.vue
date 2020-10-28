<template>
  <div class="wrapper">
    <div class="wrapper-content">
      <section>
        <div class="container">
          <div id="app">
            <h1>{{ title }}</h1>

            <div class="message" v-if="message">
              <p>{{ message }}</p>
            </div>

            <div class="new-note">
              <input type="text" v-model="note.title">
              <textarea v-model="note.description"></textarea>
              <button @click="addNote">Add note</button>
            </div>

            <div class="notes">
              <div class="note" v-for="(note, index) in notes" :key="index">
                <div class="note-header">{{ note.title }}</div>
                <div class="note-body">
                  <p>{{ note.description }}</p>
                  <span>{{ note.date }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      title: 'Note App',
      message: null,
      note: {
        title: '',
        description: ''
      },
      notes: [
        {
          title: 'First Note',
          description: 'Description for First Note',
          date: new Date(Date.now()).toLocaleString()
        },
        {
          title: 'Second Note',
          description: 'Description for Second Note',
          date: new Date(Date.now()).toLocaleString()
        },
        {
          title: 'Third Note',
          description: 'Description for Third Note',
          date: new Date(Date.now()).toLocaleString()
        }
      ]
    }
  },
  methods: {
    addNote () {
      const { title, description } = this.note

      if (title === '') {
        this.message = 'Title can\'t be blank'
        return false
      }

      this.notes.push({
        title,
        description,
        date: new Date(Date.now()).toLocaleString()
      })
      this.message = null
      this.note.title = ''
      this.note.description = ''
    }
  }
}
</script>

<style lang="scss">

</style>
