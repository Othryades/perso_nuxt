<template>
        <footer class="">
            <div>
            <h2 class="text-center text-2xl text-white">Web Developer and Defi</h2>
            <div class="options flex justify-center">                
                <NuxtLink class="text-base" to="/work" title="my work"><h3 class="font-semibold text-center text-white">My Work</h3></NuxtLink>
                <NuxtLink class="text-base" to="/about" title="about me"><h3 class="font-semibold text-center text-white">About Me</h3></NuxtLink>
                <NuxtLink class="text-base font-semibold text-center text-white" to="/stack" title="my stack"><h3 class="font-semibold text-center text-white">STACK</h3></NuxtLink>
            </div> 

            <ul class="social-logo justify-center">
                <a href="https://www.facebook.com/moris.iarossi/" title="my facebook" target="_blank">
                    <li class="text-white">Facebook</li>
                </a>
                <a href="https://github.com/Othryades" target="_blank">
                    <li class="text-white">GitHub</li>
                </a>
                <a href="https://www.linkedin.com/in/moris-iarossi/" target="_blank">
                    <li class="text-white">LinkedIn</li>
                </a>
            </ul>
            </div>
    </footer>
</template>

<style>
h2 {
    margin: 3px;
    font-weight: 300;
    text-align: center;
}

h3 {
    margin: 0;
}
footer {
    position: fixed;
    bottom: 0;
    /*position: fixed; */
    left: 50%;
    transform: translate(-50%, 0);
    display: flex;
    flex-direction: column;
    align-items: center;
}

footer ul {
    display: flex;
    padding: 30px;
}

.options {
    display: flex;
}

.options a {
    margin: 40px 10px;
}

a {
    text-decoration: none;
    /* color: rgb(255,255,255); */
}

.socials {
    width: 100px;
    height: 320px;
    background-color: rgb(30 102 8);
    border-radius: 30px 0 0 30px;
    position: fixed;
    right: 0;
    top: 27vh;
    z-index: 9;
}

@media only screen and (max-width: 600px) {
    .socials {
        display: none;
    }
}

.social {
    width: 100%;
    height: 33%;
}

.wave {
    fill: rgb(0,0,0);
    width: 100vw;
    height: 60vh;
    position: fixed;
    bottom: 0;
    left: 0;
}

.social svg {
    fill: rgb(255,255,255);
}

footer a:hover {
    color: rgb(30 102 8);
    transform: scale(1.2);
}

    @media only screen and (max-width: 600px) {
       h2 {
            font-size: 18px !important;
        }
    }
</style>
