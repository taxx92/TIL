## CSS 적용방법과 선택자들

### CSS를 적용하는 세 가지 방법

**인라인 스타일(inline style)** 방식은 HTML 태그마다 style 속성으로 CSS 코드를 넣어주는 방식
여러 요소들에 공통 속성을 재사용하여 부여할 수 없고 HTML 코드와 CSS 코드가 분리되지 않기 때문에
특별한 경우를 제외하고는 사용되지 않는다.

**내부 스타일 시트(internal style sheet)** 방식은 head 태그 안에 style 태그를 두고 그 안에 CSS 코드를 작성하는 방식
HTML과 CSS의 전체 코드량이 많지 않고 CSS가 해당 HTML 문서에서만 적용될 경우
유용하게 사용될 수 있다.

**링킹 스타일 시트(linking style sheet)** 방식은 외부의 CSS 파일을 HTML 문서에 연결하는 것
HTML과 CSS의 코드가 분리되고 CSS 코드를 여러 HTML 파일에서 공통으로 사용할 수 있으므로
가장 널리 사용되는 방식

### CSS 코드 정리

#### 기본 & 그룹 선택자

```
/* 모든 요소 선택 */
* {
  font-weight: bold;
  color: darkorange;
}

/* 같은 선택자의 경우 뒤에 오는 것이 우선순위 높음 */
* {
  color: plum;
}

/* 태그 선택자 */
p {
  color: olivedrab;
}

/* class 선택자 */
/* 태그보다 우선순위 높음 */
/* 페이지상의 여러 요소가 같은 class를 가질 수 있음 */
.blue {
  color: lightblue;
}

/* 다른 선택자에 이어붙일 수 있음(태그, 클래스 등...) */
/* 선택자는 구체적일수록 우선순위 높음 */
p.blue {
  color: slateblue;
}

.blue.dark {
  color: mediumblue;
}

p.blue.dark {
  color: darkblue;
}

/* id 선택자 */
/* class보다 우선순위 높음 */
/* id는 페이지상에서 요소마다 고유해야 함 */
#red {
  color: tomato;
}

/* 그룹 선택자 */
span, .dark, #red {
  text-decoration: underline;
}
```

#### 결합자와 가상 클래스

```
/* 자손 결합자 */
.outer li {
  color: olivedrab;
}

/* 자식(1촌 자손) 결합자 */
.outer > li {
  color: dodgerblue;
}

.outer > li li {
  text-decoration: underline;
}

/* 뒤따르는 모든 동생들 결합자 */
.starter ~ li {
  font-style: italic;
}

/* 뒤따르는 바로 다음 동생 결합자 */
.starter + li {
  font-weight: bold;
}

/* 첫 번째, 마지막 요소 가상 클래스 */
ol li:first-child,
ol li:last-child {
  color: yellowgreen;
}

/* ~가 아닌 요소 가상 클래스 */
.outer > li:not(:last-child) {
  text-decoration: line-through;
}

ul:not(.outer) li {
  font-weight: bold;
}

/* ~번째 요소 가상 클래스 */
/* #, #n, #n+#, odd, even 등 시도해보기 */
ol li:nth-child(3) {
  font-weight: bold;
  color: deeppink;
}

/* 마우스오버 가상 클래스 */
li:hover {
  font-weight: bold;
  color: blue;
}
```

---
#### 실습

```
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>

  <link rel="stylesheet" href="./style.css">
</head>
<body>
  <h1>결합자와 가상 클래스</h1>

	<ul class="outer">
		<li>육류</li>
		<li>채소</li>
		<li>유제품</li>
		<li>과일
			<ul>
				<li>사과</li>
				<li>포도</li>
				<li>딸기</li>
				<li>키위</li>
			</ul>
		</li>
	</ul>

	<ol>
		<li>한놈</li>
		<li>두시기</li>
		<li class="starter">석삼</li>
		<li>너구리</li>
		<li>다섯놈</li>
		<li>육개장</li>
		<li>칠푼이</li>
		<li>팔보채</li>
		<li>구공탄</li>
	</ol>
</body>
</html>
```

---

참고강의 - [얄코(Yalco) <제대로 파는 HTML CSS>](https://www.inflearn.com/course/%EC%A0%9C%EB%8C%80%EB%A1%9C-%ED%8C%8C%EB%8A%94-html-css/dashboard)

