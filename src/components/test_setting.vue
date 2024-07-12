<script setup>
import { ref } from 'vue'
import Switch from './switch.vue'

const showSetting = ref(false)

const showPopup = () => {
    showSetting.value = !showSetting.value
}

const emit = defineEmits(['head','tail','ch','POS','sentance','lenght'])

const setTestStatus = () => {
    emit(e);
}

</script>
<template>
    <div class='container'>
        <img @click="showPopup" src="../assets/setting.svg" alt="setting button">
        <div v-if="showSetting" class="popup">
            <Switch control = 'head' />
            <Switch control = 'tail' />
            <Switch control = 'chinese' />
            <Switch control = 'part of speech' />
            <Switch control = 'sentance' />
            <Switch control = 'lenght' />
        </div>
    </div>
</template>
<style scoped>
.container{
    position: absolute;
    right: 0px;
    display: flex;
    flex-direction: row-reverse;
    align-items: flex-start;
    z-index: 5;
}
.popup{
    background-color: gray;
    border-radius: 10px;
}
</style>