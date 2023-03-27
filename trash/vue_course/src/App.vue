<script setup>
  import { reactive, ref } from 'vue';
  import Timer from "./components/Timer.vue"

    // не работает, (разными способами пытался продублировать строку по числу кликов)
    let clicks = ref(0)
    let buttonText = ref("Hip hip hooray!!!".repeat(clicks.value + 1))
    // const buttonText = reactive ({
    //   text: "Hip hip hooray \n".repeat(clicks.value + 1),
    // })

</script>

<template>

  <div class="main">
    <timer></timer>

    <div class="content_1">
      <button class="hoorayButton" @click="clicks ++">
        <img class="button_picture" src="/button.png"><div class="buttonText"> {{ clicks }} clicked <br/> {{ buttonText }} <br/> :3 </div>
      </button>
      <div class="content_1_text"></div>
    </div>

  </div>
  
</template>

<style scoped></style>
