<template>
  <button @click="handleClick()" :style="{ background: color }" class="button">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: {
      type: String,
      default: "green",
    },
  },
  methods: {
    handleClick() {
      console.log("Clicked");
    },
  },
};
</script>

<style scoped>
.button {
  color: white;
  padding: 8px;
  cursor: pointer;
}
</style>
