<template>
	<div>
		<!-- TODO 2-1) HTML Tag '안' 데이터바인딩
			<h4 class="red" style="color: blue">xx 원룸</h4>
		-->
		<h4 class="red" :style="styleCustom">xx 원룸</h4>
		<!-- TODO 1-1) HTML Tag '사이'에 데이터바인딩하기 {{}} : 콧수염 -->
		<p>{{ price1 }}만원</p>
	</div>
	<!-- TODO Basic HTML Hard Coding -->
	<div>
		<h4>xx 원룸</h4>
		<p>xx 원</p>
	</div>
</template>

<script>

export default {
	name: 'DataBinding',
	// 데이터 저장소
	data() {
		return {
			// TODO 1-2) 데이터바인딩 오브젝트 자료형 { 자료이름: 자료 내용 }
			price1: 60,
			// TODO 2-2) HTML Tag '안' 데이터바인딩 { 자료이름: '' }
			styleCustom: 'color: blue',
		}
	},
}
</script>

<!-- TODO Question : 데이터바인딩 왜 할까?
	1) HTML에 하드 코딩해놓으면 나중에 변경이 어려움.
	2) 이게 가장 중요함. 실시간 자동 렌더링 하려면 '데이터바인딩'을 해야 한다.
-->