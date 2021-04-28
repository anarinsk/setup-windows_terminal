# Setup-windows_terminal
Setup for Windows terminal

## Basics 

+ 기본적인 사항은 공식 문서를 참고하자. 
  + https://docs.microsoft.com/ko-kr/windows/terminal/


## Default 바꾸기 

+ 디폴트에서 바꿀 것들 
  + 디폴트 프로파일 (시작 프로파일) 
  + 폰트 
  + 테마 


### 설정 바꾸기  

+ 일단 Windows Terminal에서 `설정 > Json 파일열기`를 누른다. 

```shell
"profiles": 
    {
        "defaults": {
            "fontFace" : "D2Coding ligature",
		        "fontSize" : 12,
            "antialiasingMode":"cleartype", 
            "theme": "3024 night"
        }
```

+ `profile` 항목을 찾고 아래를 바꾼다.  
  + `fontFace`
  + `fontSize`
  + `theme`

+ `D2Coding` 폰트 중에서 리거쳐를 써야 기호가 깨지지 않는다. 
+ Theme는 여기 테마를 제너레이팅하는 서비스를 참고하자. 
   + https://windowsterminalthemes.dev/
+ Theme 역시 같은 제이슨 파일 안에 넣는다. 
  + `"schemes"` 아래 넣으면 된다. 


```shell
"schemes": 
    [
        {
            "name": "3024 Night",
            "black": "#090300",
            "red": "#db2d20",
            "green": "#01a252",
            "yellow": "#fded02",
            "blue": "#01a0e4",
            "purple": "#a16a94",
            "cyan": "#b5e4f4",
            "white": "#a5a2a2",
            "brightBlack": "#5c5855",
            "brightRed": "#e8bbd0",
            "brightGreen": "#3a3432",
            "brightYellow": "#4a4543",
            "brightBlue": "#807d7c",
            "brightPurple": "#d6d5d4",
            "brightCyan": "#cdab53",
            "brightWhite": "#f7f7f7",
            "background": "#090300",
            "foreground": "#a5a2a2",
            "selectionBackground": "#4a4543",
            "cursorColor": "#a5a2a2"
          },
```

## 관리자로 실행하기 

+ WT가 처음부터 관리자로 실행되면 좋다. 
+ 그런데 WT가 UWP라서 과거와 같은 관리자 실행권한을 주지 않는다. 
+ 별도의 바로가기를 거쳐서 관리자 권한으로 실행되도록 만들 수 있다. [LINK](http://nuts4.net/post/windows-terminal-run-as-admin) 참고. 

```txt
1. Right click on your desktop, and click New -> Shortcut
2. For the location, type in the following and click next:
  C:\Windows\system32\cmd.exe /c start /b wt
3. For the name, type in "Windows Terminal", and click Next.
4. Now, right click on the new shortcut, and click Properties.
5. On the Shortcut tab, click Advanced, and click "Run as Administrator"
```

+ 현재 WT 혹은 터미날이 관리자 모드로 실행중인지 알 수 있는 방법은?
+ cmd 모드에서 `bcdedit`을 실행한다. 
