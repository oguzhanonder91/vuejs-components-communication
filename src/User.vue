<template>
  <div>
    <p>Ben User componentiyim.</p>
    <button @click="changeUser"> Kullanıcı Değiştir</button>
    <p>Childen Gelen :  {{comingFromChild}}</p>
    <p>Kullanıcı Yaşı :  {{age}}</p>

    <UserEdit @sendDataParent="comingData" :age = "age"></UserEdit>
    <UserDetail :age ="age" :userName="userName"></UserDetail>
  </div>

</template>

<script>
  import UserDetail from './UserDetail';
  import UserEdit from './UserEdit';

  export default {
    name: "User",
    data() {
      return {
        userName: "Oğuzhan ÖNDER",
        comingFromChild: "",
        age: "25"
      }
    },
    components: {UserDetail, UserEdit},
    methods: {
      changeUser() {
        this.userName = "Metehan ÖNDER";
      },
      comingData(event) {
        this.comingFromChild = event;
      },
    },
    computed : {

    }
  }
</script>

<style scoped>
  div {
    padding: 20px;
    background-color: beige;
    margin: 20px;
    border-bottom-color: black;
  }

</style>
