<!--
	13th, 정렬
		1) 정렬버튼 만들기
		2) 정렬버튼, Data를 함수 만들기
			원본이 유지되지 않는 sort() 함수
			함수로 만들어서 정렬하기(가격 낮은 순으로 정렬)
			실시간 데이터바인딩이 되기 때문에
		3) 되돌리기 버튼 만들기
			원본이 유지되는 map(), filter() 함수
		4) 되돌리기 버튼 함수 만들기

		* TODO 원복과 복사본 만들기
			roomsOriginal: [...Data] -> array / object 데이터를 각각 별개의 사본을 만들 때 ...을 사용함.
			rooms: Data
-->
<template>
	<!-- TODO 1) 정렬버튼 만들기-->
	<button @click="priceSort">가격순정렬</button>
	<!-- TODO 3) 되돌리기 버튼 만들기 -->
	<button @click="sortBack">되돌리기</button>
	<div v-for="room in rooms" :key="room">
		<img :src="room.image" class="room-img">
		<h4>{{ room.title }}</h4>
		<p>{{ room.content }}</p>
		<p>{{ room.price }}원</p>
	</div>

</template>

<script>
import Data from '@/assets/jsons/oneRoom'

export default {
	name: 'SortGrammar',
	data() {
		return {
			// 오리지널(원본 유지할때)
			// TODO 그냥 Data로 사용하면 같은 값을 공유하기 때문에 동작안함
			// TODO 별개의 사본 생성하기 : array/object 데이터를 각각 별개의 사본을 만들려면 [...array 자료]
			roomsOriginal: [...Data],
			// 정렬용(복사본)
			rooms: Data, // [{} x 6] 큰 Array 안에 데이터가 6개
		}
	},
	methods: {
		// TODO 2) 정렬버튼, Data를 함수 만들기
		priceSort() {
			// TODO 2) 정렬버튼, Data를 함수 만들기(원본이 보존되지 않는 sort()함수) : 잘 사용하지 않음.
			this.rooms.sort(function (a, b) {
				// return a - b // 오브젝트 빼기 오브젝트
				return a.price - b.price // 이게 맞는 거임
			})

			// TODO Sort Basic
			// 1) 콘솔에서 찍어 확인하는 방법
			var array = [3,5,2];
			array.sort(); // 이건 문자 정렬임.
			console.log(array)
			// 2) 숫자 정렬 하는 방법
			array.sort(function (a,b) {
				return a - b // 음수면 a를 왼쪽으로 양수면 a를 오른쪽으로
			});
		},
		// TODO 4) 되돌리기 버튼 함수 만들기(원본을 보존해주는 mpa(), filter() 함수) : 원본 데이터를 보존하는 게 유행임.
		sortBack() {
			// TODO 둘 다 Array 자료형일 경우 =(등호) : 서로 공유해주세요라는 역할을 함. 주의하기 !!!
			// this.rooms = this.roomsOriginal;
			// TODO 개별 복사본을 만들어 해결해주기
			this.rooms = [...this.roomsOriginal];
		}
	}
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
.room-img {
	width: 100%;
	height: 100%;
	margin-top: 15px;
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