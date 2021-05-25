<template>
  <div>
    <Navigator />
    <Drawer />
    <TodoList />
  </div>
</template>

<script>
import Drawer from "@/components/Drawer";
import Navigator from "@/components/Navigator";
import TodoList from "@/components/TodoList";

export default {
  components: {
    Drawer,
    Navigator,
    TodoList,
  },
};
</script>

<style>
</style>