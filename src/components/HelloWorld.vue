<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ msg: string }>()

const count = ref(0);
const dom = ref();

function returnDom () {
  const h1 = document.createElement("h1");

  h1.innerText = '你看我几分像从前';

  return h1;
}

dom.value = returnDom();

class Game {
  constructor() {}

  
}

</script>

<template>
  <!-- <h1>{{ msg }}</h1> -->

  {{dom}}
  
  <div class="box" >
    <i></i>
    <i></i>
    <i></i>
    <i></i>
  </div>

</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}

.box {
  /* border: 2px solid #42b983; */
  margin: 0px auto;
  width: 500px;
  height: 500px;
  position: relative;
  overflow: hidden;
}

.box > i {
  position: absolute;
  display: block;
}

.box > i:nth-child(1) {
  top: 0px;
  left: -100%;
  height: 2px;
  width: 100%;
  background: linear-gradient(90deg, transparent, #03e9f4);
  animation: border-top-anim 1s linear infinite;
}

@keyframes border-top-anim {
  0% {
    left: -100%;
  }
  50%,100% {
    left: 100%;
  }
}

.box > i:nth-child(2) {
  right: 0px;
  top: -100%;
  height: 100%;
  width: 2px;
  background: linear-gradient(180deg, transparent, #03e9f4);
  animation: border-right-anim 1s linear infinite;
  animation-delay: 0.25s;
}

@keyframes border-right-anim {
  0% {
    top: -100%;
  }
  50%,100% {
    top: 100%;
  }
}

.box > i:nth-child(3) {
  bottom: 0px;
  left: 100%;
  height: 2px;
  width: 100%;
  background: linear-gradient(-90deg, transparent, #03e9f4);
  animation: border-bottom-anim 1s linear infinite;
  animation-delay: 0.5s;
}

@keyframes border-bottom-anim {
  0% {
    left: 100%;
  }
  50%,100% {
    left: -100%;
  }
}

.box > i:nth-child(4) {
  top: 100%;
  left: 0px;
  height: 100%;
  width: 2px;
  background: linear-gradient(0deg, transparent, #03e9f4);
  animation: border-left-anim 1s linear infinite;
  animation-delay: 0.75s;
}

@keyframes border-left-anim {
  0% {
    top: 100%;
  }
  50%,100% {
    top: -100%;
  }
}
</style>
