# G-lang
할 일이 어지간히 없어서 만들었습니다.몇 가지 문법을 제시하여, 신입생이 될 수 있습니다.

온라인 인터프리터 주소 -> https://sihyeonlove.github.io/G-lang/g_interpreter <-

문법은 다음과 같습니다.

1.변수 선언 : 변수를 선언할 때, 모든 변수는 "학과명"으로 구성됩니다.이는 접근시도 마찬가지입니다.예를 들면 간호학과, 의예과 등등의 학과를 모두 임의로 변수로 선언할 수 있습니다.이때, 실제 가천대에 존재하지 않는 학과도 개설이 가능합니다.(추후 이 부분에 대하여 수정이 이루어질 수 있습니다.)또한, 문법상으로는 우선 정시로 합격을 하는 것으로 변수를 선언합니다.그 합불 예측 질문을 함으로써 변수를 선언하는데, 문법으로는

"정시 11111 ~~과 합격 가능한가요"

이때, 다섯자리 숫자는 수능 성적을 입력할 수 있습니다.국수영탐탐 순이 될 때, 국수영은 변수의 초기값을 나타냅니다.예를 들어 성적 16217은 162가 초기값입니다.
탐구1 과목의 성적은 이 변수의 형태를 나타냅니다.아스키 코드에 기반한 문자 char형, 혹은 그대로의 int형 중 선택할 수 있습니다.만약 탐구 1에서 5등급 이상의 좋은 성적을 받았다면 char, 아니라면 int 형태로 저장됩니다.
탐구2 과목의 성적은 중복 검사 여부입니다.만약 탐구 2에서 5등급 이상의 좋은 성적을 받았다면 기존에 동일한 이름의 학과가 존재하더라도 덮어씌웁니다.아니라면, 같은 이름의 학과의 합격 사례가 이미 존재할 경우 번역하지 않습니다.

학과명은 반드시 ~과의 형식이어야 합니다.

다음은 1의 예시 코드 / 해석입니다.

정시 14479 의예과 합격 가능한가요 // 초기값 144를 int 형태로 변수 이름 "의예과"로 저장합니다.이때, 이미 의예과 합격 사례가 있을 경우 무시합니다.

주의 !! 변수는 Stack이 아닌 Queue 방식으로 저장됩니다.먼저 선언된 변수가 나중에 먼저 출력됩니다.출력과 관련된 내용은 나중에 다루겠습니다.

2.변수의 사칙연산 : 학과명으로 변수를 선언한 뒤, (반드시 선행되어야 합니다.)이제는 수시 모집으로 변수의 상세 수치를 조정할 수 있습니다.문법 먼저 설명드리자면, 다음과 같습니다.

"(교과|종합|논술|기균) n.nn ~과 합격 가능한가요"

우선, 전형별로 높고 낮음 / 우수함 등을 구분할 의도는 없다는 점을 밝힙니다.첫 번째, 4개의 전형은 사칙연산의 종류를 결정합니다.교과는 **+**, 종합은 **-**, 논술은 **X**, 기균은 **÷**입니다.
두 번째, 내신 성적은 연산할 수치입니다.이 수치는 역순으로 배치되어 있습니다.예를 들어서, 5.67은 765, 1.00은 001, 즉, 1을 나타냅니다.
세 번째, 학과명은 반드시 ~과의 형식이어야 하며, 앞서 정시 합격 사례로 선언하였던 학과명을 가져옵니다.예를 들어, "정시 14479 의예과 합격 가능한가요"로 의예과 변수를 선언하였고, 이 변수의 값이 144를 건드리고 싶다면, 의예과를 호출하면 됩니다.

정리하자면, (정시 14479 의예과 합격 가능한가요 를 선행하여 실행하였다 가정합니다.) 전형으로 선택한 사칙연산을 성적으로 입력된 수치로 실행하는데, 학과명을 불러와 변수에 대입한다라 할 수 있습니다.
이어서 예시로, "교과 3.10 의예과 합격 가능한가요"는 의예과의 값에 13을 더하라는 의미가 될 것입니다.

3.if문 : 2와 비슷하게 학과명으로 선언된 변수의 값이 0인지 아닌지 검사합니다.0이 아니면 true, 0일 경우 false입니다.또한, 나머지 부분은 0이 아닐 경우 그 변수에 가할 연산입니다.

기본 문법은 다음과 같습니다.

"가천대 ~과 (교과|종합|논술|기균) n.nn로 합격했는데 좋나요"

2번과 나머지 문법은 같습니다.우선, 선언된 과 변수의 값을 체크합니다.이 값이 0이 아닐 경우에는, 그 변수에 대하여 사칙연산을 실시할 수 있습니다.

예를 들면, 의예과 변수의 값이 0이 아니라는 가정 하에

가천대 의예과 논술 2.00로 합격했는데 좋나요

는 의예과 변수에 2를 곱하게 될 겁니다.

4.반복연산 : 앞선 if문과 비슷합니다.단, 연산자를 다른 방식으로 지정하고, 연산의 문법이 다릅니다.

문법은 다음과 같습니다.

"가천대 ~과 농어촌 n.mx로 합격했는데 좋나요"

~과는 어떤 변수에 접근할건지 설정합니다.

n.mx부분이 중요합니다."농어촌"을 키워드로 함으로써 연산 과정이 다음과 같아집니다.모든 n, m, x는 1자리의 수입니다.

n : 더할 수입니다.
m : 사칙연산 구분입니다.1은 +, 2는 -, 3은 X, 4 이상은 ÷입니다.
x : 수행할 횟수입니다.

예를 들어, 3.18은 3을 8번 더하는 연산을 수행하라는 명령입니다.

정리해 예시를 들자면, 

가천대 의예과 농어촌 1.13 합격했는데 좋나요

는, 의예과 변수에 1을 3번 더하라는 의미입니다.

5.최종 출력 : 이 언어는 종료 시점에 모든 변수를 지정한 형태로 출력합니다.또한, 저장하는 방식은 큐(Queue)로써, 출력 또한, FIFO 방식을 따릅니다.즉, 변수가 최초 선언 -> 저장된 순서에 따라 순서에 맞추어 출력된다는 것입니다.예를 들어, 의예과(100, int), 한의예과(67, char(아스키코드로 'C'))로 저장되어 있을 경우, 모든 연산이 끝난 후 출력은 "100C"가 됩니다.

6.사전 출력 : 기존에 선언한 변수를 최종 출력보다 우선시하고싶을 경우, 다음 문법을 사용할 수 있습니다.

"가천대 ~과 (자퇴|휴학)해도 되나요"

과명은 변수의 이름입니다.여기서 호출된 변수의 값을 형식에 맞추어 최종 출력보다 우선 출력됩니다.

자퇴 / 휴학은 변수의 삭제를 결정합니다.자퇴할 경우, 해당 변수는 삭제됩니다.휴학은 단순 출력 후, 변수의 위치와 값이 유지됩니다.

예를 들면, 가천대 의예과 자퇴해도 되나요 는 의예과에 저장된 변수를 출력합니다.이는 최종 출력보다 우선 출력됩니다.

예를 들어, 의예과(100, int), 한의예과(67, char(아스키코드로 'C'))로 저장되어 있을 경우에 "가천대 한의예과 자퇴해도 되나요"를 실행 시, 출력은 "C100"이 됩니다.자퇴가 아닌 휴학일 경우, 값이 유지돼 "C100C" 가 출력됩니다.

7.코딩 : 모든 코드는 앞서 설명한 문법을 "?"로 분리합니다.C언어에서 ;로 구분하는 것과 비슷합니다.

예를 들어, 

"정시 11111 의예과 합격 가능한가요?정시 12243 간호학과 합격 가능한가요?정시 54486 의공학과 합격 가능한가요?가천대 의공학과 1.21로 합격했는데 좋나요"

이런 식으로 하실 수 있습니다.

8.? : "합격"을 "추합"으로 바꿔쓸 수 있습니다.~~이거 어디다 쓰려고 했는데 기억이 나지 않습니다.~~

9.기타 : 

-그래서 이거 튜링 완전한거 맞나요 ?
ㆍ저도 모릅니다.그냥 할 짓 없는 24학번이 없는 지식으로 대충 만든겁니다.TODO.

-뭐하시는 아줌마 아저씨인가요 ? 학과가 어디인가요 ?
ㆍ그러게요 ?

-예시 코드가 있나요 ?
ㆍ"Hello, World!"를 출력하는 코드를 아래에 드리겠습니다.

```Gacheon
정시 11111 한의예과 추합 가능한가요?정시 12211 화학과 추합 가능한가요?정시 12313 소프트웨어학과 추합 가능한가요?정시 12313 인공지능학과 추합 가능한가요?정시 11111 약학과 추합 가능한가요?정시 64728 심리학과 추합 가능한가요?정시 13511 영미어문학과 추합 가능한가요?정시 18944 경제학과 합격 가능한가요?정시 11132 전기공학과 합격 가능한가요?정시 11437 의공학과 합격 가능한가요?정시 12313 간호학과 합격 가능한가요?정시 12422 행정학과 합격 가능한가요?정시 44444 의예과 합격 가능한가요?종합 9.30 한의예과 추합 가능한가요?종합 1.20 화학과 추합 가능한가요?종합 5.10 소프트웨어학과 추합 가능한가요?종합 5.10 인공지능학과 추합 가능한가요?종합 3.06 심리학과 추합 가능한가요?종합 3.01 영미어문학과 추합 가능한가요?종합 2.01 경제학과 추합 가능한가요?종합 5.10 간호학과 합격 가능한가요?종합 4.20 행정학과 합격 가능한가요?가천대 의예과 종합 1.14로 추합했는데 좋나요
```

-이거 어디서 해 볼 수 있나요 ?
ㆍ링크를 드리겠습니다.

->  https://sihyeonlove.github.io/G-lang/g_interpreter <-

-뭐로 만들었나요 ?
ㆍJS를 기반으로 했으며, ECMAscript 환경으로, 웹 인터프리터를 구축하여 온라인으로 구현했습니다.

10.하고 싶은 말 : 진짜 할 짓 없어서 5시간 정도만 투자했습니다.사실 md 작성에 2시간 쓴 거 같습니다.부족한 거 압니다.그러니 무분별한 욕설은 자제해주세요.그냥 가천대 들어와서 기분 좋은 신입생이 뻘짓거리 했구나 생각해줘요...


++ 아니 대체 제 깃헙 주소는 어떻게 아시고 오신건가요...별 달아주셔서 감사드립니다 우선 ㅋㅋㅋㅋㅋㅋㅋ 이런거 받아본적이 없어욬ㅋㅋㅜ.ㅜ
