<template>

  <div class="black-bg" v-if="modal">
    <div class="white-bg">
      <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="modal=false">닫기</button>
    </div>
  </div>

  <div v-for="(val,i) in menu" :key="i">
    <a @click="modal=true">{{i}}.{{val}}</a>
    <button @click="count[i]++">CLICK</button>
    <h4>Count :: {{count[i]}}</h4>
    <img :src="list[i].image"/>
  </div>

  <div v-for="(val,i) in list" :key="i">
    <!-- <h4>{{val}}</h4> -->
  </div>
  
</template>

<script>

import list from './assets/data.js';


export default {
  name: 'App',
  data() {
    return {
      list : list,
      modal : false,
      count : [0,0,0],
      menu : ['HOME','ABOUT','CONTACTME'],
    }
  },
  methods:{
    increase(){
      this.count++;
    }
  },
  components: {
    
  }
}
</script>

<style>
body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
