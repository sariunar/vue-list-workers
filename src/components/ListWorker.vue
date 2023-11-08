<template>
    <h2>Список сотрудников</h2>
    <div class="worker" v-for="worker in workers" :key="worker.id" @remove="$emit('remove', worker)">
        <div><strong>Имя: </strong>{{worker.name}}</div>
        <div><strong>Фамилия: </strong>{{worker.lastname}}</div>
        <div><strong>Стаж: </strong>{{worker.experience}}</div>
        <div><strong>Возраст: </strong>{{worker.age}}</div>
        <div><strong>Адрес: </strong>{{worker.address}}</div>
        <button @click="$emit('remove', worker)" class="button">Удалить</button>
    </div>
</template>
<script>
export default {
    props: {
        workers: {
            type: Array,
            required: true,
        }
    }    
}
</script>
<style scoped>
    .worker{
        padding: 15px;
        border: 2px solid #BC9CFF;
        margin: 15px 0;
    }
    .button{
        background-color: #BC9CFF;
        color: aliceblue;
        border: none;
        padding: 10px 15px;
        cursor: pointer;
        margin-right: 15px;
        margin-top: 15px;
    }
    h2{
        margin-top: 20px;
    }
</style>