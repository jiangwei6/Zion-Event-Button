
<script setup lang="ts">
const props = defineProps<{
  globalData: Record<string, any>;
  setGlobalData: (newValue: any) => void;
  public_id: string;
  event_str: string;
  btn_str: string
}>();
function evalFunc() {
  window.dispatchEvent(new CustomEvent (props.event_str, {
    detail: { publicId: props.public_id }
  }));
}
</script>

<template>
  <button @click="evalFunc">
    {{props.btn_str}}
  </button>
</template>

<style>
.container {
  background: khaki;
}
</style>
