<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ room[userClickEvent].id }}번</h4>
			<p>{{ room[userClickEvent].title }}</p>
			<p>{{ room[userClickEvent].content }}</p>
			<button @click="$emit('closedModal')">닫기</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CustomEventGrammarModalWindowComponentHomework',
	props: {
		userClickEvent: Number,
		room: Object,
		openModalWindow: Boolean,
	},
}
</script>