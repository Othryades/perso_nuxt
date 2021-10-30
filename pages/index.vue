<template>
  <div>
    
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
          href: 'https://moris-dev.surge.sh/'
        }
      ]
  }
}
</script>