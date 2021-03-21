<template>
<div>
  <div class="wrapper">
    <div class="search">
      <form class="pure-form">
        <i class="fas fa-search"></i><input v-model="searchText" />
      </form>
    </div>
  </div>
  <p v-if="this.$root.$data.books.length === 0">Your bookshelf is empty.</p>
  <BookList :books="books" />

  <div class='wrapper'>
    <div class="new-book-form">
      <h2>Add a New Book</h2>
      <form class="pure-form" v-on:submit.prevent="addItem">
        <div>
          <label for="name">Title:</label>
          <input v-model="title">
        </div>

        <div>
          <label for="author">Author:</label>
          <input v-model="author">
        </div>

        <div>
          <label for="genre">Genre:</label>
          <input v-model="genre">
        </div>
        
        <center><button type="submit">Add</button></center>
      </form>
    </div>
  </div>

</div>
</template>

<script>
import BookList from "../components/BookList.vue"
export default {
  name: 'Home',
  components: {
    BookList
  },
  data() {
    return {
      searchText: '',
    }
  },
  computed: {
    books() {
      return this.$root.$data.books.filter(book => book.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);    }
  },
  methods: {
    addItem() {
      this.$root.$data.books.push({id: this.$root.$data.nextIndex, name: this.title, author: this.author, genre: this.genre});
      this.$root.$data.nextIndex += 1;
      this.title = '';
      this.author = '';
      this.genre = '';
    },
  }

}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.search {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

form {
  display: table;
  width: 100%;
}

i {
  display: table-cell;
  padding-left: 10px;
  width: 1px;
}

input {
  display: table-cell;
  font-size: 20px;
  border: 1px solid;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

.new-book-form {
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 50%;
}

.new-book-form h2{
  text-align: center;
}

.form-input {
  display: table-cell;
  padding-left: 10px;
  font-size: 20px;
  border: none !important;
  box-shadow: none !important;
  width: 100%;
  height: 40px;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

label {
  float: left;
}
</style>