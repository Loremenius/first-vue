<template>
  <div class="hello">
    <h1> A list of cool quotes... </h1>
    <p v-for="quote in quotes" :key="quote"> {{ quote }} </p>
    <form v-on:submit.prevent="submit">
      <input v-model.trim="quote" placeholder="Add a quote">
      <button> Add quote to the list </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      quotes:['A monument to all your sins'],
      quote:''
    }
  },
  methods:{
    submit: function () {
      this.quotes.push(this.quote)
      this.quote = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
