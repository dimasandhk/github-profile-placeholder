<template>
	<section class="home mt-5">
		<div class="container">
			<h3 class="font-weight-bold text-center">Github Profile Picture Placeholder</h3>
			<input type="text" class="form-control shadow-none" v-model="val" placeholder="Some text" />
			<ProfileCard :val="val" :src="getUrl" v-if="val && val.trim()" />
			<NoValue v-else />
		</div>
	</section>
</template>

<script>
import ProfileCard from "./components/ProfileCard.vue";
import NoValue from "./components/NoValue.vue";
import md5 from "md5";

export default {
	name: "App",
	data: () => ({
		val: ""
	}),
	computed: {
		getUrl() {
			const address = String(this.val)
				.trim()
				.toLowerCase();

			const hash = md5(address);
			return `https://www.gravatar.com/avatar/${hash}?s=300&d=retro`;
		}
	},
	components: { ProfileCard, NoValue }
};
</script>

<style lang="scss"></style>
