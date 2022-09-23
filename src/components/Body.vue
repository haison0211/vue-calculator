<script>
import Display from './Display.vue';
import ButtonWrapper from './ButtonWrapper.vue';
export default {
    components: { Display, ButtonWrapper },

    data() {
        return {
            entries: "",
            isPositive: true,
            ans: "0",
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
                this.ans++
                this.entries = this.ans.toString()

            }
            if (ops == "M-") {
                this.ans--
                this.entries = this.ans.toString()
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
            for (let i = 0; i < s.length; i++) {
                if (s[i] == "^") {
                    s = s.split("");

                    s[i] = "**";

                    s = s.join("");
                }

                // if (s[i] == "√") {
                //     s = s.split("");

                //     let next = s[i + 1]
                //    let newVal = Math.sqrt(parseFloat(next));
                //     s.splice(s[i], 2, "*", newVal)

                //     s = s.join("");
                // }
            }

            console.log(s)

            s = eval(s)
            this.ans = s.toString()
            this.entries = s.toString()
        },

        // entriesLength(str) {
        //     if (str.length > 10) {
        //         str = str.substring(0, 10);
        //     }
        //     this.entries = str
        //     return this.entries
        // }
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
    width: 350px;
    height: 500px;
    margin-left: auto;
    margin-right: auto;
    color: #fff;
    background-color: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 15px;
    backdrop-filter: blur(10px);
}
</style>