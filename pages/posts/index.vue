<template>
  <v-row>
    <post v-for="item in list" :key="item.id" :item="item"></post>      
  </v-row>
</template>

<script>
import post from '../../components/post.vue'
export default{
  components: {
    post
  },
  data(){
    return {
      list: []
    }
  },
  methods :{
      getPermalink(post) {
      let link = `/posts/${post.id}`;
      return link;
    },
  },
  mounted () {
    fetch("https://jsonplaceholder.typicode.com/posts/")
    .then(response => response.json())
    .then(data => {
      this.list = data
      
    })
    .catch(err => console.log(err))
  }
}
</script>
