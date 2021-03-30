# get_next_line

norminette v3 기준으로 작성된 코드입니다. 제어문 내에서 할당이 금지되어 있습니다.
```
ASSIGN_IN_CONTROL    (line:  16, col:  23):	Assignment in control structure
```
테스트는 42seoul wiki get-next-line페이지에 있는 스크립트를 사용하였습니다.

mandatory파트와 bonus파트의 코드가 동일합니다.

---

OPEN_MAX를 255로 설정한 이유

gnlTester에서는 `Invalid fd` 테스트 항목이 존재합니다. 1000이상의 fd가 주어지기도 합니다.
처음에는 테스터를 통과하기 위해 임의로 256을 사용하였습니다.

fd의 최대값에 대해서 검색을 하던 중 `ulimit -aS (ulimit -n)` 명령어를 사용하여 현재 프로세스가 열 수 있는 최대 file descriptor 개수를 확인 할 수 있었습니다. 
```
-n: file descriptors                256
```
fd는 0부터 시작하고 `char *save[fd]`처럼 배열로 사용하기 때문에 255로 설정하였습니다.

위 내용은 개인적인 생각이며 틀린 추론일 수 있습니다. (2021/03/30 작성됨)

---

개인맥(M1)환경에서 테스트한 결과

- [x] norminette v3

|통과여부|테스터기이름|
|:----:|:------:|
|O|42testers-gnl|
|O|gnl-lover|
|O|gnlkiller|
|O|gnlkiller2|
|O|gnlTester|
|O|Test-42|

---

ssh환경에서 테스트한 결과

- [x] norminette v2

|통과여부|테스터기이름|
|:----:|:------:|
|O|42testers-gnl|
|O|gnl-lover|
|O|gnlkiller|
|O|gnlkiller2|
|O|gnlTester|
|O|Test-42|
