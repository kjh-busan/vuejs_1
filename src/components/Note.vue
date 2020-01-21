<template>
    <div class="note">
      <h1>{{note.title}}</h1>
      <p>{{note.content}}</p>
      <button v-on:click="$emit('delete-note', note.id)">DELETE</button>
    </div>
</template>

<script>
export default {
    props: ['note']
}
</script>