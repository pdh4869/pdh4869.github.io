# dhpark's Github for Development
![image](https://github.com/pdh4869/pdh4869.github.io/assets/76561901/7332fca7-ccbe-4420-bb50-5b58fbcf8d4b)

### Stack
<img src="https://img.shields.io/badge/Vue.js-35495E?style=flate&logo=vuedotjs&logoColor=4FC08D"/>
<img src="https://img.shields.io/badge/html5-E34F26?style=flat&logo=html5&logoColor=white"/> 
<img src="https://img.shields.io/badge/css-1572B6?style=flat&logo=css3&logoColor=white"/>
<img src="https://img.shields.io/badge/javascript-F7DF1E?style=flat&logo=javascript&logoColor=black"/>
<img src="https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white"/>
<img src="https://img.shields.io/badge/spring-6DB33F?style=flat&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/springboot-6DB33F?style=flat&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/mariaDB-003545?style=flat&logo=mariaDB&logoColor=white"/>
<img src="https://img.shields.io/badge/postgresql-4169e1?style=flat&logo=postgresql&logoColor=white"/>
<img src="https://img.shields.io/badge/linux-FCC624?style=flat&logo=linux&logoColor=black"/>
<img src="https://shields.io/badge/Windows--9cf?logo=Windows&style=social"/>
<img src="https://img.shields.io/badge/python-3776AB?style=flat&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Language-C?style=flat&logo=C&logoColor=white&color=%23A8B9CC"/>


### Tools
<img src="https://img.shields.io/badge/Visual%20Studio%20Code-007ACC?style=flat&logo=Visual%20Studio%20Code&logoColor=white"/>
<img src="https://img.shields.io/badge/Anaconda-44A833?style=flat&logo=Anaconda&logoColor=white"/>
<img src="https://img.shields.io/badge/Eclipse%20IDE-2C2255?style=flat&logo=Eclipse%20IDE&logoColor=white"/>
<img src="https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white"/>
<img src="https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white"/>
<img src="https://img.shields.io/badge/Slack-4A154B?style=flat&logo=slack&logoColor=white"/>
<img src="https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=Postman&logoColor=white"/>
<img src="https://img.shields.io/badge/Vmware-607078?style=flat&logo=Vmware&logoColor=white"/>


OS - Ubuntu 22.04.3 LTS (WSL)
Tool - Visual Studio Code

# 배포 방법
```
// Docker hub에 image 배포 
sudo docker run --name blog-1 \\n-p 9052:80 -v /home/dhpark/code/pdh4869.github.io:/usr/share/nginx/html \\n-d nginx
sudo docker tag blog-1 dhparkdocker/blog-1:0.1.0
sudo docker push dhparkdocker/blog-1:0.1.0

// fly.toml 수정
// (Dockerfile 사용하지 않으려면 build를 nginx로, 배포할 블로그 폴더에서 cp . /usr/share/nginx/html/ 수행함)
# fly.toml app configuration file generated for pdh4869-github-io on 2024-02-13T17:34:30+09:00
#
# See https://fly.io/docs/reference/configuration/ for information about how to use this file.
#

app = 'pdh4869-github-io'
primary_region = 'nrt'

[build]
  #image = "nginx"
  #image = "dhparkdocker/blog-1:0.1.0"
  dockerfile = "Dockerfile"

[http_service]
  internal_port = 80
  force_https = true
  auto_stop_machines = true
  auto_start_machines = true
  min_machines_running = 0
  processes = ['app']

[[vm]]
  cpu_kind = 'shared'
  cpus = 1
  memory_mb = 256


// Dockerfile 수정
FROM nginx
COPY . /usr/share/nginx/html/


```

# 감사 - 디자인 템플릿 원천 코드
https://html5up.net/aerial
