<template>
    <v-col cols="12" sm="6" md="4">
          <v-card>
            <v-card-text>
              <div class="item--id">{{item.id}}</div>
              <div class="item--title text-h6 text--primary">
                <NuxtLink :to="getPermalink(item)">{{item.title}}</NuxtLink>
                
              </div>
              <div class="item--description text--primary">
                {{item.body}}
              </div>
            </v-card-text>
          </v-card>
        </v-col>
</template>

<script>
export default {
  layout: 'empty',
  props: {
      item: Object
  },
  data () {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  methods :{
      getPermalink(post) {
      let link = `/posts/${post.id}`;
      return link;
    },
  },
}
</script>

<style lang="css" scoped>
.item--id{
    background:#5b009b;
    color:#fff;
    border-radius:30px;
    width:30px;
    height:30px;
    display:flex;
    justify-content:center;
    align-items:center;
    margin-bottom:10px;
}
.item--title{
    line-height:24px;
    height:24px;
    overflow:hidden;
    text-overflow: ellipsis; 
    white-space: nowrap;
    margin-bottom:15px;
}
.item--title a{
    color: #5b009b;
    text-decoration:none;
}
.item--description{
    line-height:24px;
    height:72px;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-overflow: ellipsis;
}
</style>
