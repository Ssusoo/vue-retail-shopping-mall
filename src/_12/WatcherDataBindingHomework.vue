<!--
	12th, Watcher Grammar 숙제(입력한 데이터 초기화하기)
-->
<template>
	<div class="menu">
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>
	</div>
	<div v-for="room in rooms" :key="room">
		<img :src="room.image" class="room-img">
		<h4>{{ room.title }}</h4>
		<p>{{ room.content }}</p>
		<input v-model="month">
		<p>입력한 {{ month }} : {{ room.price * month }}원</p>
	</div>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'

export default {
	name: 'WatcherDataBindingHomework',
	data() {
		return {
			rooms: Data,
			menus: ['Home', 'Product', 'About'],
			month: 1,
		}
	},
	watch: {
		month(userData) {
			if (userData > 13) {
				alert('13이상 입력하지 마세요.')
			}
		},
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
.room-img {
	width: 100%;
	height: 100%;
	margin-top: 15px;
}
.menu {
	background-color: burlywood;
	padding: 20px;
	text-align: left;
}
.menu a {
	color: black;
	padding: 15px;
	border-radius: 5px;
}
</style>