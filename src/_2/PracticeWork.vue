<!--
	데이터바인딩 숙제
		products: ['역삼동원룸', '천호동원룸', '마포구원룸']
		Array 형태로 정의된 데이터를 '데이터바인딩 하기'
-->
<template>
	<div>
		<p>{{products[0]}}</p>
		<p>{{products[1]}}</p>
		<p>{{products[2]}}</p>

	</div>

</template>

<script>

export default {
	name: 'PracticeWork',
	// TODO 데이터 저장소
	data() {
		return {
			// TODO Array 형태로 정의된 데이터들.
			products: ['역삼동원룸', '천호동원룸', '마포구원룸']
		}
	},
	components : {
	}
}
</script>