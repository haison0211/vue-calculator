<script>
export default {
  props: {entries: String},
};
</script>
<template>
  <div class="display-part">
    {{ entries }}
  </div>
</template>

<style scoped>
.display-part {
  width: 100%;
  height: 100px;
  text-align: right;
  padding: 30px 15px 15px;
  font-size: 2rem;
  font-weight: 500;
  letter-spacing: 7px;
}
</style>