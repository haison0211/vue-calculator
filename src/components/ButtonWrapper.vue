<script>
import Button from "./Button.vue";
let id = 0;
export default {
  components: { Button },
  emits: ['add-num', 'add-ops', 'add-sign', 'add-cal'],
  data() {
    return {
      calKeys: [
        { id: id++, text: "C", title: "Clear", type: "cal", bg: "clear" },
        { id: id++, text: "M+", title: "Memory plus", type: "cal", bg: "ops" },
        { id: id++, text: "M-", title: "Memory minus", type: "cal", bg: "ops" },
        { id: id++, text: "ANS", title: "Recall Answer", type: "cal", bg: "ops" },
        { id: id++, text: "DEL", title: "Delete", type: "cal", bg: "del" },
        { id: id++, text: 7, title: "Number Seven", type: "num", bg: "reg" },
        { id: id++, text: 8, title: "Number Eight", type: "num", bg: "reg" },
        { id: id++, text: 9, title: "Number Nine", type: "num", bg: "reg" },
        { id: id++, text: "√", title: "Square root", type: "ops", bg: "ops" },
        { id: id++, text: "^", title: "Square", type: "ops", bg: "ops" },
        { id: id++, text: 4, title: "Number Four", type: "num", bg: "reg" },
        { id: id++, text: 5, title: "Number Five", type: "num", bg: "reg" },
        { id: id++, text: 6, title: "Number Six", type: "num", bg: "reg" },
        { id: id++, text: "/", title: "Divide", type: "ops", bg: "ops" },
        { id: id++, text: "*", title: "Multiply", type: "ops", bg: "ops" },
        { id: id++, text: 3, title: "Number Three", type: "num", bg: "reg" },
        { id: id++, text: 2, title: "Number Two", type: "num", bg: "reg" },
        { id: id++, text: 1, title: "Number One", type: "num", bg: "reg" },
        { id: id++, text: "+", title: "Add", type: "ops", bg: "ops" },
        { id: id++, text: "-", title: "Subtract", type: "ops", bg: "ops" },
        { id: id++, text: 0, title: "Zero", type: "num", bg: "reg" },
        { id: id++, text: ".", title: "Decimal", type: "sign", bg: "reg" },
        { id: id++, text: "00", title: "Double Zero", type: "num", bg: "reg" },
        { id: id++, text: "%", title: "Modulus", type: "ops", bg: "ops" },
        { id: id++, text: "=", title: "Equal to", type: "cal", bg: "ops" },
      ],
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
    <Button v-for="key in calKeys" :key="key.id" :text="key.text" :class="key.bg" :title="key.title"
      @check-type="checkType(key.type, key.text)"></Button>
  </div>
</template>

<style scoped>
.btn-wrapper {
  width: 100%;
  height: 400px;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-content: space-between;
  flex-wrap: wrap;
  border-top: 1px solid rgba(255,255,255,0.1);
}

.clear {
  background-color: red;
  background-image: linear-gradient(red, lightcoral);
}

.ops {
  background-color: darkcyan;
  background-image: linear-gradient(darkcyan, cyan);
}

.reg {
  background-color: green;
  background-image: linear-gradient(green, lightgreen);
}
.del {
  background-color: orange;
  background-image: linear-gradient(orange, rgb(241, 210, 131));
}
</style>