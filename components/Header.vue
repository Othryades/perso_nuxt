<style>
@import url("https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@100;300;400;500;700&display=swap");

.nav-link {
  color: var(--color-text);
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1rem;
  position: relative;
  padding: 0.5rem 0;
  transition: all 0.3s ease;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: var(--color-accent);
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: var(--color-accent);
}

.nav-link:hover::after {
  width: 100%;
}

.theme-toggle {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  padding: 0.5rem 1rem;
  background-color: var(--color-surface);
  border-radius: 2rem;
}

.theme-label {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--color-text);
}

.switch {
  position: relative;
  display: inline-block;
  width: 48px;
  height: 24px;
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
  background-color: var(--color-text-secondary);
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 18px;
  width: 18px;
  left: 3px;
  bottom: 3px;
  background-color: var(--color-bg);
  transition: 0.4s;
}

input:checked + .slider {
  background-color: var(--color-accent);
}

input:focus + .slider {
  box-shadow: 0 0 1px var(--color-accent);
}

input:checked + .slider:before {
  transform: translateX(24px);
}

.slider.round {
  border-radius: 24px;
}

.slider.round:before {
  border-radius: 50%;
}

@media only screen and (max-width: 600px) {
  .nav-link {
    font-size: 1rem;
  }
  
  .theme-toggle {
    padding: 0.4rem 0.75rem;
  }
  
  .theme-label {
    font-size: 0.75rem;
  }
}
</style>

<template>
  <header class="bg-black-custom">
    <ul>
      <li><NuxtLink class="nav-link" to="/" title="home">Home</NuxtLink></li>
      <li class="whitespace-nowrap">
        <NuxtLink class="nav-link" to="/contact" title="contact">Contact me</NuxtLink>
      </li>
    </ul>
    <div class="theme-toggle">
      <span class="theme-label">Light</span>
      <label class="switch">
        <input v-on:click="switcha" type="checkbox" id="checkbox" checked />
        <span class="slider round"></span>
      </label>
      <span class="theme-label">Dark</span>
    </div>
  </header>
</template>

<script>
export default {
  methods: {
    imgMode() {        
        const img = document.getElementById("my-pic");
        const checkbox = document.getElementById("checkbox");

        checkbox.addEventListener("change", () => {
            let theme = localStorage.getItem("data-theme"); // Retrieve saved them from local storage
            if (theme === "dark") {
                if (img != null) {
                    img.classList.remove("light-mode");
                }
            } else {
                if (img != null) {
                    img.classList.add("light-mode");
                }
            }
        });
    },
    switcha() {
      let theme = localStorage.getItem("data-theme");
      const checkbox = document.getElementById("checkbox"); 

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
      
          
        if (theme === "dark") {
          changeThemeToLight();
          checkbox.setAttribute("checked", "checked");
        } else {
          changeThemeToDark();
          checkbox.removeAttribute("checked"); 
        }
     

    }
  },
  mounted() {
    let theme = localStorage.getItem("data-theme");
    const checkbox = document.getElementById("checkbox");
          const changeThemeToDark = () => {
        document.documentElement.setAttribute("data-theme", "light"); // set theme to dark
        localStorage.setItem("data-theme", "dark"); // save theme to local storage
      };

      const changeThemeToLight = () => {
        document.documentElement.setAttribute("data-theme", "dark"); // set theme light
        localStorage.setItem("data-theme", "light"); // save theme to local storage
      };
    console.log('mounted', theme)
    if (theme === "dark") {
      changeThemeToDark()
      checkbox.removeAttribute("checked");      
      // img.classList.remove("light-mode");
    } else {
      changeThemeToLight()
            checkbox.setAttribute("checked", "checked");
      // img.classList.add("light-mode");
    }
  },
};
</script>