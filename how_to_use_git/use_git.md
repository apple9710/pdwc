# 깃 사용가이드

## Git 설치 및 초기 설정

### Windows 설치

```bash
# Git 공식 웹사이트에서 다운로드
# https://git-scm.com/download/win
```

### macOS 설치

```bash
# Homebrew 사용
brew install git

# Xcode Command Line Tools 사용
xcode-select --install
```

### 리눅스는 안쓰실테니... 생략! (쓰시면 말해주세여)

## 이제 사용자 설정!

```bash
# --global 빼면 해당 깃 프로젝트 내에서만 설정!
# 사용자 이름 설정
git config --global user.name "Your Name"

# 사용자 이메일 설정
git config --global user.email "your.email@example.com"

# 설정 확인
git config --list

# 특정 설정 확인
git config user.name
git config user.email

```

---

## 저장소 생성 및 복제 (프로젝트 > 깃허브)

### 새 저장소 생성

```bash
# 현재 디렉토리를 Git 저장소로 초기화
git init

# 특정 디렉토리를 저장소로 초기화
git init project-name

# 베어 저장소 생성 (서버용)
git init --bare
```

### 기존 저장소 복제 (깃허브 > 내 컴퓨터)

```bash
# 원격 저장소 복제
git clone https://github.com/username/repository.git

# 다른 이름으로 복제
git clone https://github.com/username/repository.git new-name



```

## 기본 작업 흐름

### 파일 상태 확인

```bash
# 현재 상태 확인
git status


```

### 파일 추가 (Staging)

```bash
## 특정 파일 추가 혹은 파일전체 추가 같은경우는 vscode 에서 그냥 관리 하는게 더 편해유
# 특정 파일 추가
git add 파일명.확장자

# 여러 파일 추가
git add file1.txt file2.txt

# 모든 변경 파일 추가
git add .
```

### 커밋 생성

```bash
# 기본 커밋
git commit -m "커밋 메시지"

```

### 파일 삭제 및 이동

##### **_이건궁금하시면 말해주세염 작성해놓을게여_**

### 대충 기타

```bash
# 원격 브랜치 기반으로 생성
git checkout -b local-branch origin/remote-branch

# 이거로 각자 브랜치 만들어서 해보시는 연습도...

```

### 병합 충돌 해결

```bash
# 충돌 발생 시
# 1. 충돌 파일 확인
git status

# 2. 파일 열어서 수동으로 충돌 해결
# <<<<<<< HEAD
# 현재 브랜치의 내용
# =======
# 병합하려는 브랜치의 내용
# >>>>>>> feature-branch

# 3. 충돌 해결 후 스테이징
git add resolved-file.txt

# 4. 병합 완료
git commit

# 병합 도구 사용
git mergetool
```

## 원격 저장소 작업

### 원격 저장소 관리

```bash
# 원격 저장소 목록 확인
git remote

# 상세 정보와 함께 확인
git remote -v

# 원격 저장소 추가
git remote add origin https://github.com/username/repository.git

# 원격 저장소 이름 변경
git remote rename origin upstream

# 원격 저장소 삭제
git remote remove origin

# 원격 저장소 URL 변경
git remote set-url origin https://github.com/username/new-repository.git

# 원격 저장소 정보 확인
git remote show origin
```

### 풀 (Pull)

```bash
# 현재 브랜치에 원격 변경 사항 가져오고 병합
git pull

# 특정 원격 브랜치에서 풀
git pull origin main

# 리베이스로 풀
git pull --rebase

# Fast-forward만 허용
git pull --ff-only

# 모든 원격 브랜치 풀
git pull --all
```

### 푸시 (Push)

```bash
# 현재 브랜치 푸시
git push

# 특정 브랜치 푸시
git push origin main

# 처음 푸시할 때 (업스트림 설정)
## 웬만하면 하지마세염
git push -u origin main


# 안전한 강제 푸시
## 웬만하면 하지마세여
git push --force-with-lease

```
