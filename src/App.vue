<template>
  <div>
    <Header />
     <CreateArea v-on:add-note="onAddNote" />
    <Note
      v-for="note in notes"
      v-bind:key="note.id"
      v-bind:note="note"
      v-on:delete-note="onDeleteNote"
    ></Note>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Note from "./components/Note.vue";
import CreateArea from "./components/CreateArea.vue"

export default {
  name: "app",
  components: {
    Header,
    CreateArea,
    Note,
    Footer
  },
  data: function() {
    return {
      notes: [
        { id: 1, title: "note 1", content: "Content of note 1" },
        { id: 2, title: "note 2", content: "Content of note 2" }
      ]
    };
  },
  methods: {
    onDeleteNote: function(id) {
      this.notes = this.notes.filter(note => note.id !== id);
    },
    onAddNote: function(note) {
      this.notes = [...this.notes, note];
    }
  }
};
</script>

<style>
  @import './assets/styles.css';
</style>