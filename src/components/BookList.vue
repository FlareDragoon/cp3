<template>
<div class="wrapper">
  <div class="books">
    <div class="book" v-for="book in books" :key="book.id">
      <div class="info">
        <h1>{{book.name}}</h1>
        <p>{{book.author}}</p>
      </div>
      <div class="genre">
        <h2>{{book.genre}}</h2>
        <button v-on:click="remove(book.id)" class="auto">Remove</button>
      </div>
    </div>
  </div>
</div>
</template>

<script>


export default {
  name: 'BookList',
  props: {
    books: Array
  },

  methods: {
    remove(itemID) {
      let index = this.$root.$data.books.findIndex(book => book.id == itemID)
      this.$root.$data.books.splice(index, 1);
    }

  }, 
}
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.books {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.book {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
  background: #babbc2;
}

.info {
  background: #5e75f2;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}


.genre {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>