<script>
import Display from './Display.vue';
import ButtonWrapper from './ButtonWrapper.vue';
export default {
    components: { Display, ButtonWrapper },

    data() {
        return {
            entries: "",
            isPositive: true,
            ans: "ans",
            mAns: "",
            result: 0
        }
    },

    methods: {
        addNum(inp) {
            this.entries += inp
        },

        addOps(op) {
            let ops = ["+", "-", "/", "*", "%", "√", "^"]
            if (this.entries != "") {
                if (ops.includes(this.entries.charAt(this.entries.length - 1))) {
                    this.replaceChar(op, this.entries.length - 1)
                } else {
                    this.entries += op
                }
            } else {
                this.entries = ""
            }
        },

        operations(ops) {
            if (ops == "C") {
                this.entries = ""
            }
            if (ops == "DEL") {
                this.replaceChar("", this.entries.length - 1)

            }
            if (ops == "ANS") {
                this.entries = this.ans
            }
            if (ops == "=") {
                this.calculate(this.entries)
            }
            if (ops == "M+") {
                this.entriesm = this.ans * 2

            }
            if (ops == "M-") {
                this.entries = ops
            }
        },

        addSign(sign) {
            if (sign == ".") {
                if (!this.entries.includes(sign)) {
                    this.entries += sign
                } else {
                    this.entries
                }
            }

            if (sign == "+/-") {
                if (this.isPositive) {
                    this.entries = this.entries.slice(0, 0) + "-" + this.entries.slice(0);
                    this.isPositive = false
                } else {
                    this.entries.replace("", 0)
                    this.isPositive = true
                }

            }
        },

        replaceChar(newChar, index) {
            this.entries = this.entries.split("");

            this.entries[index] = newChar;

            this.entries = this.entries.join("");

            return this.entries;
        },

        calculate(s) {
            this.result = 0,
                s = s.match(/[+\-]*(\.\d+|\d+(\.\d+)?)/g) || [];

            while (s.length) {
                this.result += parseFloat(s.shift());
            }

            this.entries = this.result.toString()
            return this.entries;
        }
    },

    // mounted() {
    //     this.entries.toString()
    // }
}
</script>

<template>
    <section class="cal-body">
        <Display :entries="entries"></Display>
        <ButtonWrapper @add-num="addNum" @add-ops="addOps" @add-sign="addSign" @add-cal="operations"></ButtonWrapper>
    </section>
</template>

<style scoped>
.cal-body {
    border: 2px solid black;
    width: 400px;
    height: 500px;
    margin-left: auto;
    margin-right: auto;
}
</style>