## 레포지토리 설명 (Repository Description) 
    - "학사 관리 시스템 프로젝트 'Allcle'의 Onpremise 인프라를 생성하는 Ansible 플레이북 레포지토리입니다."
    - "vSphere와 vCenter, ESXI Host를 사용한 가상화 환경에서 구축하였습니다."

## 프로젝트 설명(Project Description)
    - 주제 : 학사관리 시스템 < 수강 신청 웹프로젝트 (ALL - CLE) >

    ### 고객 요구 사항 (Customer Requirements)
        - **수강신청**, 학적관리, 온라인 수업 강의장 등을 제공하는 대학교 학사 관리 시스템을 구축한다.

        - 학사관리시스템은 **온프레미스 환경**에 구축하여 작동한다.
        
        - 수강신청의 경우 전교생이 동시에 접속하기에 그 트래픽을 감당할 수 있도록 구축한다.
            - 학과 정원 : 140명, 학과 : 20개, 교과 과정 : 4개학년    ⇒     **전교생 : 11,200 명**
        - 수강 신청의 경우 수강 신청 기간이 아닌 경우 사용하지 않기 때문에 AWS에서 서비스를 제공하고 트래픽이 늘어날 경우에 수요에 맞게 **Auto-Scaling** 해주고, 수강 신청 기간이 종료 될 경우 최소 사양으로 서비스를 유지한다.   ⇒ **비용관리**

        - 수강 신청 시 로그인하여 접속한 학생의 전공에 따라 해당 학생의 전공 과목이 우선적으로 나타나게 한다.

        - 과목 속성 구분 기능을 제공하여 전공 과목과 교양 과목을 따로 한번에 확인할 수 있는 기능을 제공한다.

        - 과목 이름을 검색해 찾을 수 있는 기능을 제공한다.

        - 여러 개의 과목을 담아 (장바구니) 한번에 신청할 수 있는 기능을 제공한다.

        - 시스템 구축 예산은 **700만원**으로 한다. **1000만원**

        - AWS 리전의 장애 발생 시 사용이 불가능하기에 다른 리전에서 즉각적으로(빠른 복구 시간) 서비스가 정상 작동할 수 있도록 구축한다.


    ### 사용 리소스
        - Router : Untangle

        - VM
            - Linux : Rocky Linux 9
            - Windows : Windows server 2022
        
        - Database
            - MongoDB
        
        - File System
            - NFS
        
        - DNS
            - Windows DNS 관리자
        
        - Load Balancer
            - HAProxy
            - Keepalived

        - K8s Cluster
            - Deployment
                - Pods
                    - Nginx
                    - Flask
            - Autoscaling
                - HPA
        
        - Monitoring Tools
            - Grafana
            - Prometheus
        
        - Load Testing Tools
            - Locust
