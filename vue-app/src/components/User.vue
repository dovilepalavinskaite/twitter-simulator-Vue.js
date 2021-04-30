<template>
	<div id ="user" class="col-md-3">
		<div class="card" style="width: 25rem;">
		  <img class="card-img-top" src="../assets/images/patern.png" alt="Card image cap">
		  <div class="card-body">
		    <h4 class="card-title mb-0 text-center">{{ fullName }}</h4>
		    <h6 class="card-title mint-color text-center">@{{ userName }}</h6>
		    <div class="d-flex">
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Tweets</h6>
			    	<h6 class="mint-color">{{ tweets }}</h6>
			    </div>
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Followers</h6>
			    	<h6 class="mint-color">{{ followers }}</h6>
			    </div>
			    <div class="col-md-4 card-info text-center">
			    	<h6 class="text-secondary">Following</h6>
			    	<h6 class="mint-color">{{ following }}</h6>
			    </div>
			  </div>
		  </div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'User',
	data() {
		return {
			userName: 'dovilepal',
			firstName: 'Dovile',
			lastName: 'Pakalne',
			tweets: 0,
			followers: 0,
			following: 0
		}
	},
	computed: {
		fullName() {
			return `${this.firstName} ${this.lastName}`
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
</style>