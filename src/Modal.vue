<template>
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <img :src="onerooms[clickNum].image" class="room-img">
      <h4>{{onerooms[clickNum].title}}</h4>
      <p>{{onerooms[clickNum].content}}</p>
      <!-- v-model : 여기에 입력한 데이터를 밑에 저장. ex)input 중 select, textarea 등-->
      <input v-model.number="month">
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
  props : {
    onerooms : Array,
    clickNum : Number,
    modal : Boolean
  }
}
</script>

<style>

</style>