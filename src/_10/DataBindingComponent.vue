<!--
	10th, 커스텀 이벤트 문법(오류난 모달창 해결하기)

	TODO 부모 컴포넌트의 있는 데이터를 어떻게 사용할까?
			*props에서 보낸 데이터는 수정이 금지되어 있기 때문에 못했었다.
			해결방법은
				1) 자식 컴포넌트에서 부모 컴포넌트로 메시지를 보내야 해결할 수 있다.
				2) 부모 컴포넌트에서 자식 컴포넌트 메시지 수신하기 !!!
					메시지 보내는 법은 $(달러표시) : vue만의 특별한 변수라고 생각하자!!!
					$emit('작명', 데이터)
				3) 자식이 보낸 데이터는 $event 변수에 담겨 있기 때문에 부모 컴포넌트에서는
						$event를 통해 자식 컴포넌트가 보낸 데이터 받기
				4) $emit() 함수로 만들어 사용하기
-->
<template>
	<div>
		<img :src="room.image" class="room-img">
		<!-- TODO 1-1) 자식 컴포넌트에서 부모 컴포넌트로 메시지를 보내야 해결할 수 있다.
			@click="openModal = true"
		-->
		<!-- TODO 1-2) 자식이 컴포넌트에서 보낸 데이터를 부모 컴포넌트에게 보내기
			userClickEvent = i == room.id
		-->
		<!-- TODO 4) $emit() 함수로 만들어 사용하기 -->
<!--		<h4 @click="$emit('openModal', room.id)">{{ room.title }}</h4>-->
		<h4 @click="openModal">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
export default {
	name: 'DataBindingComponent',
	props: {
		room: Object,
	},
	methods: {
		openModal() {
			this.$emit('openModal', this.room.id)
		}
	},
}
</script>