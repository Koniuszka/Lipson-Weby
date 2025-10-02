<script>
import { ref } from "vue";
import UserList from "./components/UserList.vue";
import AddUserForm from "./components/AddUserForm.vue";

export default {
  name: "App",
  components: {
    UserList,
    AddUserForm
  },
  data() {
    return {
      users: [
        { id: 1, name: "Maks", surname: "Drybler", age: 13, email: "maksiumalejajko@malejaja.pl" },
        { id: 2, name: "Jan", surname: "Piździwąs", age: 16, email: "JanekJebanyWDzbanek@wazelina.com" },
        { id: 3, name: "Matuesz", surname:"Leprechaun", age: 67, email: "mateuszwajcheprzełóż@potofgold.com" }
      ]
    };
  },
  methods: {
    addUser(newUser) {
      newUser.id = this.users.length + 1;
      this.users.push(newUser);
    }
  }
};
</script>
<template>
  <img src="../public/assets/background-image-1.jpg" alt="background-image" class="img">
  <div id="block">
    <div class="app">
      <h1>Users List</h1>


      <add-user-form @add-user="addUser" />

      <user-list :users="users" />
    </div>
  </div>
</template>
<style>
@import url('https://fonts.googleapis.com/css2?family=Alan+Sans:wght@300..900&display=swap');
*{
    font-family: "Alan Sans", sans-serif;
    overflow: hidden;

}
#block{
  display: flex;
  justify-content: center;
  height: 100vh;

}
.img{
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -50000;
  pointer-events: none;

}
h1{
  font-size: 50px;
  color: blueviolet;
  margin-left: 10px;
  margin-right: 10px;
  display: flex;
  justify-content: center;
}
.app{
  border: 1px solid black;
  height: 100%;
  width: 50%;
  background-color: grey;
  opacity:99%;
}
</style>
