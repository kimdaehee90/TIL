# HTML 문법

## 개념

웹은 HTML, CSS, JS를 이용하여 만든다고 보면 됩니다.

HTML은 하이퍼텍스트 마크업 언어(HyperText Markup Language)로서 페이지의 구조를 잡는 용도로 사용하는 언어입니다. 마크업 언어란 <>하이!<> 이런식으로 마크 안에 넣어 사용하는 언어라는 뜻으로 제목, 문단, 표, 이미 등을 정의하고 튼튼한 구조를 담당하는 정적언어 입니다. 

## HTML 문법

<TAG>content</TAG>의 형태로 태그는 열리고 닫히는 구조를 가지고 있습니다. 여기서 핵심 포인트는 뒤에 태그에 /를 넣어 꼭 닫아주어야 한다는 것입니다!!

## 부모와 자식 요소

<PARENT>

      <CHILD></CHILD>

<PARENT>

부모와 자식의 요소는 어떠한 태그 안에 또 하나의 태그가 종속되어 들어가 있는 형태로 존재할때 종속되는 태그는 자식요소 = 하위요소라고 부르며 종속하는 태그는 부모요소 = 상위요소라고 부릅니다. 여기서 자식요소는 부모요소에  종속되기 때문에 CSS를 적용할때 부모요소에 적용된 문법이 자식요소에도 적용되게 됩니다.

## 속성과 값

속성은 요소의 기능을 확장하기 위하여 사용합니다.<TAG 속성="값"></TAG>의 형태로

* <img src="./my_photo.jpg" alt="내 프로필 사진" />

* <이미지삽입 소스위치="./my_photo.jpg" 대체텍스트="내 프로필 사진" /> 

태그만 사용하면 이미지를 삽입이 불가능하여 src라는  속성을 사용하고 경로를 지정해 줍니다. alt는 만약에 my_photo.jpg라는 이미지가 보이지 않았을경우 보여질 텍스트를 말합니다.

## 빈태그

위에서 태그는 열리고 닫히는 태그가  한 쌍의 구조로 존재한다고 했습니다. 그러나 HTML에는 닫히는 태그가 없는 태그들도 존재합니다. 이를 빈 태그라고 하고 HTML의 버전에 따라 <TAG> 또는 <TAG/>로 사용해야 합니다.