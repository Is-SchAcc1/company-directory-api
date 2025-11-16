<script setup>
import MainCardSingle from './MainCardSingle.vue';
import useAPI from '@/composables/useApi';

const { employees } = useAPI()

</script>

<template>
<div class="grid grid-cols-4 gap-10 p-5">
    <MainCardSingle v-for="employee in employees" :key="employee._id" :employee="employee"></MainCardSingle>
</div>
</template>