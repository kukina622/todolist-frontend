<template>
  <v-container class="d-flex justify-center">
    <v-card width="600px" height="620px" class="mt-5">
      <v-btn icon large @click="backPage">
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-card-title class="d-flex justify-center text-h3 font-weight-bold"
        >Sign in</v-card-title
      >
      <v-card-text class="mt-10">
        <validation-observer ref="observer">
          <form>
            <v-row justify="center">
              <v-col cols="8">
                <validation-provider v-slot="{ errors }" rules="required">
                  <v-text-field
                    label="Username"
                    outlined
                    v-model="username"
                    :error-messages="errors"
                  ></v-text-field>
                </validation-provider>
              </v-col>
              <v-col cols="8">
                <validation-provider v-slot="{ errors }" rules="required">
                  <v-text-field
                    label="Password"
                    outlined
                    v-model="password"
                    :error-messages="errors"
                  ></v-text-field>
                </validation-provider>
              </v-col>
              <v-col cols="8">
                <v-btn block color="#0091EA" class="white--text" @click="submit"
                  >登入</v-btn
                >
              </v-col>
              <v-col cols="8">
                <h4>還沒有帳號嗎？</h4>
                <router-link :to="{ name: 'register' }">點此註冊</router-link>
              </v-col>
            </v-row>
          </form>
        </validation-observer>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>
import { extend, ValidationObserver, ValidationProvider } from "vee-validate";
import { required } from "vee-validate/dist/rules";

extend("required", {
  ...required,
  message: "Required!",
});

export default {
  components: {
    ValidationObserver,
    ValidationProvider,
  },
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    backPage() {
      this.$router.go(-1);
    },
    submit() {
      this.$refs.observer.validate().then((validated) => {
        if (validated) {
          console.log(true);
        }
      });
    },
  },
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