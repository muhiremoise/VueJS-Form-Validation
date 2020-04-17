<template>
    <div>
        <footer>
            <h1>{{footerText}}</h1>
        </footer>
    </div>
</template>

<script>
export default {
  
  data () {
    return {
        footerText: 'Copyright UmbrellaGrp2020#'
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
    footer{
        width: 95%;
        padding: 15px;
        background: #222;
        text-align: center;
        margin-left: auto;
        margin-right: auto;
        color: lightgreen;
    }
</style>