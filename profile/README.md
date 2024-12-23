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

프론트엔드 : React.js, Vite, TailwindCSS, TypeScript, Zustand

백엔드 : Nest.js, Typeorm, MySQL2, JWT

협업 : Slack, Notion

배포 : GitHub, GitHubActions, AWS EC2, Firebase Hosting



## 4. 프론트엔드 서비스 흐름도

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

<br/>

## 5. 백엔드 서비스 흐름도

```mermaid
flowchart TB
    
subgraph Local1 ["로컬 컴퓨터"]
    direction RL
    Local-branch-main1("Branch main")
    Local-branch-feat1("Branch feat")
    
    Local-branch-main1 --> Local-branch-feat1
end
subgraph Local2 ["로컬 컴퓨터"]
    direction LR
    Local-branch-main2("Branch main")
    Local-branch-feat2("Branch feat")

    Local-branch-main2 --> Local-branch-feat2
end

subgraph GitHubRepo ["GitHub"]
    direction BT
    subgraph feature ["Feature Branch"]
        Github-Branch-feat1("Feature1")
        Github-Branch-feat2("Feature2")
    end
    
    Github-Branch-main("main")
    
    feature -- Pull Request --> Github-Branch-main
end

Local1 --- feature
Local2 --- feature

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

FrontEnd("웹 사이트")

Route53 <----> FrontEnd
```








<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
