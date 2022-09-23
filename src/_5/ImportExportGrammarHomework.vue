<!--
	5th, import export 문법 숙제
		1) 반복문(v-for)을 이용해 처리하기
-->

<template>
	<div class="black-bg" v-if="detailModalWindow === true">
		<div class="white-bg">
			<h4>상세페이지</h4>
			<p>상세페이지 내용</p>
			<button @click="detailModalWindow = false">닫기</button>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu,i) in menus" :key="i">{{ menu }}</a>
	</div>
	<div v-for="(room, i) in rooms" :key="i">
		<!-- TODO 이렇게 아님!!!
			<img :src="room[i].image">
			<h4>{{ room[i].price }}</h4>
		-->
		<!-- TODO 1) 반복문(v-for)을 이용해 처리하기 -->
		<img :src="room.image" class="room-img">
		<h4 @click="detailModalWindow = true">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
import data from '@/assets/jsons/oneRoom.js'
export default {
	name: 'ImportExportGrammarHomework',
	data() {
		return {
			detailModalWindow: false,
			rooms: data,
			menus: ['Home', 'Product', 'About'],
		}
	},
}
</script>

<style>
body {
	text-align: center;
	margin: 0;
}
div {
	box-sizing: border-box;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	width: 100%;
	height: 100%;
	padding: 20px;
}
.white-bg {
	width: 100%;
	background-color: white;
	padding: 20px;
	border-radius: 5px;
}
.room-img {
	margin-top: 15px;
	width: 100%;
	height: 100%;
}
.menu {
	background-color: sandybrown;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	padding: 10px;
	color: black;
}
</style>