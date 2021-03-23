len(range(5))의 실행결과는 5입니다.
len(iter(range(5)))의 실행결과는 에러입니다.
(에러: TypeError: object of type 'range_iterator' has no len())

이렇게 되는 이유부터 말씀을 드리자면, range(5)는 "iterable한 객체"이기 때문에 len 함수에 의해 길이가 도출되지만, iter(range(5))는 "iterator 객체"이기 때문에 len 함수가 적용되지 않습니다. 만약 "iterator 객체"에서의 length를 알고 싶다면 list나 tuple 등으로 변환 후 len 함수를 적용하거나, sum(1 for _ in iter(range(5))) 과 같은 방식으로 알 수 있습니다.

"모든 iterator 객체는 iterable 하지만", "모든 iterable한 객체가 iterator는 아닙니다."
먼저 iterable한 객체는 "반복 가능한 자료형"을 말합니다. 우리가 흔히 쓰는 list, tuple, range, dict, set 등 모두 iterable하다고 합니다. iterable 하기 위해서는 해당 클래스 내부에 iter() 혹은 getitem() (양쪽에 더블 언더바가 붙어야합니다.) 같은 매직 메서드가 정의되어 있어야 합니다. 이 매직 메서드 중 하나라도 정의되지 않으면 해당 클래스는 iterable 하다고 할 수 없습니다.

iterator는 파이썬의 내장함수 "iter()"에 의해 변환된 객체 입니다. 이 "iter()" 함수는 위에서 설명한 매직 메서드와는 다른 함수입니다. iterator 객체는 next() 함수를 통해서 가지고 있는 반복 가능한 값들을 하나씩 꺼냅니다. 그리고 모든 값을 꺼내면 StopIteration Exception을 발생시킵니다.

조금 더 쉽게 예시를 들면서 말해보겠습니다.
문제에 나왔던 range(5)는 iterable한 객체입니다. range(5)는 range 객체이지, iterator 객체가 아닙니다. 단순히 iterable 하다고만 얘기할 수 있습니다. 그 이유는 range 객체 내에 iter() 혹은 getitem() 매직 메서드가 정의되어 있기 때문입니다.

반면 iter(range(5))는 iterator 객체입니다. 파이썬 내장함수 iter()에 의해 iterator로 변환되었기 때문입니다. 이제 iter(range(5))는 next() 함수를 이용해서 값을 하나씩 꺼내올 수 있습니다. 그리고 iter(range(5))는 iterable 하다고 할 수도 있습니다. 왜냐면 모든 iterator 객체는 iterable 하기 떄문입니다. 하지만 그 역은 성립하지 않습니다.

우리가 자주 쓰는 for i in range(5) 를 살펴보면, for문의 내부적으로는 range(5)를 iter() 함수를 통해서 iter(range(5))로써 iterator 객체로 변환합니다. 그리고 next()를 통해 0~4까지 값을 하나씩 가져오다가, 4까지 반환을 하면 StopIteration 예외를 발생시켜서 for문을 종료하는 형태로 되어있습니다. 이것이 바로 for 문의 내부 동작 과정입니다.