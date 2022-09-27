<template>
	<div>
		<img :src="room.image" class="room-img">
<!--		<h4 @click="$emit('openModal', room.id)"></h4>-->
		<h4 @click="openModal">{{ room.title }}</h4>
		<p>{{ room.price }}원</p>
	</div>
</template>

<script>
export default {
	name: 'CustomEventGrammarDataBindingHomework',
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