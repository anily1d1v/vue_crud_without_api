<template>
  <div>
    <!-- <h4>this a App.vue file</h4> -->
    <TodoList/>
  </div>
</template>
<script>
import TodoList from './components/TodoList.vue';
export default{
  name: "App",
  components:{
    TodoList
  }

};
</script>

<style scoped>
body{
  background-color: red;
}

</style>