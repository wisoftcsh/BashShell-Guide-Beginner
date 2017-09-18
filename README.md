# Bash Shell Start Guide
Installation environment
---
 - MacOS
 
## Index
1. About Bash Shell
2. Programming, Scripting
3. Bash Shell Guide
4. Bash Shell Example
  
## About Bash Shell
**Shell**
>쉘(shell)은 운영체제에서 사용자가 입력하는 명령을 일고 해석하여 대신 실행해주는 프로그램이다. 
>
>운영체제는 로그인한 사용자가 없다면 하나의 쉘도 실행되지 않는 상태다. 
>
>사용자가 로그인을 시도하면 운영체제는 ID와 패스워드를 받아들이는 로그인 프로그램을 실행하게 되고 사용자가 입력한 ID와 패스워드를 검증한 뒤 정상적인 사용자라면 쉘을 실행하여 사용자 세션을 쉘에게 넘겨준다.

출처 : [ <http://blogger.pe.kr/300> 쉘의 정의 ]

**Bourrne Again Shell**

>본 어게인 셸(Bourne-again shell)은 유닉스에서 사용하는 커맨드 셸의 일종으로 GNU 프로젝트를 위해 만들어졌다. 일반적으로 bash로 줄여 부른다.
>초기의 유닉스 셸인 본 셸(Bourne shell)과 새로 태어났다는 뜻의 영어 "born again"을 합친 이름이다. Bash는 1987년 브라이언 폭스에 의해 만들어졌다. 1990년 이후에는 쳇 레이미가 주로 관리하고 있다.
>Bash 명령어의 문법은 거의 대부분이 sh와 호환되어 쓰일 수 있다. 또한 ksh, csh 에서 많은 아이디어를 받아서 명령 히스토리, 디렉터리 스택, $RANDOM POSIX 형식 명령어 치환 등을 지원한다. 또한 입력 중에 명령어나 파일 이름을 자동 완성해 주는 기능도 지원한다.
>Bash는 다양한 리눅스 시스템, MacOS 10의 기본 셸이며, 수많은 유닉스 계열 운영체제에서 동작한다. 마이크로소프트 윈도에서도 시그윈 프로젝트 등에 의해 이식되어 있다.
Bash는 GNU GPL로 배포되고 있으며, GNU 프로젝트 FTP 사이트를 비롯하여 수많은 인터넷 사이트에서 내려받을 수 있다.

출처 : [ <http://egloos.zum.com/saintrv/v/2449301> ]

## Programming, Scripting

>프로그래밍을 처음 하는 사람들은 대개 프로그래밍 언어와 스크립팅 언어 사이의 차이를 혼동한다. 프로그래밍 언어는 일반적으로 스크립팅 언어에 비해 보다 강력하고 보다 빠르다. 
>
>프로그래밍 언어의 예로는 C, C++, Java가 있다. 
>
>프로그래밍 언어는 대개 소스 코드 (최종 프로그램이 어떻게 실행될 것인가에 대한 지시문을 담고 있는 텍스트 파일)에서 시작해서 컴파일과정을 통해 실행 가능 파일로 만들어진다. 이렇게 해서 만들어진 실행 가능 파일은 다른 운영 체제로 쉽게 이식되어지지 않는다. 
>
>예를 들어, 리눅스에서 C 프로그램을 작성했다면, Windows에서는 그 프로그램을 실행할 수 없을 것이다. 프로그램을 실행하기 위해서는 Windows 시스템 하에서 소스 코드를 다시 컴파일해야만 한다. 
> 
> 스크립팅 언어 역시 소스 코드에서 시작을 하지만 실행 가능 파일로 만들기 위한 컴파일 과정이 없다. 대신, 번역기(interpreter)가 소스 파일에서 지시문을 읽고 각 지시문을 실행시킨다. 불행히도, 번역기가 각 지시문을 하나 하나 읽어야만 하기 때문에, 일반적으로 번역기르 통해 실행되는 프로그램은 컴파일된 프로그램보다 느리다.
> 
> 스트립팅 언어의 가장 큰 장점은 소스 파일을 어떤 운영 체제에나 쉽게 이식할 수 있으며 바로 그 자리에서 번역기를 통해 실행할 수 있다는 것이다. 이런 점은 작은 프로그램에서는 장점으로 여겨질 수 있지만, 큰 규모의 어플리케이션을 작성할 것을 계획하고 있다면 프로그래밍 언어를 사용하는 편이 알맞다.

출처 : [ <http://newstars.tistory.com/127> 프로그래밍 또는 스크립팅? ]

## Bash Shell Command
### Hello World!
hello.sh 파일을 생성 후 다음 명령어를 작성

```
#! /bin/bash ## 운영체제에게 bash 번역기를 사용하라고 알려주는 코드
echo "hello World"
printf "hello world\n"
printf "%s %s\n" hello world
```

저장 후 .sh 파일을 실행합니다.

```
~$ ./hello.sh
```

만약 실행이 안될 경우 .sh 파일의 권한을 chmod를 사용해서 변경합니다. ``chmod a+x hello.sh``

#### echo, printf
- 하나의 인자(argument = parameter)를 취해서 그 인자를 화면에 프린트한다. 
- 예제에서 인자는 "hello World"가 된다.

### 주석 (Comments)
- `#` 기호로 시작하면 주석이다.

### 함수 (Function)
- 형식은 다른 언어와 차이가 없다. 그러나 function은 생략해도 된다.
- 주의할 것은 호출 코드가 함수 코드보다 반드시 뒤에 있어야 된다.

```
string_test() {
	echo "string test"
}

function string_test2() {
	echo "string test 2"
	echo "인자값 : ${@}"
}

string_test
string_test2
string_test2 "hello" "world"
```

출력 결과

```
string test
string test 2
인자값:
string test 2
인자값: hello world
```

### 변수 (Variable)
변수 사용시에는 `=` 기호 앞뒤로 공백이 없이 입력하면 대입연산자가 된다. 그리고 선언된 변수는 기본적으로 전역 변수(global variable)다. 

단 함수 안에서만 지역 변수(local variable)를 사용할 수 있는데 사용하려면 변수명 앞에 `local`을 붙여주면된다.

그런데 전역 변수는 현재 실행된 스크립트 파일에서만 유효하다. 자식 스크립트 파일에서는 사용 할 수 없는 변수다.

변수명 앞에 `export`를 붙여주면 환경 변수(environment variable)로 설정되어 자식 스크립트에서 사용 가능하다.

환경 변수 사용시 예약 변수 (reserved variable)에 주의

```
# 전역 변수 지정
string="hello world"
echo ${string}

# 지역 변수 테스트 함수
string_test() {
    # 전역 변수와 동일하게 사용함. 만약 local 뺀다면 전역 변수에 덮어씌어지게 됨
    local string="local"
    echo ${string}
}

string_test
echo ${string}

export hello_world="hello world..."
# 자식 스크립트 호출은 스크립트 경로을 쓰면된다.
```

export_test.sh

```
#환경 변수를 테스트하기 위해 export_test.sh 파일을 만들고 선언한 변수를 확인해본다.
echo ${hello_world}
```

출력 결과 

```
hello world
local
hello world
hello world...
hello world...
```

- 예약변수

|문자|설명|
|:--|:--|
|HOME|사용자의 홈 디렉토리|
|PATH|실행 파일을 찾을 경로|
|LANG|	프로그램 사용시 기본 지원되는 언어
|PWD|	사용자의 현재 작업중인 디렉토리
|FUNCNAME|	현재 함수 이름
|SECONDS|	스크립트가 실행된 초 단위 시간
|SHLVL|	쉘 레벨(중첩된 깊이를 나타냄)
|SHELL|	로그인해서 사용하는 쉘
|PPID	|부모 프로세스의 PID
|BASH	BASH| 실행 파일 경로
|BASH_ENV|	스크립트 실행시 BASH 시작 파일을 읽을 위치 변수
|BASH_VERSION|	설치된 BASH 버전
|BASH_VERSINFO	|BASH_VERSINFO[0]~BASH_VERSINFO[5]배열로 상세정보 제공
|MAIL|	메일 보관 경로
|MAILCHECK	|메일 확인 시간
|OSTYPE|	운영체제 종류
|TERM	|로긴 터미널 타입
|HOSTNAME|	호스트 이름
|HOSTTYPE|	시스템 하드웨어 종류
|MACHTYPE|	머신 종류(HOSTTYPE과 같은 정보지만 조금더 상세하게 표시됨)
|LOGNAME|	로그인 이름
|UID|	사용자 UID
|EUID	|su 명령에서 사용하는 사용자의 유효 아이디 값(UID와 |EUID 값은 다를 수 있음)
|USER	|사용자의 이름
|USERNAME|	사용자 이름
|GROUPS|	사용자 그룹(/etc/passwd 값을 출력)
|HISTFILE|	history 파일 경로
|HISTFILESIZE|	history 파일 크기
|HISTSIZE|	history 저장되는 개수
|HISTCONTROL|	중복되는 명령에 대한 기록 유무
|DISPLAY|	X 디스플레이 이름
|IFS|	입력 필드 구분자(기본값:   - 빈칸)
|VISUAL	VISUAL| 편집기 이름
|EDITOR|	기본 편집기 이름
|COLUMNS|	현재 터미널이나 윈도우 터미널의 컬럼 수
|LINES|	터미널의 라인 수
|LS_COLORS|	ls 명령의 색상 관련 옵션
|PS1|	기본 프롬프트 변수(기본값: bash\$)
|PS2|	보조 프롬프트 변수(기본값: >), 명령을 "\"를 사용하여 명령 행을 연장시 사용됨
|PS3|	쉘 스크립트에서 select 사용시 프롬프트 변수(기본값: #?)
|PS4|	쉘 스크립트 디버깅 모드의 프롬프트 변수(기본값: +)
|TMOUT|	0이면 제한이 없으며 time시간 지정시 지정한 시간 이후 로그아웃

- 위치 매개 변수

|문자|설명|
|:--|:--|
|$0|	실행된 스크립트 이름|
|$1|	$1 $2 $3...${10}인자 순서대로 번호가 부여된다. 10번째부터는 "{}"감싸줘야 함|
|$*|	전체 인자 값|
|$@|	전체 인자 값 ($* 동일하지만 쌍따옴표로 변수를 감싸면 다른 결과 나옴)|
|$#|	매개 변수의 총 개수|

- 특수 매개 변수

|문자|설명|
|:--|:--|
|$$|	현재 스크립트의 PID
|$?|	최근에 실행된 명령어, 함수, 스크립트 자식의 종료 상태
|$!|	최근에 실행한 백그라운드(비동기) 명령의 PID
|$-|	현재 옵션 플래그
|$_|	지난 명령의 마지막 인자로 설정된 특수 변수

- 매개 변수 확장

|문자|설명|
|:--|:--|
|${변수}|	$변수와 동일하지만 {} 사용해야만 동작하는 것들이 있음(예: echo ${string})
|${변수:위치}|	위치 다음부터 문자열 추출(예: echo ${string:4})
|${변수:위치:길이}|	위치 다음부터 지정한 길이 만큼의 문자열 추출(예: echo ${string:4:3})
|${변수:-단어}|	변수 미선언 혹은 NULL일때 기본값 지정, 위치 매개 변수는 사용 불가(예: echo ${string:-HELLO})
|${변수-단어}|	변수 미선언시만 기본값 지정, 위치 매개 변수는 사용 불가(예: echo ${string-HELLO})
|${변수:=단어}|	변수 미선언 혹은 NULL일때 기본값 지정, 위치 매개 변수 사용 가능(예: echo ${string:=HELLO})
|${변수=단어}|	변수 미선언시만 기본값 지정, 위치 매개 변수 사용 가능(예: echo ${string=HELLO})
|${변수:?단어}|	변수 미선언 혹은 NULL일때 단어 출력 후 스크립트 종료,(예: echo ${string:?HELLO})
|${변수?단어}|	변수 미선언시만 단어 출력 후 스크립트 종료(예: echo ${string?HELLO})
|${변수:+단어}|	변수 선언시만 단어 사용(예: echo ${string:+HELLO})
|${변수+단어}|	변수 선언 혹은 NULL일때 단어 사용(예: echo ${string+HELLO})
|${#변수}|	문자열 길이(예: echo ${#string})
|${변수#단어}|	변수의 앞부분부터 짧게 일치한 단어 삭제(예: echo ${string#a*b})
|${변수##단어}|	변수의 앞부분부터 길게 일치한 단어 삭제(예: echo ${string##a*b})
|${변수%단어}|	변수의 뒷부분부터 짧게 일치한 단어 삭제(예: echo ${string%b*c})
|${변수%%단어}|	변수의 뒷부분부터 길게 일치한 단어 삭제(예: echo ${string%%b*c})
|${변수/찾는단어/변경단어}	|처음 일치한 단어를 변경(예: echo ${string/abc/HELLO})
|${변수//찾는단어/변경단어}|	일치하는 모든 단어를 변경(예: echo ${string//abc/HELLO})
|${변수/#찾는단어/변경단어}|	앞부분이 일치하면 변경(예: echo ${string/#abc/HELLO})
|${변수/%찾는단어/변경단어}|	뒷부분이 일치하면 변경(예: echo ${string/%abc/HELLO})
|${!단어*}, ${!단어@}|	선언된 변수중에서 단어가 포함된 변수 명 추출(예: echo ${!string*}, echo ${!string@})

### 배열 (Array Variable)
- 배열 변수 사용은 반드시 괄호를 사용해야 한다.
- 1차원 배열만 지원함

```
#참고: 'declare -a' 명령으로 선언하지 않아도 배열 변수 사용 가능함
declare -a array

array=("hello" "test" "array" "world")

array[4]="variable"

array=(${array[@]} "string")

echo "hello world 출력: ${array[0]} ${array[3]}"
echo "배열 전체 출력: ${array[@]}"
echo "배열 전체 개수 출력: ${#array[@]}"
printf "배열 출력: %s\n" ${array[@]}

unset array[4]
echo "배열 전체 출력: ${array[@]}"

unset array
echo "배열 전체 출력: ${array[@]}"
```

출력 결과

```
hello world 출력: hello world
배열 전체 출력: hello test array world variable string
배열 전체 개수 출력: 6
배열 출력: hello
배열 출력: test
배열 출력: array
배열 출력: world
배열 출력: variable
배열 출력: string
배열 전체 출력: hello test array world string
배열 전체 출력:
```

### 변수 타입 지정 (Variables Revistied)

- Bash 변수는 타입을 구분하지 않고 기본적으로 문자열이다. 단 문맥에 따라서 연산 처리한다.
- 불완전한 형태의 `declare`,`typeset` 타입 지정 명령을 지원한다. ( 두 명령은 동일 )

```
# 읽기 전용
# readonly string_variable="hello world" 문법과 동일 함
declare -r string_variable

# 정수
# number_variable=10 문법과 동일 함
declare -i number_variable=10

# 배열
# array_variable=() 문법과 동일 함
declare -a array_variable

# 환경 변수
# export export_variable="hello world" 문법과 동일 함
declare -x export_variable="hello world"

# 현재 스크립트의 전체 함수 출력
declare -f

# 현재 스크립트에서 지정한 함수만 출력
declare -f 함수이름
```

### 논리 연산자 (Logical Operators)

|문자|설명|
|:--|:--|
|`&&`, -a |	논리 AND |
|`||`, -o 	|논리 OR |

### 산술 연산자 (Arithmetic Operators)

|문자|설명|
|:--|:--|
|+|	더하기
|-	|빼기
|*	|곱하기
|/	|나누기
|++|	누승(exponentiation)
|%	|modulo 나 mod (정수 나누기에서 나머지 값)
|+=|	상수값 만큼 증가(plus-equal)
|-=|	상수값 만큼 감소(minus-equal)
|*=|	상수값을 곱함(times-equal)
|/=|	상수값으로 나눔(slash-equal)
|%=|	상수값으로 나눈 나머지 값(mod-equal)

### 비트 연산자 (Bitwise Operators)

|문자|설명|
|:--|:--|
|<<|	비트 왼쪽 쉬프트(쉬프트 한 번당 2를 곱하는 것과 동일함)
|<<=|	left-shift-equal
|>>|	비트 오른쪽 쉬프트(쉬프트 한 번당 2로 나눔)
|>>=|	right-shift-equal(<<=와 반대)
|&|	비트 and
|&=|	비트 and-equal
|`|`	|비트 OR
|`|=`|	비트 OR-equa
|~	|비트 negate
|!	|비트 NOT
|^	|비트 XOR
|^=|	비트 XOR-equa

### 기타 연산자 (Miscellaneous Operators)

|문자|설명|
|:--|:--|
|,|	콤마 연산자(comma operator), 2개 이상의 산술 연산을 묶어줌


### 정수 비교 (Integer Comparison)

|문자|설명|
|:--|:--|
|-eq|	같음
|-ne|	같지 않음
|>, -gt|	더 큼(> 이중 소괄호에서 사용 가능)
|>=, -ge|	더크거나 같음(>= 이중 소괄호에서 사용 가능)
|<, -lt|	더 작음(< 이중 소괄호에서 사용 가능)
|<=, -le|더 작거나 같음(<= 이중 소괄호에서 사용 가능)

### 문자열 비교 (String Comparison)

|문자|설명|
|:--|:--|
|=, ==|	같음
|!=|	같지 않음
|<|	ASCII 알파벳 순서에 더 작음
|>|	ASCII 알파벳 순서에서 더 큼
|-z|	문자열이 NULL, 길이가 0인 경우
|-n|	문자열이 NULL이 아님
|${변수}|	문자열이 NULL이 아님

### 파일 비교 (File Test Operators)

|문자|설명|
|:--|:--|
|-e|	파일이 존재
|-f|	파일이 존재하고 일반 파일인 경우(디렉토리 혹은 장치파일이 아닌 경우)
|-s|	파일이 존재하고 0보다 큰 경우
|-d|	파일이 존재하고 디렉토리인 경우
|-b|	파일이 존재하고 블록장치 파일인 경우
|-c|	파일이 존재하고 캐릭터 장치 파일인 경우
|-p|	파일이 존재하고 FIFO인 경우
|-h|	파일이 존재하고 한 개 이상의 심볼릭 링크가 설정된 경우
|-L|	파일이 존재하고 한 개 이상의 심볼릭 링크가 설정된 경우
|-S|	파일이 소켓 디바이스인 경우
|-t|	파일이 디스크립터가 터미널 디바이스와 연관이 있음
|-r|	파일이 존재하고 읽기 가능한 경우
|-w|	파일이 존재하고 쓰기가 가능한 경우
|-x|	파일이 존재하고 실행 가능한 경우
|-g|	파일이 존재하고 SetGID가 설정된 경우
|-u|	파일이 존재하고 SetUID가 설정된 경우
|-k|	파일이 존재하고 스티키 비트(Sticky bit)가 설정된 경우
|-O|	자신이 소유자임
|-G|	그룹 아이디가 자신과 같음
|-N|	마지막으로 읽힌 후에 변경 됐음
|file1 -nt file2|	file1 파일이 file2 파일보다 최신임
|file1 -ot file2|	file1 파일이 file2 파일보다 예전것임
|file1 -ef file2|	file1 파일과 file2 파일이 같은 파일을 하드 링크하고 있음
|!|	조건이 안 맞으면 참(예: ! -e file)

### 반복문 (for, while, until)

```
# 지정된 범위 안에서 반복문 필요 시 좋음
for string in "hello" "world" "..."; do;
    echo ${string};
done

# 수행 조건이 true 일때 실행됨 (실행 횟수 지정이 필요하지 않은 반복문 필요 시 좋음)
count=0
while [ ${count} -le 5 ]; do
    echo ${count}
    count=$(( ${count}+1 ))
done

# 수행 조건이 false 일때 실행됨 (실행 횟수 지정이 필요하지 않은 반복문 필요 시 좋음)
count2=10
until [ ${count2} -le 5 ]; do
    echo ${count2}
    count2=$(( ${count2}-1 ))
done
```

### 조건문 (if...elif...else...fi)

```
tring1="hello"
string2="world"
if [ ${string1} == ${string2} ]; then
    # 실행 문장이 없으면 오류 발생함
    # 아래 echo 문장을 주석처리하면 확인 가능함
    echo "hello world"
elif [ ${string1} == ${string3} ]; then
    echo "hello world 2"
else
    echo "hello world 3"
fi

# AND
if [ ${string1} == ${string2} ] && [ ${string3} == ${string4} ]
..생략

# OR
if [ ${string1} == ${string2} ] || [ ${string3} == ${string4} ]
..생략

# 다중 조건
if [[ ${string1} == ${string2} || ${string3} == ${string4} ]] && [ ${string5} == ${string6} ]
..생략
```

### 선택문 (Case)

- 정규식을 지원하며 `|`기호로 다중 값을 입력 가능하며 조건의 문장 끝에는 `;;`기호로 끝을 표시

```
# case문 테스트를 위한 반복문
for string in "HELLO" "WORLD" "hello" "world" "s" "start" "end" "etc"; do

    # case문 시작
    case ${string} in
        hello|HELLO)
            echo "${string}: hello 일때"
            ;;
        wo*)
            echo "${string}: wo로 시작하는 단어 일때"
            ;;
        s|start)
            echo "${string}: s 혹은 start 일때"
            ;;
        e|end)
            echo "${string}: e 혹은 end 일때"
            ;;
        *)
            echo "${string}: 기타"
            ;;
    esac
    # //case문 끝

done
```

출처 : [ <http://blog.gaerae.com/2015/01/bash-hello-world.html> ]

## Bash Shell Example

- Shell script to create MySQL database and user

	+ parameters : db name, username, password

	+ usege :
		* Name it someting like `mysql-db-create.sh`
		* Make it executable `chmod a+x mysql-db-create.sh`
		* Run it `./mysql-db-create.sh dbname username password`
	
	+	mysql-db-create.sh
	
	```
	#!/bin/bash
    ok() { echo -e '\e[32m'$1'\e[m'; } # Green

	EXPECTED_ARGS=3
	E_BADARGS=65
	MYSQL=`which mysql`
 
	Q1="CREATE DATABASE IF NOT EXISTS $1;"
	Q2="GRANT ALL ON *.* TO '$2'@'localhost' 	IDENTIFIED BY '$3';"
	Q3="FLUSH PRIVILEGES;"
	SQL="${Q1}${Q2}${Q3}"
 
	if [ $# -ne $EXPECTED_ARGS ]
	then
 	 echo "Usage: $0 dbname dbuser dbpass"
	 exit $E_BADARGS
	fi
 
	$MYSQL -uroot -p -e "$SQL"

	ok "Database $1 and user $2 created with a password $3"

	```

- select database and create table
	+ usege :
		* Name it someting like `mysql-table-create.sh`
		* Make it executable `chmod a+x mysql-table-create.sh`
		* Run it `./mysql-table-create.sh dbname`
	
	+	mysql-table-create.sh
	
	```
	#!/bin/bash
	ok() { echo -e '\e[32m'$1'\e[m'; } # Green
	
	EXPECTED_ARGS=1
	E_BADARGS=65
	MYSQL=`which mysql`
	
	Q1="use $1;"
	Q2="create table user(username varchar(10) Primary key Not null , password varchar(20) not null)";
	SQL="${Q1}${Q2}"
	
	if [ $# -ne $EXPECTED_ARGS ]
	then
			 echo "Usage: $0 dbname"
			  exit $E_BADARGS
	fi
	
	$MYSQL -uroot -p -e "$SQL"
	
	ok "Database $1 create user table"

	```

- insert user data from CSV
	+ usege :
		* Name it someting like `mysql-user-insert.sh`
		* Make it executable `chmod a+x mysql-user-insert.sh`
		* Run it `./mysql-user-insert.sh dbname`
	
	+	mysql-user-insert.sh
	
	```
	#!/bin/bash
	ok() { echo -e '\e[32m'$1'\e[m'; } # Green
	
	EXPECTED_ARGS=1
	E_BADARGS=65
	MYSQL=`which mysql`
	
	Q0="use $1;"
	Q1="LOAD DATA INFILE '/Users/choiseonho/Workspace/bash/user.csv' replace INTO table user fields terminated by ',' lines terminated by '\n';"
	Q2="select * from user;"
	SQL="${Q0}${Q1}${Q2}"
	
	if [ $# -ne $EXPECTED_ARGS ]
	then
		 echo "Usage: $0 dbname"
		  exit $E_BADARGS
	fi

	$MYSQL -uroot -p -e "$SQL"

	ok "Database $1 insert user"
	```

	+ Error 
		- ERROR 1290 (HY000) at line 1: The MySQL server is running with the --secure-file-priv option so it cannot execute this statement
		- 문제 원인 : 외부 파일의 보안 위배
		- 해결 방법 : 외부 파일의 PATH 정보를 보안 등록
		 
		 ```
		 ~$ mysqld --verbose --help | grep -A 1 'Default options' //my.cnf의 위치 정보를 알 수 있다.
		 ~$ vi ~/.../my.cnf
		 ```
		 .my.cnf의 파일 내용을 다음과 같이 수정한다.
		 
		 ```
		 # Default Homebrew MySQL server config
   [mysqld]
   secure-file-priv="write CSV file path"
      # Only allow connections from localhost
   bind-address = 127.0.0.1
		 ```

		- 저장 후 mysql 서버를 재실행 한다
		`brew services restart mysql`
		
출처 : [ <https://www.tutorialspoint.com/unix_commands/bash.htm> ]

