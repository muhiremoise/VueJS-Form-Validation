<template>
    <div id="signup">
        <form>
          
            <h3>Sign Up Now</h3>
            <p v-if="errors.length">
              <span>Please collect the Error(s):</span>
              <ul>
                <li v-for="error in errors" v-bind:key="error">{{error}}</li>
              </ul>
            </p>
            <label for="">Names</label>
            <div class="flex">
              
              <input type="text" placeholder="First Name" name="FirstName" id="FirstName" v-model="FirstName">
              
              <input type="text" placeholder="Last Name" name="LastName" id="LastName" v-model="LastName">
            </div>
            <label>E-mail</label>
            <input type="email" placeholder="E-mail" name="email" id="email" v-model="email">
            <label>Password</label>
            <input type="password" placeholder="Password" name="password" id="password" v-model="password">
            <div class="btn-div">
              <button class="btn" v-on:click="CheckedForm">Submit</button>
            </div>
          
        </form>
    </div>
</template>

<script>
export default {
  
  data () {
    return {
       errors:[],
       FirstName: null,
       LastName: null,
       email:null,
       password:null,
        
    }

  },
  methods:{
    CheckedForm:function(e){
      if(this.FirstName && this.LastName && this.email && this.password)
      return true;
      this.errors=[];
      if(!this.FirstName)this.errors.push("Firstname required");
      if(!this.LastName)this.errors.push("Lastname required");
      if(!this.email)this.errors.push("E-mail required");
      else if (!this.validEmail(this.email)) {
        this.errors.push('Valid email required.');
      }
      if(!this.password)this.errors.push("Password required");
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
   #signup{
     background: #222;
    width: 30%;
    margin-left: auto;
    margin-right: auto;
    padding: 30px;
    border-radius: 0px 0px 10px 10px;
   }
   input[type=email]{
  width: 100%;
  padding: 12px 20px;
  margin: 0px 0px 10px 0px;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
input[type=password]{
  width: 100%;
  padding: 12px 20px;
  margin: 0px 0px 10px 0px;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
input[type=text]{
  width: 100%;
  padding: 12px 20px;
  margin: 0px 0px 10px 0px;
  display: inline-block;
  border: 1px solid #ccc;
  
  box-sizing: border-box;
}
input[name=FirstName]{
  border-radius: 4px 0px 0px 4px;
}
input[name=LastName]{
  border-radius: 0px 4px 4px 0px;
}
.flex{
  display: flex;
  
}
label{
  color: whitesmoke;
  font-size: 15px;
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
  padding-bottom: 5px;
  padding-top: 10px;
  border: none;
}
::placeholder{
  font-family: 'Nunito', sans-serif;
}
</style>
