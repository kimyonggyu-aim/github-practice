# 선생님 안내

목표는 문제 난이도보다 **main에서 개인 브랜치를 만들고, 자기 파일을 커밋·푸시해 제출하는 경험**입니다. 첫 수업에서는 정답 자동 채점이나 추가 프로그램 설치 없이 Markdown 파일로 진행합니다.

## 참여 방식

GitHub는 만 13세 미만 이용과 계정 공유를 허용하지 않습니다. 해당 학생에게 GitHub 계정을 만들거나 선생님 계정으로 로그인하게 하지 않습니다. 선생님이 자료를 로컬 폴더로 준비하고 학생은 로컬 Git에서 브랜치·파일·커밋을 연습합니다. 결과 파일을 받으면 선생님이 해당 수업용 이름의 브랜치에 커밋·푸시합니다. [GitHub 계정 요건](https://docs.github.com/en/site-policy/github-terms/github-terms-of-service#3-account-requirements)

직접 GitHub를 사용할 수 있는 참가자는 본인 계정과 저장소 쓰기 권한이 필요합니다. 공개 저장소라는 것만으로 같은 저장소에 브랜치를 푸시할 수 있지는 않습니다. [공동 작업자 초대 안내](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/repository-access-and-collaboration/inviting-collaborators-to-a-personal-repository)

## 수업 전 준비

1. 사용할 이름을 정합니다. `minsu`, `jiyu`, 중복 시 `minsu-2`처럼 수업용 이름을 사용합니다. 명단과 실제 개인정보의 대응표는 공개 저장소에 넣지 않습니다.
2. 직접 제출할 참가자는 **Settings → Collaborators**에서 초대하고, 본인에게 초대 수락을 확인받습니다. 이 저장소에는 아직 학생 초대가 등록되지 않았습니다.
3. 각 컴퓨터에 Git과 편집기를 준비합니다. 터미널에서 `git --version`을 확인합니다.
4. Git 작성자 정보는 저장소 안에서만 설정합니다. 예시 값은 실제 수업용 이름으로 바꿉니다. 직접 제출자는 GitHub 이메일 설정의 비공개 `noreply` 주소를 사용할 수 있습니다. 로컬 연습만 하는 학생은 아래 예처럼 실제 개인정보가 아닌 연습용 값을 사용합니다.

```sh
git config --local user.name "minsu"
git config --local user.email "minsu@classroom.invalid"
```

5. `main`에는 공통 문제와 안내를 유지합니다. 학생은 `answers/내이름.md`만 수정하고 자기 브랜치에 올립니다. 로컬 학습자에게는 네트워크 로그인이나 push를 요구하지 않습니다.

## 선생님이 대신 제출하는 경우

학생에게 받은 파일을 확인한 뒤 선생님 컴퓨터에서 진행합니다. 아래 `minsu`는 학생의 수업용 이름입니다. 같은 이름의 브랜치가 이미 있으면 새로 만들지 말고 그 브랜치로 이동합니다.

```sh
git switch main
git pull --ff-only origin main
git switch -c minsu
```

학생의 풀이를 `answers/minsu.md`에 저장한 다음:

```sh
git add answers/minsu.md
git diff --cached
git commit -m "minsu: 제출받은 문제 풀이"
git push -u origin minsu
```

기존 작업 파일이 남아 있다면 브랜치를 바꾸기 전에 먼저 정리합니다. 선생님이 업로드한 커밋을 학생 계정의 활동으로 표현하지 않습니다.

## 제출과 검토

- PR의 기준은 `base: main`, 제출 브랜치는 학생 이름입니다.
- 학생별 파일을 사용하므로 서로의 풀이가 같은 파일에서 충돌하지 않습니다.
- `.github/CODEOWNERS`는 저장소 소유자를 검토 담당자로 지정합니다. 다른 선생님에게 이관하면 이 파일과 main 보호 설정도 함께 바꿉니다.
- main 보호는 PR과 코드 소유자 승인 1개를 요구하고 강제 푸시·삭제를 허용하지 않는 설정을 사용합니다. 저장소 관리자는 운영상 예외가 있으므로 main 직접 푸시는 수업 운영 때 피합니다.
- 개인 브랜치는 개인 전용 권한 공간이 아닙니다. 공동 작업자는 다른 브랜치도 수정할 수 있으므로 서로의 브랜치를 건드리지 않는 수업 규칙이 필요합니다.
- 풀이 확인 뒤 선생님이 합칩니다. 이때 정답은 공개되므로 첫 풀이 시간을 충분히 준 뒤 합치거나, 수업 종료까지 PR 검토만 진행할 수 있습니다.

## 40분 수업 예시

| 시간 | 활동 |
| --- | --- |
| 5분 | main·브랜치·커밋·푸시를 문제집·공책·체크포인트·제출에 비유해 설명 |
| 10분 | main 받기, 내 브랜치 만들기, 풀이 파일 준비 |
| 15분 | 문제 풀이와 첫 커밋 |
| 10분 | 제출, 친구 풀이 설명 듣기, 수정 커밋 연습 |

정답 여부 외에도 자기 브랜치 사용, 자기 파일만 수정, 생각한 과정 설명을 확인합니다. 다음 수업 문제를 추가할 때는 새 활동용 브랜치 이름과 업데이트 절차를 별도로 안내합니다.
