<!--
	11th, Input(v-model)
-->
<template>
	<div class="menu">
		<a v-for="(menu, i) in menus" :key="i">{{ menu }}</a>
	</div>

	<InputModalWindowComponent
			:room="rooms"
			:open-modal-window="openModalWindow"
			:user-click-event="userClickEvent"
			@closedModal="openModalWindow = false"
	/>

	<InputDataBindingComponent
			:room="rooms[i]"
			v-for="(room,i) in rooms"
			:key="room"
			@openModal="openModalWindow = true; userClickEvent = $event"
	/>
</template>

<script>
import Data from '@/assets/jsons/oneRoom'
import InputDataBindingComponent from '@/_11/InputDataBindingComponent'
import InputModalWindowComponent from '@/_11/InputModalWindowComponent'

export default {
	name: 'InputData',
	components: {
		InputDataBindingComponent,
		InputModalWindowComponent,
	},
	data() {
		return {
			userClickEvent: 0,
			openModalWindow: false,
			menus: ['Home', 'Product', 'About'],
			rooms: Data,
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
	text-align: center;
}

.black-bg {
	background-color: rgba(0, 0, 0, 0.5);
	position: fixed;
	width: 100%;
	height: 100%;
}

.white-bg {
	background-color: white;
	width: 100%;
	border-radius: 10px;
	padding: 15px;
}

.room-img {
	margin-top: 10px;
	width: 100%;
	height: 100%;
}

.menu {
	background-color: burlywood;
	padding: 20px;
	text-align: left;
}

.menu a {
	color: black;
	padding: 15px;
	border-radius: 5px;
}
</style>