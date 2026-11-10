# 함께 푸는 GitHub 문제 교실

같은 문제를 받고, 내 브랜치에서 풀고, 친구에게 풀이를 설명해 봐요.

**main 받기 → 내 이름 브랜치 만들기 → 문제 풀기 → 커밋 → 푸시 → 제출**

`main`은 모두가 받는 문제집, 내 브랜치는 내 공책이에요. 커밋은 풀이를 저장한 체크포인트, 푸시는 GitHub에 올리는 일이에요.

## 시작 전에

- 선생님과 사용할 이름을 정해요. 예: `minsu`, `jiyu`. 영어 소문자와 숫자, `-`를 사용해요. 같은 이름이면 `minsu-2`처럼 구별해요.
- 공개 저장소이므로 이름은 수업용 별명으로 해도 좋아요. 학교·반·전화번호·사진은 올리지 않아요.
- Git과 편집기를 준비해요. GitHub에 직접 제출하는 학생은 이용 자격을 갖춘 본인 계정으로 로그인하고, 선생님의 저장소 초대를 수락해요.
- **만 13세 미만 학생:** 선생님이 준비한 로컬 연습 폴더에서 활동하고 결과 파일을 선생님께 제출해요. GitHub 업로드는 선생님이 합니다. 계정이나 비밀번호를 함께 쓰지 않아요. [선생님 안내](TEACHER.md)를 먼저 확인해 주세요.

## 1. main 받기

아래는 GitHub에 직접 제출할 수 있는 학생을 위한 터미널 순서예요. `minsu`는 모두 자기 이름으로 바꿔요.

```sh
git clone https://github.com/kimyonggyu-aim/github-practice.git
cd github-practice
git switch main
git pull --ff-only origin main
```

이미 받은 폴더가 있으면 다시 clone하지 않아요. 폴더를 연 뒤 `git status`로 저장하지 않은 변경이 없는지 확인하고 `main`을 받아요. 변경이 있으면 선생님에게 도움을 요청해요.

## 2. 내 이름 브랜치 만들기

```sh
git switch -c minsu
git branch --show-current
```

마지막 줄에 `minsu`가 나오면 성공이에요. `main`에서 문제를 풀지 않아요.

이미 만든 내 브랜치에서 이어 하려면 `git switch minsu`를 사용해요. 친구 이름 브랜치는 사용하지 않아요.

## 3. 문제 풀기

1. [문제집](problems/README.md)을 읽어요.
2. [풀이 양식](answers/template.md)을 편집기에서 복사해 `answers/minsu.md`로 저장해요.
3. 정답과 생각한 과정을 써요. 모르겠는 문제에는 어디까지 생각했는지 써도 좋아요.
4. `answers/template.md`와 친구의 풀이 파일은 바꾸지 않아요.

## 4. 내 풀이 저장하기

```sh
git status
git add answers/minsu.md
git diff --cached
git commit -m "minsu: 첫 번째 문제 풀이"
```

`git diff --cached`에서 내가 작성한 풀이만 들어 있는지 확인해요. 커밋할 때 이름·이메일 설정을 요청하면 [선생님 안내](TEACHER.md)의 준비 항목을 함께 확인해요.

## 5. 내 브랜치 올리기

```sh
git push -u origin minsu
```

올린 뒤 수정할 때는 파일을 저장하고 `git add`, `git commit`, `git push`를 다시 해요. 같은 브랜치의 제출 내용이 갱신돼요.

## 6. 풀이 제출하기

1. [저장소](https://github.com/kimyonggyu-aim/github-practice)에서 **Pull requests → New pull request**를 열어요.
2. `base: main`, `compare: 내 이름`을 골라요.
3. 제목은 `[내 이름] 문제 풀이`로 써요.
4. 제출 양식에 푼 문제와 궁금한 점을 적어요.
5. **Create pull request**를 눌러요. 선생님의 확인을 기다려요.

PR(Pull Request)은 “제 공책을 확인해 주세요”라는 제출 요청이에요. 선생님이 확인하고 합치며, 학생은 직접 Merge하지 않아요.

## 친구와 함께하는 약속

- 답만 알려주기보다 어떻게 생각했는지 설명해요.
- 친구의 풀이에서 이해가 안 되는 부분은 친절하게 물어봐요.
- 내 브랜치와 내 파일만 수정해요. 다른 사람의 브랜치를 지우거나 강제로 덮어쓰지 않아요.
- 틀려도 괜찮아요. 수정한 내용을 새 커밋으로 남기면 돼요.

## 막혔나요?

| 화면에 보이는 말 | 할 일 |
| --- | --- |
| `Permission denied` / `403` | 로그인 계정과 저장소 초대 수락 여부를 선생님과 확인해요. 공개 저장소도 올리기 권한은 필요해요. |
| `branch ... already exists` | 내가 만든 브랜치인지 확인한 뒤 `git switch 내이름`으로 이동해요. |
| `nothing to commit` | 편집기에서 파일을 저장했는지, 올바른 폴더인지 `git status`로 확인해요. |
| `non-fast-forward` / 충돌 | 강제 푸시하지 말고 선생님에게 도움을 요청해요. |

첫 수업은 이 저장소의 main에서 출발해 한 번 제출하는 활동이에요. 다음 수업의 문제와 브랜치는 선생님이 안내합니다.
