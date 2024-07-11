<script setup>
</script>
<template>
    <div>
        <label for="w">Vocabulary</label>
        <input id="w" type="text" placeholder="necessary" required>
    
        <label for="ch">Chinese</label>
        <input id="ch" type="text" placeholder="Ignorable">
    
        <label for="eg">Example Sentences</label>
        <textarea id="eg" placeholder="Ignorable" cols="30" rows="8"></textarea>
    
        <button id="sub">Submit</button>
    </div>
  </template>
<style scoped>
    div{
        display: flex;
        flex-direction: column;
        padding: 2em;
    }
</style>