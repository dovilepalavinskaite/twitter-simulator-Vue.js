<template>
	<div id="posts-feed" class="col-md-6">
		<div class="card">
  		<div class="card-body post-template">
  			<div>
  				<div class="d-flex">
		  			<img class="card-img" src="../assets/images/eagle.gif">
		  			<form class="ml-3 w-100">
		  				<textarea class="form-control" id="exampleFormControlTextarea1" placeholder="What's happening?" rows="4"></textarea>
		  			</form>
		  		</div>
	  			<div class="d-flex mt-3 flex-row-reverse">
	  				<button class="btn btn-outline-success">Tweet</button>
	  				<h6 class="mr-2 mt-2">200</h6>
	  			</div>
	  		</div>
	  		<div v-for="(post, index) in posts" :key="`post-${index}`">
	  			<div class="card mt-3 cursor-pointer">
					  <div class="card-body">
					  	<div class="d-flex">
					  		<div>
					  			<img :src="require(post.img)" >
					  		</div>
						  	<div class="d-flex">
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
					  			<i class="far fa-heart mr-2"></i>
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
	props: {
		posts: {
			type: Array
		}
	},
	methods: {
		
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

</style>