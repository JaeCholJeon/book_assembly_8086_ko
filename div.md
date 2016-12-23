#분량조절실패로 분리된 나눗셈

나눗셈은 곱셈처럼 부호있는 연산이 따로 있고 ax, dx 레지스터가 자동으로 사용된다는 것이 같습니다. 그리고 8비트 16비트 연산을 구별해야한다는 것도 같습니다.

div는 부호없는 나누기를 합니다. 오퍼랜드가 바이트일 경우 AX값을 나누고 AL에는 결과값이 AH에는 나머지가 저장됩니다. 오퍼랜드가 워드일 경우 DX:AX에 나누기를 실행하고 결과는 AX에 나머지는 DX에 저장됩니다.

dx:ax = 0:33이고 cx 값이 3일때 div cx를 하면ax=11, dx=0이 되는 식입니다.

idiv는 부호를 고려한 나누기를 하는 것뿐 다른 것들은 같습니다.

나누셈은 별로 자세하게 설명할 필요가 없을것 같습니다. 더 중요한건 div 명령이 아니라 shr, sar 을 쓰는 나눗셈입니다. 이런 shift 처리를 잘 해야 빠르게 곱셈/나눗셈을 하고 비트 연산도 할 수 있는 것입니다. 나눗셈을 주로 쓰는 연산이 좌표를 구할 때나 해시나 큐같이 배열에서 위치 찾을 때, 암호화, 비트 연산 등인데 대부분 일부러 나눗셈 명령을 쓰지 않고 shift 명령을 쓸 수 있도록 2의 배수로 나누기를 합니다. 연산 속도가 훨씬 빠르기 때문입니다. 속도가 깡패지요.

shift 연산은 다시 자세하게 설명하는게 좋을것 같습니다.

이걸로 사칙연산은 끝~