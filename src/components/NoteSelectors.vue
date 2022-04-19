<script>
import NoteSelector from "./NoteSelector.vue";
export default {
  components: {
    NoteSelector,
  },
  data: function () {
    return {
      notes: [
        { id: 1, body: "This is first note", timestamp: Date.now() },
        { id: 2, body: "This is second note", timestamp: Date.now() },
        { id: 3, body: "This is third note", timestamp: Date.now() },
        { id: 4, body: "This is fourth note", timestamp: Date.now() },
        { id: 5, body: "This is fifth note", timestamp: Date.now() },
        { id: 6, body: "This is sixth note", timestamp: Date.now() },
      ],
      selectedNoteId: 1,
    };
  },
  methods: {
    selectNote: function (note) {
      this.selectedNoteId = note.id;
    },
  },
};
</script>

<template>
  <div class="note-selectors">
    <NoteSelector
      v-for="note in notes"
      v-bind:note="note"
      v-bind:selectedNoteId="selectedNoteId"
      v-on:selectNote="selectNote"
      v-bind:key="note.id"
    />
  </div>
</template>
