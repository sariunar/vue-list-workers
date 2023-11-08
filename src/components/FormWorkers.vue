<template>
    <form class="form" @submit.prevent="">
        <h2>Создание поста</h2>
        <input v-model="worker.name" class="input" type="text" placeholder="Имя" />
        <input v-model="worker.lastname" class="input" type="text" placeholder="Фамилия" />
        <input v-model="worker.experience" class="input" type="number" placeholder="Стаж">
        <input v-model="worker.age" class="input" type="number" placeholder="Возраст">
        <input v-model="worker.address" class="input" type="text" placeholder="Адрес">
        <button class="button" @click="createWorker">Добавить</button>
    </form>
</template>
<script>
export default {
    data() {
        return {
            worker: {
                name: '',
                lastname: '',
                experience: '',
                age: '',
                address: '',
            }
        };
    },
    methods: {
        createWorker() {
            this.worker.id = Date.now();
            this.$emit('create', this.worker);
            this.worker = {
                name: '',
                lastname: '',
                experience: '',
                age: '',
                address: '',
            }
        }
    }
}
</script>
<style scoped>
    .form{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 15px;
    }
    .input{
        border: 1px solid #BC9CFF;
        padding: 10px 15px;
        margin: 15px;
        width: 40vw;
    }
    .input:focus{
        outline: none;
    }
    .button{
        background-color: #BC9CFF;
        color: aliceblue;
        border: none;
        padding: 10px 15px;
        cursor: pointer;
    }
</style>