<!--
	11th, Input(v-model)
		<input
			입력할 때마다 뭐 실행해주세요.
			@input="",
		>
		<input
			입력하고 커서다른데 찍으면 뭐 실행해주세요.
			@change="",
		>
		$event == 자바스크립트에서 e라는 파라미터랑 같은 역할을 한다.

		TODO 자바스크립트 이벤트 리스너
			HTML요소.addEventListener('click', function(e) {
				e.preventDefault() (기본동작막기)
			})

		1) <input>에 입력한 값을 데이터로 저장하는 방법 1(@input="" 활용하기)
			1-1) 데이터 저장소에 데이터 등록하기
			1-2) $event를 이용해 month 파라미터 넘기기
			1-3) 사용자가 선택한 month 데이터 확인하기
		2) <input>에 입력한 값을 데이터로 저장하는 방법 2(v-model)
			v-model="month"에 입력한 데이터를 밑(month)에 저장해주세요.
			2-1) v-model="데이터이름"
				<input v-model="month">
				input뿐 아니라 <textarea v-model="">이나 <section v-model="">
				데이터 저장소에 데이터 값이 중요하다. 1 숫자면 숫자 'abcd' 문자면 문자
			2-2) 나중에

		* TODO input에 입력한 것은 전부 문자자료형이 된다 !!!
			v-model에 등록한 값을 숫자도 문자로 받는 게 아니라 숫자로 받고 싶으면
			TODO v-model.number="month"로 처리하면 된다.
-->
<template>
	<div class="black-bg" v-if="openModalWindow === true">
		<div class="white-bg">
			<h4>상품번호 : {{ room[userClickEvent].id }}번</h4>
			<p>{{ room[userClickEvent].title }}</p>
			<!-- TODO 1-2) $event를 이용해 month 파라미터 넘기기(type="checkbox")-->
			<input @input="month= $event.target.value">
			<p>{{ room[userClickEvent].content }}</p>
			<!-- TODO 1-3) 사용자가 선택한 month 데이터 확인하기 -->
			<p>{{ month }}개월 선택함 : {{ room[userClickEvent].price * month }}원</p>
			<!-- TODO 2) <input>에 입력한 값을 데이터로 저장하는 방법 2(v-model) -->
			<textarea v-model="content"></textarea>
			<p>text : {{ content }}</p>
			<!-- TODO * Section option -->
			<div style="margin-bottom: 5px">
				<select>
					<option>212</option>
					<option>213</option>
					<option>214</option>
				</select>
			</div>
			<button @click="$emit('closedModal')">닫기</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'InputModalWindowComponent',
	data() {
		return {
			// TODO 1-1) 데이터 저장소에 데이터 등록하기(초기값 세팅 : 숫자)
			month: 1,
			// TODO 2) <input>에 입력한 값을 데이터로 저장하는 방법 2(v-model)(초기값 세팅 : 문자)
			content: 'abcd',
		}
	},
	props: {
		openModalWindow: Boolean,
		room: Object,
		userClickEvent: Number,
	},
}
</script>