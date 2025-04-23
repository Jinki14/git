# Git 사용법 정리

## 1. Git 시작하기
### 1.1. Git 설치
- [Git 공식 사이트](https://git-scm.com/)에서 Git을 다운로드하여 설치한다.
- 설치 후 `git --version` 명령어로 설치 여부 확인.

### 1.2. Git 초기화
- 프로젝트 폴더에서 `git init` 명령어로 Git 저장소를 초기화한다.

```bash
git init
2. Git 기본 명령어
2.1. 파일 상태 확인
git status 명령어로 현재 파일의 상태를 확인한다.

Untracked files: Git으로 관리되지 않는 파일

Changes not staged for commit: 수정했지만 커밋되지 않은 파일

bash
복사
편집
git status
2.2. 파일 추가 및 커밋
파일을 Git에 추가하려면 git add 명령어를 사용한다.

git add . : 모든 변경 사항을 추가

git add [파일명] : 특정 파일만 추가

파일을 커밋하려면 git commit 명령어를 사용한다.

bash
복사
편집
git add .
git commit -m "커밋 메시지"
3. 브랜치와 병합
3.1. 브랜치 만들기 및 이동
새 브랜치를 만들고 이동하려면 git checkout -b [브랜치명] 명령어를 사용한다.

bash
복사
편집
git checkout -b feature-branch
3.2. 브랜치 병합
작업이 끝난 후, main 브랜치로 돌아가서 병합한다.

bash
복사
편집
git checkout main
git merge feature-branch
3.3. 충돌 해결
병합 시 충돌이 발생하면, Git은 충돌된 파일을 알려준다.

충돌된 부분을 수동으로 수정하고, git add와 git commit으로 해결한다.

4. 원격 저장소와 GitHub
4.1. GitHub 저장소 만들기
GitHub에서 새 저장소를 생성하고, 주소를 복사한다.

4.2. 원격 저장소 연결
git remote add origin [GitHub 저장소 URL] 명령어로 원격 저장소를 연결한다.

bash
복사
편집
git remote add origin https://github.com/username/repository.git
4.3. 코드 푸시 (Push)
git push origin [브랜치명] 명령어로 로컬 브랜치를 GitHub에 푸시한다.

첫 번째 푸시는 -u 옵션을 사용해 연결을 설정한다.

bash
복사
편집
git push -u origin main
4.4. 코드 풀 (Pull)
git pull origin [브랜치명] 명령어로 GitHub의 최신 상태를 로컬로 가져온다.

bash
복사
편집
git pull origin main
4.5. GitHub에서 로컬로 복제 (Clone)
git clone [저장소 URL] 명령어로 원격 저장소를 로컬로 복제한다.

bash
복사
편집
git clone https://github.com/username/repository.git
5. 실습 예시
5.1. 새로운 브랜치에서 작업하기
main 브랜치에서 A, B, C 파일을 만든다.

새로운 브랜치를 만들고, B 파일을 수정한 후 커밋한다.

main 브랜치로 돌아가서, feature-branch를 merge한다.

최종적으로 GitHub에 push한다.

bash
복사
편집
# 1. `main` 브랜치에서 작업
echo "A" > A.txt
echo "B" > B.txt
echo "C" > C.txt
git add .
git commit -m "A, B, C 파일 생성"

# 2. 새로운 브랜치에서 `B` 수정
git checkout -b feature-branch
echo "B' 수정" > B.txt
git add B.txt
git commit -m "B 수정"

# 3. `main` 브랜치로 돌아가서 병합
git checkout main
git merge feature-branch

# 4. GitHub에 푸시
git push origin main
6. Git 활용 팁
git status로 항상 작업 상태 확인

주기적으로 커밋하고 푸시하여 작업 내용을 기록

다른 사람과 협업 시, 항상 git pull로 최신 상태를 가져오기

yaml
복사
편집

---
