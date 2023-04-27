<template>
  <div>
    <div id="about">
      <ul>
        <li v-for="p in projects">
          <h2>{{ p.name }}</h2>
          <p> {{ p.detail }} </p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Project',
    data() {
      return{
        projects:[
          {
            name: "Under Construction",
            detail: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Debitis, laborum."
            
          }
        ]
      }
    }
  }
</script>

<style scoped>
#about {
  position: absolute;
  right: 0;
  bottom: 0;
  width: 60%;
}

li {
  padding: 1rem;
}

li h2{
  margin: 0;
  margin-bottom: 1rem;
  clear: both;
  float: right;
}

li p{
  margin: 0;
  display:inline-block
}

li h2:hover{
  color: var(--sec-color)
}
</style>