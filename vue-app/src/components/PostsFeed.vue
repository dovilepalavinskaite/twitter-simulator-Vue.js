<template>
	<div id="posts-feed" class="col-md-6">
		<div class="card">
  		<div class="card-body post-template">
  			<div>
  				<div class="d-flex">
		  			<img class="card-img" src="../assets/images/user-round.png">
		  			<form class="ml-3 w-100" @submit.prevent="addNewMsg">
		  				<textarea class="form-control text-area" id="exampleFormControlTextarea1" placeholder="What's happening?" rows="4" v-model="newMsg" :class="{ '--exceeded': msgCharCount > 280 }"></textarea>
		  				<div class="d-flex mt-3 flex-row-reverse">
	  						<button class="btn btn-outline-success" :class="{ 'disabled': msgCharCount > 280 }">Tweet</button>
	  						<h6 class="mr-2 mt-2">({{ msgCharCount }}/280)</h6>
	  					</div>
		  			</form>
		  		</div>
	  		</div>
	  		<div v-for="(post, index) in posts" :key="`post-${index}`">
	  			<div class="card mt-3 cursor-pointer">
					  <div class="card-body">
					  	<div class="d-flex">
						  	<div class="d-flex">
						  		<img class="person-img mr-2 mb-2" :src="getImgUrl(post)" v-bind:alt="post">
							  	<h4 class="card-text mr-1">{{ post.fullname }}</h4>
							  	<h6 class="card-text text-secondary mt-1">@{{ post.username }}</h6>
							  </div>
							</div>
					  	<p class="card-text">{{ post.post }}</p>
					  	<div class="d-flex">
					  		<div class="d-flex text-secondary mr-2">
					  			<i class="far fa-comment mr-2"></i>
					  			<h6 class="card-text">{{ post.comments }}</h6>
					  		</div>
					  		<div class="d-flex text-secondary">
					  			<i :class="['fas', 'fa-heart', 'mr-2', likeClass(post)]" @click="likePost(post)"></i>
					  			<h6 class="card-text">{{ post.likes }}</h6>
					  		</div>
					  	</div>
					  </div>
					</div>
	  		</div>
  		</div>
		</div>
	</div>	
</template>

<script>
export default {
	name: 'PostsFeed',
	data() {
		return {
			newMsg: ''
		}
	},
	props: {
		posts: {
			type: Array
		},
		user: {
			type: Object
		}
	},
	computed: {
		msgCharCount() {
			return this.newMsg.length;
		}
	},
	methods: {
		getImgUrl(post) {
		  return require('../assets/images/' + post.img)
		},
		likeClass(post) {
			return post.liked ? 'fa-heart-active' : '';
		},
		likePost(post) {
			post.liked = !post.liked;

			post.liked ? post.likes++ : post.likes--;
		},
		addNewMsg() {
			if (this.newMsg) {
				this.posts.unshift({
					id: this.posts.length + 1,
					fullname: this.user.fullName,
					username: this.user.userName,
					post: this.newMsg,
					likes: 0,
					comments: 0
				})
				this.user.tweets++;
			}
			this.newMsg = '';
		}
	}
}

</script>

<style>
	
.card-img {
	width: 3rem;
	height: 43px;
}

.post-template {
	background-color: #f2f2f2;
}

.cursor-pointer {
	cursor: pointer;
}

.cursor-pointer:hover {
	background-color: #f2f2f2;
}

.fa-heart:hover {
	color: red;
}
.fa-heart-active {
	color: red;
}

.text-area.--exceeded {
	color: red;
	border-color: red;
}

.btn.dissabled {
	border: 1px solid #999999;
  background-color: #cccccc;
  color: #666666;
}

.person-img {
	width: 3rem;
}

</style>