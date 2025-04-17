<template>
    <h3>Add new transaction</h3>
    <form id="form" @submit.prevent="onSubmit">
        <div class="form-control">
            <label for="text">Text</label>
            <input type="text" id="text" v-model="text" placeholder="Enter text...">
        </div>
        <div class="form-control">
            <label for="amount">Amount <br />
                (negative - expense, postive -income)
            </label>

            <input type="text" id="amount" v-model="amount" placeholder="Enter amount...">
        </div>
        <button class="btn">Add transaction</button>
    </form>
</template>

<script setup>


import { ref } from 'vue';
import { useToast } from 'vue-toastification';

const text = ref('')
const amount = ref('')
const emit = defineEmits(['transactionsSubmitted']);
const toast = useToast();



const onSubmit = () => {

    if (!text.value || !amount.value) {
        toast.error('Both fields must be filled');
        return;
    }
    

    
    const textPattern = /^[A-Za-z\s]+$/;
    if (!textPattern.test(text.value)) {
        toast.error('Text field must only contain letters');
        return;
    }

    const parsedAmount = parseFloat(amount.value);
    if (isNaN(parsedAmount)) {
        toast.error('Amount must be a number');
        return;
    }

    
    const transactionData = {
        text: text.value.trim(),
        amount: parsedAmount
    };
    emit('transactionsSubmitted', transactionData)

    // console.log(text.value, amount.value)

    text.value = '';
    amount.value = '';

};
</script>