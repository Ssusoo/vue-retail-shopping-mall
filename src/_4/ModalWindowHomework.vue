<!--
	4ht, 모달창 숙제
		닫기 버튼 만들기
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상세페이지</h4>
			<p>상세페이지 내용</p>
			<!-- TODO 모달창 닫기 버튼 -->
			<button  @click="openModalWindow = false">닫기</button>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu,i) in menus" :key="i">{{ menu }}</a>
	</div>
	<div>
		<img :src="require('@/assets/images/room0.jpg')" class="room-img">
		<h4 @click="openModalWindow = true">{{ products[0] }}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[0] += 1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[0] }}</span>
	</div>
	<div>
		<img :src="require('@/assets/images/room1.jpg')" class="room-img">
		<h4 @click="openModalWindow = true">{{ products[1] }}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[1] += 1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[1] }}</span>
	</div>
	<div>
		<img :src="require('@/assets/images/room2.jpg')" class="room-img">
		<h4 @click="openModalWindow = true">{{ products[2] }}</h4>
		<p>50만원</p>
		<button @click="eventHandlerCount[2 ]+= 1">허위매물신고</button> <span>신고수 : {{ eventHandlerCount[2] }}</span>
	</div>

<!--	<div v-for="(product, i) in products" :key="i">-->
<!--		<h4>{{ product }}</h4>-->
<!--		<p>50만원</p>-->
<!--	</div>-->
</template>

<script>
export default {
	name: 'ModalWindowHomework',
	data() {
		return {
			eventHandlerCount: [0, 0, 0],
			openModalWindow: false,
			products: ['인사동원룸', '신림동원룸', '구로동원룸'],
			menus: ['Home', 'Product', 'About']
		}
	},
	methods: {
		increase() {
			this.eventHandlerCount +=1 ;
		}
	}
}
</script>

<style>
body {
 margin: 0;
}
div {
	box-sizing: border-box;
}
.black-bg {
	width: 100%;
	height: 100%;
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	padding: 20px;
}
.white-bg {
	width: 100%;
	background-color: white;
	padding: 20px;
	border-radius: 10px;
}

.room-img {
	padding-top: 25px;
	width: 100%;
}
.menu {
	background-color: burlywood;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>

