#  마크다운 문법

## 1. 제목(heading)

제목은 `#`으로 표현 가능하다. 제목의 레벨은 `#`의 갯수로 나타내는데, 1~6단계가지 표현 가능하다. 

### 제목3

#### 제목4

##### 제목5

###### 제목6

## 2. 목록

목록은 순서가 있는 목록과 순서가 없는 목록으로 구분된다. 

1. 순서가 있는 목록

2. 순서가 있습니다.

   1. tab을 통해 단계를 표현할 수 있습니다. 

   엔터

3. 엔터 

* 순서가 없는 목록

  * tab을 통해 단계를 나타낼 수 있습니다.

  엔터

* 엔터

  

## 3. 코드 블록

인라인 코드 블록과 전체 코드 블록이 있으며, 전체 코드 블록은 언어에 따른 syntax highlighting  기능을 대부분 지원한다. 

`inline`

```python
print('hello')
#파이썬 주석
def foo(a):
    return a
```

```javascript
# 파이썬에서는 주석
//자바스크립트 주석
```

## 4. 주석

[구글](https://google.com)

## 5. 인용문

> 인용문을 작성할 수 있습니다. 

## 6. 표

| 순번 | 이름   |
| ---- | ------ |
| 1    | 홍길동 |
| 2    | 펭수   |

## 7. 이미지

![V2_1920x![test](C:\Users\student\test.png)1080](C:\Temp\V2_1920x1080.jpg

위의 이미지는 절대 경로(c드라이버)로 작성되어 있기 때문에, 외부에 공개(github)하면 이미지가 깨져서 보인다. 

따라서, 다음과 같이 typora 설정을 하자. 

* 파일>환경 설정에서 `이미지` 탭 클릭하고 아래의 내용 모두 체크
  * 로컬 이미지에 위 규칙 적용
  * 온라인 이미지에 위 규칙 적용
  * 가능하다면 상대적 위치 사용
* copy image to custom folder를 누른 후
  * ./images로 설정
* 설정하면, 이후 이미지로부터 마크다운 파일 위치를 기준으로  images 폴더를 생성하여 이미지를 복사함.
![test](images/test-1577335539642.png)

## 8. 기타 문법

수직선

---

**굵게(볼드체)**

*기울임체(이탤릭체)*

~~취소선~~
