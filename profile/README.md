## Hi there 👋

## 프론트엔드 배포 전략

```mermaid
flowchart BT
    
subgraph Front ["프론트엔드 작업"]
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

GithubAction

Github-Branch-main --> GithubAction

subgraph Firebase ["Firebase 웹 서버"]
    HTML
    CSS
    JS
end

GithubAction --> Firebase

User

Firebase <----> User

Firebase <-- 정보 교류 --> Backend["API 백엔드 서버"]
```

<br/>

## 백엔드 배포 전략

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
