<template>
  <v-container fluid>
    <v-row justify="center">
      <!-- title -->
      <v-col cols="12">
        <h1>我的一天</h1>
        <v-subheader>5月31日，星期六</v-subheader>
      </v-col>
      <v-divider></v-divider>
      <!-- undo -->

      <v-col cols="12">
        <h2>未完成</h2>
        <v-simple-table>
          <thead>
            <tr>
              <td width="140px"></td>
              <td>項目名稱</td>
              <td>時間</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <v-btn icon>
                  <v-icon color="success">mdi-check-circle-outline</v-icon>
                </v-btn>
                <v-btn icon @click="dialog_modify = true">
                  <v-icon color="warning">mdi-pencil-circle-outline</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="error">mdi-close-circle-outline</v-icon>
                </v-btn>
              </td>
              <td>123</td>
              <td>123</td>
            </tr>
          </tbody>
        </v-simple-table>
      </v-col>
      <!-- done -->
      <v-col cols="12">
        <h2>已完成</h2>
        <v-simple-table>
          <thead>
            <tr>
              <td width="140px"></td>
              <td>項目名稱</td>
              <td>時間</td>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <v-btn icon>
                  <v-icon color="warning">mdi-pencil-circle-outline</v-icon>
                </v-btn>
                <v-btn icon>
                  <v-icon color="error">mdi-close-circle-outline</v-icon>
                </v-btn>
              </td>
              <td>123</td>
              <td>123</td>
            </tr>
          </tbody>
        </v-simple-table>
      </v-col>
      <!-- user input -->
      <v-footer class="pa-0" color="rgba(0,0,0,0.7)">
        <v-col cols="10" class="pa-0">
          <v-text-field
            dark
            hide-details
            background-color="transparent"
            outlined
            prepend-inner-icon="mdi-plus-circle-outline"
          ></v-text-field>
        </v-col>
        <v-col cols="2" class="white--text">
          <v-btn icon @click="date_picker_input = true">
            <v-icon color="white">mdi-calendar</v-icon>
          </v-btn>
          {{ selected_month_input }}
        </v-col>
      </v-footer>
    </v-row>

    <!-- input date -->
    <v-dialog v-model="date_picker_input" width="300px">
      <v-date-picker v-model="selected_month_input"></v-date-picker>
    </v-dialog>
    <!-- modify item -->
    <v-dialog v-model="dialog_modify" width="600px">
      <v-card>
        <v-card-title class="font-weight-bold white--text"
          >修改項目</v-card-title
        >
        <v-card-text class="mt-6">
          <v-text-field outlined></v-text-field>
          <v-date-picker v-model="selected_month_modify"></v-date-picker>
          <div class="d-inline-block">
            <span class="black--text font-weight-bold text-h4 ml-6">{{
              selected_month_modify
            }}</span>
          </div>
        </v-card-text>
        <v-card-actions>
          <v-btn color="#0091ea" class="white--text">修改 </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      date_picker_input: false, //使用者新增時
      selected_month_input: undefined, //使用者新增時
      selected_month_modify: undefined, //使用者修改時
      dialog_modify: false,
    };
  },
};
</script>

<style scoped>
* {
  font-family: "微軟正黑體";
}
.v-footer {
  position: absolute;
  bottom: 25px;
  width: 95%;
}
.v-card__title {
  background-color: #0091ea;
}
</style>