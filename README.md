# cssMaster - flex

chapter 0.
  1. block(옆으로 끝 없는 margin이 생), inline(text와 같은 성질, 높이와 너비 설정 불가능), inline-block(margin의 제거)
  2. nth-child

chapter 1. (축에 대한 설명과 부모 태그를 이용한 자식 태그 조종)
  0. flexbox가 좋은 이유: 화면의 크기의 제약을 받지 않는다.
  1. 부모 태그(직계)에 flex를 걸어주면 자식 태그들이 inline-block처럼 움직인다.
  2. (flex-direction이 row일 때) 수평축: main-axis, 수직축: cross-axis
  3. align-items는 cross-axis, justify-content는 main-axis
  4. align-items는 부모 태그의 높이에 대한 조절. (즉, 부모 태그는 높이 설정이 되어 있어야 한다!!!)

chapter 2. (자식 태그의 단독적인 이동)
  1. align-self (단, 부모 태그의 높이가 적절한지 확인할 것)
  2. order (order은 기본값이 0. 더 큰 숫자로 설정하면 html 태그 순서가 뒤로 밀림)

chapter 3.
  0. flex box는 너비를 바꾸는 한이 있더라도 한 축에 몰아넣으려고 한다.(width를 설정 했더라도)
  1. flex-wrap (기본값: nowrap)
  2. flex-wrap: wrap으로 바꾸면 child의 크기를 지켜라고 명령한다.
  3. align-content (child 크기를 지키면서 줄이 두 개로 바뀌면 그 줄 사이의 간격을 조정하는 녀석)

chapter 4.(반응형 디자인을 할 때 유용한 도구)
  0. flex-shrink / 기본값: 1 (flex-wrap: nowrap일 때 child들의 너비가 무시되면서 좁혀질 수 있는데 이때 어떤 child가 줄어들지 조절가능)
  1. 특정 자식 태그에 넣어주어야 한다.
  2. flex-shrink: 2로 하면 2배로 빠르게 줄어든다.
  3. flex-grow는 반대로 작동한다. 빈 공간을 가진다.

chapter 5.
  0. flex-basis (찌그러지기 전의 처음 width)
  1. 절대 실제 width 값이 아님.
  2. flex-grow, flex-shrink 등의 의해서 바뀌게 됨.
  3. main-axis 축을 기준으로 적용된다.


# cssMaster - grid

chapter 0. (사용하는 이유)
  0. flex로 격자 모양을 만들기는 성가시다.

chapter 1.
  0. 기본 세팅
  1. grid-template-column: 300px 300px 300px or repeat(3, 300px)
  2. grid-template-row: 200px 200px 200px or repeat(3, 200px)
  3. column-gap, row-gap, gap (간격 설정)

chapter 2.
  0. grid-template-areas (grid를 이용해서 범위를 더 유동적으로 설정할 수 있습니다.)
  (grid 부모)
  1. grid-template-columns: 300px 300px 300px 300px;
     grid-template-rows: repeat(4,200px);
     grid-template-areas:
        "header header header header"
        "content content content nav"
        "content content content nav"
        "footer footer footer footer";
  (grid 자식)
  2. grid-area: header or content or nav or footer;

chapter 3.
  0. 어쩌면 grid-template-areas 보다 더 능률있게 큰 범위를 조종할 수 있을 것입니다.
  1. grid-column-start: 1, grid-column-end: 5;
  2. grid-column-start: 1, grid-column-end: 5;
  3. shortCut 버전: grid-column: 1 / 5, grid-row: 1 / -1; (-1이라는 표현은 반대편 시작점이다. 즉, 종점.)

chapter 4.
  0. fraction = fr
  1. repeat(4, 1fr) 이런 식으로 표현하면 전체화면의 4등분
  2. px은 절대적인 사이즈지만, fr은 상대적이라 전체 창을 줄이면 같이 줄어든다.
  3. 높이의 경우 height를 직접 설정해주지 않으면 fr이 마음대로 조종되지 않는다. ex) height: 50vh;
  4. grid-template:
        "header header header header" 1fr(여기는 높이를 조종합니다) / (생략됐지만 여기는 가로 길이를 조종합니다.) (ex, 1fr 1fr 1fr 1fr)
        "content content content nav" 2fr
        "footer footer footer footer" 1fr
     
chapter 5.
  0. justify-items (수평 길이 자체는 나둔 채 내용물이 수평으로 이동한다.)
  1. align-items (수직 길이 자제는 나둔 채 내용물이 수직으로 이동한다.)
  2. 기본값은 stretch

chapter 6.
  1. justify-content 와 align-content
  2. items는 item 안에서 벌어지는 일이고, content는 grid 자체가 이동하는 모습을 보여준다.
