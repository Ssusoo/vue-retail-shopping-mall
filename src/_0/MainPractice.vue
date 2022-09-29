<!--
	final, 부동산 쇼핑몰 전체 복습
		복습 메뉴얼
			1) 메뉴 만들기(v-for)
			2) Json 데이터 데이터바인딩하기
			3) 모달창 만들기
			4) 클릭이벤트(신고수)
			5) 모달창 디테일(클릭했을 때)
			6) 컴포넌트1(할인팝업)
			7) 컴포넌트2(3) 모달창 만들기)
			8) 컴포넌트3(2) Json 데이터 데이터바인딩하기)
			9) 커스텀 이벤트 문법(오류난 모달창 해결하기)
			10) Input(v-model)
			11) Watcher : alert창 만들기
			12) Watcher : 데이터 초기화 시키기
			13) 정렬 버튼 만들기 [
				원본 데이터가 보존되지 않는 sort() 함수
				원본 데이터가 보존되는 map() / filter() 함수
			]
			14) 라이프사이클 훅으로 할인쿠폰 컴포넌트 2초후에 없애기
			15) 라이프사이클 훅으로 할인쿠폰 컴포넌트 1초마다 1%씩 내리기
-->
<template>
	<div class="menu">
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>
	</div>
	<MainDataBindingComponent
		:room="rooms[i]"
		v-for="(room, i) in rooms"
		:key="room"
	/>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import MainDataBindingComponent from '@/_0/components/MainDataBindingComponent'

export default {
	name: 'MainPractice',
	components: {
		MainDataBindingComponent,
	},
	data() {
		return {
			rooms: Data,
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
	text-align: center;
}
.black-bg {
	background-color: rgba(0,0,0,0.5);
	position: fixed;
	width: 100%;
	height: 100%;
}
.room-img {
	width: 100%;
	height: 100%;
	margin-bottom: 10px;
}
.menu {
	text-align: left;
	background-color: sandybrown;
	padding: 20px;
}
.menu a {
	padding: 15px;
}
</style>