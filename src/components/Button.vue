<template>
  <button @click="OnClick()" :style="{ background: color }" class="btn">
    {{ title }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    title: String,
    color: String,
  },
  methods: {
    OnClick() {
      this.$emit("btn-click");
    },
  },
};
</script>