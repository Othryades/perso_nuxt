<template>
  <div class="bg-black-custom">
    <div class="gradient-overlay"></div>
    
    <Header/>
    <Wave/>
    <Hero/>

    

    <Footer/>
  </div>  
</template>


<script>
export default {
  head: {
    title: 'Home page',
    meta: [
      {
        hid: 'description',
        name: 'description',
        content: 'Home page description'
      }
    ],
    link: [
      {
        rel: 'canonical',
        href: 'https://moriswebdev-portofolio.netlify.app/'
      }
    ]
  }
}
</script>

<style>
.gradient-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to bottom, rgba(10, 10, 10, 0.1) 0%, rgba(10, 10, 10, 1) 100%);
  pointer-events: none;
  z-index: 1;
  animation: fadeIn 2s ease forwards;
  opacity: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>