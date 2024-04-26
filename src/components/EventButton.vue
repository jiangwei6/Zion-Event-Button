<script setup lang="ts">
const props = defineProps<{
  globalData: Record<string, any>;
  setGlobalData: (newValue: any) => void;
  public_id: string;
  vara: string;
  varb: string;
  btn_str: string
}>();
function evalFunc() {
  console.log('dispatchEvent');
  // window.dispatchEvent(new CustomEvent (props.event_str, {
  //   detail: { publicId: props.public_id }
  // }));
  window.dispatchEvent(new CustomEvent('automa:execute-workflow', {
	detail: { 
		publicId: props.public_id,
		data: {
			variables: {
				vara: props.vara,
				varb: props.varb
			}
		} 
	}
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
