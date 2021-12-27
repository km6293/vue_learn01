<template>

  <Modal :onerooms="onerooms" :clickNum="clickNum" :modal="modal" />

  <div class="menu">
    <a v-for="a in menu" :key="a">{{a}}</a>
  </div>

  <Discount/>

  <div v-for="(room,i) in onerooms" :key="i">
    <img :src="onerooms[i].image" class="room-img">
    <h4 @click="modal = true; clickNum = i">{{onerooms[i].title}}</h4>
    <p>{{onerooms[i].price}}원</p>
  </div>

</template>

<script>

import data from './assets/oneroom';
import Discount from './Discount.vue';
import Modal from './Modal.vue';

export default {
  name: 'App',
  data(){
    return{
      clickNum : 0,
      onerooms : data,
      modal : false,
      declarations : [0,0,0],
      menu : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  methods: {
    increase(){
      this.declarations += 1
    }
  },
  components: {
    Discount : Discount,
    Modal
  }
}
</script>

<style>
body {
  margin : 0
}

div{
  box-sizing: border-box;
}

.discount{
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}

.white-bg{
  width: 100%; background: white;
  border-radius:8px;
  padding: 20px;
}

.room-img{
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;  
}

.menu a{
  color: white;
  padding: 10px;
}

</style>
