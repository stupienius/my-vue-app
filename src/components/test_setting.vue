<script setup>
import { ref } from 'vue'
import Switch from './switch.vue'

const props = defineProps(['switchStates'])
const showSetting = ref(false)

const showPopup = () => {
    showSetting.value = !showSetting.value
}

const emit = defineEmits(['setStatus'])

const setTestStatus = (component, which) => {
    emit('setStatus', { which: which, component: component });
}

</script>

<template>
    <div class='container'>
        <img @click="showPopup" src="../assets/setting.svg" alt="setting button">
        <div v-if="showSetting" class="popup">
            <Switch @switch="setTestStatus($event, 0)" :checked="switchStates[0]" control="head" />
            <Switch @switch="setTestStatus($event, 1)" :checked="switchStates[1]" control="tail" />
            <Switch @switch="setTestStatus($event, 2)" :checked="switchStates[2]" control="chinese" />
            <Switch @switch="setTestStatus($event, 3)" :checked="switchStates[3]" control="part of speech" />
            <Switch @switch="setTestStatus($event, 4)" :checked="switchStates[4]" control="sentance" />
            <Switch @switch="setTestStatus($event, 5)" :checked="switchStates[5]" control="lenght" />
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