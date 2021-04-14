<template>
    <header>
        <h1>{{title}}</h1> 
        <Button name = 'add task' color= "#07c44f"/>
        <Button name = 'edit task' color= "#3907c4b7"/>
        <Button name = 'delete task' color= "#c40756e0"/>
    </header>
</template>

<script>
import Button from './Button'
export default {
    name: 'Header',
    props: {
        title: String,
    },
    components: {
        Button
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
    
</style>