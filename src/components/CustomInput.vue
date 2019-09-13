<template>
  <input :value="value" @input="(event) => $emit('input', event.target.value)">
</template>

<script>
export default {
  name: 'CustomInput',
  props: {
    value: String,
    required: true,
  },
}
</script>
