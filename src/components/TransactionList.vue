<template>
    <h3>History</h3>
    <ul id="list" class="list">
        <li v-for="transaction in transactions" :key="transactions.id"
            :class="transaction.amount < 0 ? 'minus' : 'plus'">

            {{ transaction.text }} <span>{{ transaction.amount }}</span>
            <button @click="deleteTransaction(transaction.id)" class="delete-btn">x</button>

        </li>
    </ul>
</template>

<script setup>

import { defineProps} from 'vue';
const emit = defineEmits(['transactionsDeleted']);

const props = defineProps({
    transactions: {
        type:Array,
        required: true,
    }
    
});

const deleteTransaction = (id) =>{
emit('transactionsDeleted', id);
};
</script>