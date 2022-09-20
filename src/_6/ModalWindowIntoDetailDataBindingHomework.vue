<!--
	6th, 모달창 내에 상세페이지 만들기 숙제(이름과 내용 넣어보기)

	TODO 동적인 UI 만드는 법
		1) UI 상태를 저장해둘 데이터 만들기
		2) 데이터에 따라 HTML 어떻게 보일지
		3) UI 조작하는 버튼 만들기
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<!-- TODO 2) 데이터에 따라 HTML 어떻게 보일지 -->
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content }}</p>
			<button @click="openModalWindow = false">닫기</button>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<!-- TODO 3) UI 조작하는 버튼 만들기 -->
		<!--
			TODO * userClickEvent=i를 뺄 경우 2)에서는 각각의 title을 클릭해도 0번만 나옴
				이유는 1) UI 상태를 저장해둘 데이터의 기본값이 0이기 때문에 !!!
		-->
		<h4 @click="openModalWindow = true; userClickEvent = i">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
import data from '@/assets/jsons/oneRoom'

export default {
	name: 'ModalWindowIntoDetailDataBindingHomework',
	data() {
		return {
			// TODO 1) UI 상태를 저장해둘 데이터 만들기
			userClickEvent: 0,
			openModalWindow: false,
			rooms: data,
			menus: ['Home', 'Product', 'About'],
		}
	},
}
</script>

<style>
body {
	margin: 0;
}
div {
	text-align: center;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	width: 100%;
	height: 100%;
	position: fixed;
	padding: 15px;
}
.white-bg {
	background-color: white;
	padding: 10px;
	border-radius: 5px;
	width: 100%;
}
.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
}
.menu {
	text-align: left;
	background-color: sandybrown;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	padding: 10px;
	color: black;
}
</style>