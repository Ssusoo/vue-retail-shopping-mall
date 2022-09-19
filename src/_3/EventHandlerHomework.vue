<!--
	3th, 이벤트핸들러 숙제
		1) 이벤트핸들러 데이터 Array로 바꾸기
		2) 이벤트핸들러 데이터 버튼 태그에 적용시키기
-->

<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div>
		<h4>{{ products[0]}}</h4>
		<p>50만원</p>
		<!-- TODO 1) 이벤트핸들러 데이터 Array로 바꾸기 -->
		<button @click="eventHandlerCount[0]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[0] }}</span>
	</div>
	<div>
		<h4>{{ products[1]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[1]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[1] }}</span>
	</div>
	<div>
		<h4>{{ products[2]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[2]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[2] }}</span>
	</div>
</template>

<script>
export default {
	name: 'EventHandlerHomework',
	data() {
		return {
			// TODO 2) 이벤트핸들러 데이터 버튼 태그에 적용시키기
			eventHandlerCount: [0, 0, 0],
			menus: ['Home', 'Products', 'About'],
			products: ['인사동원룸', '신림동원룸', '구로동원룸']
		}
	},
	methods: {
		inCrease() {
			this.eventHandlerCount+=1;
		}
	}
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