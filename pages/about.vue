<template>
  <div class="page-container">
    <Header/>

    <main class="content">
      <AboutMe/>
    </main>
    
    <Footer2/>
    <!-- <Hero/> -->
  </div>  
</template>

<script>
export default {}
</script>

<style>
.page-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.content {
  flex: 1;
  padding-bottom: 2rem;
}
</style>