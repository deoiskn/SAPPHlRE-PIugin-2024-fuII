<script>
export default {
  props: {
    type: {
      type: String,
      default: 'text',
      validator: (value) => ['text', 'password', 'email'].includes(value),
    },
    modelValue: {
      type: String,
      default: '',
    },
  },
  emits: ['update:modelValue'],
};
</script>

<template>
  <input
    class="input"
    :type="type"
    :value="modelValue"
    @input="($event) => $emit('update:modelValue', $event.target.value)"
  />
</template>

<style>
.input {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 0.25rem;
}
</style>
