<template>
  <form
    v-on:submit.prevent="bookSubmit()"
    class=""
    action="#"
    method="post"
  >
    <input
      v-model="bookData.bookTitle"
      type="text"
      name="title"
      value=""
      placeholder="Book Title"
    >
    <input
      v-model="bookData.bookAuthor"
      type="text"
      name="author"
      value=""
      placeholder="Book Author"
    >
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input
        v-model="bookData.finishedReading"
        name="finishedReading"
        type="checkbox"
      >

    </div>
    <label for="borrowed">borrowed</label>
    <input
      type="radio"
      name="ownership"
      value="borrowed"
    >
    <label for="bought">bought</label>
    <input
      type="radio"
      name="ownership"
      value="bought"
    >
    <button
      type="submit"
      name="button"
    >Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit() {
      this.$emit("addBook", this.bookData);
    }
  }
};
</script>

<style>
</style>
