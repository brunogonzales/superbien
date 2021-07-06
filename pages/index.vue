<template>
	<div>
		<img :src="image.url" :width="image.width" height="image.height"/> 
		<button class="px-3 py-2 shadow-lg rounded bg-black font-medium text-white"  @click="$fetch">otro gato</button>
	</div>
</template>

<script>
export default {
	data(){
		return {
			image:null
		}
	},
	async fetch(){
		const response = await this.$nuxt.context.$axios.get("https://api.thecatapi.com/v1/images/search")
		this.image = response.data[0]
	}


}
</script>
