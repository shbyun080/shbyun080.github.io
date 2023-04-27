<script>
import {RouterLink, RouterView} from 'vue-router'
export default {
  name: 'App',
  data() {
    return {
      schemeID: 0,
      palette: [
        {
          color: "#eee",
          secondary: "#ffa600",
          background: "#112a42"
        },
        {
          color: "#111",
          secondary: "#00d",
          background: "#ddd"
        }
      ]
    }
  },
  methods: {
    randomizeColor() {
      this.schemeID = Math.floor(Math.random() * this.palette.length)
    }
  },
  computed: {
    colors(){
      return{
        '--bg-color': this.palette[this.schemeID].background,
        '--prim-color': this.palette[this.schemeID].color,
        '--sec-color': this.palette[this.schemeID].secondary
      }
    }
  },
  created() {
    this.randomizeColor()
  }
}
</script>

<template>
  <div id="topcontainer" :style="colors">
    <div id="appcontainer">
      <div id="main">
        <h1>Sanghyun Byun</h1>
        <p>Computer Vision, NLP, Machine Learning.</p>
        <div id="nav">
          <router-link class="routers" :to="{ name: 'Home' }" :style="colors">Home</router-link>
          <router-link class="routers" :to="{ name: 'Project'}" :style="colors">Project</router-link>
          <router-link class="routers" :to="{ name: 'Contact' }" :style="colors">Contact</router-link>
        </div>
      </div>
    <RouterView id="routerview"/>
    </div>  
  </div>
</template>

<style>
body {
  height: 100vh;
  width: 100%;
  display: flex;
  padding: 0;
  margin: 0;
}

h1 {font-size: 5rem;}
p {font-size: 1.2rem;}
h2 {font-size: 2rem;}
a {font-size: 1.2rem;}
a.router-link-exact-active{font-size: 1.4rem;}
a:hover {font-size: 1.4rem;}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  flex: 1;
  display: flex;
  padding: 0;
  margin: 0;
}

#topcontainer {
  flex: 1;
  display: flex;
  padding: 0;
  margin: 0;
  background-color: var(--bg-color);
  color: var(--prim-color);
}

#appcontainer {
  flex: 1;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  display:flex;
  margin: 4rem;
  border: solid 2px;
}

#main {
  flex: 50%;
  margin: 10px;
}

#routerview {
  flex: 50%;
  margin: 10px;
  position: relative;
  text-align: right;
  float: left;
  overflow: hidden;
}

#main h1 {
  font-weight: lighter;
  padding: 0;
  margin: 0;
}

#main p {
  font-style: italic;
}

#nav a{
  font-weight: bold;
  text-decoration: none;
  padding: 10px;
  display: block;
  float: left;
  clear: both;
  list-style-type: none;
  height: 2rem;
  align-items: center;
}

#nav a.router-link-exact-active{
  color: var(--sec-color);
  border-left: solid 2px var(--sec-color);
  padding-left: 1rem;
}

ul {
  list-style-position: inside;
  padding: 0;
  margin: 0;
}

li {
  list-style-type: none;
}

a {
  color: inherit;
}
</style>