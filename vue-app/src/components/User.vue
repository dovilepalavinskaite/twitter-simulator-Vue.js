<template>
	<div id ="user" class="col-md-3">
		<div class="card" style="min-width: 100%">
		  <img class="card-img-top" src="../assets/images/patern.png" alt="Card background image">
		  <div class="card-body">
		  	<div class="d-flex">
		  		<img  class="user-img mr-3" src="../assets/images/user-round.png" alt="User image">
		  		<h4 class="card-title mb-0 text-center">{{ user.fullName }}</h4>
		  	</div>
		    <h6 class="card-title mint-color text-center">@{{ user.userName }}</h6>
		    <div class="d-flex">
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Tweets</h6>
			    	<h5 class="mint-color">{{ user.tweets }}</h5>
			    </div>
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Followers</h6>
			    	<h5 class="mint-color">{{ user.followers }}</h5>
			    </div>
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Following</h6>
			    	<h5 class="mint-color">{{ user.following }}</h5>
			    </div>
			  </div>
		  </div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'User',
	props: {
		user: {
			type: Object
		}
	}
}

</script>

<style>
	.card-info h6 {
		font-size: 12px;
	}
	.mint-color {
		color: #48c072;
	}

	.card {
		-webkit-box-shadow: -4px 9px 10px 0px rgba(0,0,0,0.33); 
		box-shadow: -4px 9px 10px 0px rgba(0,0,0,0.33);
	}

	.user-img {
		width: 80px;
		margin-top: -40px;
	}
</style>