<template>
  <div>
    <form class="new-book-form" @submit.prevent="addBook">
      <label>Title:</label>
      <input class="title-input" type="text" v-model="title" required />
      <label>Author:</label>
      <input class="author-input" type="text" v-model="author" required />
      <label>Isbn:</label>
      <input class="isbn-input" type="text" v-model="isbn" required />
      <button type="submit">
        add book
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "add-book",
  data() {
    return {
      title: "",
      author: "",
      isbn: "",
    };
  },
  methods: {
    addBook() {
      let bookData = {
        title: this.title,
        author: this.author,
        isbn: this.isbn,
      };
      this.$store.commit("addBook", bookData);
    },
  },
};
</script>

<style></style>
