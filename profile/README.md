# 📖 Link Up

![image](https://github.com/user-attachments/assets/3eb77613-171f-465f-a347-258759ff4e6d)

- 코딩 스터디부터 러닝 크루까지 다양한 모임을 만들고 찾을 수 있는 서비스입니다.
- 프로젝트 기간 : 24년 12월 6일(금) ~ 24년 12월 23일(월) (약 2주)

[프로젝트 깃허브](https://github.com/Team-LinkUp)
[프론트 깃허브](https://github.com/chaesunbak/study-matcher-frontend)
[백엔드 깃허브](https://github.com/damhyeong/Programmers_TeamRepo)
[팀 노션 페이지](https://www.notion.so/Link-Up-2882ea41fbc64059970ebd5e8e3962c2?pvs=4)


## 1. 팀원 구성

<div align="center">

## Team

|<img src="https://avatars.githubusercontent.com/u/111514472?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/152577867?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/114223031?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/96518301?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|Cho SeungYeon<br/>[@layout-SY](https://github.com/layout-SY)|[@chaesunbak](https://github.com/chaesunbak)|damhyeong<br/>[@damhyeong](https://github.com/damhyeong)|[@Kim-Hyunhee](https://github.com/Kim-Hyunhee)|
|프론트엔드|프론트엔드|백엔드|백엔드|



</div>

## 2. 역할 분담

### 🍊 조승연

- 유저 페이지
- 글, 댓글 페이지

### 👻 채문성

- 모임찾기, 모임 상세보기 페이지
- 반응형 레이아웃

### 🌝 공담형

- 유저 CRUD API 제작
- CI / CD 제작
- AWS 인프라 관리

### 😎 김현희

- 모임, 게시글, 댓글 CRUD API 제작

<br>

## 3. 기술스택

### 프론트엔드
<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=black"> <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=Vite&logoColor=white"> <img src="https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=TailwindCSS&logoColor=white"> <img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=TypeScript&logoColor=white"> <img src="https://img.shields.io/badge/Zustand-F36D00?style=for-the-badge&logo=Zustand&logoColor=white"> <img src="https://img.shields.io/badge/ReactQuery-FF4154?style=for-the-badge&logo=ReactQuery&logoColor=white">


### 백엔드

<img src="https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=NestJS&logoColor=white"> <img src="https://img.shields.io/badge/TypeORM-FE0803?style=for-the-badge&logo=TypeORM&logoColor=white"> <img src="https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white"> <img src="https://img.shields.io/badge/JWT-F36D00?style=for-the-badge&logo=JWT&logoColor=white">

### 협업

<img src="https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=Notion&logoColor=white"> <img src="https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=Slack&logoColor=white">


### 배포

<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"> <img src="https://img.shields.io/badge/githubactions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white"> <img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white"> <img src="https://img.shields.io/badge/firebase-DD2C00?style=for-the-badge&logo=firebase&logoColor=white">

## 4. 서비스 흐름도

<img width="686" alt="스크린샷 2024-12-23 오전 10 49 36" src="https://github.com/user-attachments/assets/95ed7b87-98fe-405a-97a1-d913668a7a60" /> <img width="577" alt="스크린샷 2024-12-23 오전 10 49 53" src="https://github.com/user-attachments/assets/04921046-d560-463b-ac7f-cb5231225492" />


<details>
<summary>프론트엔드 서비스 흐름도</summary>

<!-- summary 아래 한칸 공백 두어야함 -->
```mermaid
flowchart BT
    

    subgraph FrontGitHubRepo ["Frontend GitHub Repository"]
        direction BT
        subgraph feature ["Feature Branch"]
            Github-Branch-feat1("Feature1")
            Github-Branch-feat2("Feature2")
        end

        Github-Branch-main("main")
        feature -- Pull Request --> Github-Branch-main
    end

GithubAction

Github-Branch-main --> GithubAction

subgraph Firebase ["Firebase Hositng"]
    subgraph Node.js ["Node.js Web Server"]
        subgraph ReactApp ["React Application"]
    
    end
end
end

GithubAction --> Firebase


Node.js <-- HTML,CSS,JS --> User["Client(or Browser)"]

User <-- API Request & Response --> Backend["Backend Server"]
```

</details>


<details>
<summary>백엔드 서비스 흐름도</summary>

<!-- summary 아래 한칸 공백 두어야함 -->
```mermaid
flowchart TB
    
subgraph GitHubRepo ["GitHub"]
    direction BT
    subgraph feature ["Feature Branch"]
        Github-Branch-feat1("Feature1")
        Github-Branch-feat2("Feature2")
    end
    
    Github-Branch-main("main")
    
    feature -- Pull Request --> Github-Branch-main
end

subgraph GithubAction ["Github Actions"]
    direction TB
    Env("환경 변수")
    SSL("RSA 키")
    Cmd("어플리케이션 명령어")
end

Github-Branch-main --> GithubAction

subgraph AWS ["AWS"]
    direction TB
    subgraph VPC ["보안 네트워크 그룹(VPC)"]
        subgraph EC2
            PM2
            Nest("Nest Application")
            PM2 --> Nest
            Nginx("Nginx\n (https 구현 위함)")
            Nginx <---> Nest
        end
        subgraph RDS
            MariaDB
        end
        EC2 <---> RDS
    end
    subgraph Route53
        nest-aws.site("https nest-aws.site 도메인 \n (public IPv4)")
    end
    
    Nginx <--> Route53
    
end

GithubAction --> PM2

Route53 <----> Client
```
</details>


## 5. 주요 기능

- 모임 찾기 기능 : 주제와 키워드별로 원하는 모임을 찾을 수 있어요.
<img width="200" alt="스크린샷 2024-12-23 오전 11 54 19" src="https://github.com/user-attachments/assets/5381ab82-5c1d-43c3-b518-03e79a1cc176" />

- 모임 생성 기능 : 내 모임을 만들 수 있어요.
<img width="200" alt="스크린샷 2024-12-23 오후 12 19 54" src="https://github.com/user-attachments/assets/220f6f1b-1869-46f1-905a-0a14a22e41e4" />

- 모임 찾기 기능 : 원하는 모임에 참여할 수 있어요.
<img width="200" alt="스크린샷 2024-12-23 오전 11 54 53" src="https://github.com/user-attachments/assets/564f51c4-909b-4702-80d1-57f771431f6c" />

- 모임 게시판 기능 : 모임 게시판에 글과 댓글을 남길 수 있어요.
<img width="200" alt="스크린샷 2024-12-23 오전 11 56 28" src="https://github.com/user-attachments/assets/ad220367-6edd-45b7-93c4-cec5eee45798" />

- 내 정보 관리 기능 : 내 정보를 관리할 수 있어요
<img width="200" alt="스크린샷 2024-12-23 오전 11 55 11" src="https://github.com/user-attachments/assets/8a8974cb-1956-4c2b-8ff7-c347db925f02" />

## 6. 트러블 슈팅

## 7. 회고

### 조승연

- CRUD만 하면 된다는 단순한 생각으로 시작했지만 그 무엇보다 기본에 충실한 프로젝트 였다고 생각합니다.
유효성 검사와 예외 처리를 통해 UX에 부정적인 영향을 끼치지 않게끔 사용자 관점에서 생각해보려 노력했고 이를 통해 다양한 방식으로 개발을 진행하며 각종 라이브러리와 기술의 필요성을 느끼며 그 사용의 목적성이 뚜렷해지는 시간이었습니다.

이번 경험으로 다름 많은 기술을들을 알아보고, 배우며 나에게 직면한 상황에 알맞는 기술을 만들어보고 싶단 목표가 생겼습니다.

### 👻 채문성

- 그저 CRUD는 단순할 것이라고 얕보았지만, 실제 개발 과정에서는 여러 예외 상황들을 마주하면서, 로딩중, 데이터 없음, 에러, 권한없음 같은 다양한 상황에서 유저에게 올바른 피드백을 제공하는 것이 중요하다는 것 배우는 소중한 경험을 했습니다.
 또한, 바로 코드를 치기보다는,  사전에 구체적인 계획을 세우고 어떤 어려움이 있을지 정리하고, 어떤 부분에 있어서 학습이 필요할지 파악하는 것이, 성장하고 생산성을 높이는데에서 중요하다고 느꼈습니다. 프로젝트 초반에는 여유가 있었는데 이때, 예상되는 문제들을 파악하고, React Query를 통한 Optimistic Update 같은 개념들을 미리 학습하였다면 이를 적용할 시간이 충분하였을 것 같다는 아쉬움이 남습니다.
 처음으로 풀스택 팀 프로젝트를 진행해보면서, 공유해야될 정보가 많았는데 이를 어떻게 하면 효율적으로 전달하고 관리할수 있을까 고민할 수 있었습니다. 문서로 효과적으로 소통하는 법을 시도해보면서 팀 전체의 생산성을 올리기 위한 방법을 고민해볼 수 있었던 좋은 경험이었습니다.


<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
