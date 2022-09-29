<!--
	14th, 뷰 라이프 사이클
		컴포넌트는 웹페이지에 표시되기까지 일련의 스탭을 거친다.
		그 스탭을 가리켜 '라이프 사이클'이라고 한다.

		1) Create 단계 : 데이터만 존재하는 단계
		2) Mount 단계 : <template> 사이에 있던 걸 실제 HTML로 바꿔 줌
		3) 컴포넌트 생성 : index.html에 장착 된다.
		4) Update 단계 : data가 변하면 HTML 이 재렌더링된다고 했었는데,
				실제로 컴포넌트가 재렌더링된다. 그걸 'Update'라고 한다.
		5) Unmount 단계 : 강제를 삭제하면 컴포넌트가 삭제된다.

		* TODO 뷰 라이프 사이클을 배우는 이유?
			뷰 라이프 사이클은 컴포넌트들이 생명주기에 따라 생성되고 사라지는데,
			컴포넌트 단계 중간중간에 'Lifecycle Hook'을 걸어서 중간에 원하는 코드를 실행가능하게 할 수 있다.
			예를 들어 컴포넌트가 Mount 단계(실제 HTML로 바꾸는 단계)로 넘어가기 전에 'Lifecycle Hook'을 통해 이것 좀 실행해주세요.
			또 다른 예는 Update 단계(재렌더링) 전에 'Lifecycle Hook'을 통해 이것 좀 실행해주세요.
			TODO * 혹은 Create 단계(데이터만 존재하는 단계)에서 Lifecycle Hook을 사용할 수도 있음.
			TODO 결론, Lifecycle Hook을 사용하기 위해 'Lifecycle' 개념을 배우는 거다.
계->