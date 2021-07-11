<template>
  
  <v-form ref="form"  lazy-validation>
    <v-container class="custom-container">
      <v-row justify="center" align="center">
        <v-col cols="12" md="6">
          <v-row>
            <v-col cols="12"> 
              <h1>Login</h1>
              <p>You can type any username and password but they must provide some validation rules</p>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12">
              <v-text-field
                v-model="username"
                :rules="usernameRules"
                label="Username"
                outlined
                required>
              </v-text-field>
              <v-text-field
                v-model="password"
                :rules="passwordRules"
                :type="'password'"
                outlined
                label="Password"
                required>
              </v-text-field>
              <v-btn v-on:click="handleSubmit" x-large block class="purple-btn">LOGIN</v-btn>
            </v-col>
          </v-row>
          
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>

export default {
  layout: 'empty',
  data(){
    return {
      username: "",
      password: "",
      usernameRules: [
        v => !!v || 'Username is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      passwordRules: [
        v => !!v || 'Password is required',
        v => (v && v.length >= 8) || 'Password must be more than 8 characters',
      ],
    }
  },
  methods: {
    handleSubmit: function(e){
      if(this.$refs.form.validate()){
        this.$router.push('/posts')
      }else{
        alert("Please check your information")
      }
      
      
    }
  }
}
</script>

<style lang="css">
  .custom-container{
    padding:0;
    height:100vh;
    display:flex;
    flex-direction:column;
    justify-content:center;
  }
  .purple-btn{
    background:#5b009b !important;
    color:#fff !important;
  }
</style>