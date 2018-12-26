<template>
  <div class="MediaObject">
    <slot name="image"/>
    <slot/>
  </div>
</template>

<script>
export default {
  name: `MediaObject`,
};
</script>
