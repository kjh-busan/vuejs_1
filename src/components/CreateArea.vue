<template>
  <div>
    <form v-on:submit="onSubmit">
      <input v-model="note.title" name="title" placeholder="Title" />
      <textarea v-model="note.content" name="content" placeholder="Take a note..." rows="3" />
      <button v-on:click="addNote">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      note: { id: Math.floor(Math.random() * 10000), title: "", content: "" }
    };
  },
  methods: {
      addNote: function() {
         const newNote = {...this.note};
         this.$emit('add-note', newNote);
         this.note.id =  Math.floor(Math.random() * 10000);
         this.note.title = "";
         this.note.content = ""; 
      },
      onSubmit: function(e) {
          e.preventDefault();
      }
  }
};
</script>