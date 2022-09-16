<!--
	2th, 반복문 숙제
		TODO 상품목록도 축약해보자!!!
-->
<template>
	<!--2th, 반복문 수업 내용 -->
	<div class="menu">
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>
	</div>

	<!-- TODO 반복문 사용전 -->
<!--	<div>-->
<!--		<h4>{{products[0]}}</h4>-->
<!--		<p>50만원</p>-->
<!--	</div>-->
<!--	<div>-->
<!--		<h4>{{products[1]}}</h4>-->
<!--		<p>40만원</p>-->
<!--	</div>-->

	<!-- TODO 반복문 사용후 -->
	<div v-for="(product, i) in products" :key="i">
		<h4>{{product}}</h4>
		<p>50만원</p>
	</div>
</template>

<script>
export default {
	name: 'ForHomework',
	data() {
		return {
			menus: ['Home', 'Products', 'About'],
			products: ['역삼동원룸', '오류동원룸', '신림동원룸'],
		}
	}
}
</script>

<style>
.menu {
	background: burlywood;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>