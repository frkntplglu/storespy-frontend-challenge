<template>

  <v-container>
      <v-row>
        <h1 class="post--title">{{post.title}}</h1>
        <p class="post--description">{{post.body}}</p>
        <v-btn @click="goBack" dark depressed color="purple">
          <v-icon left dark>mdi-arrow-left</v-icon>
          Go Back
        </v-btn>
      </v-row>
    </v-container>
</template>

<script>
export default{
  data(){
    return {
        isLoaded: true,
      post: []
    }
  },
  methods: {
      goBack() {
        this.$router.go(-1);
      },
    },
  mounted () {
    const id = this.$route.params.id
    fetch(`https://jsonplaceholder.typicode.com/posts/${id}`)
    .then(response => response.json())
    .then(data => {
      this.post = data
      this.isLoaded = false
    })
    .catch(err => console.log(err))
  }
}
</script>

<style lang="css" scoped>
  .post--title{
    color: #5b009b;
    font-size:36px !important;
    font-weight:700;
    line-height:1;
    margin-top:30px;
  }
  .post--description{
    font-size:18px;
    margin-top:15px;
  }
</style>