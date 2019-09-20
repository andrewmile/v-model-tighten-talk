<template>
  <div id="app" class="container mx-auto mt-20">

    <!-- Normal Input -->
    <div class="border mx-auto w-3/4" v-show="page == 1">
      <h3 class="m-4 ml-10 text-2xl">Normal Input</h3>
      <img src="normal.png" class="ml-10 my-6">
      <div class="flex content-around">
        <input class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="first">
        <input class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="first">
      </div>
    </div>

    <!-- Custom Input -->
    <div class="border mx-auto w-3/4" v-show="page == 2">
      <h3 class="m-4 ml-10 text-2xl">Custom Input</h3>
      <img src="custom.png" class="ml-10 my-6">
      <div class="flex content-around">
        <CustomInput class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="second" />
        <CustomInput class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="second" />
      </div>
    </div>

    <!-- Encapsulate Logic -->
    <div class="border mx-auto w-3/4" v-show="page == 3">
      <h3 class="m-4 ml-10 text-2xl">Encapsulate Logic</h3>
      <img src="caps.png" class="ml-10 my-6">
      <div class="flex content-around">
        <AllCaps class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="third" />
        <AllCaps class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="third" />
      </div>
    </div>

    <!-- Managing Component State -->
    <div class="border mx-auto w-3/4" v-show="page == 4">
      <h3 class="m-4 ml-10 text-2xl">Managing Component State</h3>
      <img src="name.png" class="ml-10 my-6">
      <div class="flex content-around">
        <PersonName class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="name" />
        <PersonName class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="name" />
      </div>
    </div>

    <!-- Composing Multiple Inputs -->
    <div class="border mx-auto w-3/4" v-show="page == 5">
      <h3 class="m-4 ml-10 text-2xl">Composing Multiple Inputs</h3>
      <img src="address.png" class="ml-10 my-6">
      <div class="flex content-around">
        <Address class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="address" />
        <Address class="border center py-2 px-4 m-10 mt-0 w-3/4" v-model="address" />
      </div>
    </div>

    <!-- Buttons -->
    <div class="mx-auto mt-12 w-3/4">
      <button class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded" @click="page = page - 1" :disabled="page == 1">
        Previous
      </button>
      <button class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded ml-8" @click="page = page + 1" :disabled="page == 5">
        Next
      </button>
    </div>
  </div>
</template>

<script>
import CustomInput from './components/CustomInput.vue';
import AllCaps from './components/AllCaps.vue';
import PersonName from './components/PersonName.vue';
import Address from './components/Address.vue';

export default {
  name: 'app',
  data() {
    return {
      page: 1,
      first: '',
      second: '',
      third: '',
      name: '',
      address: {
        street: '',
        city: '',
        state: '',
        zip: '',
      },
    };
  },
  components: {
    CustomInput,
    AllCaps,
    PersonName,
    Address,
  },
}
</script>
