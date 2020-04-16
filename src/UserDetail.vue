<template>
  <div>
    <p>Ben UserDetail componentiyim.</p>
    <p>Yeni Kullanıcı Adı : {{userName}}</p>
    <p>Büyük Harfle Kullanıcı Adı : {{toUpperCaseName}}</p>
    <p>Kullanıcı Yaşı : {{age}}</p>

  </div>
</template>

<script>
  import {eventBus} from './main';
  export default {
    name: "UserDetail",
    props: {
      userName: {
        type: String,
        required: true
      },
      age : {
        type: String
      }
    },
    computed: {
      toUpperCaseName() {
        return this.userName.toUpperCase();
      },
    },
    created() {
      eventBus.$on("ageWasUpdated" , (age)=>{
        this.age = age;
      })
    }
  }
</script>

<style scoped>
  div {
    background-color: aqua;
  }

</style>
