<script>
import Button from "./Button.vue";
let id = 0;
export default {
  components: { Button },
  data() {
    return {
      calKeys: [
        { id: id++, text: "C", title: "Clear", width: 1 },
        { id: id++, text: "M+", title: "Memory plus", width: 1 },
        { id: id++, text: "M-", title: "Memory minus", width: 1 },
        { id: id++, text: "ANS", title: "Recall Answer", width: 1 },
        { id: id++, text: "DEL", title: "Delete", width: 1 },
        { id: id++, text: "7", title: "Number Seven", width: 1 },
        { id: id++, text: "8", title: "Number Eight", width: 1 },
        { id: id++, text: "9", title: "Number Nine", width: 1 },
        { id: id++, text: "√", title: "Square root", width: 1 },
        { id: id++, text: "^", title: "Square", width: 1 },
        { id: id++, text: "4", title: "Number Four", width: 1 },
        { id: id++, text: "5", title: "Number Five", width: 1 },
        { id: id++, text: "6", title: "Number Six", width: 1 },
        { id: id++, text: "/", title: "Divide", width: 1 },
        { id: id++, text: "x", title: "Multiply", width: 1 },
        { id: id++, text: "3", title: "Number Three", width: 1 },
        { id: id++, text: "2", title: "Number Two", width: 1 },
        { id: id++, text: "1", title: "Number One", width: 1 },
        { id: id++, text: "+", title: "Add", width: 1 },
        { id: id++, text: "-", title: "Subtract", width: 1 },
        { id: id++, text: ".", title: "Decimal", width: 1 },
        { id: id++, text: "0", title: "Zero", width: 1 },
        { id: id++, text: "+/-", title: "Plus/minus", width: 1 },
        { id: id++, text: "%", title: "Modulus", width: 2 },
        { id: id++, text: "=", title: "Equal to", width: 2 },
      ],
    };
  },
};
</script>

<template>
  <div class="btn-wrapper">
    <Button
      v-for="key in calKeys"
      :key="key.id"
      :text="key.text"
      :title="key.title"
      :width="key.width"
    ></Button>
  </div>
</template>

<style scoped>
.btn-wrapper {
  width: 100%;
  height: 400px;
  background-color: gray;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}
</style>