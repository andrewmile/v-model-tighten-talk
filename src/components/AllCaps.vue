<template>
  <input :value="value" @input="upperCase">
</template>

<script>
export default {
  name: 'AllCaps',
  props: {
    value: String,
    required: true,
  },
  methods: {
    upperCase(e) {
      this.$emit('input', e.target.value.toUpperCase());
    },
  },
}
</script>
