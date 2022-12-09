# My Hompage Project
## 아키텍처
### 개요
- 전체적으로 웹서버와 DB서버로 구성됨
- 설계도 피그잼 링크 => https://www.figma.com/file/Dk27FnkDnW8nDTyPdlUUKm/myhomepage-project-architecture?t=3XalnG514n5f9vbY-6

### 웹서버
- 웹서버는 EC2 인스턴스에 우분투를 탑재함
- 우분투에서 도커로 Node.js와 Nginx 컨테이너를 각각 구동하고 서로 연계할 예정

### Node.js 서버
- tsc-watch: 코드 변경을 감지하여 자동으로 서버를 재시작 해주는 모듈. 개발시에만 사용하고 배포시에는 pm2로 전환해야 할 것으로 보임.
- marked: 마크다운 문자열을 html로 파싱해주는 모듈. 초기 확인용으로 사용하고 추후 자체 제작 모듈로 교체할 예정.
- dynamoose: MongoDB의 mongoose와 유사한 ODM(Object Document Mapper) 툴. RDBMS의 ORM은 편의적인 성격이 큰 반면, NoSQL에서는 원활한 협업과 유지보수를 위해 가급적 ODM을 사용해야 할 것으로 보임.

### DB서버
- DB서버는 AWS의 DynamoDB를 사용
