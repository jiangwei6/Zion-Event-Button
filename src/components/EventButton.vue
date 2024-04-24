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
  <div @click="evalFunc" class="event-button">
    {{props.btn_str}}
  </div>
</template>

<style>
.event-button {
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  height: 100%;
}
</style>
