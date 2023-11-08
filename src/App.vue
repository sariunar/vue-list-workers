<template>
    <div class="app">
        <h1>Сотрудники</h1>
        <button class="button" @click="showModal" >Добавить сотрудника</button>

        <modal-window v-model:show="modalVisible">
            <form-workers @create="createWorker" />
        </modal-window>
        <list-worker v-bind:workers="workers" @remove="removeWorker" />        
    </div>
</template>

<script>
import FormWorkers from './components/FormWorkers.vue';
import ListWorker from './components/ListWorker.vue';
import ModalWindow from './components/ModalWindow.vue';
export default {
	components: { FormWorkers, ListWorker, ModalWindow },
    data() {
        return {
            workers: [
                {id: 1, name: 'Иван', lastname: 'Иванов', experience: '2', age: '26', address: 'Московская Область, Мытищинский Район, Мытищи Город, Ульяновская Улица, Дом 3'},
                {id: 2, name: 'Светлана', lastname: 'Иванов', experience: '8', age: '35', address: 'Московская Область, Мытищинский Район, Мытищи Город, Ульяновская Улица, Дом 3'},
                {id: 3, name: 'Максим', lastname: 'Иванов', experience: '3', age: '27', address: 'Московская Область, Мытищинский Район, Мытищи Город, Ульяновская Улица, Дом 3'},
            ],
            modalVisible: false,
        }
    },
    methods: {
        createWorker(worker) {
            this.workers.push(worker);
            this.modalVisible = false;
        },
        removeWorker(worker) {
            this.workers = this.workers.filter(p => p.id !== worker.id);
        },
        showModal() {
            this.modalVisible = true;
        },
    }
};
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .app{
        margin: 20px;
    }
    .button{
        background-color: #BC9CFF;
        color: aliceblue;
        border: none;
        padding: 10px 15px;
        cursor: pointer;
        margin-right: 15px;
        margin: 15px 0;
    }
</style>
