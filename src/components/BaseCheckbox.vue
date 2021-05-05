<template>
  <input
    type="checkbox"
    :checked="modelValue"
    class="field"
    @change="$emit('update:modelValue', $event.target.checked)"
    :id="uuid"
  />
  <label :v-for="uuid" v-if="label">{{ label }}</label>
</template>
<script>
import UniqueID from "../features/UniqueID";
export default {
  props: {
    label: {
      type: String,
      default: "",
    },
    modelvalue: {
      type: Boolean,
      default: false,
    },
  },
  setup() {
    const uuid = UniqueID().getID();
    return {
      uuid,
    };
  },
};
</script>
