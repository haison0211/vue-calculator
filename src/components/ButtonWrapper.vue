<script>
import Button from "./Button.vue";
let id = 0;
export default {
  components: { Button },
  // props: ['entries'],
  emits: ['add-num', 'add-ops', 'add-sign', 'add-cal'],
  data() {
    return {
      calKeys: [
        { id: id++, text: "C", title: "Clear", type: "cal" },
        { id: id++, text: "M+", title: "Memory plus", type: "cal" },
        { id: id++, text: "M-", title: "Memory minus", type: "cal" },
        { id: id++, text: "ANS", title: "Recall Answer", type: "cal" },
        { id: id++, text: "DEL", title: "Delete", type: "cal" },
        { id: id++, text: 7, title: "Number Seven", type: "num" },
        { id: id++, text: 8, title: "Number Eight", type: "num" },
        { id: id++, text: 9, title: "Number Nine", type: "num" },
        { id: id++, text: "√", title: "Square root", type: "ops" },
        { id: id++, text: "^", title: "Square", type: "ops" },
        { id: id++, text: 4, title: "Number Four", type: "num" },
        { id: id++, text: 5, title: "Number Five", type: "num" },
        { id: id++, text: 6, title: "Number Six", type: "num" },
        { id: id++, text: "/", title: "Divide", type: "ops" },
        { id: id++, text: "*", title: "Multiply", type: "ops" },
        { id: id++, text: 3, title: "Number Three", type: "num" },
        { id: id++, text: 2, title: "Number Two", type: "num" },
        { id: id++, text: 1, title: "Number One", type: "num" },
        { id: id++, text: "+", title: "Add", type: "ops" },
        { id: id++, text: "-", title: "Subtract", type: "ops" },
        { id: id++, text: ".", title: "Decimal", type: "sign" },
        { id: id++, text: 0, title: "Zero", type: "num" },
        { id: id++, text: "+/-", title: "Plus/minus", type: "sign" },
        { id: id++, text: "%", title: "Modulus", type: "ops" },
        { id: id++, text: "=", title: "Equal to", type: "cal" },
      ],
      // keyType: this.calKeys.type,
    };
  },

  methods: {
    checkType(type, val) {
      if (type == "num") {
        this.$emit('add-num', val)
      }
      if (type == "ops") {
        this.$emit('add-ops', val)
      }
      if (type == "sign") {
        this.$emit('add-sign', val)
      }
      if (type == "cal") {
        this.$emit('add-cal', val)
      }
    },
  }
};
</script>

<template>
  <div class="btn-wrapper">
    <!-- <div>{{ entries }}</div> -->
    <Button v-for="key in calKeys" :key="key.id" :text="key.text" :title="key.title"
      @check-type="checkType(key.type, key.text)"></Button>
  </div>
</template>

<style scoped>
.btn-wrapper {
  width: 100%;
  height: 400px;
  /*background-color: gray;*/
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-content: space-between;
  flex-wrap: wrap;
  border-top: 1px solid rgba(255,255,255,0.1);
}
</style>