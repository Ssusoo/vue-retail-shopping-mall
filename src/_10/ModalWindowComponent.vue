<!--
	10th, 커스텀 이벤트 문법(오류난 모달창 해결하기)

	TODO 부모 컴포넌트의 있는 데이터를 어떻게 사용할까?
			*props에서 보낸 데이터는 수정이 금지되어 있기 때문에 못했었다.
			해결방법은
				1) 자식 컴포넌트에서 부모 컴포넌트로 메시지를 보내야 해결할 수 있다.
				2) 부모 컴포넌트에서 자식 컴포넌트 메시지 수신하기 !!!
			메시지 보내는 법은 $(달러표시) : vue만의 특별한 변수라고 생각하자!!!
			$emit('작명', 데이터)
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ room[userClickEvent].id }}번</h4>
			<p>{{ room[userClickEvent].title }}</p>
			<p>{{ room[userClickEvent].content }}</p>
		</div>
	</div>
</template>

<script>
export default {
	name: 'ModalWindowComponent',
	props: {
		openModalWindow: Boolean,
		room: Object,
		userClickEvent: Number,
	},
}
</script>