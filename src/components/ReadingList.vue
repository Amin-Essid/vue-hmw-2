<template>
  <div class="book-container">
    <div v-for="book in books" :key="book.title">
      <BookCard :book="book" />
    </div>
  </div>
</template>

<script>
import BookCard from "@/components/BookCard.vue";
export default {
  name: "reading-list",
  components: { BookCard },
  data() {},

  computed: {
    books() {
      return this.$store.getters.books;
    },
  },
};
</script>

<style>
.book-container {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
}
</style>
