# ISA(Instruction Set Architecture)
- ISA는 명령어 집합 또는 명령어 집합 구조라고 부름
- ISA는 CPU의 언어이자 하드웨어가 소프트웨어를 어떻게 이해할지에 대한 약속임
- ISA는 CPU의 종류에 따라 달라질 수 있음 <br>
  예를 들어, 인텔 노트북 CPU와 애플 아이폰 CPU의 ISA는 서로 다름 <br>
  따라서 자신에게 맞는 명령어 집합이 아니라면 CPU는 명령어를 이해할 수 없음
- 동일한 소스코드라도 ISA가 다른 컴퓨터에서 컴파일하면 다른 어셈블리어를 가지게 됨 (사용한 컴파일러의 종류에 따라서도 어셈블리어가 달라짐)
- CPU가 이해하는 명령어가 달라지면, 하드웨어 설계적으로도 많은 부분이 달라짐 (레지스터 개수, 메모리 관리 방법 등)
- ISA의 종류에 따라 명령어 병렬 처리 기법을 적용에 대한 유불리가 달라짐 <br>
  명령어 병렬 처리기법을 도입하기 유리한 ISA에 CISC와 RISC가 있음

# CISC (Complex Instruction Set Computer)
- CISC는 복잡한 명령어 집합을 활용하는 컴퓨터라고 부름
- CISC는 다양한 가변길이 명령어를 활용하고, 다양한 주소 지정 방식도 가짐
- 다양하고 강력한 명령어를 활용한다는 것은 적은 수의 명령어로도 프로그램을 실행할 수 있다는 것과 같음 <br>
  따라서 메모리를 최대한 아끼며 개발해야했던 과거에는 CISC 방식이 유행했음
- 하지만 CISC는 복잡하고 다양한 기능을 제공하는 탓에 명령어의 크기와 실행되기까지의 시간이 일정하지 않고, <br>
  복잡한 명령어 때문에 명령어 하나를 실행하는 데 여러 클럭 주기를 필요로 함 <br>
  이는 곧 각 단계에 소요되는 시간이 가급적 1 클럭이어야하는 명령어 파이프라이닝 기법에서 큰 걸림돌이 됨 <br>
  따라서 현대 CPU에서 높은 성능을 내기 위한 핵심 기술인 파이프라이닝을 사용하는 것에 제한이 생기고, 이는 곧 CISC의 치명적 단점이 됨 <br>
  또한, 복잡하고 다양한 기능을 제공하지만 정작 주로 사용되는 명령어는 몇 가지가 되지 않는 다는 것이 밝혀짐
- 결론적으로, CISC는 복잡하고 다양한 기능을 제공하여, 적은 수의 명령으로 프로그램을 실행시키고 메모리를 절약할 수 있지만, <br>
  명령의 크기와 실행시간이 일정하지 않아 파이프라이닝이 어렵고, 제공되어지는 대다수의 명령어가 실제로는 잘 사용되지 않는다는 한계가 있음
- 대표적으로는 인텔의 X86, X86-64 CPU가 있음

# RISC (Reduced Instruction Set Computer)
- RISC는 CISC에 비해 적은 명령어를 가지지만, CISC에 비해 짧고 규격화된 명령어(크기와 실행시간이 일정)을 제공하고, <br>
  되도록 1클럭 내외로 실행되는 명령어를 지향함 <br>
  즉, RISC는 고정길이 명령어를 활용함
- 명령어의 규격화, 1 클럭 내외의 실행은 곧 파이프라이닝에 최적화 되어 있는 것과 같음 <br>
  또한, 메모리에 직접 접근하는 명령어를 load, store 두 개로 제한하여, 메모리 접근을 단순화하고 최소화시킴
- RISC는 메모리 접근을 단순화, 최소화 시키는 대신 레지스터를 적극 활용함 <br>
  따라서 CISC에 비해 레지스터를 활용한 연산이 많고, 범용 레지스터의 개수도 더 많음 <br>
  물론 사용가능한 명령어의 개수는 CISC보다 적기 때문에 더 많은 명령으로 프로그램을 작동시킴
- 대표적인 예시로는 애플의 ARM CPU가 있음


