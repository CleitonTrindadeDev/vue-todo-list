<template>
  <!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title></title>
</head>
<body class="bg-gray-800">
    <!-- Content -->
    <div class="px-3 py-10 md:px-10">
        <div class="w-full sm:w-1/2 lg:w-1/3 mx-auto">
        <pre>
        
        </pre>

          <TodoSpinner v-if="loading"/>

          <template v-else>

           <TodoFormAdd/>

           <TodoItens
           v-if="$store.state.todos.length"
           />

           <TodoEmpty v-else/>

          </template>
         
        </div>
    </div>
    <!--/ Content -->

</body>
</html>
</template>

<script>
import TodoSpinner from './components/TodoSpinner.vue';
import TodoFormAdd from './components/TodoFormAdd.vue';
import TodoItens from './components/TodoItens.vue';
import TodoEmpty from './components/TodoEmpty.vue';



export default {
  name: 'App',
  components: {TodoSpinner, TodoFormAdd, TodoItens, TodoEmpty},

  data(){
    return{
      loading:false
    }
  },
  created(){
    //ajax 
    this.loading = true
    this.$store.dispatch('getTodos').then(() => {//aqui joga para o vuex
      this.loading = false
    })
  }


}
</script>

<style>

</style>
