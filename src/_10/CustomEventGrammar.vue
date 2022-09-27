<!--
	10th, 커스텀 이벤트 문법(오류난 모달창 해결하기)

	복습 메뉴얼
		1) 메뉴 만들기(v-for)
		2) Json 데이터 데이터바인딩하기
		3) 모달창 만들기
		4) 클릭이벤트(신고수)
		5) 모달창 디테일(클릭했을 때)
		6) 컴포넌트1(할인팝업)
		7) 컴포넌트2(3) 모달창 만들기)
		8) 컴포넌트3(2) Json 데이터 데이터바인딩하기)

		TODO 부모 컴포넌트의 있는 데이터를 어떻게 사용할까?
			*props에서 보낸 데이터는 수정이 금지되어 있기 때문에 못했었다.
			해결방법은
				1) 자식 컴포넌트에서 부모 컴포넌트로 메시지를 보내야 해결할 수 있다.
				2) 부모 컴포넌트에서 자식 컴포넌트 메시지 수신하기 !!!
					메시지 보내는 법은 $(달러표시) : vue만의 특별한 변수라고 생각하자!!!
					$emit('작명', 데이터)
				3) 자식이 보낸 데이터는 $event 변수에 담겨 있기 때문에 부모 컴포넌트에서는
					$event를 통해 자식 컴포넌트가 보낸 데이터 받기
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<ModalWindowComponent
			:room="rooms"
			:open-modal-window="openModalWindow"
			:user-click-event="userClickEvent"
	/>

	<!-- TODO 2-1) 부모 컴포넌트에서 자식 컴포넌트 메시지 수신하기 !!! -->
	<!-- TODO 2-2) 자식 컴포넌트에서 보낸 데이터를 $event를 통해 부모 컴포넌트에서 받기 -->
	<!-- TODO 3) 자식이 보낸 데이터는 $event 변수에 담겨 있기 때문에 부모 컴포넌트에서는 $event를 통해 자식 컴포넌트가 보낸 데이터 받기 -->
	<DataBindingComponent
			:room="rooms[i]"
			v-for="(room,i) in rooms"
			:key="room"
			@openModal="openModalWindow = true; userClickEvent = $event"
	/>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import DataBindingComponent from '@/_10/DataBindingComponent'
import ModalWindowComponent from '@/_10/ModalWindowComponent'

export default {
	name: 'CustomEventGrammar',
	components: {
		DataBindingComponent,
		ModalWindowComponent,
	},
	data() {
		return {
			userClickEvent: 0,
			openModalWindow: false,
			menus: ['Home', 'Product', 'About'],
			rooms: Data,
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
	background-color: rgba(0, 0, 0, 0.5);
	position: fixed;
	width: 100%;
	height: 100%;
}

.white-bg {
	background-color: white;
	width: 100%;
	border-radius: 10px;
	padding: 15px;
}

.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
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