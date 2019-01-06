<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <input v-model="userIn"/>
    <button  v-on:click="add">add</button>
    <li v-for="stuff in val"
          v-bind:key="stuff.id"
    >
    <HelloWorld v-bind:onClick='remove' v-bind:change="update" v-bind:stuff='stuff'/>
    </li>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data: function() {
    return {
      val: [],
      userIn: "",
      count: 0
      }
  },
  methods:{
    add: function(){
      this.val.push({id: this.count, item: this.userIn});
      this.count++;
    },
    remove: function(index){
      for(let i =0;i< this.val.length;i++){
        if(this.val[i].id===index){
          this.val.splice(i,1)
        }
      }
    },
    update: function(index,v){
      for(let i =0;i< this.val.length;i++){
        if(this.val[i].id===index){
          this.val[index].item=v;
        }
      }
    }
  }
}
</script>
