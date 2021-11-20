<template>
  <header class="py-5 bg-black-custom">
    <ul>
      <li><NuxtLink class="text-white" to="/" title="home">Home</NuxtLink></li>
      <li class="whitespace-nowrap	">
        <NuxtLink id="zzz" class="text-white" to="/contact" title="contact"
          >Contact me</NuxtLink
        >
      </li>
    </ul>
    <div class="d-block w-6/12">
    <div class="pt-3">
      <div class="flex justify-end items-center space-x-2 mx-auto relative">
        <span class="text-xs text-white">Light </span>
        <div>
          <label class="switch">
            <input type="checkbox" id="checkbox" checked />
            <span class="slider round"></span>
          </label>
        </div>
        <span class="text-xs font-semibold text-white">Dark</span>
      </div>
    </div>
    </div>

  </header>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100;300;400;500;700&display=swap");

body {
  /* background-color: rgb(20,20,20); */
  /* color: rgb(255,255,255); */
  font-family: "Josefin Sans", sans-serif;
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
.switch {
  position: relative;
  display: inline-block;
  width: 60px;
  height: 34px;
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
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
  transition: transform 0.3s linear;
}

input:checked + .slider {
  background-color: rgb(43, 138, 14);
  transition: transform 0.3s linear;
}

input:focus + .slider {
  box-shadow: 0 0 1px rgb(43, 138, 14);
  transition: transform 0.3s linear;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
  transition: transform 0.3s linear;
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>

<script>
export default {
  methods: {
    imgMode() {        
        const img = document.getElementById("my-pic");
        const checkbox = document.getElementById("checkbox");

        checkbox.addEventListener("change", () => {
            let theme = localStorage.getItem("data-theme"); // Retrieve saved them from local storage
            if (theme === "dark") {
                console.log('dddd')
                if (img != null) {
                    img.classList.remove("light-mode");
                }
            } else {
                console.log('dddd')
                if (img != null) {
                    img.classList.add("light-mode");
                }
            }
        });
    },
  },
  mounted() {
    let theme = localStorage.getItem("data-theme");
    const checkbox = document.getElementById("checkbox");    
    // this.imgMode()

    if (theme === "dark") {
      // changeThemeToLight()
      checkbox.removeAttribute("checked");
      // img.classList.remove("light-mode");
    } else {
      // changeThemeToDark()
      checkbox.setAttribute("checked", "checked");
      // img.classList.add("light-mode");
    }

    const changeThemeToDark = () => {
      document.documentElement.setAttribute("data-theme", "light"); // set theme to dark
      localStorage.setItem("data-theme", "dark"); // save theme to local storage
    };

    const changeThemeToLight = () => {
      document.documentElement.setAttribute("data-theme", "dark"); // set theme light
      localStorage.setItem("data-theme", "light"); // save theme to local storage
    };

    // Get the element based on ID
    // Apply retrived them to the website
    checkbox.addEventListener("change", () => {
        
      let theme = localStorage.getItem("data-theme"); // Retrieve saved them from local storage
      if (theme === "dark") {
        changeThemeToLight();
      } else {
        changeThemeToDark();
      }
    });
  },
};
</script>