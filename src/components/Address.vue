<template>
  <div>
    <input
      v-model="address.street"
      @input="$emit('input', address)"
      placeholder="Street"
      class="border center py-2 px-4 m-10 mt-0 w-3/4"
    >
    <input
      v-model="address.city"
      placeholder="City"
      @input="$emit('input', address)"
      class="border center py-2 px-4 m-10 mt-0 w-3/4"
    >
    <input
      v-model="address.state"
      placeholder="State"
      @input="$emit('input', address)"
      class="border center py-2 px-4 m-10 mt-0 w-3/4"
    >
    <input
      v-model="address.zip"
      placeholder="Zip"
      @input="$emit('input', address)"
      class="border center py-2 px-4 m-10 mt-0 w-3/4"
    >
  </div>
</template>

<script>
export default {
  name: 'Address',
  props: {
    value: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      address: this.value,
    };
  },
  watch: {
    value(newValue) {
      this.name = newValue;
    },
  },
}
</script>

<style scoped>
  input {
    margin: 5px;
  }
</style>
