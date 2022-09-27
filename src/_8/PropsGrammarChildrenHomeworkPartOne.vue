<!--
	8th, 프록스(props) 문법 숙제
-->
<template>
	<!-- 3) 팝업창 만들기 -->
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<!-- 5) 팝업창 디테일(클릭했을 때) -->
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content }}</p>
			<!-- TODO 6) 컴포넌트1(할인팝업) -->
			<PropsGrammarDiscountComponentHomework />
<!--			<button @click="openModalWindow = false">닫기</button>-->
		</div>
	</div>
</template>

<script>
import PropsGrammarDiscountComponentHomework from '@/_8/PropsGrammarDiscountComponentHomeworkPartOne'

export default {
	name: 'PropsGrammarChildrenHomework',
	components: {
		PropsGrammarDiscountComponentHomework,
	},
	// TODO 2) 자식 컴포넌트에서 props 데이터 등록하기
	props: {
		openModalWindow: Boolean,
		rooms: Array,
		userClickEvent: Number,
	},
}
</script>

<style>

</style>


<!--
	8th, 프록스(props) 문법 숙제
-->
<!--<template>-->
<!--	<div class="black-bg" v-if="openModalWindow === true">-->
<!--		<div class="white-bg">-->
<!--			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>-->
<!--			<p>{{ rooms[userClickEvent].title }}</p>-->
<!--			<p>{{ rooms[userClickEvent].content}}</p>-->
<!--			&lt;!&ndash; TODO 데이터를 수정한 거기 때문에 props가 에러가 남. &ndash;&gt;-->
<!--			&lt;!&ndash;			<button @click="openModalWindow = false">닫기</button>&ndash;&gt;-->
<!--			<DiscountBanner/>-->
<!--		</div>-->
<!--	</div>-->
<!--</template>-->

<!--<script>-->
<!--export default {-->
<!--	name: 'PropsGrammarChildrenHomework',-->
<!--	// TODO 2) 자식 컴포넌트에서 props 데이터 등록하기-->
<!--	props: {-->
<!--		// 데이터이름: 자료형 이름(Number, String, Array, Object ... etc)-->
<!--		rooms: Array,-->
<!--		userClickEvent: Number,-->
<!--		// TODO 위에 처럼 받아온 props는 수정했기 때문에 에러가 남.-->
<!--		openModalWindow: Boolean,-->
<!--	}-->
<!--}-->
<!--</script>-->

<!--<style>-->

<!--</style>-->