<template>
	<div>
		<Head>
			<Title>Store | {{ product.title }}</Title>
			<Meta name="decription" :content="product.description" />
		</Head>
		<ProductInfo :product="product"/>
	</div>
</template>


<script setup>
	const { id } = useRoute().params
	const uri = 'https://fakestoreapi.com/products/' + id;

	//fetch the product
	const { data: product } = await useFetch(uri);

	if (!product.value) {
		throw createError({ statusCode: 404, statusMessage: 'Product not found', fatal: true })
	}

	definePageMeta({ layout: "forproduct" })
</script>


<style scoped>

</style>