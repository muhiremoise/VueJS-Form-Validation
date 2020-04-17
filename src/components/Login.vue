<template>
    <div id="login">
        <form>
            <h3>Login Here</h3>
            <p v-if="errors.length">
                <b>Please correct the error(s):</b>
                <ul>
                    <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
                </ul>
            </p>
            <div style="padding:10px;">
                <label>E-mail</label><br>
                <input type="email" placeholder="E-mail" name="email" id="email" v-model="email">
            </div>
            <div style="padding:10px;"  >
                <label>Password</label>
                <input type="password" placeholder="Password" name="password" id="password" v-model="password">
            </div>
            <div class="btn-div">
                <button class="btn" v-on:click="CheckForm">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
  
  data () {
    return {
        errors:[],
        email: null,
        password: null,

    }

  },
  methods:{
      CheckForm:function(e)
       {
      if(this.email && this.password) return true;
      this.errors = [];
      if(!this.email) this.errors.push("Email required.");
      else if (!this.validEmail(this.email)) {
        this.errors.push('Valid email required.');
      }
      if(!this.password) this.errors.push("Password required.");
      e.preventDefault();
    },
    validEmail: function (email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    }
  }
}
</script>

<style scoped>
 
label{
  color: whitesmoke;
  font-size: 20px;
}
input[type=email]{
  width: 100%;
  padding: 12px 20px;
  margin: 0px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
input[type=password]{
  width: 100%;
  padding: 12px 20px;
  margin: 0px 0;
  display: inline-block;
  border: 1px solid #222;
  border-radius: 4px;
  box-sizing: border-box;
}
#login{
  background: #222;
  width: 30%;
  margin-left: auto;
  margin-right: auto;
  padding: 30px;
  border-radius: 0px 0px 10px 10px;
}
.btn{
  width: 100%;
  height: 30px;
  border-radius: 5px;
  border: none;
  background: palevioletred;
  color:white;
  font-family: 'Nunito', sans-serif;
  

}
.btn:hover{
  cursor: pointer;

}
.btn-div{
  width: 20%;
  margin-left: auto;
  margin-right: auto;
  padding: 50px;
  border: none;
}
   
</style>
