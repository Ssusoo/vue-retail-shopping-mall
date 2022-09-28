<!--
	12th, Watcher Grammar 숙제(입력한 데이터 초기화하기)
		TODO 해결방법 isNaN() 함수 사용하기 !!!
			자바스크립트로 숫자인지 문자인지 판단하기 위해서
			isNaN() 함수 안에 숫자를 입력하면 false, 글자를 입력하면 true가 나온다.
			'123'이라는 숫자인척하는 글자도 false가 나옴


		TODO 1) 숫자만 입력하라는 alert() 창 띄우기
		TODO 2) month의 초기값을 1로 다시 초기화 하기
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
			// TODO false면 숫자, true면 문자
			if (isNaN(userData) == true) {
				// TODO 1) 숫자만 입력하라는 alert() 창 띄우기
				alert('문자를 입력하지 마세요.')
				// TODO 2) month의 초기값을 1로 다시 초기화 하기
				this.month = 1;
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