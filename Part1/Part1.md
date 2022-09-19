## CH 01. 환경설정

파이썬 개발환경 설정

## CH 02. 데이터 타입과 컬렉션

list tuple dict set

```python


//파이썬 개발환경 설정
# hello python
## hello
### hello
**python**
- 1
    - 1
        - 1
        
a=5
print(a)
> hihi

c= None
print(c)

a=1
b=1.1
print(a == b)

a = 9
#a = a-3
a-=3
print(a)

a **=3
print(a)

// 문자열 타입의 이해
c=""" Hello World 
It's nice day."""

print(c)

print('Hello World \n\n')

a='Hello World'
print(a[10])
print(a[-1])
print(a[11])
a[:5]

//문자열 함수
a.upper()
a.replace('H','j')

//format

temperature = 25.5
prob =80.0
a= '오늘 기온은 {}도 이고, 비올 확률은 {}% 입니다.'.format(temperature, prob)
print(a)

a= 'hello world what a nice day'
a.split()

a.split('w')

//list

a=[]
print(a)

a=[1,2,3,4,5]
print(a)

a='hello world'
b= list(a)
print(b)
c=(1,2,3)
d=list(b)
print(d)

a= [1,2,3,4,5]
print(a[2])
print(a[4])
print(a[-1])

a ='hello world'
print(a[0])

#a[0]='j' 안됨 불변이라
d= 'j'+a[1:]
print(d)

a = [1,2,3,4,5]
a[0]=100
print(a)

a=[1,2,3,4,5]
a.append(10)
print(a)

a=[1,2,3,4,5]
b=[6,7,8,9,10]
a.extend(b)
print(a)

a=[1,2,3,4,5]
b=[6,7,8,9,10]
a+=b
print(a)

a.insert(1,40)
print(a)

a = [1,2,3,4,5,6,10]
b=7
c= b in a #False
print(c)

a=[1,2,3,9]
a.index(9)

//sort

a.sort(reverse= False)
print(a)
b=sorted(a,reverse=True)
print(b)

//tuple

a=[1,2,3]
b=(1,2,3)
a[0]=100
b[0]=100
print(a,b)

a=(1,2,3)
type(a)

a,b= 100, 200
print(a, b)

a= 5
b=4
print(a,b)

#logic
temp=a
a=b
b=temp

print(a, b)

a= 5
b=4
print(a,b)

#logic
a, b = b, a

print(a, b)

//dictionary

a={"Korea":"Seoul","Canada":"ottawa"}
print(a["Korea"])
a["Japan"]="Tokyo"
print(a)

a= {'a':1, 'b':2, 'c':3}
b= {'a':4, 'd':5, 'e':7}
a.update(b)
print(a)

a= {'a':1, 'b':2, 'c':3}
a.pop('b')
print(a)

a= {'a':1, 'b':2, 'c':3}

del a['b']
print(a)

a= {'a':1, 'b':2, 'c':3}
print(a)
a.clear()
print(a)

a= {'a':1, 'b':2, 'c':3}
print(a)
'b' in a

print(a.get('d'))

print(a)

print(a.keys())

print(a.values())

print(list(a.keys()))

print(list(a.values()))

//set

a={1,2,3}
b={2,3,4}
print(type(a))
print(a.union(b))
print(a.intersection(b))
print(a.difference(b))
print(a.issubset(b))
```

## CH 03. 조건문과 반복문

- if elif else
- while
- for

```python
#우선순위 NOT> AND > OR

if 6>= 5 :
    print('a')
    print('b')
    print('c')
print('bbbbbbbbb')

if 6== 5 :
    print('a')
    print('b')
    print('c')
print('bbbbbbbbb')

a=10
b=9
c=8

if a==10 and b==9 :
    print('true')

if a==10 or b==9 and c==12 :
    print('true')

if not a==10:
    print('true')

# 각 타입의 기본값들 --> False로 인식

a=[]
if a :
    print('true')

# 각 타입의 기본값들 --> False로 인식

a=[]
if a :
    print('true')

a=0
if a :
    print('true')

a=1
if a:
    print('true')

# 짝수면 2로 나눈값 출력, 홀수면 1더한값 출력

a= 10
if a % 2 ==0:
    print(a/2)
else:
    print(a+1)

//While

a=[1,2,3,4,6,7,8,100]

i=0 # 인덱스
while i <len(a):
    print('value',a[i],'index',i)
    i +=1
    
print('hahaha')

a=[1,2,3,4,6,7,8,100]

i=0 # 인덱스
while i <len(a):
    if a[i] %2 :
        print(a[i])
    else:
        print(a[i]/2)
    i +=1

a=[1,21,30,4,6,7,8,100]
i=0
while i <len(a):
    
    if a[i]>20:
        break
    print(a[i])
    i+=1
print('haha')

a=7
while a>0 :
    a-=1
    if a==5:
        continue
    print(a)

#1-100 더하기

num=1
_sum =0
while num <=100 :
    _sum+=num
    num+=1
    print(_sum, num)
print(_sum)

//for

a=[1, 2, 3, 4, 5]
for i in a:
    print(i, i**2)
print('hahah')

a='hello world'
for character in a :
    print(character)

a=[1, 2, 3, 4, 5]
for num in a:
    if num%2==0:
        print(num/2)
    else:
        print(num+1)

a= {'Korea':"Seoul", "Japan":'tokyo',"Canada":"ottawa"}
for key in a:
    print(key, a[key])

for key in a.values():
    print(key)

list(a.items())

for key , value in a.items():
    print(key, value)

a= [1,2,3,4,5]
for index, value in enumerate(a):
    print(index, value)

a=[100, 90, 80,70, 60, 50]
for  num in a:
    if num <80:
        break
    print(num)

# 해당아이템을 건너뛰고싶을떄 사용
a=[100, 90, 80,70, 60, 50]
for  num in a:
    if num >80:
        continue
    print(num)

a=[1,2,4]
for i in a :
    for j in a :
        print(i*j)

for i in range(2,10):
    for j in range(1,10):
        print(i,'x',j,'=',i*j)

i=1
while i in range(1,10):
    i+=1
    j=1
    while j in range(1,10):
        print(i,'x',j, '=',i*j)
        j+=1

list(range(10))

list(range(5,101,5))

# 연습문제 1 구구단 for
for i in range(2,9):
    for j in range(1,9):
        print(i,'x',j,'=',i*j)

#연습문제 2
nums = list(range(1,101))
for i in nums:
    if i%2==0 or i%11==0:
        print(i)

#연습문제 3 -최대최소구하기
a=[22,1,3,4,7,98,21,55,87,99,19,20,45]
_min=a[0]
_max=a[0]

for x in a:
  
    if x<_min:
        _min=x
print(_min)

for y in a :
    if y >_max:
        _max=y
print(_max)

#한번에
_min=a[0]
_max=a[0]

for x in a:
  
    if x<_min:
        _min=x
    if x>_max:
        _max=x
print(_min, _max)

#연습문제 4
a=[22,1,3,4,7,98,21,55,87,99,19,20,45]
_sum =0
for i in a:
    _sum+=i
print(_sum/len(a))

#While
i=0
_sum=0

while i < len(a):
    _sum+=a[i]
    i+=1
print(_sum/len(a))
```

## CH 04. 함수 이해 및 활용

- def 이해 , 간단한 함수 만들기
- return 이해

```python
#함수의 이해 및 활용, 기본파라미터, 키워드 파라미터이해, 변수의 스코프이해
#def
def add(x, y):
    n= x + y
    return n

l=len([1,2,3])
c= add(300, 30)
print(l)
print(c)

def test():
    print('haha')
    print('good')
    return 100
a= test()
print(a)

def test1(x, y):
    print(x,y)
    n= x + y
    return n
a= test1(100, 200)
print(a)

def add(x,y=1,z=5):
    a= x+y+z
    return a
print(add(2))
print(add(10,20))
print(add(10,20,30))

def test2(x,y,z):
    a= x+y+z
    return a
print(test2(x=1, y=2, z=5))

def weird_multiply(x,y):
    if x>10:
        return x*y
    
    print(x+y)
    return (x*2)*y
    print(x*2)*y
    
a= weird_multiply(1,2)
b= weird_multiply(12,2)
print(a)
print('---------')
print(b)

def weird_multiply(x,y):
    if x>10:
        return 
    
    print(x+y)
    return (x*2)*y
    
    
c= weird_multiply(12,5)
print(c)

def weird_multiply(x,y):
    if x>10:
        return x*y
 
c= weird_multiply(2,5)
print(c)

def add_mul(x,y):
    s=x+y
    m=x*y
    return s, m
c=add_mul(20, 3)
d, e = add_mul(20, 3)
print(c)
print(type(c))
print(d, e)

//변수의 범위
num1=10
num2=20
def test(num1, num2):
    print(num1, num2)
    return num1 + num2
test(30, 40)
print(num1, num2)

//가변길이 인자
#**kwargs--> *args라 표기 많이함
#type : tuple
#개수 상관 없이 인자에 입력 가능하게 함

def test(*args): # argument # type은 튜플로 됨
    print(type(x))
test()

def test(*args):
    for i in args:
        print(i)
test(1,2,3,4,5)

#Keyword parameter
#**가 붙은 경우에는 키워드 파라미터로 인식
#즉 함수호출시, 파라미터의 이름과 값을 함께 전달가능
#**kwargs : key word arguments -->dictionary

def test2(**kwargs):
    for key, value in kwargs.items():
        print('key',key, 'value', value)
test2(a=1, b=2, c=3, d='apple')

a='오늘 온도 : 30도, 강수확률 : 60%'
print(a)

a='오늘 온도 : {today_temp}도, 강수확률 : {today_prob}%, 내일 온도 : {tomorrow_temp}도'.format(tomorrow_temp=23, today_temp=25, today_prob=50)
print(a)

#lamda함수의 이해 및 사용
#단일문으로 표현되는 익명함수
#lambda 사용할 변수 : return할 값

#1
def square2(x):
    return x**2
square2(5)

square = lambda x:x**2
square(5)

#2
def add(x,y):
    return x+y

add2= lambda x,y:x+y
add2(1,2)

#3
def str_len(s):
    return len(s)
str_len('goods')

#4
strings=['bob', 'charles', 'alexander3', 'teddy']
strings.sort(key=str_len)
print(strings)

strings=['bob', 'charles', 'alexander3', 'teddy']
strings.sort(key= lambda s:len(s))
print(strings)

#filter, map, reduce
#filter(함수, 리스트) -- 리스트 각각원소에 함수 적용해서 참만 걸러냄
#map(함수, 리스트) -- 리스트를 함수적용한 리스트로 만듬
#reduce(함수, 리스트) --앞 두개 연산 --> y, y와 다음꺼 계산 -->k, 결국 하나로 줄임

def even(n):
    return n%2 ==0
even(3)

nums=[1,2,3,4,5,6,7,8,11,23]
list(filter(even, nums))

#filter
nums=[1,2,3,4,5,6,7,8,11,23]
list(filter(lambda n:n%2==0, nums))

#map
#주어진 리스트, 리스트의 제곱을 한 숫자로 새로운 리스트

nums=[1,2,3,4,5,6]
list(map(lambda n:n**2, nums))

list(map(even, nums))

list(map(lambda n:n%2==0, nums))

import functools
a=[1,3,5,8]
#리스트내의 모든 합의 숫자
functools.reduce(lambda x,y:x+y,a)

functools.reduce(lambda x,y:x*y,a)

//연습문제
#1 주어진 숫자리스트의 평균을 구하는 함수 출력
#2 해당 숫자가 소수인지 아닌지 판별
#3 2부터 해당 숫자사이에 소수가 몇개인지 출력

#1
def mean(nums):
#     j=0
#     for i in args:
#         j+=i
    return sum(nums)/len(nums)
mean([1,2,3,4,5])

#2 
def is_prime(num):
    for i in range(2,num):
        if num%i==0:
            return False
    return True
      
print(is_prime(103))

def num_prime(num):
    count=0
    for j in range(2,num+1):
       if is_prime(j):
        count+=1
    return count
    
      
print(num_prime(103))
```

## CH 05. 파이썬 모듈

- 모듈의 이해 및 사용과 import 방법

## CH 06. 클래스와 인스턴스

1. 클래스 & 오브젝트 이해하기
    - class : 인간이라는 타입
        - 속성(attribute) : 이름, 국적, 나이
        - 행동(method) : 먹다, 자다, 일어나다
    - object : 홍길동, 임꺽정 등 실제로 존재하는 객체
    - class : ‘List’ 라는 타입 — 틀
        - 속성(attribute) : Items
        - 행동(method) : append, extend
    - object : [1, 2, 3] [’Hello World’, ‘World’] — 틀에 저장되어있는 내용
2. 클래스 정의 및 사용하기
    - 실세계의 것을 모델링하여 속성(attribute)와 동작(method)를 갖는 데이터 타입
    - python에서의 string, int, list, dict 모두가 다 클래스로 존재
    - 학생이라는는 클래스를 만들때, 학생을 나타내는 속성과 학생이 행하는 행동을 함께
    - 정의 할 수 있음
    - 따라서, 다루고자 하는 데이터(변수)와 다루는 연산(함수)를 하나로 캡슐화(encapsulation)하여 클래스로 표현
    - 모델링에서 중요시 하는 속성에 따라 클래스의 속성과 행동이 각각 달라짐
    
    ```python
    class test:
        pass
    class test2:
        pass
    
    class Person:
        pass
    bob = Person()
    cathy = Person()
    
    a = list()
    b = list()
    
    print(type(bob), type(cathy))
    print(type(a), type(b))
    
    //결과
    <class '__main__.Person'> <class '__main__.Person'>
    <class 'list'> <class 'list'>
    ```
    
3. 생성자(**init**)이해 및 사용하기
    
    ```python
    class Person:
        def __init__(self, name, age):
    #         print(self, 'is generated')
            self.name = name
            self.age = age
    # self뒤에있는것이 속성명이되고, (self, name, age)부분은 값만전달해주는 parameter임
    #(self, name, age)에서 name 과 age를 이름을 다르게 바꿔도 됨
    
    #     def __init__(self, n, a):
    #         print(self, 'is generated')
    #         self.name = n
    #         self.age = a
    p1 = Person('Bob', 30)
    p2 = Person('Kate', 20)
    
    print(p1.name, p1.age)
    print(p2.name ,p2.age)
    ```
    
4. self  키워드의 이해 및 사용하기
    
    ```python
    # self : 그 객체 스스로 자신을 말하는것
    # a라는 객체에 Person 이라는 클래스를 부여하고 그 클래스 안에 method 두가지를 만든것
    # a.sleep을 하면 self에 a라는 객체가 스스로 들어간다.
    
    class Person :
        def __init__(self, name, age):
            print('self:', self)
            self.name = name
            self.age = age
        def sleep(self):
            print('self:', self)
            print(self.name,'은 잠을 잡니다.')
    a = Person('Aron', 12)
    b = Person('Bob', 30)
    print(a)
    print(b)
    a.sleep()
    b.sleep()
    
    //결과
    self: <__main__.Person object at 0x0000013812962588>
    self: <__main__.Person object at 0x0000013812962648>
    <__main__.Person object at 0x0000013812962588>
    <__main__.Person object at 0x0000013812962648>
    self: <__main__.Person object at 0x0000013812962588>
    Aron 은 잠을 잡니다.
    self: <__main__.Person object at 0x0000013812962648>
    Bob 은 잠을 잡니다.
    
    ```
    
5. method, static method 정의 및 사용하기
    
    ```python
    
    ```
    
6. 클래스 상속의 이해 ( 코드를 재사용하기 2)
7. 클래스 연산자 재정의 이해 및 사용
8. 클래스 연습문제 풀이
