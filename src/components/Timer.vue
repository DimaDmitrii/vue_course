<script setup>
import { ref,watch } from 'vue';

  function timer() {
    let today = new Date()      // запомним текущую дату
    let birthDay = new Date()   // установим дату дня рождения
    birthDay.setMonth(6)    // 6й месяц начиная с 0=Январь (Июль)
    birthDay.setDate(7)     // 7е число месяца
    birthDay.setHours(0)    // 0 часов
    birthDay.setMinutes(0)  // 0 минут
    birthDay.setSeconds(0)  // 0 секунд
    if (birthDay.getTime() < today.getTime())   // если день рождения в этом году уже прошёл
    {   birthDay.setFullYear(today.getFullYear() + 1)    }  // установим дату следующего дня рождения через год

    let days = Math.floor( (birthDay.getTime() - today.getTime()) / (1000 * 60 * 60 * 24) )
    let hours = Math.floor( (birthDay.getTime() - today.getTime()) / (1000 * 60 * 60) ) - days * 24
    let minutes = Math.floor( (birthDay.getTime() - today.getTime()) / (1000 * 60) ) - (days * 24 + hours) * 60
    let seconds = Math.floor( (birthDay.getTime() - today.getTime()) / (1000) ) - ((days * 24 + hours) * 60 + minutes) * 60
    // console.log("---", days, hours, minutes,seconds)
    
    return [days, hours, minutes, seconds]
  }
  
  watch(
    {},
    () => {
      setInterval(() => {timeLeft.value = timer()}, 1000)
    },
    { immediate: true }
  )

  const timeLeft = ref (timer())

</script>

<template>
    
  <div class="timer">
    <div id="timerDays">{{ timeLeft[0] }} days</div>
    <div id="timerHours">{{ timeLeft[1] }} hours</div>
    <div id="timerMinutes">{{ timeLeft[2] }} minutes</div>
    <div id="timerSeconds">{{ timeLeft[3] }} seconds</div>
    <div class="timerParagraph">left before Kolya's birthday</div>
  </div>

</template>
