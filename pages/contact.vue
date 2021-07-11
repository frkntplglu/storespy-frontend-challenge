<template>
  
  <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-row>
            <v-col cols="12"> 
              <h1>Contact</h1>
              <p>Please feel free to get contact with me in each topic</p>
            </v-col>
          </v-row>
          <v-row>
            <v-col cols="12"> 
              <ul>
                <li><b>Email : </b> {{email}}</li>
                <li><b>Phone : </b> {{phone}}</li>
                <li><b>GitHub : </b> {{github}}</li>
                <li><b>Twitter : </b> {{twitter}}</li>
              </ul>
            </v-col>
          </v-row>
          
        </v-col>
      </v-row>
    </v-container>
</template>

<script>

export default {
  data(){
    return {
      email: "frkntplglu@gmail.com",
      phone: "0543 336 97 69",
      twitter: "@frkntplglu",
      github: "@frkntplglu",
      
    }
  },
}
</script>
