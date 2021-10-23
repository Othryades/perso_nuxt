<template>
    <header class="py-5">
        <ul>
            <li><NuxtLink class="text-base" to="/">Home</NuxtLink></li>
            <li><NuxtLink class="text-base" to="/contact">Contact me</NuxtLink></li>          
        </ul>
    </header>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100;300;400;500;700&display=swap');

  body {
      background-color: rgb(20,20,20);
      color: rgb(255,255,255);
      font-family: 'Josefin Sans', sans-serif;
      font-weight: 300;
  }
  header {
      display: flex;
      justify-content: center;
  }
  header ul {
      display: flex;
      padding: 10px 10px 50px 10px;
  }
  li {
    list-style: none;
    margin: 5px 10px;
  }
</style>
