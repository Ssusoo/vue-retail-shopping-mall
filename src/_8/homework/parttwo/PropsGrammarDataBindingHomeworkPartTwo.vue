<!--
	8th, 프록스(props) 문법 숙제 Part2(상품목록을 컴포넌트로 바꾸기)
		1) 상품목록 div 태그를 자식 상품목록 컴포넌트로 옮기기
		2) 부모 컴포넌트에서 자식 컴포넌트 import하기
		3) components: {} 안에 자식 컴포넌트 등록하기
		4) 부모 컴포넌트에서 자식 컴포넌트 등록하기
		5) 등록한 <PropsGrammarDataBindingComponentHomeworkPartTwo /> 갖다쓰기
		6) 자식 컴포넌트에서 부모로부터 받을 데이터 props 설정하기
		7) 부모 컴포넌트에서 자식 컴포넌트에 넘겨줄 props 데이터 등록하기

	TODO 반복문 복습
		TODO 1) 숫자를 넣으면 숫자만큼 반복
		<a v-for="menu in 3" :key="menu"></a>

		TODO 2) 숫자(3)대신 데이터 자료형을 넣을 경우 '데이터만큼 반복'
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>

		TODO 3) 작명을 2개까지 가능하다.
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>

		TODO 4) i를 보면(0,1,2)까지 출력된 걸 확인할 수 있음.
		<a v-for="(menu, i) in menus" :key="i">{{ i }}</a>
-->

<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
	<!-- TODO 5) 등록한 <PropsGrammarDataBindingComponentHomeworkPartTwo /> 갖다 쓰기-->
	<!-- TODO 7) 부모 컴포넌트에서 자식 컴포넌트에 넘겨줄 props 데이터 등록하기 -->
	<PropsGrammarDataBindingComponentHomeworkPartTwo
			:room="rooms[i]"
			v-for="(room,i) in rooms"
			:key="room"
	/>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
// TODO 2) 부모 컴포넌트에서 자식 컴포넌트 import하기
import PropsGrammarDataBindingComponentHomeworkPartTwo from '@/_8/homework/parttwo/PropsGrammarDataBindingComponentHomeworkPartTwo'

export default {
	name: 'PropsGrammarDataBindingHomeworkPartTwo',
	components: {
		// TODO 3) components: {} 안에 자식 컴포넌트 등록하기
		PropsGrammarDataBindingComponentHomeworkPartTwo,
	},
	data() {
		return {
			// 5) 모달창 디테일(클릭했을 때)
			userClickEvent: 0,
			// 4) 클릭이벤트(신고수)
			eventHandlerCount: [0,0,0,0,0,0,0,0,0],
			// 3) 모달창 만들기
			openModalWindow: 0,
			menus: ['Home', 'Product', 'About'],
			rooms: Data,
		}
	},
	methods: {
		increase() {
			this.eventHandlerCount += 1;
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
.white-bg {
	background-color: white;
	width: 100%;
	padding: 20px;
	border-radius: 5px;
}
.discount {
	background-color: darkgreen;
	padding: 20px;
	margin-bottom: 10px;
	border-radius: 5px;
}
.menu {
	background-color: sandybrown;
	padding: 20px;
	border-radius: 5px;
	text-align: left;
}
.menu a {
	padding: 15px;
	color: black;
}
.room-img {
	margin-top: 15px;
	width: 100%;
	height: 100%;
}
</style>