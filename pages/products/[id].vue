<template>
	<div>
		<p>Product details for {{ id }}</p>
		<p>This product is awesome!</p>
	</div>
</template>


<script setup>
	const { id } = useRoute().params
	definePageMeta({ layout: "forproduct" })
</script>


<style scoped>

</style>