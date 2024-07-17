<script setup>
const props = defineProps(['control'])

const emit = defineEmits(['switch'])

const handlechange = (event) => {
    emit('switch',event.target.checked)
    console.log(event.target.checked)
}

</script>


<template>
    <div class="containe">
        <p>{{ control }}</p>
        <div class="center">
            <label class="switch">
                <input @change="handlechange" type="checkbox">
                <span class="slider"></span>
            </label>
        </div>
    </div>
</template>

<style scoped>
.containe{
    height: 50px;
    width: 200px;
    display: flex;
    flex-direction: row;
    gap: 10px;
    padding: 10px;    
}
p{
    display: flex;
    width: 80%;
    text-align: center;
    justify-content: center;
}
.center{
    display: flex;
    align-items: center;
}
.switch {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 25px;
}
.switch input {
    opacity: 0;
    width: 0;
    height: 0;
}
.slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    transition: .4s;
    border-radius: 34px;
}
.slider:before {
    position: absolute;
    content: "";
    height: 17px;
    width: 17px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    transition: .4s;
    border-radius: 50%;
}
input:checked + .slider {
    background-color: #a09e17;
}
input:checked + .slider:before {
    transform: translateX(26px);
}

</style>