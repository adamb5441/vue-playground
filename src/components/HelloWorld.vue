<template>
  <div class="hello">
      <li v-for="stuff in list"
      v-bind:list="stuff"
      v-bind:key="stuff.id"
      >
      {{ stuff.item }}
      <button  v-on:click="onClick(stuff.id)">delete</button>
    </li>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    onClick: Function,
    list: Array
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
