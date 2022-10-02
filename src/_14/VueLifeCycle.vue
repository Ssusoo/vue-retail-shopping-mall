<!--
	14th, 뷰 라이프 사이클
		컴포넌트는 웹페이지에 표시되기까지 일련의 스탭을 거친다.
		그 스탭을 가리켜 '라이프 사이클'이라고 한다.

		1) Create 단계 : 데이터만 존재하는 단계
		2) Mount 단계 : <template> 사이에 있던 걸 실제 HTML로 바꿔 줌
		3) 컴포넌트 생성 단계 : index.html에 장착 된다.
		4) Update 단계 : data가 변하면 HTML 이 재렌더링된다고 했었는데,
				실제로 컴포넌트가 재렌더링된다. 그걸 'Update'라고 한다.
		5) Unmount 단계 : 강제를 삭제하면 컴포넌트가 삭제된다.

		* TODO 뷰 라이프 사이클을 배우는 이유?
			뷰 라이프 사이클은 컴포넌트들이 생명주기에 따라 생성되고 사라지는데,
			컴포넌트 단계 중간중간에 'Lifecycle Hook'을 걸어서 중간에 원하는 코드를 실행가능하게 할 수 있다.
			예를 들어 컴포넌트가 Mount 단계(실제 HTML로 바꾸는 단계)로 넘어가기 전에 'Lifecycle Hook'을 통해 이것 좀 실행해주세요.
			또 다른 예는 Update 단계(재렌더링) 전에 'Lifecycle Hook'을 통해 이것 좀 실행해주세요.
			TODO * 혹은 Create 단계(데이터만 존재하는 단계)에서 Lifecycle Hook을 사용할 수도 있음.
			TODO 결론, Lifecycle Hook을 사용하기 위해 'Lifecycle' 개념을 배우는 거다.

		TODO Lifecycle Hook 사용하는 방법
			1) <script> 사이사이에 딴지를 걸어 사용할 수 있다. mounted() {} -> before~
			2) Discount 컴포넌트가 2초후에 사라지게 만들기
				2-1) UI 현재 데이터(상태) 만들기
				2-2) 그거에 따라 보이는지 안보이는지(setTimeout 함수사용하기)

		TODO * 서버에서 데이터를 가져올 때도 Lifecycle Hook 안에 코드를 짠다.

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
	<VueLifeCycleDiscountComponent
		v-if="showDiscount === true"
	/>
</template>

<script>
import VueLifeCycleDiscountComponent from '@/_14/component/VueLifeCycleDiscountComponent'
export default {
	name: 'VueLifeCycle',
	components: {
		VueLifeCycleDiscountComponent,
	},
	// TODO 1) <script> 사이사이에 딴지를 걸어 사용할 수 있다. mounted() {} -> before~
	//  mount 후에 뭔가 실행하고 싶을 때
	mounted() {
		// TODO 2-2) 그거에 따라 보이는지 안보이는지(setTimeout 함수사용하기)
		//  그냥 함수가 아니라 ()=>{} (자바스크립트에서 제공하는 에러 function임.
		setTimeout(()=> {
			this.showDiscount = false;
		}, 2000);
	},
	// TODO mount 되기 전에 뭔가 실행하고 싶을 때
	beforeMount() {
	},
	data() {
		return {
			// TODO 2-1) UI 현재 데이터(상태) 만들기
			showDiscount: true,
			menus: ['Home', 'Product', 'About'],
		}
	},
}
</script>

<style>
body {
	margin: 0px;
}
.menu{
	background-color: aquamarine;
	padding: 20px;
	text-align: left;
}
.menu a {
	padding: 15px;
}
.discount {
	text-align: center;
	background-color: burlywood;
	padding: 20px;
	border-radius: 5px;
}
</style>