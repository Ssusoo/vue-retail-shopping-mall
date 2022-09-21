<!--
	7th, 컴포넌트 만들기
-->

<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>
</template>

<script>
export default {
	name: 'Component',
	data() {
		return {
			menus: ['Home', 'Product', 'About'],
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
}
.menu {
	text-align: left;
	background-color: burlywood;
	padding: 15px;
	border-radius: 5px;
}
.menu a {
	color: black;
	padding: 10px;
}
</style>