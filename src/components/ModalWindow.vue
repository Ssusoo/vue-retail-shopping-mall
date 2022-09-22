<!--
	8th, Props 문법 (모달창 컴포넌트 만들기)
		실제 ModalWindowComponent.vue에 있는 모달창을 컴포넌트로 바꾸는 작업에서
		데이터 바인딩한 데이터가 실제 모달 컴포넌트에 없기 때문에 제목을 눌러도 얼리지 않는 오류가 생김

		TODO 어떻게 해결할 수 있을까?
		1) ModalWindowComponent.vue에서 데이터저장소에 저장한 데이터를 복붙해올까? 그건 별로다
		2) 데이터는 한 곳에 보관하돼 필요하면 데이터를 가져다 쓰는 방식이 제일 좋다.

		TODO 보관한 데이터를 어떻게 가져올까?
			그게 바로 props 문법이다.

		TODO props는 read-only임.
			받아온 걸 수정하면 안된다.
			그 말은 openModalWindow = false(x) 수정된 상태이기 때문에 안되는 거임.
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ rooms[userClickEvent].id }}번</h4>
			<p>{{ rooms[userClickEvent].title }}</p>
			<p>{{ rooms[userClickEvent].content}}</p>
			<!-- TODO 데이터를 수정한 거기 때문에 props가 에러가 남. -->
<!--			<button @click="openModalWindow = false">닫기</button>-->
			<DiscountBanner/>
		</div>
	</div>
</template>

<script>
export default {
	name: 'ModalWindow',
	// TODO 2) 자식 컴포넌트에서 props 데이터 등록하기
	props: {
		// 데이터이름: 자료형 이름(Number, String, Array, Object ... etc)
		rooms: Object,
		userClickEvent: Number,
		// TODO 위에 처럼 받아온 props는 수정했기 때문에 에러가 남.
		openModalWindow: Boolean,
	}
}
</script>

<style>

</style>