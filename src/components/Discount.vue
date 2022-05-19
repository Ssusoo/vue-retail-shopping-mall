<template>

	<!-- 할인 배너 -->
	<div class="discount">
		<h4>지금 결제하면 20% 할인</h4>
	</div>

</template>

<script>

export default {
	// eslint-disable-next-line vue/multi-word-component-names
	name: 'Discount'

}
</script>

<style>
.discount{
	background: aliceblue;
	padding: 10px; /*색깔의 크기*/
	margin: 10px; /*네모 박스 기준으로 사이 간격 */
	border-radius: 5px;
}
</style>