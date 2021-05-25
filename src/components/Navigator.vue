<template>
  <v-app-bar app clipped-left color="#0091EA">
    <v-app-bar-title class="white--text"> To Do List </v-app-bar-title>
    <v-spacer></v-spacer>
    <v-btn color="#FFFFFF" outlined :to="{ name: 'register' }">註冊</v-btn>
    <v-btn
      color="#FFFFFF"
      class="ml-3 light-blue--text text--accent-4"
      :to="{ name: 'login' }"
      >登入</v-btn
    >
  </v-app-bar>
</template>

<script>
export default {};
</script>

<style scoped>
.v-btn {
  font-family: "微軟正黑體";
}
</style>
