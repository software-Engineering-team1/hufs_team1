# hufs_team1

### :bulb: project subject
머신러닝 기반 사용자 맞춤 개인 코디 서비스
<br>

### :bulb: Project Problem Statement
#### Functional
* SMART ICE CLOSET 은 바쁜 현대인과 옷을 고르는데 어려움을 겪는 일반인을 위한 서비스로 날씨, 해시태그, 색을 기반으로 옷을 추천해주는 스마트 옷장이다. 

<br>

* 기존의 코디 추천 시스템은 쇼핑몰의 옷 기반으로 가장 어울릴 만한 옷을 조합하여 사용자에게 보여주는 추천 시스템을 사용하고 있지만, SMART ICE CLOSET 은 본인의 옷을 기반으로 한 추천시스템이다. 

<br>

* 먼저, 사용자가 자신의 옷을 촬영하여 등록한다. 그 후에, 원하는 색상과 해시태그를 선택하여 추천버튼을 누르게 되면 현재 날씨와 사용자의 취향에 맞게 현재 옷장에 있는 옷으로 코디 추천을 하게 된다. <br> 또한, 사용자의 옷 착용 빈도수를 추천에 반영하여 더욱 사용자에 최적화된 추천을 할 수 있게 한다. 

<br>

* SMART ICE CLOSET은 날씨를 기반으로 하기때문에 날씨 정보 API를 사용한다. 날씨 정보가 필요한 이유는 현재날씨에 적합한 옷을 추천하기 위함이다.(롱패딩을 여름에 추천해주면 안된다.) 
또한 사용자의 옷장에 옷이 있는지 없는지 판단하고, 현재 옷장에 존재하는 옷들 중에서 추천해주기 위해 임베디드보드와 카메라가 옷장에 설치되어 있다.

#### Nonfunctional
* 현재 날씨를 반영하기 위에 날씨 정보를 30분간격으로 refresh 해준다.
* 옷 정보 초기화 버튼이 없으므로 저장된 옷 정보들을 초기화 시킬 수 있는 결함을 발생시키면 안된다.
* 옷에 대한 분류가 정확히 이루어져야 한다.
* 사용자의 취향에 따라 정확히 추천되어야 한다.


### :bulb: participants
|Participant|Roles|Skills|Training needs|
|:---|:---|:---|:---|
|이유진|Team Leader(liasion) <br> Meachine Learning Developer <br> Embedded developer|programming : Python, Java, Javascript, C <br> databases : MySQL, SQLite <br> Configuration management <br> Framework : Django, Express.js, Jsp|Meachine Learning, UML|
|이재성|UI/UX Designer <br> Android Application Developer|programming : C, Python, Kotlin <br> Configuration management <br> Framework : Django|UML|
|정지원|Database designer <br> Backend Developer|programming ; C, Python, Java, Javascript <br> Configuration management <br> Framework : Spring, Django|UML <br> MySQL|
|이영상|Meachine Learning Developer <br> Facilities management|programming : C, Python, Java <br> Configuration management <br> Framework : Django|UML|
