<template>
  <div>
    <p> Ben UserEdit componentiyim</p>
    <p>Kullanıcı Yaşı : {{age}}</p>
    <button @click="sendToParent"> User (Root) veri Gönder</button>
    <button @click="changeAge">Yaşı değiştir</button>
  </div>
</template>

<script>
  import {eventBus}  from './main';
  export default {
    name: "UserEdit",
    props: ["age"],
    data() {
      return {
        sendData: "Sana Gönderdim Bunu User UserEditten Geldim."
      }
    },
    methods: {
      sendToParent() {
        this.$emit("sendDataParent", this.sendData);
      },
      changeAge() {
        this.age = "35";
        //this.$emit("ageWasUpdated", age)
        eventBus.changeAge(this.age);
      }
    },
  }
</script>

<style scoped>
  div {
    background-color: chartreuse;
  }

</style>
