<!--
	4th, 모달창
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<div>
		<img :src="require(`@/assets/images/room0.jpg`)" class="room-img">
		<h4>{{ products[0] }}</h4>
		<p>50만원</p>
	</div>
	<div>
		<img :src="require(`@/assets/images/room1.jpg`)" class="room-img">
		<h4>{{ products[1] }}</h4>
		<p>50만원</p>
	</div>
	<div>
		<img :src="require(`@/assets/images/room2.jpg`)" class="room-img">
		<h4>{{ products[2] }}</h4>
		<p>50만원</p>
	</div>

</template>

<script>
export default {
	name: 'ModalWindow',
	data() {
		return {
			menus: ['Home', 'Product', 'About'],
			products: ['신림동원룸', '구로동원룸', '역삼동원룸']
		}
	},
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

/* 이미지 경로 지정 src */
.room-img {
	width: 100%;
	margin-top: 40px;
}
</style>