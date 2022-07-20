# Part 2. Operating Sytem
Made by. 김영주 김지섭 김지훈 조형준 하태린

## [1.1. Operating System]
#### 💡 운영체제란 무었인가?

## [1.2 Process & Thread]
#### 💡 프로세스와 스레드의 차이에 대해서 설명하시오.
#### 💡 교착상태(Deadlock)와 기아상태에 대해 설명하시오.

## [1.3. OS Schedular]
#### 💡 OS 스케줄러란?


<br/><br/>

## 1.1. Operating System

#### 💡 운영체제란 무었인가?

> 운영 체제(OS, Operating System)
> 
> 하드웨어를 관리하고, 컴퓨터 시스템의 자원들을 효율적으로 관리하며, 응용 프로그램과 하드웨어 간의 인터페이스로써 다른 응용 프로그램이 유용한 작업을 할 수 있도록 환경을 제공해준다.
> 
> 즉, 운영 체제는 **사용자가 컴퓨터를 편리하고 효과적으로 사용할 수 있도록 환경을 제공하는 시스템 소프트웨어**라고 할 수 있다.
> 
> (*종류로는 Windows, Linux, UNIX, MS-DOS 등이 있으며, 시스템의 역할 구분에 따라 각각 용이점이 있다.*)


### **1. 프로세스 관리**

운영체제에서 작동하는 응용 프로그램을 관리하는 기능이다.

어떤 의미에서는 프로세서(CPU) 관리하는 것이라고 볼 수도 있다. 현재 CPU를 점유해야 할 프로세스를 결정하고, 실제로 CPU를 프로세스에 할당하며, 이 프로세스 간 공유 자원 접근과 통신 등을 관리하게 된다.

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/Operation%20System.html#_2-%E1%84%8C%E1%85%A5%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%8E%E1%85%B5-%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5-2)2. 저장장치 관리**

1차 저장장치에 해당하는 메인 메모리와 2차 저장장치에 해당하는 하드디스크, NAND 등을 관리하는 기능이다.

- 1차 저장장치(Main Memory)
    - 프로세스에 할당하는 메모리 영역의 할당과 해제
    - 각 메모리 영역 간의 침범 방지
    - 메인 메모리의 효율적 활용을 위한 가상 메모리 기능
- 2차 저장장치(HDD, NAND Flash Memory 등)
    - 파일 형식의 데이터 저장
    - 이런 파일 데이터 관리를 위한 파일 시스템을 OS에서 관리
    - `FAT, NTFS, EXT2, JFS, XFS` 등 많은 파일 시스템들이 개발되어 사용 중

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/Operation%20System.html#_3-%E1%84%82%E1%85%A6%E1%84%90%E1%85%B3%E1%84%8B%E1%85%AF%E1%84%8F%E1%85%B5%E1%86%BC-2)3. 네트워킹**

네트워킹은 컴퓨터 활용의 핵심과도 같아졌다.

TCP/IP 기반의 인터넷에 연결하거나, 응용 프로그램이 네트워크를 사용하려면 **운영체제에서 네트워크 프로토콜을 지원**해야 한다. 현재 상용 OS들은 다양하고 많은 네트워크 프로토콜을 지원한다.

이처럼 운영체제는 사용자와 컴퓨터 하드웨어 사이에 위치해서, 하드웨어를 운영 및 관리하고 명령어를 제어하여 응용 프로그램 및 하드웨어를 소프트웨어적으로 제어 및 관리를 해야한다.

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/Operation%20System.html#_4-%E1%84%89%E1%85%A1%E1%84%8B%E1%85%AD%E1%86%BC%E1%84%8C%E1%85%A1-%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5-2)4. 사용자 관리**

우리가 사용하는 PC는 오직 한 사람만의 것일까? 아니다.

하나의 PC로도 여러 사람이 사용하는 경우가 많다. 그래서 운영체제는 한 컴퓨터를 여러 사람이 사용하는 환경도 지원해야 한다. 가족들이 각자의 계정을 만들어 PC를 사용한다면, 이는 하나의 컴퓨터를 여러 명이 사용한다고 말할 수 있다.

따라서, 운영체제는 각 계정을 관리할 수 있는 기능이 필요하다. 사용자 별로 프라이버시와 보안을 위해 개인 파일에 대해선 다른 사용자가 접근할 수 없도록 해야 한다. 이 밖에도 파일이나 시스템 자원에 접근 권한을 지정할 수 있도록 지원하는 것이 사용자 관리 기능이다.

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/Operation%20System.html#_5-%E1%84%83%E1%85%B5%E1%84%87%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%89%E1%85%B3-%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%84%8B%E1%85%B5%E1%84%87%E1%85%A5-2)5. 디바이스 드라이버**

운영체제는 시스템의 자원, 하드웨어를 관리한다. 시스템에는 여러 하드웨어가 붙어있는데, 이들을 운영체제에서 인식하고 관리하게 만들어 응용 프로그램이 하드웨어를 사용할 수 있게 만들어야 한다.

따라서, 운영체제 안에 하드웨어를 추상화 해주는 계층이 필요하다. 이 계층이 바로 디바이스 드라이버라고 불린다. 하드웨어의 종류가 많은 만큼, 운영체제 내부의 디바이스 드라이버도 많이 존재한다.

이러한 수많은 디바이스 드라이버들을 관리하는 기능 또한 운영체제가 맡고 있다.

<br></br>
<br></br>

## 1.2 Process & Thread

#### 💡 프로세스와 스레드의 차이에 대해서 설명하시오.

- 프로세스 : 실행중인 프로그램
- 스레드 : 프로세스 안에서 실행되는 작업의 단위

프로세스는 **자신만의 메모리 공간(자원)** 을 할당 받아 사용한다.

스레드는 **힙, 데이터, 코드영역을 공유한다.**

기본적으로 프로세스마다 **최소 1개(메인 스레드)** 의 스레드를 소유한다.

프로세스는 각각 별도의 메모리 공간을 할당

- Code : 실행되어지는 코드가 저장되어 있는 메모리 영역
- Data : 전역변수, 정적 변수, 배열 등 초기화된 데이터, 공유변수 저장
- Heap : 동적할당 시 할당되는 메모리 영역
- Stack : 지역변수, 매개변수, 리턴 값 (임시 메모리 영역) 등 저장(각 스레드가 공유 x)

![initial](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/d0ef11ee-d7d5-46cb-b8b0-6561824c3d15/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T101025Z&X-Amz-Expires=86400&X-Amz-Signature=62b84bd0fd8992f32d39491163ae31bdaca32e75a09db9cabddd75ca9d303229&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)

<br></br>
<br></br>

#### 💡 교착상태(Deadlock)와 기아상태에 대해 설명하시오.

## **데드락 (DeadLock, 교착 상태)**

> 두 개 이상의 프로세스나 스레드가 서로 자원을 얻지 못해서 다음 처리를 하지 못하는 상태
> 
> 
> 무한히 다음 자원을 기다리게 되는 상태를 말한다.
> 
> 시스템적으로 한정된 자원을 여러 곳에서 사용하려고 할 때 발생한다.
>


- 데드락이 일어나는 경우

![initial](https://t1.daumcdn.net/cfile/tistory/243E89355714C26E28)

프로세스1과 2가 자원1, 2를 모두 얻어야 한다고 가정해보자

t1 : 프로세스1이 자원1을 얻음 / 프로세스2가 자원2를 얻음

t2 : 프로세스1은 자원2를 기다림 / 프로세스2는 자원1을 기다림

현재 서로 원하는 자원이 상대방에 할당되어 있어서 두 프로세스는 무한정 wait 상태에 빠짐

→ 이것이 바로 **DeadLock**!!!!!!

(주로 발생하는 경우)

> 멀티 프로그래밍 환경에서 한정된 자원을 얻기 위해 서로 경쟁하는 상황 발생
> 
> 
> 한 프로세스가 자원을 요청했을 때, 동시에 그 자원을 사용할 수 없는 상황이 발생할 수 있음. 이때 프로세스는 대기 상태로 들어감
> 
> 대기 상태로 들어간 프로세스들이 실행 상태로 변경될 수 없을 때 '교착 상태' 발생
>

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%83%E1%85%A6%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%86%A8-deadlock-%E1%84%87%E1%85%A1%E1%86%AF%E1%84%89%E1%85%A2%E1%86%BC-%E1%84%8C%E1%85%A9%E1%84%80%E1%85%A5%E1%86%AB)*데드락(DeadLock) 발생 조건***

> 4가지 모두 성립해야 데드락 발생
> 
> 
> (하나라도 성립하지 않으면 데드락 문제 해결 가능)
> 
1. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%89%E1%85%A1%E1%86%BC%E1%84%92%E1%85%A9-%E1%84%87%E1%85%A2%E1%84%8C%E1%85%A6-mutual-exclusion)상호 배제(Mutual exclusion)**
    
    > 자원은 한번에 한 프로세스만 사용할 수 있음
    > 
2. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%8C%E1%85%A5%E1%86%B7%E1%84%8B%E1%85%B2-%E1%84%83%E1%85%A2%E1%84%80%E1%85%B5-hold-and-wait)점유 대기(Hold and wait)**
    
    > 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 존재해야 함
    > 
3. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%87%E1%85%B5%E1%84%89%E1%85%A5%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%B7-no-preemption)비선점(No preemption)**
    
    > 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없음
    > 
4. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%89%E1%85%AE%E1%86%AB%E1%84%92%E1%85%AA%E1%86%AB-%E1%84%83%E1%85%A2%E1%84%80%E1%85%B5-circular-wait)순환 대기(Circular wait)**
    
    > 프로세스의 집합에서 순환 형태로 자원을 대기하고 있어야 함
    >
 ### **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%83%E1%85%A6%E1%84%83%E1%85%B3%E1%84%85%E1%85%A1%E1%86%A8-deadlock-%E1%84%8E%E1%85%A5%E1%84%85%E1%85%B5)*데드락(DeadLock) 처리***

---

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%80%E1%85%AD%E1%84%8E%E1%85%A1%E1%86%A8-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%85%E1%85%B3%E1%86%AF-%E1%84%8B%E1%85%A8%E1%84%87%E1%85%A1%E1%86%BC-%E1%84%92%E1%85%AC%E1%84%91%E1%85%B5)교착 상태를 예방 & 회피**

1. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%8B%E1%85%A8%E1%84%87%E1%85%A1%E1%86%BC-prevention)예방(prevention)**
    
    교착 상태 발생 조건 중 하나를 제거하면서 해결한다 (자원 낭비 엄청 심함)
    
    > 상호배제 부정 : 여러 프로세스가 공유 자원 사용점유대기 부정 : 프로세스 실행전 모든 자원을 할당비선점 부정 : 자원 점유 중인 프로세스가 다른 자원을 요구할 때 가진 자원 반납순환대기 부정 : 자원에 고유번호 할당 후 순서대로 자원 요구
    > 
2. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%92%E1%85%AC%E1%84%91%E1%85%B5-avoidance)회피(avoidance)**
    
    교착 상태 발생 시 피해나가는 방법
    
    > 은행원 알고리즘(Banker's Algorithm)
    > 
    > - 은행에서 모든 고객의 요구가 충족되도록 현금을 할당하는데서 유래함
    > - 프로세스가 자원을 요구할 때, 시스템은 자원을 할당한 후에도 안정 상태로 남아있게 되는지 사전에 검사하여 교착 상태 회피
    > - 안정 상태면 자원 할당, 아니면 다른 프로세스들이 자원 해지까지 대기

### **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%80%E1%85%AD%E1%84%8E%E1%85%A1%E1%86%A8-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%85%E1%85%B3%E1%86%AF-%E1%84%90%E1%85%A1%E1%86%B7%E1%84%8C%E1%85%B5-%E1%84%92%E1%85%AC%E1%84%87%E1%85%A9%E1%86%A8)교착 상태를 탐지 & 회복**

교착 상태가 되도록 허용한 다음 회복시키는 방법

1. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%90%E1%85%A1%E1%86%B7%E1%84%8C%E1%85%B5-detection)탐지(Detection)**
    
    자원 할당 그래프를 통해 교착 상태를 탐지함
    
    자원 요청 시, 탐지 알고리즘을 실행시켜 그에 대한 오버헤드 발생함
    
2. **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%92%E1%85%AC%E1%84%87%E1%85%A9%E1%86%A8-recovery)회복(Recovery)**
    
    교착 상태 일으킨 프로세스를 종료하거나, 할당된 자원을 해제시켜 회복시키는 방법
    
    > #프로세스 종료 방법
    > 
    > - 교착 상태의 프로세스를 모두 중지
    > - 교착 상태가 제거될 때까지 하나씩 프로세스 중지
    > 
    > ### **[#](https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html#%E1%84%8C%E1%85%A1%E1%84%8B%E1%85%AF%E1%86%AB-%E1%84%89%E1%85%A5%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%B7-%E1%84%87%E1%85%A1%E1%86%BC%E1%84%87%E1%85%A5%E1%86%B8)자원 선점 방법**
    > 
    > - 교착 상태의 프로세스가 점유하고 있는 자원을 선점해 다른 프로세스에게 할당 (해당 프로세스 일시정지 시킴)
    > - 우선 순위가 낮은 프로세스나 수행 횟수 적은 프로세스 위주로 프로세스 자원 선점
    
<br></br>
<br></br>

## 1.3. OS Schedular

#### 💡 OS 스케줄러란?

*프로세스를 스케줄링하기 위한 Queue 에는 세 가지 종류가 존재한다.*

- Job Queue : 현재 시스템 내에 있는 모든 프로세스의 집합
- Ready Queue : 현재 메모리 내에 있으면서 CPU 를 잡아서 실행되기를 기다리는 프로세스의 집합
- Device Queue : Device I/O 작업을 대기하고 있는 프로세스의 집합

각각의 Queue 에 프로세스들을 넣고 빼주는 스케줄러에도 크게 **세 가지 종류가** 존재한다.

![inital](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/8b4c2ae6-a291-4f50-92fa-5414b12b0104/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220720%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220720T101347Z&X-Amz-Expires=86400&X-Amz-Signature=decbca8c644c69d81146a575e4de90bb24634cb87320e29a2c1fcdaeefd381aa&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject)
- **장기스케줄러(Long-term scheduler or job scheduler)**
    
    메모리는 한정되어 있는데 많은 프로세스들이 한꺼번에 메모리에 올라올 경우, 대용량 메모리(일반적으로 디스크)에 임시로 저장된다. 이 pool 에 저장되어 있는 프로세스 중 어떤 프로세스에 메모리를 할당하여 ready queue 로 보낼지 결정하는 역할을 한다.
    
    - 메모리와 디스크 사이의 스케줄링을 담당.
    - 프로세스에 memory(및 각종 리소스)를 할당(admit)
    - degree of Multiprogramming 제어(실행중인 프로세스의 수 제어)
    - 프로세스의 상태new -> ready(in memory)
    
    *cf) 메모리에 프로그램이 너무 많이 올라가도, 너무 적게 올라가도 성능이 좋지 않은 것이다. 참고로 time sharing system 에서는 장기 스케줄러가 없다. 그냥 곧바로 메모리에 올라가 ready 상태가 된다.*
    
- **단기스케줄러(Short-term scheduler or CPU scheduler)**
    - CPU 와 메모리 사이의 스케줄링을 담당.
    - Ready Queue 에 존재하는 프로세스 중 어떤 프로세스를 running 시킬지 결정.
    - 프로세스에 CPU 를 할당(scheduler dispatch)
    - 프로세스의 상태ready -> running -> waiting -> ready

- **중기스케줄러(Medium-term scheduler or Swapper)**
    - 여유 공간 마련을 위해 프로세스를 통째로 메모리에서 디스크로 쫓아냄 (swapping)
    - 프로세스에게서 memory 를 deallocate
    - degree of Multiprogramming 제어
    - 현 시스템에서 메모리에 너무 많은 프로그램이 동시에 올라가는 것을 조절하는 스케줄러.
    - 프로세스의 상태ready -> suspended
    
- **Process state - suspended**
    
    Suspended(stopped) : 외부적인 이유로 프로세스의 수행이 정지된 상태로 메모리에서 내려간 상태를 의미한다. 프로세스 전부 디스크로 swap out 된다. blocked 상태는 다른 I/O 작업을 기다리는 상태이기 때문에 스스로 ready state 로 돌아갈 수 있지만 이 상태는 외부적인 이유로 suspending 되었기 때문에 스스로 돌아갈 수 없다.
    
    
    
    
    
    출처 :
    
    https://k39335.tistory.com/32
    https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/4_Threads.html
    https://velog.io/@syleemk/%EB%A9%B4%EC%A0%91-%EB%8C%80%EB%B9%84-%EC%9A%B4%EC%98%81%EC%B2%B4%EC%A0%9C
    https://chanhuiseok.github.io/posts/cs-2/
    https://gyoogle.dev/blog/computer-science/operating-system/DeadLock.html
    
    
