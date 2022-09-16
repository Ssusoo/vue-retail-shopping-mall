<!--
	2-1th, 반복문으로 넘어가기 전, 메뉴 만들기(반복문 사용전)
-->
<template>
	<!-- TODO 1) 메뉴 만들 때 CSS 스타일 입히기
				div 태그와 a 태그
	-->
	<div class="menu">
		<!--
			TODO Question?
				코드를 짜다보면 a 태그처럼 반복적인 HTML 태그가 나오는데,
				이런건 어떻게 처리할까?
		-->
		<a>Home</a>
		<a>Products</a>
		<a>About</a>
	</div>
</template>

<script>
export default {
	name: 'BeforeMenuChapterWithoutFor',
	data() {
		return {

		}
	},
}
</script>

<style>
/* TODO 2) div 태그
*/
.menu {
	background: darkslateblue;
	padding: 15px;
	border-radius: 5px;
}
/* TODO 3) a 태그
*/
.menu a {
	color: white;
	padding: 10px;
}
</style>