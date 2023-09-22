# git 학습

## 커밋
- commit : (영한사전 정의)저지르다
- git의 기본단위이다.
  - 커밋 하나는 독립적인 버전을 나타낸다.
  - 사진찍기와 유사하다.
  - 커밋마다 설명이 담긴 메시지가 존재한다.
- 커밋은 코드에 논리적인 변경이 있을 때 하나 생성한다.
- 커밋 컨벤션 (commit convention)
  - 협업에 알맞고 가독성이 좋은 커밋을 작성하기 위한 방법이다.
  - 1. commit message structure
    - <type> [optional scope]: <description>
    - spacess
    - [optional body] 
    - space
    - [optional footer(s)]
  - 2. commit type
    - Feat: 새로운 기능 추가
    - Fix: -버그 수정
    - Design: 사용자 UI디자인 변경
    - !BREAKING CHANGE: 큰 API변경
    - HOTFIX: 급격하게 치명적인 버그 수정
    - Style: 코드 포멧 변경, 세미콜론 누락 등 코드내용의 실질적인 변경이 없는 경우
    - Refactor: 프로덕션 코드 리팩토링(코드 개선 작업)
    - Comment: 주석 추가 및 입력
    - Docs: 문서 작성
    - Test: 테스트 코드 작성, 프로덕트 코드(실제 작동하는 코드)는 변경 없음
    - Chore: 빌드 업무 수정, 매니지 수정 등, 프로덕트 코드는 변경 없음
    - Rename: 파일, 폴더명 수정
    - Remove: 파일, 폴더 삭제
  - 3. Subject
    - 제목은 간결히, 50자 내로 작성한다.
  - 4. Body
    - 최대한 상세히 작성한다.
    - 어떻게 보다는 무엇을, 왜 변경하였는지에 대한 내용을 작성한다.
  - 5. Footer(s)
    - 선택사항
    - 이슈트랙커 id작성한다.
    - 여러 이슈를 나열할 때는 쉼표(,)로 구분한다.

## 스테이징 영역
- 스테이징 영역은 커밋 전 , 커밋에 포함시킬 파일들만 임시로 올려두는 영역이다.
  - stage : 무대에 올리다.
- `.gitignore` 파일 
  - 커밋에 포함되면 안되는 파일들을 관리하는 파일
  - 저장소마다 1개씩 세팅되어있는게 일반적임
  - [Toptal의 gitignore generator](https://www.toptal.com/developers/gitignore)를 사용해서 운영체제, 개발 환경(IDE), 사용하는 프로그래밍 언어에 맞는 gitignore파일을 생성할 수 있음
    - 이 외에도 VSCodedp Extension을 설치해 gitignore 파일을 관리하기도 함

## 브랜치
- branch: (영한사전 정의)나뭇가지
- (일반적으로) 일감을 해결할 때 일감에 해당하는 이슈를 만들고, 이슈에 해당하는 브랜치를 생성함

### 브랜치 병합
- 이슈에 해당하는 브랜치에서 작업을 끝내고 주요 브랜치인 `main`, `development`등에 병합 요청을 하게된다.
- 병합 요청이 승인되면 내가 작업하는 브랜치가 주요 브랜치로 병합된다.

#### 충돌
- 두 브랜치에서 같은 코드를 수정한 후, 병합하려고 할 때 발생한다.
- 충돌이 발생하면, 충돌이 발생한 파일을 열어서 최종적으로 남기고 싶은 코드만 남긴다.(특수 문자는 삭제).
- `git add`, `git commit`으로 병합을 마무리 한다.

### 명령어
- 브랜치 생성: `git branch 브랜치명`
- 생성된 브랜치 확인: `git branch`
- 브랜치 전환
  1. `git switch 브랜치명`
  2. `git checkout 브랜치명`
- 브랜치 생성 및 전환
  1. `git checkout -b 브랜치명`
- 브랜치 병합: `git merge`
  - 주의: `A`브랜치를 `B`브랜치로 병합 하려고 할 때, **`B`브랜치가 체크아웃** 되어있는 상태에서 `git merge A`를 입력해야 함
