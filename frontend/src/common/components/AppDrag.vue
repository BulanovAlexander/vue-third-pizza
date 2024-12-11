<script setup>
import { DATA_TRANSFER_PAYLOAD } from "@/common/constants";

const props = defineProps({
  draggable: {
    type: Boolean,
    required: false,
  },
  dataTransfer: {
    type: Object,
    required: true,
  },
});

function onDragStart({ dataTransfer }) {
  const data = JSON.stringify(props.transferData);
  dataTransfer.setData(DATA_TRANSFER_PAYLOAD, data);
}
</script>

<template>
  <div
    :draggable="draggable"
    @dragstart.self="onDragStart"
    @dragover.prevent
    @dragenter.prevent
  >
    <slot />
  </div>
</template>
