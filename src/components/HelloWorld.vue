<template>
  <div class="hello">
      <li v-for="stuff in list"
      v-bind:list="stuff"
      v-bind:key="stuff.id"
      >
        <div v-if="show">
        <input type="text" v-model="stuff.item"/>
        <button>update</button>
        </div>
        <div v-else>
      {{ stuff.item }}
        </div>
      <button  v-on:click="onClick(stuff.id)">delete</button>
      <button v-on:click="tog()">edit</button>
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
  data: function(){
    return{
      show: true
    }
  },
  methods: {
    tog: function(){
      console.log("the function is running")
      if(this.show == false){
        this.show = true
      }
      else {
        this.show = false
      }
    }
  }
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
