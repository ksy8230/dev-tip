# MacOS에서 메이븐 실행 명령어 설치

## 현상

-

## 해결

맥에서는 brew 명령어를 이용해 maven을 설치할 수 있다.

```
brew install maven
```

칩셋이 다른 M1 맥북의 경우 `Cannot install under Rosetta 2 in ARM default prefix (/opt/homebrew) 라는 에러`가 발생하는데  
이때는 명령어 앞에 arch -arm64를 붙여주고 설치하면 된다.

```
# Rosetta2 관련 에러 발생 시
arch -arm64 brew install [packege or program]
```
