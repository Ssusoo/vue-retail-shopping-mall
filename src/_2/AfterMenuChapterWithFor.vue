<!--
	2-2th, 반복문으로 메뉴 만들기(반복문 사용후)
		반복문 문법
			HTML 태그 안에 <태그 v-for="?? in ??>
			1) <태그 v-for="작명 in 횟수">
			2) <태그 v-for="작명 in 횟수" :key="작명">
				작명 in '횟수'에 TODO 데이터도 집어넣을 수 있다.
			3) <태그 v-for="작명 in 데이터" :key="작명">{{ 작명 }}</태그>
				횟수(3) 대신 데이터 자료형을 넣고
				TODO 태그 사이에 데이터바인딩 반복문의 '작명'을 해주면
				TODO 데이터 자료형만큼 반복문이 작동한다.
			4) TODO 작명을 두 개까지 할 수 있다.
				<태그 v-for="(작명, i) in 데이터" :key="작명">{{ 작명 }}</태그>
-->

<template>
	<div class="menu">
		<!-- TODO 1) 숫자를 넣으면 숫자만큼 반복 -->
		<a v-for="menu in 3" :key="menu"></a>

		<!-- TODO 2) 숫자(3)대신 데이터 자료형을 넣을 경우 '데이터만큼 반복' -->
		<a v-for="menu in menus" :key="menu">{{ menu }}</a>

		<!-- TODO 3) 작명을 2개까지 가능하다. -->
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>

		<!-- TODO 4) i를 보면(0,1,2)까지 출력된 걸 확인할 수 있음. -->
		<a v-for="(menu, i) in menus" :key="i">{{ i }}</a>
	</div>
</template>

<script>
export default {
	name: 'AfterMenuChapterWithFor',
	data() {
		return {
			// TODO 2-2) 데이터 자료형
			menus: ['Home', 'Products', 'About']
		}
	},
}
</script>

<style>
.menu {
	background: burlywood;
	border-radius: 5px;
	padding: 10px;
}
.menu a {
	color: black;
	padding: 5px;
}
</style>