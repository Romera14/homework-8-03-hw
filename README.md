# Домашнее задание к занятию "`8.3. Gitlab`" - `Паромов Роман`




## Задание 1



![настройки gitlab-runner](https://github.com/Romera14/homework-8-03-hw/blob/main/Снимок%20экрана%202022-10-30%20в%2017.14.02.png)
![настройки gitlab-runner](https://github.com/Romera14/homework-8-03-hw/blob/main/Снимок%20экрана%202022-10-30%20в%2017.14.28.png)

---

### Задание 2
```
yaml
stages:
  - test
  - build
  
test:
  stage: test
  image: golang:1.17
  script: 
   - go mod init example.com/m
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```

![Скриншоты сборок](https://github.com/Romera14/homework-8-03-hw/blob/main/Снимок%20экрана%202022-10-31%20в%2022.10.16.png)`


---
## Дополнительные задания (со звездочкой*)
### Задание 3
```
stages:
  - build
  - test

test:
  only:
    changes:
     - "*.go"
  stage: test
  image: golang:1.17
  script: 
   - go mod init example.com/m
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .
```

![скриншот сборки](https://github.com/Romera14/homework-8-03-hw/blob/main/Снимок%20экрана%202022-10-31%20в%2022.29.46.png)`
