<template>

  <!-- <div class="start" :class="{ end : modal }"> -->
  <!-- 애니메이션 밑이 위랑 똑같은것 css도 마찬가지 -->
  <transition name="fade">
    <Modal @closeModal="modal = false" :onerooms="onerooms" :clickNum="clickNum" :modal="modal" />
  </transition>
  <!-- </div> -->

  <div class="menu">
    <a v-for="a in menu" :key="a">{{a}}</a>
  </div>

  <Discount />
  <!-- 자식이 값 변경 못해서 메시지만 보냄. 자식한테 받은거 똑같은 작명으로 쓰면 됨 -->
  <Card @openModal="modal = true; clickNum = $event" :oneroom="onerooms[i]" v-for=" (a,i) in onerooms" :key="i" />
    
</template>

<script>

import data from './assets/oneroom';
import Discount from './Discount.vue';
import Modal from './Modal.vue';
import Card from './Card.vue';

export default {
  name: 'App',
  // 데이터는 한 곳에 보관하고 필요하면 가져다 씀. ex) props로 부모 -> 자식 
  data(){
    return{
      object : {
        name : 'kim',
        age : 20
      },
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
    // 밑 3개 같은 의미
    Discount : Discount,
    Modal,
    Card
  }
}
</script>

<style>

.fade-leave-from{ opacity: 1; }
.fade-leave-active{ transition: all 1s; }
.fade-leave-to { opacity: 0; }

.fade-enter-from{ transform: translateY(-1000px); }
.fade-enter-active{ transition: all 1s; }
.fade-enter-to { transform: translateY(0px); }


/* .start{
  opacity: 0;
  transition: all 1s;
}

.end{
  opacity: 1;
} */

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
