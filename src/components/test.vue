<script setup>
import { ref, onMounted } from 'vue'
import Setting from './test_setting.vue'

const testStatus = ref([true, true, true, true, true, true])
const wordList = ref([])

function  storeSetting(){
    localStorage.setItem('testSetting', JSON.stringify(testStatus.value))
}

function loadlibrary(){
    const library = localStorage.getItem('vocabularyList')
    if(library){
        wordList = JSON.parse(library)
    }
}

function loadSetting(){
    const storedSettings = localStorage.getItem('testSetting')
    if (storedSettings) {
        testStatus.value = JSON.parse(storedSettings)
    }
}

 

function handleStatuses(component){
    testStatus.value[component.which] = component.component
    storeSetting()
}

if (localStorage.getItem('testSetting') === null) {
    storeSetting()
}

onMounted(() => {
    loadSetting()
})
</script>

<template>
    <div class="test">
        <div class="setting">
            <Setting @setStatus="handleStatuses" :switchStates="testStatus" />
        </div>
        <div class="quiz">
            <p v-show="testStatus[2]" class="ch">stupienius</p>
            <p v-show="testStatus[3]" class="pos">(v)</p>
            <p v-show="testStatus[0]" class="head">h</p>
            <input type="text" id="test">
            <p v-show="testStatus[1]" class="tail">r</p>
            <p v-show="testStatus[5]" class="len">5</p>
            <p v-show="testStatus[4]" class="sentence">you are the apple of my eyes</p>
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
.sentence{
    border-radius: 5px;
    grid-row: 4/5;
    grid-column: 1/12;
}
</style>
