<template>

  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in menu" :key="a">{{a}}</a>
  </div>

  <div>
    <img src="./assets/room0.jpg" class="room-img">
    <h4 @click="modal = true">{{products[0]}}</h4>
    <p>50 만원</p>
    <button @click="declarations[0]++">허위매물신고</button> 
    <span>신고수 : {{declarations[0]}}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg">
    <h4>{{products[1]}}</h4>
    <p>60 만원</p>
    <button @click="declarations[1]++">허위매물신고</button> 
    <span>신고수 : {{declarations[1]}}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg">
    <h4>{{products[2]}}</h4>
    <p>70 만원</p>
    <button @click="declarations[2]++">허위매물신고</button> 
    <span>신고수 : {{declarations[2]}}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data(){
    return{
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
