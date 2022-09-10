<script>
import Display from './Display.vue';
import ButtonWrapper from './ButtonWrapper.vue';
export default {
    components: { Display, ButtonWrapper }
}
</script>

<template>
    <section class="cal-body">
        <Display></Display>
        <ButtonWrapper></ButtonWrapper>
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