<script setup>
import CardDetails from '@/views/CardDetails.vue';
import { faker } from '@faker-js/faker';

// const firstname = faker.person.firstName()
// const lastname = faker.person.lastName()
// const fullname = faker.person.fullName({firstName: firstname, lastName: lastname})
// const job_title = faker.person.jobTitle()
// const bio = faker.lorem.lines(2)
// const username = faker.internet.username({firstName: firstname, lastName: lastname}).toLowerCase()
const props = defineProps({
  employee: {
    type: Object,
    required: true,
    default: () => {
      return {
        _id: "dfnai35noas56",
        userName: "jperez",
        fistName: "Joseph",
        lastName: "Perez",
        title: "Computer Science Wizard",
        quote: "You shall not pass!",
        __v: 0,
        
      }
    },
    },
})
</script>

<template>
    <!-- {{ fullname }} <br /> -->
    <RouterLink :to="{ name: 'CardDetails', params: {id: props.employee._id}}">
      <div class="border border-grey-400 rounded-lg shadow bg-gray-200 h-full">
        <img class="object-fill h-480 w-960 rounded-t-xl" v-bind:src="faker.image.urlLoremFlickr({category: 'cats', height: 480, width: 960}) "  />
        <div class="p-4">
              <p class="mb-2 text-2xl font-bold">{{ props.employee.firstName }}{{ props.employee.lastName }}</p> 
              <p class="mb-3 font-normal text-gray-700">{{ props.employee.title}}</p>
              <p class="mb-3 font-normal text-gray-700">{{ props.employee.quote }}</p>
        </div>
    </div>
    </RouterLink>
</template>