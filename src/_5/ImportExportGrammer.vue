<!--
	5th, import export 문법
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상세페이지</h4>
			<p>상세페이지 내용</p>
			<button @click="openModalWindow=false">닫기</button>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu,i) in menus" :key="i">{{ menu }}</a>
	</div>
	<div>
		<img :src="require('@/assets/images/room0.jpg')" class="room-img">
		<h4 @click="openModalWindow=true">{{ products[0]}}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[0]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[0] }}</span>
	</div>
	<div>
		<img :src="require('@/assets/images/room1.jpg')" class="room-img">
		<h4 @click="openModalWindow=true">{{ products[1]}}</h4>
		<p>60만원</p>
		<button @click="eventHandlerCount[1]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[1] }}</span>
	</div>
	<div>
		<img :src="require('@/assets/images/room2.jpg')" class="room-img">
		<h4 @click="openModalWindow=true">{{ products[2]}}</h4>
		<p>70만원</p>
		<button @click="eventHandlerCount[2]+=1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[2] }}</span>
	</div>
</template>

<script>
export default {
	name: 'ImportExportGrammer',
	data() {
		return {
			openModalWindow: false,
			eventHandlerCount: [0, 0, 0,],
			products: ['인사동원룸', '신림동원룸', '구로동원룸'],
			menus: ['Home', 'Product', 'About']
		}
	},
}
</script>

<style>
body {
	margin: 0px;
}
div {
	box-sizing: border-box;
	text-align: center; /* Quirks Mode 를 위한 가운데 정렬 */
}
.black-bg {
	width: 100%;
	height: 100%;
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	padding: 20px;
}
.white-bg {
	background-color: white;
	width: 100%;
	padding: 20px;
	border-radius: 5px;
}
.room-img {
	margin-top: 25px;
	width: 100%;
}
.menu {
	background-color: burlywood;
	padding: 15px;
	border-radius: 5px;
	text-align: left;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>