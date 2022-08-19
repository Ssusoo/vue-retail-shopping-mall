<template>
	<!-- TODO div 반복문 축약 -->
	<div>
		<h4 :style="styleCustom">xx 원룸</h4>
		<p>{{ price1 }}만원</p>
	</div>
	<div>
		<h4>xx 원룸</h4>
		<p>{{ price2 }}만원</p>
	</div>
</template>

<script>

export default {
	name: 'V-for',
	data() {
		return {
			price1: 10,
			price2: 5,
			styleCustom: 'color: blue',
			products: ['역삼동', '삼성동'],
		}
	}
}
</script>