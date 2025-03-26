<template>
  <div class="divider-parent flex">
    <div class="divider"></div>
    <span class="main-title">{{ this.text }}</span>
    <div class="divider-r"></div>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>
<style lang="css">
@import "@/components/7.Divider/TheDivider.css";
</style>
