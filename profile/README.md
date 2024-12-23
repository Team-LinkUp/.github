# 📖 Link Up

![image](https://github.com/user-attachments/assets/3eb77613-171f-465f-a347-258759ff4e6d)

- 코딩 스터디부터 러닝 크루까지 다양한 모임을 만들고 찾을 수 있는 서비스입니다.
- 프로젝트 기간 : 24년 12월 6일(금) ~ 24년 12월 23일(월) (약 2주)


## 1. 팀원 구성

<div align="center">

| **조승연** | **채문성** | 공담형 | 김현희 |
| --- | --- | --- | --- |
| [<img src="](https://github.com/layout-SY)https://avatars.githubusercontent.com/u/111514472?v=4" height=150 width=150> <br/> @layout-SY | [<img src="](https://github.com/chaesunbak)https://avatars.githubusercontent.com/u/152577867?v=4" height=150 width=150> <br/> @chaesunbak | [img src="](https://github.com/chaesunbak)[https://avatars.githubusercontent.com](https://avatars.githubusercontent.com/u/152577867?v=4)/damhyeong” /> | https://avatars.githubusercontent.com/Kim-Hyunhee |
| 프론트엔드 | 프론트엔드 | 백엔드 | 백엔드 |

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







<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
