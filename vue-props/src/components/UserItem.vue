<script>
export default {
  name: "UserItem",
  props: ["user"],
  data() {
    return {
      show: false
    }
  }
}
</script>
<template>
  <div class="NamesPlaceholder">
    <div style="border:1px solid black; margin:5px; padding:5px;">
      <p>{{ user.name }} {{ user.surname }} age {{ user.age }}</p>
      <button @click="show = !show">
        {{ show ? "Hide" : "Show Details" }}
      </button>
      <p v-if="show">Email: {{ user.email }}</p>
    </div>
  </div>
</template>
<style>
</style>
