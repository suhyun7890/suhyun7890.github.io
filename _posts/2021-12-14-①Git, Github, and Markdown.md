---
layout: post
title: "①Git, Github, and Markdown"
date: 2021-12-14 18:09:30 +0900
categories: 유레카프로젝트
comments: true
---

## Git이란?

- 분산 버전관리 시스템
- 여러 사람이 한 코드를 관리할 수 있음

### 로컬 저장소 생성

```
# 현재 작업 중인 디렉토리를 git 저장소로 지정
git init

# 현재 Git 상태 확인
git status

# example.py를 생성 혹은 수정
git add example.py

# 변경사항 등을 반영한 new commit 생성 
git commit -m "comment"

# commit 기록 확인 (Author, Commitor, Date 등)
git log
```

### Git Branch

- 코드의 흐름을 분산시켜 더욱 효율적인 개발이 가능함

```
# Branch 생성
git branch <branch_name>

# Branch 전환
git checkout <branch_name>

# Branch 병합
git merge <branch_name>

# Branch 삭제
git branch -d <branch_name>
```


### Github

- Git의 로컬 저장소를 넘어 원격 저장소에서도 협업이 가능함


## Makrdown

- 일반 텍스트로 서식이 있는 문서를 작성하는 방법

#### 문법 1. Header
- #, ##, ### 등으로 제목(header) 작성

#### 문법 2. Italic
- 앞뒤에 *나 _를 붙여 기울임체(italic) 작성

#### 문법 3. Bold
- 앞뒤에 **나 __를 붙여 강조체(bold) 작성

#### 문법 4. Strikethrough
- 앞뒤에 ~를 붙여서 취소선(strikethrough) 작성

#### 문법 5. Unordered List
- -나 *으로 순서 없는 리스트(unordered list) 작성

#### 문법 6. Ordered Lost
- 1, 2, 3 등으로 순서 리스트(ordered list) 작성

#### 문법 7. Code
- 앞뒤에 `을 붙여서 코드(code) 작성
- `print()`

#### 문법 8. Code Block
- 앞뒤에 ```을 붙여서 코드블록(code block) 작성
```python
x = input()
y = x + 2
```

##### 이 외의 문법은 Markdown Guide - Basic Syntax에서 확인 가능