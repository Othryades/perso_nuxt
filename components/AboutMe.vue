<template>
    <section>
        <h2 class="subtitle text-white">about me</h2>

        <div class="about-me">
            <img id="my-pic" src="@/assets/pics/moris.jpg" loading="eager" width="200" height="200" alt="Moris pic">
            <p class="text-white">            
I'm a Full Stack Web Developer with a great experience in Front End, 7 years working experience in the internet industry in various fields. Passionate about web technologies, serverless solution and responsive design.
Skilled in Js, Vue.js, PHP, Bootstrap, Firebase & AWS.
            </p>
        </div>

    </section>
</template>

<style scoped>
#my-pic {
  object-fit: cover;
  transform: translateZ(0); /* Force hardware acceleration */
  will-change: transform; /* Hint to browser for optimization */
}
</style>
