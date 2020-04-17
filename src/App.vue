<template>
  <div>
    <h2 class="text-centered">Your App Now</h2>
    <div class="buttons">
      <button class="butn" v-on:click="component='signup-form'">Sign Up</button>
      <button class="bton" v-on:click="component='login-form'">Login</button>
    </div>
    <component v-bind:is="component"></component>
    
  </div>
</template>

<script>

//import Header from './components/Header.vue'
//import Footer from './components/Footer.vue'
//import Dudes from './components/Dudes.vue'
import Signup from './components/Signup.vue'
import Login from './components/Login.vue'


export default {
  
    /*components: {
        'app-header': Header,
        'app-footer': Footer,
        'app-dudes': Dudes
    },*/
    components: {
        'signup-form': Signup,
        'login-form': Login
    },

  data () {
    return {
      component: 'signup-form',
    }

  },
  methods:{
   
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito&family=Playfair+Display&display=swap');
h2,h1,label,h3,p{
  color: lightgray;
  font-family: 'Nunito', sans-serif;
}
input{
  color: #222;
}
li{
  list-style: none;
}
.text-centered{
  text-align: center;
  font-size: 30px;
  color: white;
} 
.buttons{
  display: flex;
  width: 34.4%;
  margin-left: auto;
  margin-right: auto;
  color: white;
}
.butn{
  width: 50%;
  font-size: 20px;
  background-color: palevioletred;
  border: none;
  color: white;
  border-radius: 10px 0px 0px 0px;
  border-right: 1px solid #222;
  font-family: 'Nunito', sans-serif;
  cursor: pointer;
}
.bton{
  width: 50%;
  padding: 20px;
  font-size: 20px;
  border: none;
  color: white;
  border-radius: 0px 10px 0px 0px;
  background-color: palevioletred;
  font-family: 'Nunito', sans-serif;
  cursor: pointer;
} 

h3{
  color: whitesmoke;
  text-align: center;
  font-size: 30px;
} 
</style>
