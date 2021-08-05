# 변수와 상수

변수와 상수는 특정 이름에 특정 값을 담는 용도로 사용합니다. 변수와 상수를 이해하기 위해선 먼저 **변수와 상수**를 어떻게 쓰는지를 보아야 합니다.

'''
let variable = 1;

console.log(variable);

const constant = 2;

console.log(constatnt);
'''

variable이란 변수에 1을 담고 console이라는 출력하는 함수를 이용해 variable을 출력하면 1이라는 값이 출력됩니다. 또한 constant라는 상수에 2를 담고 출력하면 2라는 상수가 출력됩니다.
변수와 상수는 이런식으로 어떠한 값을 담는 그릇이라 보면 됩니다. 이렇게 variabel이라는 변수를 만드는것을 선언이라 합니다.


## 변수

변수와 상수가 그럼 다른것이 무엇인가?라는 의문이 들면 정상입니다. 변수란 바뀔수 있는 값을 말합니다. 

'''
let variable = 1;

console.log(variable);// 1

variable = 2;

console.log(variable);// 2
'''

변수의 선언은 let이라는 키워드를 사용합니다. 변수는 변할 수 있기 때문에 1이라는 값을 주었지만 뒤에 2라는 값을 다시 할당하면 variable의 값은 2로 바뀝니다.

## 상수

상수는 선언한 변수가 더이상 변하지 않는 값을 말합니다. 

'''
const constant = 2;

console.log(constatnt);// 2

constant = 3;

console.log(constatnt);// erro
'''

위의 코드처럼 상수로 변수를 선언하면 더이상 다른 값을 할당할 수 없기 때문에 3을 새로 할당하는것 자체가 불가합니다.

**벨로퍼트님의 블로그 참조**
  
