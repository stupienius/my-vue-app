<script setup>
import { ref } from 'vue'
import Setting from './test_setting.vue'

const testStatus = ref([false,false,false,false,false,false])

const handleStatues = (component) => {
    testStatus.value[component.which] = component.component
}

</script>
<template>
    <div class="test">
        <div class="setting">
            <Setting @setStatus="handleStatues" />
        </div>
        <div class="quiz">
            <p v-show="testStatus[0]" class="ch">chinese</p>
            <p class="pos">(v)</p>
            <p class="head">h</p>
            <input type="text" id="test">
            <p class="tail">r</p>
            <p class="len">5</p>
            <p class="sentance">you are the apple of my eyes</p>
        </div>
    </div>
</template>
<style scoped>
.test{
    position: relative;
}
p{
    font-size: larger;
    font-weight: bolder;
    line-height: 30px;
    text-align: center;
}
.quiz{
    position: fixed;
    height: 350px;
    width: 300px;
    display: grid;
    grid-template-rows: 30px 30px 30px auto;
    grid-template-columns: repeat(11,1fr);
    outline: yellow solid 3px;
    border-radius: 5px;
}
.ch{
    grid-row:1/2;
    grid-column:3/8 ;
}
.pos{
    grid-row: 1/2;
    grid-column: 8/10;
}
.head{
    text-align: end;
    grid-row: 2/3;
    grid-column: 1/2;
}
input{
    grid-row: 2/3;
    grid-column: 2/11;
}
.tail{
    text-align: start;
    grid-row: 2/3;
    grid-column: 11/12;
}
.len{
    grid-row: 3/4;
    grid-column: 6/7;
}
.sentance{
    border-radius: 5px;
    grid-row: 4/5;
    grid-column: 1/12;
}
</style>