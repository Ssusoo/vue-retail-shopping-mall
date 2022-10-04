<!--
	7th, 컴포넌트 만들기
		: 긴 HTMl을 한 단어로 줄일 수 있는 문법

		1) 컴포넌트를 위해 홍보 UI 만들기(할인 배너 만들기)
			: 엄청 길다고 가정해보고 그걸 컴포넌트로 만들어 줄 거임.
			* TODO 실제 HTML 코드를 한 글자로 축약할 수 있다면? <DiscountBanner/>
				-> 그게 바로 컴포넌트 문법이다.
		2) 할인 배너 CSS 스타일 주기
		3) 컴포넌트 문법을 사용하기 위해서 component 디렉토리에서 HTML을 만들어 주어야 함.
		4) 할인 배너 HTML 태그 Discount.vue로 옮기기
		5) TODO DiscountBanner.vue(컴포넌트로)로 옮긴 할인 배너 Component.vue에서 사용하는 방법
			5-1) DiscountBanner.vue import하기
			5-2) Components: {} 안에 등록하기
			5-3) 등록한 <DiscountBanner/> 갖다 쓰기

	* TODO Question? 굳이 이런 컴포넌트 문법을 왜 쓸까?
		1) 아름다워서
		2) 재사용성이 쉬움
		3) 컴포넌트로 축약을 했으면 20%에서 30%로 수정할 때
			컴포넌트만 바꿔주면 100개를 바꾸는 게 아니라 하나만 끝나면 된다.

-->
<template>
	<!-- TODO 1) 컴포넌트를 위해 홍보 UI 만들기(엄청 길다고 가정해보자) -->
	<!-- TODO 3) 아래 할인 배너를 Dicount.vue로 옮기기-->
<!--	<div class="discount">-->
<!--		<h4>지금결제하면 20% 할인</h4>-->
<!--	</div>-->
	<!-- TODO 5-3) 등록한 <DiscountBanner/> 갖다 쓰기 -->
	<DiscountBanner/>

	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content}}</p>
			<button @click="openModalWindow = false">닫기</button>
			<!-- TODO *재사용성이 용이한 컴포넌트 * -->
			<DiscountBanner/>
		</div>
	</div>

	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div v-for="(room, i) in rooms" :key="i">
		<img :src="room.image" class="room-img">
		<h4 @click="openModalWindow = true; userClickEvent = [i]">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
// TODO 5-1) Discount.vue import하기
import DiscountBanner from "@/_8/components/DiscountBanner";

export default {
	name: 'Component',
	components: {
		// TODO 5-2) Components: {} 안에 등록하기
		DiscountBanner,
		// 작명 : import Name
		// DiscountBanner: DiscountBanner,
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
/* TODO 2) 할인 배너 CSS 스타일 주기 */
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