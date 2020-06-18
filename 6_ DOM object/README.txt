(2)HTML DOM 객체(Document Object Model)
	1)HTML 태그를 객체화 시킨것: HTML태그 당 하나의 DOM 객체 생성
	
	2)DOM 트리: HTML 태그의 포함관계에 따라 DOM 트리에 부모 자식 관계
	-document>html>head>title
	-document>html>body>p+form...
	
	3)DOM 객체의 구성
	•프로퍼티(property) • 메소드(method) • 컬렉션(collection) • 이벤트 리스너(event listener) • CSS3 스타일

	4)this 키워드: DOM객체 자신을 가르킴
	
	5)document객체: html 최상위 객체 
	
	6)form 태그 

	7)이벤트
	 ⓐHTML 태그 내에 작성  
		<p onmouseover="this.style.backgroundColor='orchid'" 		     			onmouseout="this.style.backgroundColor='white'"> 마우스 올리면 orchid 색으로 변경</p> 
	 ⓑDOM 객체의 이벤트 리스너 프로퍼티에 작성  
		<p id=“p”>마우스 올리면 orchid 색으로 변경</p>
		function over() { // onmouseover 리스너로 사용할 함수 ... }
		var p = document.getElementById("p"); p.onmouseover = over; // onmouseover 리스너로 over() 함수 등록

 	 ⓒDOM 객체의 addEventListener() 메소드 이용
		<script> 
		var p; 
		function init() { // 문서가 완전히 로드되었을 때 호출 
			p = document.getElementById("p"); 
			p.onmouseover = over; // over()를 onmouseover 리스너로 등록 
			p.onmouseout = out; // out()를 onmouseout 리스너로 등록 
		}
		function over() { p.style.backgroundColor="orchid"; } 
		function out() { p.style.backgroundColor="white"; } 
		</script>

	ⓓ익명함수를 이용한 event
`
		function init() { // 문서가 완전히 로드되었을 때 호출 
			p = document.getElementById("p"); 
			p.onmouseover = function () { // 익명 함수 this.style.backgroundColor = "orchid"; }; 			p.addEventListener("mouseout", function () { this.style.backgroundColor="white"; } // 익명 함수 ); }