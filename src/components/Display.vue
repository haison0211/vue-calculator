<script>
export default {
  props: { entries: String, isError: Boolean },
};
</script>
<template>
  <div class="display-part" :class="{ errMsg: isError }">
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
  letter-spacing: 5px;
}

.errMsg {
color: #ff0000;
  font-size: 1.5rem;
  font-weight: 400;
  text-shadow: 2px 2px white;
  text-align: center;
}
</style>