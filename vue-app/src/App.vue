<template>
  <div id="nav">
 <!--    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
  </div>
  <router-view :posts="posts"/>
</template>

<script>

export default {
  name: 'app',
  data() {
    return {
      posts: 
      [
        {
          id: 1, 
          fullname: 'Michael Rod',
          username: 'roddmaster',
          post: 'Hi everybody.',
          comments: 7,
          likes: 3,
          img: '../assets/images/user1.png'
        },
        {
          id: 2,
          fullname: 'Alycia Hamilton',
          username: 'flowerpower',
          post: 'Today ate at HARVEYS. Amazing food and atmosphere.',
          comments: 10,
          likes: 1,
          img: 'assets/images/user1.png'
        },
        {
          id: 3,
          fullname: 'Bob Scott',
          username: 'booklover',
          post: 'What is your favourite book?',
          comments: 5,
          likes: 3,
          img: 'assets/images/user1.png'
        }
      ]
    }
  }
}

</script>



<style>
</style>
