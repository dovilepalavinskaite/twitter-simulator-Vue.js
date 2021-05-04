<template>
	<div id="following">
		<div class="card" style="width: 25rem;">
		  <div class="card-body">
		    <h5 class="font-weight-bold">Who to follow?</h5>
		  </div>
		  <hr>
		  <div class="card-body" v-for="(person, index) in people" :key="`person-${index}`">
		    <div class="d-flex">
		    	<div>
		    		<img class="person-img mr-3 mb-3" :src="getImgUrl(person)" v-bind:alt="person">
		    	</div>
		    	<div>
				  	<h4 class="card-text mr-1 mt-2">{{ person.fullName }}</h4>
				  	<h6 class="card-text text-secondary mt-1">@{{ person.userName }}</h6>
				  </div>
			  </div>
			  <button :class="['btn', 'btn-outline-success', btnFollowed(person)]" @click="followPerson(person)">{{ person.status }}</button>
			  <hr>
		  </div>
		</div>
	</div>
</template>

<script>

export default {
	name: 'following',
	props: {
		people: {
			type: Array
		},
		user: {
			type: Object
		}
	},
	methods: {
		getImgUrl(person) {
		  return require('../assets/images/' + person.img)
		},
		btnFollowed(person) {
			return person.followed ? 'btn-followed' : '';
		},
		followPerson(person) {
			person.followed = !person.followed;
			person.followed ? this.user.following++ : this.user.following--;
			person.followed ? person.status = "Followed" : person.status = "Follow";
		}
	}
}

</script>

<style>
	
.btn-followed {
	background-color: #28a745;
	color: white;
}

.person-img {
	width: 5rem;
}

</style>