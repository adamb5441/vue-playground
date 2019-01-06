<template>
  <div class="hello">

        <div v-if="show">
        <input type="text" value={stuff.item} v-model="userIn"/>
        <button v-on:click="change(stuff.id,userIn)">update</button>
        </div>
        <div v-else>
      {{ stuff.item }}
        </div>
      <button  v-on:click="onClick(stuff.id)">delete</button>
      <button v-on:click="tog()">edit</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    onClick: Function,
    change: Function,
    stuff: String
  },
  data: function(){
    return{
      show: false,
      userIn: ""
    }
  },
  methods: {
    tog: function(){
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
