<template>
  <v-container class="d-flex justify-center">
    <v-card width="600px" height="620px" class="mt-5">
      <v-btn icon large @click="backPage">
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-card-title class="d-flex justify-center text-h3 font-weight-bold"
        >Sign up</v-card-title
      >
      <v-card-text class="mt-10">
        <v-row justify="center">
          <v-col cols="8">
            <v-text-field label="Username" outlined></v-text-field>
          </v-col>
          <v-col cols="8">
            <v-text-field label="Password" outlined></v-text-field>
          </v-col>
          <v-col cols="8">
            <v-text-field label="Confirm password" outlined></v-text-field>
          </v-col>
          <v-col cols="8">
            <v-btn block color="#0091EA" class="white--text">註冊</v-btn>
          </v-col>
        </v-row>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
export default {

  methods:{
    backPage(){
      this.$router.go(-1)
    }
  }
};
</script>

<style scoped>
* {
  font-family: "微軟正黑體";
}
a {
  text-decoration: none;
}
</style>