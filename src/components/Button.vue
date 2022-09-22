<script>
export default {
  props: ["id", "text", "title", "type"],
  emits: ["check-type"]
};
</script>

<template>
  <div class="key-btn">
    <button :title="title" class="cal-key" @click="$emit('check-type')">
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
  width: 55px;
  height: 55px;
  cursor: pointer;
  font-size: 1.1rem;
  border-radius: 5px;
  position: relative;
  display: inline-block;
  background-color: green;
  background-image: linear-gradient(green, lightgreen);
  background-color: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(30px);

}
</style>