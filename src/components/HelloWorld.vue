<script setup>
import { ref } from 'vue'

defineProps({
  msg: String
})

const address = ref(null);
const map =  ref(null);

const mapSearch = function(){
  console.log("mapSearch");
  map.value = address.value;
};

</script>

<template>
  <div>
    <input type="text" v-model="address" />
    <button v-on:click="mapSearch">検索</button>
  </div>
  <div>
  <iframe :src="'https://maps.google.co.jp/maps?output=embed&q=' + map" style="width:100%; height:80vh;"></iframe>
  </div>
</template>

<style scoped>
</style>
