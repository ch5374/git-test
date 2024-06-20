## 조선해양 exe 실행

기본적의 exe 파일은 무한루프 형태로 실행됩니다(라이브러리 
import 시에 시간이 오래 걸리기 때문에 초기에 라이브러리들을 불러놓고
코드만 계속 실행시킵니다)

```
exe
├── data
└── main.exe
```
다음과 같은 폴더 구조에서 실행이 되고 
main.exe 파일은 data에 파일이 있을 시에 연산을 시작하고 그 이외에는 
파일을 기다리는 대기 상태에 있습니다.

```
exe
├── data
│    ├── conf_256x192_0.bin
│    ├── conf_256x192_1.bin
│    ├── ...
│    ├── depth_256x192_0.bin
│    ├── depth_256x192_1.bin
│    └── ...
└── main.exe
```
bin 파일이 들어오면 연산을 시작하고 result.txt 값을 만들며
동시에 data 안에 있는 bin 파일을 삭제합니다.

```
exe
├── data
│    ├── ...
│    └── ...
├── main.exe
└── result.txt
```

현재의 exe 세팅으로 Bundle 15, 즉 data에 conf_256x192_0.bin ~ conf_256x192_14.bin/
depth_256x192_0.bin ~ depth_256x192_14.bin 까지 해서 총 30개의 파일이 있을 때
작동하게 됩니다. 


