<template>
    
        <ul>
            <li v-for="(tarea,index) in tareas" :key="index">
                {{tareas[index]}}
                <button @click="deleteItem(index)">Eliminar</button>
            </li>
        </ul>
</template>

<script>
export default ({
    name: "ItemsCopia",
    props: {
        tareas: Array
    },
    methods: {
        deleteItem(index){
            this.$emit('deleteItem', index)
        }
    }
})
</script>

<style>
button{
    margin-left: 20px;
}
</style>