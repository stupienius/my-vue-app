<script setup>
defineProps(['control'])
</script>

<template>
    <div class="containe">
        <p>{{ control }}</p>
        <div class="center">
            <label class="switch">
                <input type="checkbox">
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
    width: 60px;
    height: 28px;
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
    height: 21px;
    width: 21px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    transition: .4s;
    border-radius: 50%;
}
input:checked + .slider {
    background-color: #2196F3;
}
input:checked + .slider:before {
    transform: translateX(26px);
}

</style>