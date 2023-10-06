# EduOline
1. Introduction to the functions of the project
This is a B2C model vocational skills online education system, which is divided into a front-end user system and a back-end operation platform.
2. Functional classification of projects
   Front-end display: homepage site, course center, user center, lecturer display, articles, comments and Q&A
   Backend system: member management, lecturer management, course management, article information, Q&A management, advertising management, statistical analysis, message management (system messages, email messages, short messages), help center
   Online on-demand: Alibaba Cloud COS, video on demand, messaging
   Online payment: WeChat login and payment
3. Core requirements and technical implementation of the project
   Performance: Consider high-frequency centralized access. The number of user visits in the initial stage of the project is not large. If you consider operational promotion, you may see a sudden increase in server visits. Therefore, you must consider distributed deployment and introduce caching;
   Scalability: System functions will continue to expand with the increase in the number of users and changing Internet user needs. Therefore, considering the scalability requirements of the system, it is necessary to use a microservice architecture and introduce message middleware;
   High availability: storage is highly reliable. A variety of abnormal situations need to be considered: machine failure, computer room failure. For machine failure, we need to design a MySQL same-machine room backup plan; for machine room failure, we need to design a MySQL cross-machine room synchronization plan.
   Security: System information has a certain degree of privacy. For example, users' personal identity information does not contain strong privacy or sensitive information. Therefore, account password management and database access control are used.
   Cost: The main costs of video websites are server costs, traffic costs, storage costs, and streaming media R&D costs. Small companies can consider using cloud servers and cloud services.
4. Project technical structure
   Customer Service System:
     Web publishing layout: CICD + K8S + cloud native storage
   Backend Management System:
     1) Front-end:
           Browser: HTML5, CSS3, JS, Ajax, ECharts, SEO
           NodeJS Server: Node.js, NPM, Webpack, Bavel, ES6, VUE, ElementUI, EasyMock
     2) Backend:
          Business layer: Alibaba Cloud video on demand, WeChat login and payment, EasyExcel
          User layer: SSO, JWT, OAuth 2.0, third-party APP login, SpringSecurity
          Service layer:
                  Configuration center: Nacos, Git
                  Service Center: Nacos, Feign, GateWay, Spring Cloud Bus
                  Message queue: RabbitMQ
          Development layer:
                  Development framework: SpringBoot, Spring Cloud, MyBaties_Plus, Spring MVC, Swagger
                  Server: CICD+K8S released
                  Container: Docker, Containerd
          Storage layer: Rook-ceph, MySQL, Redis, Alibaba Cloud OSS, system log, HikariCP
