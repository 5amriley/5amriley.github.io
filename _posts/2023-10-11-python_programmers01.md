---
layout: single
title: "2023/10/11 programmers 파이썬 문제 : 조건 문자열"
---

조건 문자열이라는 문제가 있어서 풀어보았는데 기존의 방법보다 더 효율적인 방법이 있어 기록.
이 문제의 경우 대소 연산자를 문자열 형태로 나누어 제공하고, 그 연산자대로 연산한 결과를 반환하는 것이다.
나의 경우에는 단순하게 if를 활용하여 case를 4개로 나누어 답을 입력하였다. 아래가 나의 소스코드.
def solution(ineq, eq, n, m):
    operator = ineq + eq
    answer = 0   # 조건문 안에만 answer가 있으면 그 answer는 조건문 안의 지역 변수.
    if operator == '>=':
        if n >= m:
            answer = 1
        else:
            answer = 0
    if operator == '<=':
        if n <= m:
            answer = 1
        else:
            answer = 0
    if operator == '>!':
        if n > m:
            answer = 1
        else:
            answer = 0
    if operator == '<!':
        if n < m:
            answer = 1
        else:
            answer = 0
    
    return answer

하지만, eval 이라는 기가막힌 함수가 있었다.
이 함수는 "표현식"을 매개변수로 받아 결과값을 반환하는 함수이다.
문자열로 주어진 연산자를 합치기까지 해야하는 이번 문제에 최적인 것이다.
eval(str(n)+ineq+eq.replace('!', '')+str(m)) 로 해결할 수 있다!

이번 문제를 통해 eval() 함수에 대해 알게 된 것이 수확이다.
앞으로 요긴하게 써먹어야겠다~
