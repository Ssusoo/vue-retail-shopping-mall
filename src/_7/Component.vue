<!--
	7th, 컴포넌트 만들기
-->

<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : 번</h4>
			<p>{{ rooms[userClickEvent]}}</p>
			<p>내용</p>
			<button @click="openModalWindow = false">닫기</button>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<h4 @click="openModalWindow = true; userClickEvent[i]">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'

export default {
	name: 'Component',
	data() {
		return {
			userClickEvent: 0,
			eventHandlerCount: [0, 0, 0],
			openModalWindow: false,
			rooms: Data,
			menus: ['Home', 'Product', 'About'],
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
	text-align: center;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	padding: 20px;
	width: 100%;
	height: 100%;
	position: fixed;
}
.white-bg {
	background-color: white;
	border-radius: 5px;
	padding: 15px;
}
.room-img {
	width: 100%;
}
.menu {
	text-align: left;
	background-color: burlywood;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>