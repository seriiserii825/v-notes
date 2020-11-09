<template>
  <div class="message">
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  props: ['message']
}
</script>

<style scoped lang="scss">
.message {
  font-weight: bold;
  text-align: center;
  color: #c90101;
}
</style>
