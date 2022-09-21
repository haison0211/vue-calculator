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
            mAns:""
        }
    },

    methods: {
        addNum(inp) {
            this.entries += inp
        },

        addOps(op) {
            let ops = ["+", "-", "/", "*", "%", "√", "^"]
            // this.entries += op
            if (this.entries != "") {
                if (ops.includes(this.entries.charAt(this.entries.length - 1)) ) {
                    // this.entries.replace(this.entries.charAt(this.entries.length - 1), op)
                    // this.entries[this.entries.lastIndexOf()] = op
                    console.log(this.entries.charAt(this.entries.length - 1))
                    // this.entries += "op"
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
                this.entries += "d"
            }
            if (ops == "ANS") {
                this.entries = this.ans
            }
            if (ops == "=") {
                this.entries = ops
            }
            if (ops == "M+") {
                this.entriesm = this.ans * 2

            }
            if (ops == "M-") {
                this.entries = ops
            }
        },

        addSign(sign) {
            if(sign == ".") {
                if (!this.entries.includes(sign)) {
                    this.entries += sign
                } else {
                    this.entries
                }
            }

            if (sign == "+/-") {
                if (this.isPositive) {    
                    this.entries += "b"
                    this.isPositive = false
                } else {
                    this.isPositive = true
                    this.entries.replace("b", "")
                }
                
            }
        }
    },

    mounted() {
        this.entries.toString()
    }
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