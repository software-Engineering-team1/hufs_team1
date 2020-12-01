# hufs_team1

### :bulb: project subject
머신러닝 기반 사용자 맞춤 개인 코디 서비스
<br>

### :bulb: participants
|Participant|Roles|Skills|Training needs|
|:---|:---|:---|:---|
|이유진|Team Leader(liasion) <br> Machine Learning Developer <br> Embedded developer|programming : Python, Java, Javascript, C <br> databases : MySQL, SQLite <br> Configuration management <br> Framework : Django, Express.js, Jsp|Machine Learning, UML|
|이재성|UI/UX Designer <br> Android Application Developer|programming : C, Python, Kotlin <br> Configuration management <br> Framework : Django|UML|
|정지원|Database designer <br> Backend Developer|programming ; C, Python, Java, Javascript <br> Configuration management <br> Framework : Spring, Django|UML <br> MySQL|
|이영상|Machine Learning Developer <br> Facilities management|programming : C, Python, Java <br> Configuration management <br> Framework : Django|UML|

<br>

### :bulb: Project Problem Statement
#### Functional
* SMART ICE CLOSET 은 바쁜 현대인과 옷을 고르는데 어려움을 겪는 일반인을 위한 서비스로 날씨, 해시태그, 색을 기반으로 옷을 추천해주는 시스템이다. 

<br>

* 기존의 코디 추천 시스템은 쇼핑몰의 옷 기반으로 가장 어울릴 만한 옷을 조합하여 사용자에게 보여주는 추천 시스템을 사용하고 있지만, SMART ICE CLOSET 은 본인의 옷을 기반으로 한 추천시스템이다. 

<br>

* 먼저, 사용자가 자신의 옷을 촬영하여 등록한다. 그 후에, 원하는 색상과 해시태그를 선택하여 추천버튼을 누르게 되면 현재 날씨와 사용자의 취향에 맞게 현재 옷장에 있는 옷으로 코디 추천을 하게 된다. 또한, 사용자의 옷 착용 빈도수를 추천에 반영하여 더욱 사용자에 최적화된 추천을 할 수 있게 한다. 

<br>

* SMART ICE CLOSET은 날씨를 기반으로 하기때문에 날씨 정보 API를 사용한다. 날씨 정보가 필요한 이유는 현재날씨에 적합한 옷을 추천하기 위함이다.(롱패딩을 여름에 추천해주면 안된다.) 
또한 사용자의 옷장에 옷이 있는지 없는지 판단하고, 현재 옷장에 존재하는 옷들 중에서 추천해주기 위해 임베디드보드와 카메라가 옷장에 설치되어 있다.

#### Nonfunctional
* 현재 날씨를 반영하기 위에 날씨 정보를 30분간격으로 refresh 해준다.
* 옷 정보 초기화 버튼이 없으므로 저장된 옷 정보들을 초기화 시킬 수 있는 결함을 발생시키면 안된다.
* 옷에 대한 분류가 정확히 이루어져야 한다.
* 사용자의 취향에 따라 정확히 추천되어야 한다.

<br>

### :bulb: Use case Diagram & Scenario
#### Use case Diagram (이유진)
![image](https://user-images.githubusercontent.com/53362054/95646672-f4848680-0b05-11eb-8b21-3b008c0da427.png)

#### Scenario
|||
|:---|:---|
|Scenario no.1|Take a picture of clothes|
|Participating actor instances|youjin : User / Phone camera|
|Flow of events|1. youjin은 어플의 Camera 버튼을 누른다. <br> 2. youjin은 capture 버튼을 눌러 Phone camera로 검은색 반팔 티셔츠를 촬영한다. <br> 3. youjin은 save photo 버튼을 눌러 옷 사진을 저장한다. <br> 4. youjin이 어플의 My closet 버튼을 누른다. <br> 5. youjin은 top 카테고리에 들어가 검은색 반팔 티셔츠가 등록되어있는지 확인한다.|

|||
|:---|:---|
|Scenario no.2|Recommended today's cody|
|Participating actor instances|jiwon : User / young : Open weather API provider|
|Flow of events|1. jiwon이 어플의 today cody 버튼을 누른다. <br> 2. jiwon이 검정색과 캐주얼스타일을 선택해 recommend 버튼을 누른다. <br> 3. jiwon은 young이 제공한 날씨에 맞는 세벌의 cody를 추천받는다. <br> 4. jiwon은 마음에 드는 cody 한 벌을 골라 select this cody 버튼을 누른다.|

#### Use case Description (이유진)
|||
|:---|:---|
|Use case Description|Recommend cody|
|Participating actor instances|User|
|Flow of events|1. User가 어플의 today cody 버튼을 누른다. <br> 2. User는 원하는 색상과 스타일을 선택해 recommend 버튼을 누른다. <br> 3. Server는 사용자가 선택한 색상과 스타일, 날씨 정보를 토대로 세가지 옷 세트를 추천한 후 결과를 Mobile Application 으로 전송한다. <br> 4. Mobile Application은 Server로부터 받은 결과를 어플에 띄운다. <br> 5. User는 세가지 옷 세트중에 가장 마음에 드는 세트 하나를 선택한다.|

<br>

### :bulb: Sequence diagram
#### Register clothes (정지원)
![image](https://user-images.githubusercontent.com/53362054/95746414-b50a9580-0cd1-11eb-9260-84c6b481b470.png)

#### Recommend clothes (이영상)
![image](https://user-images.githubusercontent.com/53362054/95746659-20546780-0cd2-11eb-8d61-cce5655dd2d8.png)

#### Recognize clothes comming in/out (이재성)
![image](https://user-images.githubusercontent.com/53362054/95749371-6f040080-0cd6-11eb-8a08-0577dbc2f6b3.png)

<br>

### :bulb: Class diagram (다같이)
![image](https://user-images.githubusercontent.com/53362054/95816251-97810e80-0d59-11eb-912d-077441b470d8.png)

<br>

### :bulb: Object diagram (이유진)
![image](https://user-images.githubusercontent.com/53362054/95816275-a8ca1b00-0d59-11eb-8e00-bc9846f1ec73.png)

<br>

### :bulb: Design goal
* Usability - 사용자가 사용하기 쉽도록 application으로 만든다.
* Response time - Android에서 사용자의 옷 image를 로드할 때 imageView대신 glide라이브러리를 사용해서 빠르게 로드할 수 있게 만든다.

### :bulb: Deployment Diagram
![image](https://user-images.githubusercontent.com/53362054/100755228-4cb57600-342f-11eb-9fec-f549ad7f797e.png)


#### 1. 옷 등록 <br>
```
TakePictures(Android-RegisterClothes) -> SendData(Android-Communication) 
-> <<socket>> 
-> GetData(MLServer-Communication) -> ClassifyClothes(MLServer-ClassifyClothes) -> SendData(MLServer-Communication) 
-> <<http>> 
-> GetData(Server-Communication) -> Database
```
* Android 에서 옷 사진 촬영 -> ML로 사진 소켓으로 전송 -> ML에서 옷 분류(색, 패턴, 카테고리/Train된 Model을 통해서) -> 결과를 서버로 전송 -> 서버에서 받아서 Database에 저장
  
#### 2. 옷 추천 <br>
```
SelectColor&SelectStyle&GetWeatherInfo(Android-GetInfoForRecommend) -> SendData(Android-Communication) 
-> <<http>> 
-> GetData(Server-Communication) -> RecommendCody(Server-WebServer) -> SendData(Server-Communication) 
-> <<http>> 
-> GetData(Android-GetData)
```
* Android에서 색,스타일, 날씨정보 서버로 전송 -> 추천알고리즘(이때 LoadData를 통해 Database에서 옷 정보들 가져옴) -> 추천결과 Android로 다시 전송  
  
#### 3. 옷 유무 체크 <br>
```
RecognizeLight+RecognizeGesture+TakePictures(EmbeddedBoard-CheckClothesStatus) -> SendData(EmbeddedBoard-SendData) 
-> <<socket>> 
-> GetData(MLServer-Communication) -> ClassifyClothes(MLServer-ClassifyClothes) -> SendData(MLServer-Communication) 
-> <<http>> 
-> GetData(Server-Communication) -> Database
```

* 옷장에 부착된 라즈베리파이에서 옷을 넣었는지/뺐는지 센서로 확인& 넣은/뺀 옷을 카메라로 사진촬영 -> ML로 사진과 유무 정보 socket으로 전송 -> ML 에서 카메라로 찍힌 옷을 분류(어떤 옷인지) -> Server로 옷의정보와 옷의 유무를 전송 ->  Server는 받아서 DB에 저장

