<template>
   <!-- Todo items -->
            <div class="space-y-2">
                <TodoIten
                v-for="todo in $store.state.todos"
                :key="todo.id"
                :todo="todo"
                />     
            </div>
            <!--/ Todo items -->
</template>

<script>
import TodoIten from './TodoIten.vue'
export default {
    components:{
        TodoIten
    }
}
</script>

<style>

</style>