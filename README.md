# PARISBAGUETTE
## 설명
구매하고 싶은 음식들을 골라서 장바구니에 넣어보세요.
금액을 충전해서 장바구니안에 음식을 구매하고 영수증을 모달로 띄워주는 웹 입니다.

항목별로 음식을 확인할수 있고
장바구니에 고른 물건에 대해서 다음의 기능을 제공해요.  전체삭제 , 삭제, 갯수 추가와 감소, 선택해제
<br>
<br>

## 🔧 사용툴, 사용언어
 - Typescript
 - CSS3
 - HTML5
<br>
<br>

## 🔍 기능설명
 1. 상품 목록
    - 상품이미지를 클릭하면 해당 상품정보가 장바구니에 기록 됩니다.
    - 상단 메뉴에서 종류별로 상품을 볼수있습니다.
    - 페이지 하단에 더보기 버튼을 통해서 더많은 상품정보를 확인 할수 있습니다.

 2. 장바구니 
    - 장바구니에 상품이 담겨있면 장바구니 열기 버튼에 아이콘이 표시됩니다.
    - 장바구니에 담긴 상품의 수량을 증감 할수있으며 수량은 1 이하로 내려가지 않습니다. 
    - 장바구니에 담긴 상품을 한개만 제거 또는 모든 상품을 제거 할 수 있습니다.
    - 장바구니에 담긴 상품을 선택해제 할 수 있습니다. 선택해제된 상품은 결제이후에도 장바구니에 남아있습니다.

  3. 영수증
    - 다음의 정보를 제공합니다 결제금액 , 잔여금액 , 상품명 , 결제일시
    - 영수증을 닫으면 장바구니가 초기화 됩니다 . 
<br>
<br>

## 👩‍💻 감상
인터넷 쇼핑몰의 장바구니의 기능을 
구현하고 싶어서 지금의 프로젝트를 계획하게 되었습니다.
장바구니의 추가 제거 등의 기능들이 같은 dom요소와
금액의 값을 참조하고 있어서
하나의 값을 여럿 참조하고 있을때
수정사항을 즉각 반영할수 있도록 요소를 다시 dom에 그려주는 함수를
만들고 각 장바구니의 기능들마다 호출해서 변경된 값을 바로 돔에 그려줄수 있게 고려하면서 코드를 작성했습니다 .
<br>
<br>

## 📚 어려웠던점
- 이번 프로젝트를 진행하기전에 계획했던 두가지가 있었습니다 . 
기능을 함수단위로 쪼개서 만들고 각 기능들을 필요시마다
함수단위로 호출하면서 코드를 재사용하자 라는 목표와
함수 변수의 호이스팅을 전부 배제하고 코드를 작성할것 
위 두가지를 고려하면서 코드를 작성을 하면서
위에서 선언한 함수내부에서 아래에서 선언한 함수의 기능을
필요로 하는 일들이 몇번 있었습니다 .
그 아래에 선언 된 함수의 위치를 옮기거나 
필요로하는 함수보다 위에 선언한 변수에 할당해서 사용했습니다.

- 깊이가 깊은 객체의 깊은복사
data.js의 원본 객체를 수정하지 않고
복제한 객체 통해서 값의 수정,변경 계획했습니다.
하지만 스프레드 연산자로 배열을 복사하고 객체 프로퍼티에 접근을 해도
원본 메모리의 객체를 참조하고 있는걸 확인 했습니다 . 

배열 내부의 객체를 하나하나 복사해서 값으로 넣어주기엔 코드양이
너무 길어져서
JSON.parse(JSON.stringify(productData)) 방법으로 
깊은복사를 진행했습니다 . 
