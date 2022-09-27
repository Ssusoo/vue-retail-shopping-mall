<!--
	9th, Props 문법(props로 데이터 보내기)
		props 보낼 때 다양한 자료형 입력가능
			작명="문자자료"(String)
			:작명="1234"(Number)
-->
<template>
	<!-- TODO 1) props로 데이터 보내기 -->
	<!-- 둘 다 같은 의미임.
		v-bind="object"(전체 보내기) == :name="objects.name", :age="objects.age"(개별적으로 보내고 싶을 때)
	-->
	<PropsGrammarNumberStringComponent
			:objects="objects"
	/>
</template>

<script>
import PropsGrammarNumberStringComponent from '@/_9/PropsGrammarNumberStringObjectComponent'

export default {
	name: 'PropsGrammarNumberStringObject',
	components: {
		PropsGrammarNumberStringComponent,
	},
	data() {
		return {
			objects: {
				name: 'kim',
				age: 20,
			}
		}
	},
}
</script>