<template>
  <div>
    <h2>List of Ninjas</h2>
    <ul>
        <li v-for="ninja in ninjas" v-bind:key="ninja">{{ ninja }}</li>
    </ul>
    
  </div>
</template>

<script>
export default {
  
  data () {
    return {
      ninjas:['Yoshi','Bebe','Midele']
    }
  }
}
</script>

<style scoped>
  h2{
    color: dodgerblue;
  }
</style>