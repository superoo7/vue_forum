<template>
  <div>
    <h1>Vue Forum</h1>
    <div v-for="thread in threads" class="col-large push-top">
      <h2>{{thread.title}}</h2>
      <div class="post-list">
        <div class="post" v-for="postId in thread.posts">
          <div class="user-info">
            <a href="#" class="username">
              {{users[posts[postId].userId].name}}
            </a>
            <a href="#">
              <img class="avatar-large" :src="users[posts[postId].userId].avatar">
            </a>
            <p class="desktop-only text-small">
              112 posts
            </p>
          </div>
          <div class="post-content">
            <div>
              <p>{{posts[postId].text}}</p>
            </div>
          </div>
          <div class="post-date text-faded">
            {{posts[postId].publishedAt}}
          </div>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
import sourceData from '@/data'
console.log(sourceData)

export default {
  data () {
    return {
      threads: sourceData.threads,
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
