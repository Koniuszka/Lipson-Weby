<script>
import UserItem from "./UserItem.vue"

export default {
  name: "UserList",
  props: ["users"],
  components: { UserItem }
}
</script>
<template>
  <div class="user-list">
    <h2>Użytkownicy:</h2>
    <div class="scroll-box">
      <user-item v-for="u in users" :key="u.id" :user="u"></user-item>
    </div>
  </div>
</template>
<style>
h2{
  display: flex;
  justify-content: center;
}
.user-list {
  width: 750px;
}

.scroll-box {
  max-height: 300px;
  overflow-y: auto;
  border: 1px solid #ccc;
  padding: 5px;

}
::-webkit-scrollbar{
  display: none;
}
</style>
