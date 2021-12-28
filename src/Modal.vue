<template>
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <img :src="onerooms[clickNum].image" class="room-img">
      <h4>{{onerooms[clickNum].title}}</h4>
      <p>{{onerooms[clickNum].content}}</p>
      <p>{{onerooms[clickNum].price}} 원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props : {
    onerooms : Array,
    clickNum : Number,
    modal : Boolean
  }
}
</script>

<style>

</style>