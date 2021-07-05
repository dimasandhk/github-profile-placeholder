<template>
	<div class="row mt-3">
		<div class="col-12 col-md-12 col-lg-6">
			<img :src="src" />
		</div>
		<div class="col-12 col-md-12 col-lg-6">
			<h5 class="font-weight-bold">Value: {{ val }}</h5>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		val: String,
		src: String
	}
};
</script>

<style lang="scss" scoped></style>
