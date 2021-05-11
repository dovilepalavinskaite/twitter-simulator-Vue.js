<template>
  <div id="nav">
 <!--    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> -->
  </div>
  <router-view :posts="posts" :user="user" :people="people"/>
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
          img: 'user1.png',
          liked: false
        },
        {
          id: 2,
          fullname: 'Alycia Hamilton',
          username: 'flowerpower',
          post: 'Today ate at HARVEYS. Amazing food and atmosphere.',
          comments: 10,
          likes: 1,
          img: 'user2.png',
          liked: false
        },
        {
          id: 3,
          fullname: 'Bob Scott',
          username: 'booklover',
          post: 'What is your favourite book?',
          comments: 5,
          likes: 3,
          img: 'user3.png',
          liked: false
        }
      ],
      user: 
      {
        userName: 'dovilepal',
        fullName: 'Dovile Pakalne',
        tweets: 0,
        followers: 0,
        following: 0,
        img: '../assets/images/user-round.png'
      },
      people:
      [
        {
          fullName: 'Brian Josh',
          userName: 'doggo',
          followed: false,
          img: 'person1.jpeg',
          status: 'Follow'
        },
        {
          fullName: 'Maria Adams',
          userName: 'isaymeow',
          followed: false,
          img: 'person2.png',
          status: 'Follow'
        },
        {
          fullName: 'Joanna Aims',
          userName: 'fromParis',
          followed: false,
          img: 'person3.jpeg',
          status: 'Follow'
        }
      ]
    }
  }
}

</script>



<style>
</style>
