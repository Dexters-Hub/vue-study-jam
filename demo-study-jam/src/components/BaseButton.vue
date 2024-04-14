<script>
export default {
  name: 'BaseButton',
  props: {
    left: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<template>
  <button>
    <slot v-if="left"> Left Button </slot>
    <slot v-else>Cancel</slot>
  </button>
</template>
