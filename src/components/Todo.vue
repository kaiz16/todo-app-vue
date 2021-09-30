<template>
  <div style="margin: 10px;">
    <span>Todo {{ todo }}</span>
    <button v-on:click="$emit('complete')">Complete</button>
    <button v-on:click="$emit('delete')">X</button>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: String,
      required: true,
    },
  },
};
</script>

<style></style>
