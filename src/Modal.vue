<template>
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <img :src="onerooms[clickNum].image" class="room-img">
      <h4>{{onerooms[clickNum].title}}</h4>
      <p>{{onerooms[clickNum].content}}</p>
      <!-- v-model : 여기에 입력한 데이터를 밑에 저장. ex)input 중 select, textarea 등-->
      <input v-model.number="month">
      <!-- 밑에꺼는 마우스로 조절하는 재밌는 놈 -->
      <!-- <input type="range" min="1" max="12"> -->
      <p> {{month}} 개월 선택함 : {{onerooms[clickNum].price * month}} 원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data(){
    return {
      month : 1,
    }
  },
  // input 감시(제어)하는 놈 - 데이터 변할 때마다 코드 실행됨.
  watch: {
    // data 이름이랑 같아야 됨. 
    // month(a,b) : a - 변경 될 month 데이터, b - 변경 전 month 데이터
    month(a){
      if(isNaN(a) == true){
        alert("숫자만 입력 가능합니다.");
        this.month = 1
      } 
    },
  },
  props : {
    onerooms : Array,
    clickNum : Number,
    modal : Boolean
  },
  updated(){
    if(this.month == 2){
      alert('2는 좀');
      this.month = 3
    }
  }
}
</script>

<style>

</style>