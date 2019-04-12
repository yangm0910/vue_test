<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <input v-model="todo"/><button @click="submit">submit</button>
    <ul v-for="(item,index) in list"  :key="index">
        <li v-bind="item">{{item}}<button @click="remove(index)">remove</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data(){
    return{
      todo:"todo",
      count:2,
      list: ["1","2"]
    }
  },
  methods: {
    submit: function(){
      this.list.push(this.todo);
    },
    remove: function(index){
      this.list.splice(index,1)
    },
    reverse: function() {
      return this.msg
        .split("")
        .reverse()
        .join("");
    },
    now: function() {
      return Date.now();
    }
  }
  // computed:{
  //   now: function(){
  //     return "1";
  //   }
  // }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
