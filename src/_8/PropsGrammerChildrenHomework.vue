<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content }}</p>
<!--			<button @click="openModalWindow = false">닫기</button>-->
		</div>
	</div>
</template>

<script>
export default {
	name: 'PropsGrammerChildrenHomework',
	props: {
			rooms: Object,
			userClickEvent: Number,
			openModalWindow: Boolean,
	}
}
</script>

<style>

</style>