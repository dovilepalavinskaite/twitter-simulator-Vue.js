<template>
  <div id="home" class="row mt-5 ml-5">
  	<User :user="user" />
  	<PostsFeed :posts="posts" :user="user"/>
  	<Following :user="user" :people="people"/>
  </div>
</template>

<script>

import User from '../components/User'
import PostsFeed from '../components/PostsFeed'
import Following from '../components/Following'

export default {
  name: 'Home',
  components: { User, PostsFeed, Following },
  props: {
		posts: {
			type: Array
		},
		user: {
			type: Object
		},
		people: {
			type: Array
		}
	}
}
</script>

<style>

body {
	background-color: #f0eeed;
}

</style>