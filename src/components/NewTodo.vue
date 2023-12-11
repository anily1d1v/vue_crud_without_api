<template>
    <form @submit.prevent="addTodo()" class="col-6 col-lg-6 mb-1">
        <input placeholder="Enter New Todo" v-model="newTodo" type="text" class="form-control">
    </form>

</template>
<script>
export default{
    data(){
        return{
            newTodo:""
        }
    },

    methods:{
         addTodo(){
            if(this.newTodo.length > 1){
                this.$emit("on-addtodo", this.newTodo);
            }
            this.newTodo = "";
         }
    }
}

</script>

