<!--
	10th, 커스텀 이벤트 문법(오류난 모달창 닫기 버튼 해결하기)

	복습 메뉴얼
		1) 메뉴 만들기(v-for)
		2) Json 데이터 데이터바인딩하기
		3) 모달창 만들기
		4) 클릭이벤트(신고수)
		5) 모달창 디테일(클릭했을 때)
		6) 컴포넌트1 [
			할인팝업
		]
		7) 컴포넌트2 [
			3) 모달창 만들기
		]
		8) 컴포넌트3 [
			2) Json 데이터 데이터바인딩하기
		]
		9) 커스텀이벤트 [
			5) 모달창 디테일(클릭했을 때)
			6) 컴포넌트1(할인팝업)
			7) 컴포넌트2(3) 모달창 만들기)
			8) 컴포넌트3(2) Json 데이터 데이터바인딩하기)
		]
		TODO 10) 부모 컴포넌트, 커스텀이벤트(모달창 닫기 버튼 처리하기)
		TODO 11) 자식 컴포넌트, 커스텀이벤트(모달창 닫기 버튼 처리하기)
-->
<template>
	<div>
		<img :src="room.image" class="room-img">
<!--		<h4 @click="$emit('openModal', room.id)"></h4>-->
		<h4 @click="openModal">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
export default {
	name: 'CustomEventGrammarDataBindingHomework',
	props: {
		room: Object,
	},
	methods: {
		openModal() {
			this.$emit('openModal', this.room.id)
		}
	},
}
</script>