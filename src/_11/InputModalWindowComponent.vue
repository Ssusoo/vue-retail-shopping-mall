<!--
	11th, Input(v-model)
		<input
			입력할 때마다 뭐 실행해주세요.
			@input="",
		>
		<input
			입력하고 커서다른데 찍으면 뭐 실행해주세요.
			@change="",
		>
		$event == 자바스크립트에서 e라는 파라미터랑 같은 역할을 한다.
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ room[userClickEvent].id }}번</h4>
			<p>{{ room[userClickEvent].title }}</p>
			<!-- TODO -->
			<input @input="month= $event.target.value">
			<!-- TODO -->
			<p>{{ month }}개월 선택함 : {{ room[userClickEvent].content }}</p>
			<button @click="$emit('closedModal')">닫기</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'InputModalWindowComponent',
	data() {
		return {
			// TODO
			month: 1,
		}
	},
	props: {
		openModalWindow: Boolean,
		room: Object,
		userClickEvent: Number,
	},
}
</script>