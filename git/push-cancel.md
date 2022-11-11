# push 취소 방법

1. reset
2. amend

## 1. reset

### 커밋 이력 조회

```
git log --oneline
```

HEAD : 현재 브랜치, 가장 최근의 commit.

### 돌아가고 싶은 시점의 commit 지정, 그 이후의 이력 삭제

```
git reset --hard "해당commit"
```

- reset hard : 돌아갈 시점 이후의 모든 이력을 지운다.
- reset soft : 이력을 남긴다.

### 원격저장소를 내가 되돌린 상태(현재)와 같게 만들기

```
git push -f origin master
```

---

## REF

- https://ninano1109.tistory.com/3
- https://inpa.tistory.com/entry/GIT-%E2%9A%A1%EF%B8%8F-git-add-commit-push-%EC%B7%A8%EC%86%8C%ED%95%98%EA%B8%B0-%F0%9F%92%AF-%EC%A0%95%EB%A6%AC-git-reset-restore-clean#git-push-%EC%B7%A8%EC%86%8C%ED%95%98%EA%B8%B0
  이 링크 참고해서 내용 더 추가해놓자
