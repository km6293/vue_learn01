<template>
  <div>
    <img :src="oneroom.image" class="room-img">
    <!-- emit 부모한테 메시지 보냄 -->
    <h4 @click="$emit('openModal', oneroom.id)" >{{oneroom.title}}</h4>
    <p>{{oneroom.price}}원</p>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props : {
    oneroom : Array
  }
}
</script>

<style>

</style>