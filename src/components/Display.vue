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
  border: 1px solid red;
  height: 100px;
  text-align: right;
  padding: 40px 15px 15px;
  /*font-size: 1.5rem;
  font-weight: 500;*/
}
</style>