<!--
	8th, 프록스(props) 문법
		모달창 컴포넌트부터 만들자
			1) DiscountBanner.vue import하기
			2) Components: {} 안에 등록하기
			3) 등록한 <DiscountBanner/> 갖다 쓰기

		TODO Props 문법
			부모와 자식 컴포넌트로 나눌 수 있는데,
			자식 컴포넌트가 부모가 갖고 있는 데이터를 쓰려면
			props로 데이터를 전송해야 한다.

		TODO props로 자식 컴포넌트에게 데이터 보내는 방법
			1) 데이터 전송하기(부모 컴포넌트에서)
				v-bin: 혹은 세미콜론 :데이터="데이터"
			2) 데이터 등록하기(자식 컴포넌트에서)
			3) 데이터 갖다쓰기(자식 컴포넌트에서)

		TODO 꿀팁 !!!
			애초에 자식 컴포넌트에 데이터를 저장하면 되는 거 아닌가 할 수 있지만
			부모도 쓰는 데이터라면 애초에 "부모 컴포넌트에 만들어주는 게 좋음".
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<!-- TODO 3) 등록한 <DiscountBanner/> 갖다 쓰기 -->
	<ModalWindow
			:rooms="rooms"
			:userClickEvent="userClickEvent"
			:openModalWindow="openModalWindow"
	/>

	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<h4 @click="openModalWindow = true; userClickEvent = [i]">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
		<DiscountBanner/>
	</div>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import DiscountBanner from "@/components/DiscountBanner";
// TODO 1) ModalWindow.vue import하기
import ModalWindow from "@/components/ModalWindow";

export default {
	name: 'PropsGrammar',
	components: {
		// TODO 2) Components: {} 안에 등록하기
		ModalWindow,
		DiscountBanner,
	},
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
.discount {
	background-color: aqua;
	padding: 10px;
	margin: 10px;
	border-radius: 5px;
}
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