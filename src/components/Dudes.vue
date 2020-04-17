<template>
    <div id="dudes">
        
        <ul>
            <li v-for="dude in dudes" v-bind:key="dude" v-on:click="dude.show=!dude.show">
                <h2>{{dude.name}}</h2>
                <h3 v-show="dude.show">{{dude.speciality}}</h3>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  
  data () {
    return {
        dudes:[
            {name:'Blaise', speciality:'Capati Killer', show:false},
            {name:'Samuel', speciality:'Fart Producer', show:false},
            {name:'Yoshi', speciality:'HTML Viper', show:false},
            {name:'Ryu', speciality:'Capati Killer', show:false},
            {name:'Angular', speciality:'Capati Damner', show:false},
            {name:'Hotishi', speciality:'Capati Killer', show:false},
            
        ]
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
    #dudes{
        width: 100%;
        max-width: 1200px;
        margin:40px auto;
        padding:0 20px;
        box-sizing: border-box;
    }
    ul{
        display: flex;
        flex-wrap: wrap;
        list-style-type: none;
        padding: 0;
    }
    li{
        flex-grow: 1;
        flex-basis: 300px;
        text-align: center;
        padding: 30px;
        border:1px solid #222;
        margin: 10px;
    }
    
</style>