<template>
<Header /> 
<div class="container">
    <Balance :total="+total"/> 
    <IncomeExpenses :income="+income" :expenses="+expenses" /> 
    <TransactionList :transactions="transactions" @transactionsDeleted="handelTransactionDeleted" />
    <AddTransaction @transactionsSubmitted="handelTransactionSubmitted" />
</div>
</template>

<script setup>
import Header from './components/Header.vue';
import Balance from './components/Balance.vue';
import IncomeExpenses from './components/IncomeExpenses.vue';
import TransactionList from './components/TransactionList.vue';
import AddTransaction from './components/AddTransaction.vue';
import { ref, computed , onMounted } from 'vue';
import {useToast} from 'vue-toastification';

const toast = useToast();

onMounted(() =>{
    const savedTransactions = JSON.parse(localStorage.getItem('transactions'));

    if(savedTransactions){
        transactions.value = savedTransactions;
    }
})
const transactions = ref([]);

const total = computed(() =>{
    return transactions.value.reduce((acc ,transactions) =>{
        return acc + transactions.amount;
    }, 0);
});


const income = computed(() =>{
    return transactions.value.
    filter((transaction) => transaction.amount > 0)
    .reduce((acc ,transactions) =>{
        return acc + transactions.amount;
    }, 0).toFixed(2);
    
});

const expenses = computed(() =>{
    return transactions.value.
    filter((transaction) => transaction.amount < 0)
    .reduce((acc ,transactions) =>{
        return acc + transactions.amount;
    }, 0)
    .toFixed(2);
});

//submit Transaction
const handelTransactionSubmitted = (transactionData) => {
transactions.value.push({
    id: generateUniqueId(),
    text: transactionData.text,
    amount: transactionData.amount
});
    saveTransactionsToLocalStorage();   
    toast.success('Transactions added')
};

const generateUniqueId = () =>{
    return Math.floor(Math.random() * 10000);
};


//Delete Transaction
const handelTransactionDeleted = (id) => {
    transactions.value = transactions.value.filter((transactions)=> transactions.id !== id);

    saveTransactionsToLocalStorage(); 
    toast.success('Transaction deleted ');
};

//save to local storage 

const saveTransactionsToLocalStorage = () =>{
    localStorage.setItem('transactions' , JSON.stringify(transactions.value));
}
</script>