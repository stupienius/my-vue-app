<script setup>
import { ref } from 'vue'
import Switch from './switch.vue'

const showSetting = ref(false)

const toggleSetting = () => {
    showSetting.value = !showSetting.value
}

const emit = defineEmits(['head','tail','ch','POS','sentance','lenght'])

const setTestStatus = () => {
    emit(e);
}

</script>
<template>
    <div class='container'>
        <img @click="toggleSetting" src="../assets/setting.svg" alt="setting button">
        <div class="popup">
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
    display: flex;
    flex-direction: row-reverse;
}
.popup{
    background-color: gray;
    border-radius: 10px;
}
</style>