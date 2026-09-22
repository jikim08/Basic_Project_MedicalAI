# Basic-Project MedicalAI

---

## git branch 전략

- 메인 브랜치: main
- 보조 브랜치: 각자 학번

## git commit, PR시

- Rule 1: Commit 양식은 아래를 따릅니다
- Rule 2: 제목, 내용은 모두 영어로 작성

```python
# <타입>: <제목>

##### 제목은 최대 50 글자까지만 입력 ############## -> |

# 본문은 위에 작성
######## 본문은 한 줄에 최대 72 글자까지만 입력 ########################### -> |

# 꼬릿말은 아래에 작성: ex) #이슈 번호

# --- COMMIT END ---
# <타입> 리스트
#   feat    : 기능 (새로운 기능)
#   fix     : 버그 (버그 수정)
#   refactor: 리팩토링
#   style   : 스타일 (코드 형식, 세미콜론 추가: 비즈니스 로직에 변경 없음)
#   docs    : 문서 (문서 추가, 수정, 삭제)
#   test    : 테스트 (테스트 코드 추가, 수정, 삭제: 비즈니스 로직에 변경 없음)
#   chore   : 기타 변경사항 (빌드 스크립트 수정 등)
# ------------------
#     제목 첫 글자를 대문자로
#     제목은 명령문으로
#     제목 끝에 마침표(.) 금지
#     제목과 본문을 한 줄 띄워 분리하기
#     본문은 "어떻게" 보다 "무엇을", "왜"를 설명한다.
#     본문에 여러줄의 메시지를 작성할 땐 "-"로 구분
# ------------------
```

# Git Merge 규칙

1. **브랜치 분리**
   - `main`: 최종 완성 코드
   - `develop`: 기능 통합 브랜치
   - `feature/*`: 기능 개발 브랜치

2. **직접 작업 금지**
   - `main`, `develop`에서 직접 개발하지 않는다.
   - 기능별 `feature/*` 브랜치에서 작업한다.

3. **Merge 전 최신화**
   ```bash
   git switch develop
   git pull origin develop

   git switch feature/기능명
   git merge develop
   ```
   - 충돌이 발생하면 Merge 전에 해결한다.

4. **Pull Request 사용**
   - 기능 개발 완료 후 `feature → develop` PR을 생성한다.
   - 최소 1명의 팀원이 코드를 확인한 후 Merge한다.

5. **Conflict 처리**
   - 다른 팀원의 코드를 임의로 삭제하지 않는다.
   - 충돌 해결이 어렵다면 해당 코드를 작성한 팀원과 확인한다.

6. **Merge 후 정리**
   - Merge가 완료된 `feature` 브랜치는 삭제한다.

### 기본 흐름

`develop 최신화 → feature 생성 → 개발 → commit/push → PR → 코드 리뷰 → develop Merge`

```python
ex)
docs: Update README

가독성이 더 좋은 commit 메시지로 업데이트 하였습니다.
```

202212215 이재현 확인했습니다.