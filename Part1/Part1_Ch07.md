# 정규표현식과 re모듈의 사용 

- 1. 정규표현식(re) 에 대한 이해 및 숙지
- 특정 패턴과 일치하는 문자열을 '검색', '치환', '제거'하는 기능을 지원
- e.g) 이메일 형식 판별, 전화번호 형식 판별, 숫자로만 이루어진 문자열 등
- raw string 
    - 문자열 앞에 r이 붙으면 해당 문자열이 구성된 그대로 문자열로 변환


```python
a = 'abcdef\n' #escape 문자열
print(a)

b = r'abcdef\n'
print(b)
```

    abcdef
    
    abcdef\n
    

### 기본패턴
- search 기능
- a, X, 9 등등 문자 하나하나의 character들은 정확히 해당 문자와 일치
    - e.g) 패턴 test는 test문자열과 일치
    - 대소문자의 경우 기본적으로 구별하나, 구별하지 않도록 설정 가능
- 몇몇 문자들에 대해서는 예외가 존재하는데, 이들은 특별한 의미로 사용됨
    - .^$* + ?{}[]\|()

- \w - 문자
- \s - 공백
- \t, \n, \r - tab, newline, return
- \d - 숫자 character [0-9]
- ^ = 시작, $ = 끝 각각 문자열의 시작과 끝을 의미
- \가 붙으면 스페셜한 의미가 없어짐. 예를들어 \\.는 .자체를 의미, \\\는 \\를 의미


### search method
- 첫번째로 패턴을 찾으면 match 객체를 반환
- 패턴을 찾지 못하면 None 반환


```python
import re
```


```python
m = re.search(r'abc', '123abcdef')
print(type(m))
print(m.start())
print(m.end())
print(m.group())
```

    <class 're.Match'>
    3
    6
    abc
    


```python
# \d : 숫자하나 \d\d:숫자연속두개
# seach 함수는 가장 먼저 찾는 패턴을 보여줌
m = re.search(r'\d\d', '112abcdef119')
m
```




    <re.Match object; span=(0, 2), match='11'>




```python
m = re.search(r'\d\d\d', '112abcdef119')
m
```




    <re.Match object; span=(0, 3), match='112'>




```python
m = re.search(r'\d\d\d\w', '112abcdef119')
m
```




    <re.Match object; span=(0, 4), match='112a'>



###  \d : 영어 대소문자, 숫자      
###  . : 아무거나


```python

m = re.search(r'..\w\w', '@#$%ABCDabcd')
m
```




    <re.Match object; span=(2, 6), match='$%AB'>



## []문자들의 범위를 나타내기 위해 사용
- [] 내부의 메타 캐릭터는 캐릭터 자체를 나타냄
- e.g)
- [abck] : a or b or c or k
- [abc.^] : a or b or c or . or k
- [a-d] : - 와 함께 사용되면 해당 문자 사이의 범위에 속하는 문자 중 하나
- [0-9] : 모든 숫자
- [a-z] : 모든 소문자
- [A-Z] : 모든 대문자
- [a-zA-Z0-9] : 모든 알파벳 문자 및 숫자
- [^0-9] : ^가 맨 앞에 사용 되는 경우 해당 문자 패턴이 아닌 것과 매칭 --> 숫자가 아닌 것


```python
 re.search(r'[cbm]at', 'cat')
```




    <re.Match object; span=(0, 3), match='cat'>




```python
 re.search(r'[cbm]at', 'mat')
```




    <re.Match object; span=(0, 3), match='mat'>




```python
re.search(r'[0-9]haha', '1hahah')
```




    <re.Match object; span=(0, 5), match='1haha'>




```python
re.search(r'[0-4]haha', '7hahah')
```


```python
re.search(r'[abc.^]aron', 'caron' )
```




    <re.Match object; span=(0, 5), match='caron'>




```python
re.search(r'[^abc]aron', 'aaron')
```


```python
re.search(r'[^abc]aron', '#aron')
```




    <re.Match object; span=(0, 5), match='#aron'>



# \
1. 다른 문자와 함께 사용되어 특수한 의미를 지님
    - \d : 숫자 -> [0-9]와 동일
    - \D : 숫자가 아닌 문자 ->  [^0-9]와 동일
    - \s : 공백문자(띄어쓰기, 탭, 엔터등)
    - \S : 공백이 아닌 문자
    - \w : 알파벳대소문자, 숫자[0-9a-zQA-Z]와 동일
    - \W : non alpha-numeric 문자 [^0-9a-zA-z]와 동일
2. 메타 캐릭터가 캐릭터 자체를 표현하도록 할 경우 사용
    - \\. , \\\


```python
re.search('\sand', 'apple and banana')
```




    <re.Match object; span=(5, 9), match=' and'>




```python
re.search('\Sand', 'apple and banana')
```


```python
re.search('.and', 'pand')
```




    <re.Match object; span=(0, 4), match='pand'>



# . 
- 모든 문자를 의미


```python
re.search('\.and', '.and')
```




    <re.Match object; span=(0, 4), match='.and'>




```python
re.search(r'p.g', 'pig')
```




    <re.Match object; span=(0, 3), match='pig'>



### 반복패턴
- 패턴 뒤 *, +, ?는 해당 패턴이 반복적으로 존재하는지 검사
    - '+' -> 1번 이상의 패턴이 발생
    - '*' -> 0번 이상의 패턴이 발생
    - '?' -> 0 혹은 1번의 패턴이 발생
    
### 반복패턴은 가장 많은부분 매칭된것을 결과로 반환 --> greedy



```python
# a로 시작, b or c or d가 0번이상 반복, b로 끝
# ab
# abcb
# abcbdccb
# 반복패턴은 가장 많은부분 매칭된것을 결과로 반환 --> greedy
re.search(r'a[bcd]*b', 'abcbdccb')
```




    <re.Match object; span=(0, 8), match='abcbdccb'>




```python
re.search(r'b\w+a', 'banana')
```




    <re.Match object; span=(0, 6), match='banana'>




```python
re.search(r'i+', 'piigiii')
#가장 빨리 찾은것 반환
```




    <re.Match object; span=(1, 3), match='ii'>




```python
re.search(r'pi*g', 'piiig')
```




    <re.Match object; span=(0, 5), match='piiig'>




```python
re.search(r'pi*g', 'pg')
```




    <re.Match object; span=(0, 2), match='pg'>




```python
re.search(r'pi+g', 'pg')
```


```python
re.search(r'https?', 'httpk:/www.naver.com')
```




    <re.Match object; span=(0, 4), match='http'>



###  ^*
### *\$
- ^문자열 맨앞부터 일치하면 검색
- $문자열 맨뒤부터 일치하면 검색


```python
re.search(r'b\w+a','cabana')
```




    <re.Match object; span=(2, 6), match='bana'>




```python
re.search(r'^b\w+a','babana')
```




    <re.Match object; span=(0, 6), match='babana'>




```python
re.search(r'b\w+a$','cabana')
```




    <re.Match object; span=(2, 6), match='bana'>




```python
re.search(r'b\w+a$','cabanap')
```

## grouping

- ()을 사용해 그루핑
- 매칭결과를 그룹별로 분리 가능
- 패턴 명시할때, 각 그룹을 괄호()안에 넣어 분리하여 사용




```python
m = re.search(r'\w+@.+', 'test@gmail.com' )
print(m)
print(m.group())
```

    <re.Match object; span=(0, 14), match='test@gmail.com'>
    test@gmail.com
    


```python
m = re.search(r'(\w+)@(.+)', 'test@gmail.com' )
print(m)
print(m.group(1))
print(m.group(2))
print(m.group(0))
```

    <re.Match object; span=(0, 14), match='test@gmail.com'>
    test
    gmail.com
    test@gmail.com
    

# {}
- *, +, ?을 사용해 반복패턴은 찾을 수 있지만 횟수 제한 불가
- 패턴뒤 {}에 숫자명시 ->횟수제한 가능
- {4} - 4번 반복
- {3,4} - 3~4번 반복


```python
re.search(r'pi{3}g', 'piiig')
```




    <re.Match object; span=(0, 5), match='piiig'>




```python
re.search(r'pi{3,5}g', 'piiiiig')
# min = 3, max = 5
```




    <re.Match object; span=(0, 7), match='piiiiig'>



## 미니멈 매칭(non - greedy way)
- 기본적으로 *, +, ? 사용하면 greedy 하게 동작
 - *?, +?을 이용해 해당기능 사용


```python
re.search(r'<.+>', '<html>hahah.</html>')
```




    <re.Match object; span=(0, 18), match='<html>hahah.<html>'>




```python
re.search(r'<.+?>', '<html>hahah.</html>')
```




    <re.Match object; span=(0, 6), match='<html>'>



## {}?
- {m,n}? ->최소 m번 매칭 검출


```python
re.search(r'a{3,5}','aaaaa')
```




    <re.Match object; span=(0, 5), match='aaaaa'>




```python
re.search(r'a{3,5}?','aaaaa')
```




    <re.Match object; span=(0, 3), match='aaa'>



## match
- search 와 유사하지만, 주어진 문자열의 시작부터 비교해 패턴이 있는지 확인


```python
re.search(r'\d\d\d', 'my number is 123')
```




    <re.Match object; span=(13, 16), match='123'>




```python
re.match(r'\d\d\d', 'my number is 123')
```


```python
re.match(r'\d\d\d', '123 is my number')
```




    <re.Match object; span=(0, 3), match='123'>




```python
re.match(r'^\d\d\d', '123 is my number')
```




    <re.Match object; span=(0, 3), match='123'>



## findall
- search가 최초로 매칭되는 패턴 반환이면, findall은 매칭되는 전체 패턴 반환
- 매칭 전체를 리스트로 반환


```python
re.search(r'a+','aaaa')
```




    <re.Match object; span=(0, 4), match='aaaa'>




```python
re.findall(r'a+', 'aaaa')
```




    ['aaaa']




```python
re.findall(r'[\w-]+@[\w.]+', 'test-3@gmail.com haha test2@gmail.com nice test')

```




    ['test-3@gmail.com', 'test2@gmail.com']



## sub
- 문자 대치


```python
re.sub(r'[\w-]+@[\w.]+','great', 'test-3@gmail.com haha test2@gmail.com nice test')
```




    'great haha great nice test'




```python
re.sub(r'[\w-]+@[\w.]+','great', 'test-3@gmail.com haha test2@gmail.com nice test' , count =1)
# count = 1 ->한개만 (deafault -> count =0 -> 전체)
```




    'great haha test2@gmail.com nice test'



## compile


```python
#자주 사용할 패턴 컴파일
email_reg = re.compile(r'[\w-]+@[\w.]+')
email_reg.search('test@gmail.com haha good')
```




    <re.Match object; span=(0, 14), match='test@gmail.com'>



## 연습문제
1. 이메일 추출
2. 올바른 이메일만 추출


```python
#1
import requests
from bs4 import BeautifulSoup

def get_news_content(url):
    response = requests.get(url)
    content = response.text
    
    soup = BeautifulSoup(content, 'html5lib')
    div = soup.find('div', attrs = {'id' : 'harmonyContainer'})
    
    content = ''
    for paragraph in div.find_all('p'):
        content +=paragraph.get_text()
    return content

news1= get_news_content('https://news.v.daum.net/v/20190617073049838')
print(news1)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-36-0aedca9c2292> in <module>
         15     return content
         16 
    ---> 17 news1= get_news_content('https://news.v.daum.net/v/20190617073049838')
         18 print(news1)
    

    <ipython-input-36-0aedca9c2292> in get_news_content(url)
         11 
         12     content = ''
    ---> 13     for paragraph in div.find_all('p'):
         14         content +=paragraph.get_text()
         15     return content
    

    AttributeError: 'NoneType' object has no attribute 'find_all'



```python
email_reg = re.compile(r'[\w-]+@[\w.]+\w+')
email_reg.search(news1)
```


```python
#2
import re
webs = ['http://www.test.co.kr', 
        'https://www.test1.com', 
        'http://www.test.com', 
        'ftp://www.test.com', 
        'http:://www.test.com',
       'htp://www.test.com',
       'http://www.google.com', 
       'https://www.homepage.com.']
m=[]
for i in webs:
    m += re.findall(r'https?://w{3}\.[\w.]+\w+$', i )
print(m)


```

    ['http://www.test.co.kr', 'https://www.test1.com', 'http://www.test.com', 'http://www.google.com']
    


```python
#2 답
webs = ['http://www.test.co.kr', 
        'https://www.test1.com', 
        'http://www.test.com', 
        'ftp://www.test.com', 
        'http:://www.test.com',
       'htp://www.test.com',
       'http://www.google.com', 
       'https://www.homepage.com.']



web_reg = re.compile(r'https?://[\w.]+\w+$')
#map 함수사용 --> 새로운 리스트를 규칙에 의해 사용
list(map(lambda w:web_reg.search(w) != None, webs))
```




    [True, True, True, False, False, False, True, False]




```python

```
