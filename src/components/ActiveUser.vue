<template>
  <ul>
    <li>
      <h2>UserName:{{ name }}</h2>
      <h3>Age:{{ age }}</h3>
      <button @click="$emit('delete', id)">Delete</button>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    age: {
      type: Number,
      required: true,
    },
  },
  emit: ["delete"],
};
</script>
