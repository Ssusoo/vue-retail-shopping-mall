<!--
	3th, 이벤트 핸들러
		HTML 클릭시 코드를 실행하는 법
			버튼을 눌렀을 때 자바스크립트 실행하기
				전통방식 : onclick="작명"
				Vue 방식 : v-on:click="작명" or @click="작명"

		TODO 오늘 할 것은 버튼을 눌렀을 때 '신고수'를 +1씩 증가시키기
			eventHandlerCount++ or eventHandlerCount+=1

		1) 데이터로, 버튼 이벤트 핸들러 만들기
		2) 함수로, 버튼 이벤트 핸들러 만들기
-->
<template>
	<!-- 반복문으로 만든 메뉴 -->
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div>
		<h4>{{ products[0] }}</h4>
		<p>50만원</p>
		<!-- TODO 1) 버튼식 이벤트 핸들러 만들기 -->
		<!--		<button>허위매물신고</button> <span>신고수 : 0</span>-->
<!--		<button @click="eventHandlerCount++">허위매물신고</button> <span>신고수 : {{ eventHandlerCount }}</span>-->

		<!-- TODO 2) 함수를 만들어서 이벤트 핸들러 동작 시키기 -->
		<button @click="inCrease">허위등록신고</button> <span>신고수 : {{ eventHandlerCount }}</span>
	</div>
	<div>
		<h4>{{ products[1] }}</h4>
		<p>55만원</p>
	</div>
	<div>
		<h4>{{ products[2] }}</h4>
		<p>80만원</p>
	</div>

	<!-- 반복문으로 만든 상품목록 -->
	<!--	<div v-for="(product, i) in products" :key="i">-->
	<!--		<h4>{{product}}</h4>-->
	<!--		<p>50만원</p>-->
	<!--	</div>-->
</template>

<script>
export default {
	name: 'EventHandler',
	data() { // 데이터저장소 시작
		return {
			menus: ['Home', 'Products', 'About'],
			products: ['역삼동원룸', '천호동원룸', '신림동원룸'],
			// TODO 1-2) 신고수 데이터
			eventHandlerCount: 0,
		}
	},// 데이터저장소 끝
	// TODO 2-2) 함수만들기(함수 앞에 this == data.)
	methods: {
		inCrease() {
			this.eventHandlerCount += 1;
		}
	},
}
</script>

<style>
.menu {
	background: burlywood;
	padding: 15px;
	border-radius: 5px;
}

.menu a {
	color: black;
	padding: 10px;
}
</style>