<!-- // Script is in some way equivalent to script.js. This is place
to define variables, methods and imports of other Vue compoennts. -->
<script setup>
// Understanding ref article: https://blog.logrocket.com/understanding-vue-refs/#:~:text=Ref%20s%20are%20Vue.,element%20in%20your%20Vue%20instance.
// When ref attribute is added to element, this element then can be referenced
// in template. It is sort of templatecement of getElementById (but better)
import { ref } from "vue";

// Define variables and constants
let count = ref(0);
let name = ref("Alberto Horta");

// Define functions
function increment() {
  count.value++;  
  contentText.value = userInput.value;
  console.log(name.value)
  let userInput = ref(""); // Variável para armazenar o texto do input
  let contentText = ref(""); // Variável para armazenar o texto que será exibido em content
}
</script>


<template>
  
  <!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Albert's Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="navbar">Parametric View - by {{name}} </div>
    <div id="sidebar">Menu<br>
      <br>
      <input type="text" v-model="userInput" placeholder="Digite algo aqui"><br>
      <button @click="increment">Submit</button>
      <br>
      <br>
      <input type="text" placeholder="Digite algo aqui"><br>
      <button @click="increment">Submit</button>
    </div>
    <div id="content">{{ contentText }}</div>
    <div id="content">Main</div>
</body>
</html>
</template>

<!-- Style is for CSS styling -->
<style>
body, html {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
}

#navbar {
    background-color: #333;
    color: white;
    padding: 20px 0;
    text-align: center;
    height: 20px;
    width: 100%;
}

#sidebar {
    background-color: #ccc;
    padding: 20px;
    position: fixed;
    left: 0;
    text-align: center;
    top: 60px;
    height: calc(100%);
    width: 10%;
    overflow: auto;
}

#content {
    margin-left: 12%;
    padding: 20px;
}
</style>