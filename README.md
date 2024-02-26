# 🏕️ 캠핑온탑 campingOnTop

![캠핑온탑 로고](https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/98ccf4ba-f892-4069-b429-787847f04931)


<br>
<br>

# 💪 팀원 구성

<div align="left">

|                    **임태우**                    |                 **길민석**                 |                **한경훈**                |                   **이준국**                    |                **장대현**                |
| :----------------------------------------------: | :----------------------------------------: | :--------------------------------------: | :---------------------------------------------: | :--------------------------------------: |
| [@Tesssssssssy](https://github.com/Tesssssssssy) | [@gilms0730](https://github.com/gilms0730) | [@Kyungqq](https://github.com/heejiyang) | [ @Lee-Jun-Guk](https://github.com/Lee-Jun-Guk) | [@poil4291](https://github.com/poil4291) |

</div>

<br>
<br>


# Badges
<div align="left">
  <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=GitHub&logoColor=white"/>

  <br>

  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white"/>
  <img src="https://img.shields.io/badge/Amazon AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white"/>

  <br>

  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=Docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kubernetes-skyblue?style=flat-square&logo=Kubernetes&logoColor=white"/>
  <img src="https://img.shields.io/badge/Jenkins-red?style=flat-square&logo=Jenkins&logoColor=white"/>
  
  <br />
</div>

<br>
<br>

# 🖥️ Architecture

### [system architecture](https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/c525e13f-feb7-40bd-a14d-401540ba46b9)

### [Cluster Architecture](https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/e2095b2d-69f3-4e5b-8d8b-ae6551c8f8c6)


<br>
<br>

# Devops 운영 환경
<details>
<summary>docker hub images</summary>
<img width="1128" alt="docker hub frontend" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/e98d8da9-69fb-4535-8eee-5907b95cb796">
<img width="1084" alt="docker hub backend" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/b2dbdc66-68f9-45a1-bbe1-6efeb3877096">

<summary>k8s</summary>
<img width="1136" alt="k8s pv" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/bf896283-8787-4af2-8a5c-fa416cf7bd17">
<img width="1084" alt="k8s pvc" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/fd78ddfa-7ffb-4dec-a0d6-9552b7ff2fec">
<img width="1055" alt="k8s pod" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/b9906480-cc8b-4ca1-abd9-1d9c0b556bd3">
<img width="1058" alt="k8s deployment" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/bc1dc7ea-ea4d-41b7-86a7-2e2b5abfd247">
<img width="1173" alt="k8s statefulset" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/96c24ee2-1980-4815-87f3-37f1476d7d3a">
<img width="981" alt="k8s config map" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/3f942505-d3e6-4a13-9ae7-c34d4696fbb4">
</details>

<details>
<summary>Jenkins</summary>
<img width="1249" alt="jenkins 화면" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/93f4ac20-7245-4dfd-8feb-a4541a8a8b4f">
</details>

<br>
<br>

# CI/CD 시나리오
<details>
<summary>CI</summary>

1. github remote repository에 push <br>

2. github webhook으로 Jenkins에 알림 <br>

3. Jenkins가 푸쉬된 새 코드를 가져오기 위해 git clone <br>

4. Jenkins는 Build 단계에서 mvn을 통해 컴파일 및 패키지 <br>

5. 빌드 전후로 Slack의 '#백엔드' 채널로 알림 전송 (성공, 실패) <br>

</details>

<br>

<details>
<summary>CD</summary>

1. Jenkins는 Docker Build 단계에서 새로운 Docker Image를 Build하고 tag 지정 (9.x) <br>

2. Build된 Docker Image는 Docker Push를 통해 Docker Hub로 push (tessssssssy/frontend, campingontop) <br>

3. Jenkins는 미리 등록한 K8S Cluster의 master 서버에 ssh로 Deployment를 update <br>

4. update된 Deployment 파일은 kubectl 명령어를 통해 K8S Cluster에 적용 <br>

5. 배포 성공, 실패 시 Slack의 '#백엔드' 채널로 알림 전송 <br>

</details>

<br>
<br>

# CI/CD 기대 효과
<details>
<summary>CI</summary>
코드를 변경했을 때 자동으로 Build되어 빠르고 안정적으로 코드를 통합할 수 있고
항상 배포 준비가 완료된 상태를 유지할 수 있다. 

</details>

<br>

<details>
<summary>CD</summary>
개발자가 Github의 remote repository에 code를 push할 때마다 자동으로 빌드 및 배포되기 때문에
수동 배포에 비해 시간과 노력을 크게 절약할 수 있고 사용자에게 즉각적인 업데이트를 제공할 수 있다. 

</details>

<br>
<br>

# 시연 화면
<details>
<summary>frontend</summary>
<img width="689" alt="frontend1" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/e04f3e32-6bca-41f6-b0ae-338a85161592">
<img width="882" alt="frontend2" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/8cdfb3e4-9b62-4c29-a2f7-4bd59428bf53">
<img width="1092" alt="frontend3" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/9c8fd9fe-e6d4-44ad-8669-f6c24127c7a5">
<img width="1042" alt="frontend4" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/734d353a-4f29-47f2-be1f-283c758b6e96">
<img width="1009" alt="frontend5" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/8407be9e-ced3-4c22-bec3-66a8f5ac8959">
<img width="1256" alt="frontend6" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/d56a2691-4b2a-4699-955b-4827f0febd28">
<img width="1065" alt="frontend9" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/71e8bae4-a231-403b-a3f0-c7cef2efd9e8">
<img width="1202" alt="frontend7" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/872d86fa-cb1b-4615-b2fd-5e901820fc51">
<img width="1146" alt="frontend8" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/a3781c71-73d1-4ed9-84e4-578b2f1b9446">
</details>

<br>

<details>
<summary>backend</summary>
<img width="621" alt="backend1" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/786419b4-f616-4624-b52f-c614668eac06">
<img width="1261" alt="backend2" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/348f2e67-585b-4b42-8d77-f9f167e1764e">
<img width="881" alt="backend2-0" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/4588d726-d922-4c50-add6-424848d965cd">
<img width="1232" alt="backend3" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/b1354b70-29d9-420e-a168-e84766b99609">
</details>

<br>

<details>
<summary>Slack Alarm</summary>
<img width="1032" alt="slack alarm" src="https://github.com/beyond-sw-camp/be02-4th-MTM-cityCamp/assets/105422037/0eff4dbe-165f-40ce-b6ee-92de738dc90b">
</details>

<br>
<br>

# Devops project 보완 요소
<details>
<summary>완성도</summary>

1. DB를 Statefulset으로 생성하고 database 생성까지는 되었지만 백엔드와의 연결 및 통신 실패. <br>

2. Architecture를 더 상세하게 표현하지 못함. <br>

3. npm, mvn 테스트 코드 실행 못함 <br>

4. 완성된 부분을 영상 및 gif로 만들지 못함. <br> 

5. ... <br>

</details>
