<template>
    <div id="navbar" class="container">  
        <div id="title">Elnaz's website</div>
    </div>

    <div id="flex">
       <div id="sidebar" class="container">
           Sidebar
           <div>
               <input type="text" v-model="selector" placeholder="#">
               <input type="text" v-model="color" placeholder="Color">
               <button @click="changeColor">Change Color</button>
           </div>
           
           <div>
               <input type="text" v-model="newText" placeholder="New Text">
               <button @click="updateMainText">Change Text</button>
           </div>
       </div>
       <div id="main" class="container">
           {{ text }}
       </div>
   </div>
</template>

<script setup>
import { ref } from 'vue';

const text = ref('Elnaz'); 
const newText = ref(''); 

const selector = ref('');
const color = ref('');

function updateMainText() {
    text.value = newText.value;
}

function changeColor() {
    const elements = document.querySelectorAll(selector.value);
    elements.forEach(el => {
        el.style.backgroundColor = color.value; 
    });
}
</script>

<style scoped>

</style>


<style scoped>
html {
    background-color: rgb(59, 59, 59); 
    color: white;
}

body {
    margin: 0;
}

div {
    box-sizing: border-box;
}

img {
    height: 100%;
    width: auto;
}

#navbar {
    height: 50px;
    border: 1px dotted red; 
}

#flex {
    display: flex;
    height: calc(100vh - 50px);
}

#sidebar {
    width: 30%;
    border: 1px dotted blue; 
}

#main {
    width: 70%;
    border: 1px dotted green; 
}

#title {
    width: 70%;
    float: left;
}

#logo {
    width: 30%;
    height: 100%;
    float: right;
    text-align: right;
}

.container {
    border-style: dotted;
    border-width: 1px;
}
</style>