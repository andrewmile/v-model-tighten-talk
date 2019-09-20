<template>
  <input v-model="name" @input="$emit('input', titleCase)">
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
  data() {
    return {
      name: this.value,
    };
  },
  computed: {
    titleCase() {
      if (! this.name.length) {
        return '';
      }

      return `${this.name[0].toUpperCase()}${this.name.slice(1)}`;
    },
  },
  watch: {
    value(newValue) {
      this.name = newValue;
    },
  },
}
</script>
