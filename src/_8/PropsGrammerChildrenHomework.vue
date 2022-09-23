<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content}}</p>
			<!-- TODO 데이터를 수정한 거기 때문에 props가 에러가 남. -->
			<!--			<button @click="openModalWindow = false">닫기</button>-->
			<DiscountBanner/>
		</div>
	</div>
</template>

<script>
export default {
	name: 'PropsGrammerChildrenHomework',
	// TODO 2) 자식 컴포넌트에서 props 데이터 등록하기
	props: {
		// 데이터이름: 자료형 이름(Number, String, Array, Object ... etc)
		rooms: Array,
		userClickEvent: Number,
		// TODO 위에 처럼 받아온 props는 수정했기 때문에 에러가 남.
		openModalWindow: Boolean,
	}
}
</script>

<style>

</style>