<template>
    <div>
        <header>
            <h1>{{title}}</h1>
        </header>
    </div>
</template>

<script>
export default {
  
  data () {
    return {
        title: 'The Net Dudes'
    }

  },
  methods:{
    
  }
}
</script>

<style scoped>
    template{
        margin: 0;
        padding: 0;
    }
    header{
        width: 95%;
        padding: 15px;
        background: lightgreen;
        text-align: center;
        margin-left: auto;
        margin-right: auto;
    }
</style>