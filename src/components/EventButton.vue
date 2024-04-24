<script setup lang="ts">
const props = defineProps<{
  globalData: Record<string, any>;
  setGlobalData: (newValue: any) => void;
  public_id: string;
  event_str: string;
  btn_str: string
}>();
function evalFunc() {
  console.log('dispatchEvent');
  window.dispatchEvent(new CustomEvent (props.event_str, {
    detail: { publicId: props.public_id }
  }));
}
</script>

<template>
  <div @click="evalFunc">
    {{props.btn_str}}
  </div>
</template>

<style>
.container {
  background: khaki;
}
</style>
