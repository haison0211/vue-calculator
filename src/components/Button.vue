<script>
export default {
  props: ["id", "text", "title", "width"],
};
</script>

<template>
  <div class="key-btn">
    <button :title="title" :width="width" class="cal-key">
      {{ text }}
    </button>
  </div>
</template>

<style scoped>
.key-btn {
  width: fit-content;
}

.cal-key {
  padding: 10px;
  width: 70px;
  height: 70px;
  cursor: pointer;
  background-color: rgb(194, 192, 192);
  border: none;
  font-size: 1.5rem;
  border-radius: 5px;
}
</style>