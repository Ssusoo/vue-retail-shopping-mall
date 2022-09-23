<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<h4 @click="openModalWindow = true; userClickEvent = [i]">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
	<PropsGrammerDiscountComponentHomework />

	<PropsGrammerChildrenHomework
		:rooms="rooms"
		:openModalWindow="openModalWindow"
		:userClickEvent="userClickEvent"
	/>
</template>

<script>
import PropsGrammerDiscountComponentHomework from '@/_8/PropsGrammerDiscountComponentHomework'
import data from '@/assets/jsons/oneRoom'
import PropsGrammerChildrenHomework from '@/_8/PropsGrammerChildrenHomework'

export default {
	name: 'PropsGrammerParentsHomework',
	components: {
		PropsGrammerDiscountComponentHomework,
		PropsGrammerChildrenHomework,
	},
	data() {
		return {
			userClickEvent: 0,
			openModalWindow: false,
			rooms: data,
			menus: ['Home', 'Product', 'About'],
		}
	},
}
</script>

<style>
.discount {
	background-color: red;
	padding: 20px;
	border-radius: 20px;
}

body {
	margin: 0;
}
div {
	text-align: center;
	box-sizing: border-box;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	width: 100%;
	height: 100%;
	position: fixed;
}
.white-bg {
	background-color: white;
	width: 100%;
	border-radius: 20px;
	padding: 30px;
}
.room-img {
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