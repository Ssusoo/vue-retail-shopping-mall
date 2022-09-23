<!--
	5th, import export 문법

		1) Jsons/oneRoom.js 데이터 설정하기
		2) import oneRoom.js 데이터 export 하기
		3) 데이터 저장소에 data 변수 선언하기
		4) 템플릿에 데이터바인딩하기
		5) HTML 태그 안의 속성 데이터 바인딩하기

		* TODO HTML 태그안의 속성 데이터바인딩할 때 :(콜론)을 넣으면 된다.
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
		<!-- TODO 5) HTML 태그 안의 속성 데이터 바인딩하기 -->
		<img :src="rooms[0].image" class="room-img">

		<!-- TODO 4) 템플릿에 데이터바인딩하기 -->
		<h4 @click="openModalWindow=true">{{ rooms[0].title}}</h4>
		<p>{{ rooms[0].price }}원</p>
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
// TODO 2) import oneRoom.js 데이터 export 하기
import data from '@/assets/jsons/oneRoom.js'

export default {
	name: 'ImportExportGrammar',
	data() {
		return {
			// TODO 3) 데이터 저장소에 data 변수 선언하기
			rooms: data,
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