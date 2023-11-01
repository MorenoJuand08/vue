<script setup>
  import { ref } from 'vue';
  let notification= ref (0)

function addValue(){
  notification.value++
  console.log(notification)
}

function minusValue(){
  if(notification.value>=1){
    notification.value--
  }
}

addValue()

</script>

<template>
<div class="wrapper">
  <div class="profile">
    <div class="notification" v-show="notification > 0">{{ notification }}</div>
  </div>
  <div class="box">
    <div class="button" @click="minusValue">-</div>
    <div class="button" @click="addValue">+</div>
  </div>
  <div v-if="notification == 0">Buuuu! Nadie te escribe😢</div>
  <div v-else>Revisa tu inbox</div>
</div>
</template>

<style scoped>
  .wrapper {
    background-color: #349998;
    width: 60%;
    border-radius: 8px;
    margin: 0 auto;
    padding-top: 32px;
    overflow: hidden;
  }

  .profile {
    background-color: purple;
    width: 120px;
    height: 120px;
    margin: 0 auto;
    border-radius: 100%;
    position: relative;
    background-image: url('https://elireview.com/wp-content/uploads/2016/12/reed-profile-square.jpg');
    background-size: cover;
  }

.notification{
  position: absolute;
  background-color: #f24006;
  min-width: 18px;
  height: 18px;
  border-radius: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  top: 0;
  right: 0;
}

  .box {
    text-align: center;
    padding-bottom: 16px;
    margin-top: 12px;
  }

  .button {
  background-color: peru;
  border-radius: 4px;
  padding: 2px 0;
  font-weight: bold;
  color: white;
  display: inline-block;
  width: 40px;
  cursor: pointer;
  
  }

  .button:first-child {
    margin-right: 8px;
  }

  .button:last-child{
    margin-left: 8px;
  }

</style>
