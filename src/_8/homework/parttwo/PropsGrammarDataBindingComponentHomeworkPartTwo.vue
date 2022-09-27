<!--
	8th, 프록스(props) 문법 숙제 Part2(상품목록을 컴포넌트로 바꾸기)
-->
<template>
	<!--
		TODO v-for이 있기 때문에 div 하나를 축약한 게 아니라
				div 6개를 축약한 거임(이렇게 하면 안됨)
				* v-for을 지워주기
	-->
<!--	<div v-for="(room, i) in rooms" :key="i">-->
	<!-- TODO 1) 상품목록 div 태그를 자식 상품목록 컴포넌트로 옮기기 -->
	<div>
		<img :src="room.image" class="room-img">
		<!-- @click="openModalWindow = true; userClickEvent = [i]"(삭제 먼저함 추후에 다시 봄)-->
		<h4>{{ room.title}}</h4>
		<p>{{ room.price}}원</p>
	</div>
</template>

<script>

export default {
	name: 'PropsGrammarDataBindingComponentHomeworkPartTwo',
	// TODO 6) 자식 컴포넌트에서 부모로부터 받을 데이터 props 설정하기
	props: {
		room: Array,
		openModalWindow: Boolean,
		userClickEvent: Number,
	},
}
</script>
