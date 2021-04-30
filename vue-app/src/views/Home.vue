<template>
  <div id="home" class="d-flex mt-5 ml-5">
  	<User />
  	<PostsFeed :posts="posts" />
  </div>
</template>

<script>

import User from '../components/User'
import PostsFeed from '../components/PostsFeed'

export default {
  name: 'Home',
  components: { User, PostsFeed },
  props: {
		posts: {
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