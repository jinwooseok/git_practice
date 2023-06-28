# git_practice
이 프로젝트는 git을 연습하기 위한 저장소이다.

See [Demo](https://www.google.com/)

###[Demo]는 html에서 <a>와 같은 역할

<a href="https://www.google.com/">Demo</a>

## Documentation

###Installation

```shell
$ git clone {repo url}
$ cd {reponame}
$ pip install -r requirements.txt
```

###How To Start

```shell
$ python main.py
```

###Dependency

- Python==3.10
- django==3.0.0
- requests==0.10.0

### Features

- 오늘의 운세 출력
- 오늘의 운세 저장
- 오늘의 운세 더보기

 웹프레임 설계

![Untitled](%E1%84%8B%E1%85%B0%E1%86%B8%E1%84%91%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%B7%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%80%E1%85%A8%20bdfdff72c0724605beec2b47d55e9772/Untitled.png)

![Untitled](%E1%84%8B%E1%85%B0%E1%86%B8%E1%84%91%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%B7%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%80%E1%85%A8%20bdfdff72c0724605beec2b47d55e9772/Untitled%201.png)

main

| 요소 | 특징 | 기능 | url 이동 |
| --- | --- | --- | --- |
| main-1 |  | 클릭 시 analytics&graph 페이지로 이동 | o |
| main-2 |  | 클릭 시 merge&process 페이지로 이동 | o |
| main-3 | login 전에는 hidden, login 시 등장 | 클릭 시 file_management 페이지로 이동 | o |

---

![Untitled](%E1%84%8B%E1%85%B0%E1%86%B8%E1%84%91%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%B7%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%80%E1%85%A8%20bdfdff72c0724605beec2b47d55e9772/Untitled%202.png)

merge&process 

| 요소 | 특징 | 액션 | url 이동 |
| --- | --- | --- | --- |
| mp-1 |  | 클릭 시 analytics&graph 페이지로 이동 | o |
| mp-2 |  | 클릭 시 merge&process 페이지로 이동 | o |
| mp-3 | login 전에는 hidden, login 시 등장 | 클릭 시 file_management 페이지로 이동 | o |
| mp-3-1  * | mp2-1에 해당하는 열을 보여줌 | 클릭 시 3-2에 해당하는 열의 table추가 | x |
| mp-3-2 | mp-3-1에서 선택한 열로 구성된 테이블을 보여줌. |  | x |

---

![Untitled](%E1%84%8B%E1%85%B0%E1%86%B8%E1%84%91%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%B7%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%80%E1%85%A8%20bdfdff72c0724605beec2b47d55e9772/Untitled%203.png)

analytics&graph 

| 요소 | 특징 | 액션 | url 이동 |
| --- | --- | --- | --- |
| ag-1 | 기능을 포함한 네비게이션 바 |  | x |
| ag-1-1 | 관리중인 파일을 호출 | 클릭 시 파일선택 모달 호출 | x |
| ag-1-2 | 분석을 위한 조건 호출 | 클릭 시 변수를 선택하는 모달 호출 | x |
| ag-1-3 | merge&process로 이동 | 클릭 시 merge&process 페이지로 이동 | o |
| ag-1-4  * | 그래프 도구 호출 | 그래프 생성 조건을 담은 모달 호출 | x |
| ag-2 | 테이블이 포함된 영역 |  | x |
| ag-2-1  * | 시트 추가 시 새로운 파일 선택 | 파일 선택 창 호출 | x |
|  |  |  |  |

---

![Untitled](%E1%84%8B%E1%85%B0%E1%86%B8%E1%84%91%E1%85%B3%E1%84%85%E1%85%A6%E1%84%8B%E1%85%B5%E1%86%B7%20%E1%84%89%E1%85%A5%E1%86%AF%E1%84%80%E1%85%A8%20bdfdff72c0724605beec2b47d55e9772/Untitled%204.png)

file_management

| 요소 | 특징 | 액션 | url 이동 |
| --- | --- | --- | --- |
| fm-1 | 파일의 상태를 보여줌 |  | o |
| fm-2  * | 관리 파일을 선택 및 삭제 | 클릭 시 파일 옆에 체크박스 활성화 | o |
| fm-3  * | login 전에는 hidden, login 시 등장 | 클릭 시 파일 저장 과정 실행 | o |
|  |  |  |  |
|  |  |  |  |

---

*** fm-3** 

파일 업로드 창 호출

파일을 업로드

업로드된 파일 > multiple file, post 형식으로 url 전송 > view > django orm > mysql_db table에 저장

파일저장형식

유저별로 생성 > 유저 고유id와 파일 고유id를 key로 하여 저장

파일이름규칙

-공백>’_’ , 중복이름파일>번호매김, 확장자 포함, 길이 30자 이내, 특수문자 불가능

*** fm-2**

관리 파일 삭제 > db에서 선택한 유저 고유id, 파일 고유id를 찾아 삭제

*** ag-1-4**

그래프 도구 호출 시 기준으로 할 열 선택 > 생성할 그래프의 예시 및 join방식을 보여줌 > 선택 시 그래프를 생성

*** ag-2-1**

시트 추가를 누를 시에 파일이 나열되어 있는 모달 호출

파일 선택 시 작업: db에서 파일경로를 가져온다 → django view에서 파일경로를 통해 파일을 가져온다 → 파일을 json의 형태로 변환 → 템플릿에 렌더링을 진행

*** mp-3-1**

mp-2에서 여러 테이블을 다루기 때문에 대분류로 테이블명, 소분류로 column명을 보여줌

ag-1-4와 같이 기준으로 할 열을 선택 → 기준으로서의 조건에 부합하지 않으면 데이터를 처리하여 맞추는 방향으로 유도 → 부합할 경우 기준으로 하여 계속 column을 선택 → 원하는 형태로 변환
