<template>
  <input :value="value" @input="upperCase">
</template>

<script>
export default {
  name: 'AllCaps',
  props: {
    value: {
      type: String,
      required: true,
    },
  },
  methods: {
    upperCase(e) {
      this.$emit('input', e.target.value.toUpperCase());
    },
  },
}
</script>
