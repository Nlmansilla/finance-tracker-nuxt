<template>
    <section class="flex items-center justify-between mb-101">
        <h1 class="text-4xl font-extrabold">
            Summary
        </h1>
        <div>
            <USelectMenu v-model="selectedView" :options="transactionViewOptions" />
        </div>
    </section>

    <section class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 sm:gap-16 mb-10">
        <Trend color="green" title="Income" :amount="4000" last-amount="3000" :loading="false" />
        <Trend color="red" title="Expense" :amount="4000" last-amount="5000" :loading="false" />
        <Trend color="green" title="Investments" :amount="4000" last-amount="3000" :loading="false" />
        <Trend color="red" title="Savings" :amount="4000" last-amount="4100" :loading="false" />
    </section>
</template>

<script setup>
import { transactionViewOptions } from '~/constants'

const transactionView = ['Yearly', 'Monthly', 'Daily'];
const selectedView = ref(transactionViewOptions[1])
</script>