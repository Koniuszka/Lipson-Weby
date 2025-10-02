<script>
export default {
  name: "AddUserForm",
  data() {
    return {
      name: "",
      surname: "",
      age: "",
      email: ""
    }
  },
  methods: {
    sendUser() {
      this.$emit("add-user", {
        name: this.name,
        surname: this.surname,
        age: this.age,
        email: this.email
      })
      this.name = ""
      this.surname = ""
      this.age = ""
      this.email = ""
    }
  }
}
</script>
<template>
  <form @submit.prevent="sendUser">
    <h2>Add User Form</h2>
    <input v-model="name" placeholder="Name">
    <input v-model="surname" placeholder="Surname">
    <input v-model="age" type="number" placeholder="Age">
    <input v-model="email" type="email" placeholder="Email">
    <button type="submit">Add</button>
  </form>
</template>
