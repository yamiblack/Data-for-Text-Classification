# Chatbot-Architecture

# Architecture


<img src="https://firebasestorage.googleapis.com/v0/b/social-robot-bao.appspot.com/o/%EC%B1%97%EB%B4%87%20%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90.jpg?alt=media&token=7034322d-07c2-401f-869b-3fcb9206093a">

###### *클릭해서 확대해서 보시길 바랍니다.*



<br>
<br>
<br>

# 데이터 규칙

 
<br>
<br>
<br>

## 1. 파일 규칙
### 1-1. 반드시 아래와 같은 방식(4단)의 경로를 가지게 해주세요
* data - 품사폴더 - 대분류폴더 - 소분류.csv 
* 예) data - 명사 - 음식 - 치킨.csv

<br>
<br>

### 1-2. 파일의 형식은 문장과 파일명을 콤마로 구분한형식으로 작성해주세요
```
예) 치킨.csv :
아 이따 치킨,치킨
오늘이야 말로 치킨,치킨
```

```
예) 커피.csv : 
달달한 커피 향기,커피 
달콤한 카페라테,커피 
```

<br>
<br>

### 1-3. 네이버 맞춤법 검사기에 맞춰서 문장을 등록해주세요 <br>
* 예) 맛 좋은 초콜렛 => 맛 좋은 초콜릿 

<br>

* 만약 네이버 맞춤법 검사기가 못잡아내는 경우 두가지 모두 써주세요
* 예) 맛 좋은 감자칩 => 
* 문장1 : 맛 좋은 감자칩 
* 문장2 : 맛 좋은 감자 칩

<br>
<br>
<br>

## 2. 조사 규칙

'이네' '이구나' '이야' <br> 
'은' '는' '이' '가' <br>
'로' '으로' '을' '를' <br>

<br>

* 위의 조사들은 사용을 지양해주세요. (무조건 안되는건 아닙니다 ) <br>
* 위에 언급한 조사 이외의 조사, 예를들어 "너도"에서 '도' 등의 <br>
사는 내용적 의미가 있으므로 사용해도 됩니다. <br>

<br>
<br>

## 3. 품사별 설명

<br>

### 3-1. 명사 : 
* 지나치게 세부적이지 않은 범위에서 제작해주시면 됩니다. <br>
* 파일당 라인수는 30 ~ 50 줄 사이이며, 되도록 동사를 사용하지 말해주세요. <br>
* 만약 동사를 쓴다면 '했다', '하다', '그랬다' 등의 포괄적인 동사만 허용하고 <br>
구체적인 동사(먹다, 보다, 자다 등)는 되도록 사용을 지양합니다.

```
* 예) 치킨.csv 
아 오늘 치킨 
혹시 너 치킨 
...
```

```
* 예) 숙제.csv 
아 숙제 했다 
숙세 했었지 
... 
```

<br>

#### 3-1-1. 명사를 작성하는 방법

* 세부적인 명사를 직접 기록하는 방법 : <br>

```
예) 치킨.csv 
아 오늘 치킨 
혹시 너 치킨
...
```

* 포괄적인 명사를 함께 기록하는 방법 : <br>
(세부적인 명사에 없는 단어만 사용합니다. <br>
예를들어 치킨.csv가 있으면 음식.csv에는 치킨이 포함되지 않습니다.) <br>


```
예) 음식.csv 
난 정말 김치 
내 어묵 
이따 갈비탕 
```

<br>
<br>
<br>


### 3-2. 동사 : 
* 마찬가지로 지나치게 세부적이지 않은 범위에서 제작해주시면 됩니다. <br>
* 파일당 라인수는 50 ~ 70 줄 사이이며, 되도록 명사를 사용하지 말해주세요. <br>
* 만약 명사를 쓴다면 '이 거', ' 저 거', 등의 대명사만 허용하고 <br>
구체적인 명사(치킨, 티비, 버스 등)는 되도록 사용을 지양합니다.

<br>

```
* 예) 놀람.csv 
진짜 놀랐어 
와 나 진짜 놀랐어 
... 
```

```
* 예) 먹음.csv 
그 거 먹는다 
아까 먹었지 
... 
```
```
* 예) 뭐야.csv 
저 거 뭐냐 
방금 뭐였지 
... 
```

<br>

#### 3-2-1. 동사를 작성하는 방법

* 일반형 : <br>

```
예) 있어.csv 
그 거 있어 
아 그런 거 있잖아 
... 
```

* 질문형 : <br>
```
예) 있니.csv 
혹시 그런 거 있니 
정말 있니 
... 
```
<br>
<br>
<br>



### 3-3. ETC
<br>

* 다양한 발화의도 + 자주나오는 명사와 동사의 조합 문장을 저장하는 공간입니다.
* 파일당 라인수는 50 ~ 70 줄 사이입니다.

<br>

#### i. 인사, 되묻기, 의성어, 대답 등의 다양한 발화 의도

<br>

#### ii. 정말 많이 나올만한 발화 의도는 여기에 적어주면 됩니다. <br>
예를들어 3-3-2번에 적어주는 문장은 명사 + 동사를 모두 포함하는 있습니다. <br>
예를 들어 이름을 물어보는 이름질문이 있을 수 있습니다. <br>
이 것은 명사(이름) + 동사(질문)이 포함됩니다. <br>

<br>
<br>
<br>


## 제작기간 : 

*2019.05 ~ 2019.12*

<br>
<br>
<br>

  
## 데이터 제작자 : 
전북대학교 소프트웨어공학과 고현웅 <br>
전북대학교 소프트웨어공학과 이주환 <br>
전북대학교 소프트웨어공학과 이주형 <br>
전북대학교 소프트웨어공학과 정현명 <br>
전북대학교 소프트웨어공학과 최민성 <br>



