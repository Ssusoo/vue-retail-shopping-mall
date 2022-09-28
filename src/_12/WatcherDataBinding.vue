<!--
	12th, Watcher Grammar(데이터 감시자)
		데이터를 감시하는 함수라고 생각하면 된다.
			1) 데이터가 제대로 변화가 되고 있는지 체크한다.
			2) 이상한 데이터가 들어오지 않았는지 확인한다.
			* 사용자의 input이면 Watcher로 감시한다.

	TODO 1) 스크립트에 watch: { 감시할 데이터(){} } 만들기
		숫자를 입력했는지 문자를 입력했는지 감시하고 싶으면
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
	name: 'WatcherDataBinding',
	data() {
		return {
			rooms: Data,
			menus: ['Home', 'Product', 'About'],
			month: 1,
		}
	},
	watch: {
		// TODO 1) 스크립트에 watch: { 감시할 데이터(){} } 만들기
		month(userData) { // 사용자가 입력한 a라는 정보가 아래 a로 출련된다고 생각
			//  TODO *month라는 데이터가 변할 때마다 여기 있는 코드가 실행된다.
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