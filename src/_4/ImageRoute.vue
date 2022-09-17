<!--
	4th, 이미지
		절대경로 : http:// ~
		상대경로 : 내가 같은 폴더의 이미지를 넣고 싶을 때
	TODO 내가 -src에서 가져올 때 경로는 './'부터 시작한다!!!

		1) 이미지 경로 지정(src)
		2) 이미지 CSS 스타일 입히기(style)
-->

<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div>
		<!-- TODO 1) 이미지 경로 지정 src -->
		<img src="./images/room0.jpg" class="room-img">
		<h4>{{ products[0]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[0]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[0] }}</span>
	</div>
	<div>
		<img src="./images/room1.jpg" class="room-img">
		<h4>{{ products[1]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[1]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[1] }}</span>
	</div>
	<div>
		<img src="./images/room2.jpg" class="room-img">
		<h4>{{ products[2]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[2]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[2] }}</span>
	</div>
</template>

<script>
export default {
	name: 'ImageRoute',
	data() {
		return {
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
/* TODO 2) 이미지 경로 지정 src */
.room-img {
	width: 100%;
	margin-top: 40px;
}
</style>