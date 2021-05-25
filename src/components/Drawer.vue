<template>
  <v-navigation-drawer app permanent :mini-variant.sync="mini" clipped>
    <v-btn icon class="mt-2 mb-2" large @click="mini = !mini">
      <v-icon v-if="mini">mdi-chevron-right</v-icon>
      <v-icon v-else>mdi-chevron-left</v-icon>
    </v-btn>
    <!-- list item -->
    <v-list>
      <v-list-item-group>
        <v-list-item v-for="item in items" :key="item.title">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
export default {
  data() {
    return {
      items: [{ title: "我的一天", icon: "mdi-weather-sunny" }],
      mini: false,
    };
  },
};
</script>

<style scoped>
.v-list-item__title {
  font-family: "微軟正黑體";
  font-weight: bold;
  font-size: 16px;
}
</style>