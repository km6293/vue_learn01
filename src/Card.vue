<template>
  <div>
    <img :src="oneroom.image" class="room-img">
    <h4 >{{oneroom.title}}</h4>
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