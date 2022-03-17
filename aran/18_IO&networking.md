# 18.IO 기반 입출력 및 네트워킹  
#### 1.IO 패키지 소개  
###### -개울을 뜻하는 Stream은 그 의미 그대로 데이터가 단일 방향 (출발지에서 나와 도착지로 흘러가는 것)으로 흘러가는 것을 말한다.

#### 2.입력스트림 & 출력스트림
###### -프로그램이 출발지, 도착지냐에 따라 스트림의 종류가 구분된다.  
###### -입력시 입력스트림(InputStream), 출력시 출력스트림(OutputStream)  
###### -데이터 입력은 키보드, 파일이 될 수 있고 출력은 모니터, 파일 등이 될 수 있음  
###### -입력과 출력 스트림을 결정하는 기준은 프로그램 기준이며 하나의 스트림이 입,출력을 동시에 할 수 없음 (Stream은 단방향이기 때문)  
###### -자바 내의 입출력 관련  API는 java.io 패키지에서 제공

##### 2-1.바이트 기반 스트림
###### -그림, 멀티미디어, 문자 등 모든 종류의 데이터 입출력  
| 입력스트림 | 출력스트림 |
| ------ | ------ |
| InputStream | OutputStream |

##### (A)InputStream  
| function | explanation | null |
| ------ | ------ | ------ |
| read() | 입력 스트림으로부터 1바이트를 읽고 읽은 바이트 리턴 | 읽을 바이트가 없을 땐 -1 리턴 | 
| read(byte[] b) | 입력 스트림으로부터 받은 바이트를 매개값으로 주어진 바이트 계열 배열에 저장하고 바이트 수 리턴 | 읽을 바이트가 없을 땐 -1 리턴 |
| read(byte[] b, int off, int len) | 입력 스트림으로부터 len개의 바이트만큼 읽고 매개값으로 주어진 바이트 배열 b부터 len개 저장, len 또는 실제 읽은 바이트 수를 리턴 | 읽을 바이트가 없을 땐 -1 리턴 |
| close() | 시스템 자원 반납 & 입력 스트림을 닫는다 | |

##### (B)OutputStream
| function | explanation |
| ------ | ------ |
| write(int b) | 출력 스트림에 1바이트를 보낸다 |
| write(byte[] b) | 출력 스트림에 매개변수 배열 b의 모든 바이트를 보낸다 | 
| write(byte[] b, int off, int len) | 출력 스트림에 매개변수 배열[off]부터 len개까지의 바이트를 보낸다 |
| flush() | 버퍼에 잔류하는 모든 바이트 출력 |
| close() | 시스템 자원 반납 & 출력 스트림 닫는다 |

###### -출력스트림 내부에 있는 버퍼에 데이터를 쌓아놨다가 순서대로 출력  
###### -fluse()함수는 그런 버퍼에 잔류하고 있는 데이터를 모두 출력 후 버퍼를 비워준다.  
###### -fluse()함수로 모든 데이터 출력후 close()함수로 시스템 자원을 모두 풀어준다.  

##### 2-2.문자 기반 스트림  
| 입력스트림 | 출력스트림 |
| ------ | ------ |
| Reader | Writer |

##### (A)Reader  
| function | explanation | null |
| ------ | ------ | ------ |
| read() | 입력 스트림으로부터 한 개의 문자를 받고 입력 수 리턴 | 읽을 바이트가 없을 땐 -1 리턴 | 
| read(char[] a) | 입력 받은 문자들을 매개변수 배열 a에 저장하고 입력받은 문자수 리턴 | 읽을 바이트가 없을 땐 -1 리턴 |
| read(char[] a, int off, int len) | len개의 문자를 읽고 매개변수 배열 a[off]부터 len개까지 저장 후 입력받은 문자수 리턴 | 읽을 바이트가 없을 땐 -1 리턴 |
| close() | 시스템 자원 반납 & 입력 스트림을 닫는다 | |

##### (B)Writer  
| function | explanation |
| ------ | ------ |
| write(int c) | 출력 스트림으로 주어진 한 문자를 보낸다 |
| write(char[] a) | 출력 스트림에 매개변수 a를 보낸다 | 
| write(char []a, int off, int len) | 출력 스트림에 매개변수 a[off]부터 len개 까지의 문자를 보낸다 |
| write(String str) | 출력 스트림에 주어진 문자열을 보낸다 |
| wirte(String str, int off, int len) | 출력 스트림에 문자열 off 순번부터 len개까지 문자열을 보낸다 |
| flush() | 버퍼에 잔류하는 모든 문자열 출력 |
| close() | 자원 반납 및 스트림 닫기 |

###### -OutputStream과 똑같이 fluse() 함수를 통해 버퍼에 적재된 문자열 출력 후 스트림을 비운다음 close()로 자원을 닫아준다.

#### 3.콘솔 입/출력
###### -Console은 키보드로 입력 받고 화면으로 출력하는 소프트웨어  
###### -유닉스&리눅스는 터미널, Window는 명령 프롬프트가 Console에 해당  
###### -자바 콘솔은 System.in 을 통해 입력, System.out 을 통해 출력  
 
##### (A)System.in 필드  
```java
	InputStream is = System.in;
	int asciiCode = is.read(); // asciiCode 변수 안에는 입력값의 아스키코드가 들어감
```
###### -a를 입력했을 때, asciiCode에는 a키인 97번과 Enter 값인 13,10번이 차례로 들어간다.  
###### (Enter는 캐리지 리턴(13)과 라인피드(10)의 결합)

```java
	char inputChar = (char)97; // 입력값 그대로를 알고 싶을 땐 char 타입으로 형변환하면 된다.
```

##### (B)System.out 필드   
```java
	InputStream is = System.in; // InputStream 변수 생성
	byte[] datas = new byte[100]; // 입력값 담을 배열 생성

	System.out.print("이름 : ");
	int nameByte = is.read(datas); // 입력받은 데이터를 datas 배열에 담는다.
	String name = new String(datas, 0, nameByte-2); // 2를 빼는 이유는 데이터 입력시 enter에 해당하는 아스키코드 (13,10을 제외하기 위함)
	System.out.println("입력한 이름 : "+name); // 콘솔에 입력한 이름 출력
```

##### (C)Console 클래스  
###### -콘솔에서 입력받은 문자열을 쉽게 읽을 수 있도록 java6 부터 java.io.Console 클래스 제공  
```java
	Console console = System.console(); // Console 객체를 얻기 위해 System의 정적 메소드 호출
	*정적메소드 : static method라고도 하며 객체 생성없이 클래스를 통해서 메서드 호출이 가능

	System.out.print("아이디 : ");
	String id = console.readLine(); // readLine() : Enter키 입력 전 모든 문자열을 읽는 함수
	System.out.println(id); // 입력한 id 출력
```

##### (D)Scanner 클래스  
###### -기본타입(정수,실수)를 읽을 수 없는 Console과는 달리 Scanner 클래스는 기본 타입의 값을 바로 읽을 수 있다.  
###### -Scanner 객체를 생성하기 위해 생성자안에 System.in을 매개값으로 주면 된다.  
```java
	Scanner scanner = new Scanner(System.in);
	String str = scanner.nextLine();
	System.out.println(str);
```

#### 4.파일 입출력  
##### 4-1.File 클래스  
###### -file 클래스는 파일 크기, 속성, 이름 등의 정보를 리턴해주는 기능과 파일 생성, 삭제 기능 제공  
###### -File 클래스르의 내장함수는 알아서 찾아보도록! (굉장히 많음)  

##### 4-2.FileInputStream  
###### -파일을 바이트 단위로 읽을 때 사용하는 바이트 기반 입력 스트림
```java
	FileInputStream fs = new FileInputStream("경로");

	File file = new File("경로");
	FileInputStream fs = new FileInputStream(file);
```

##### 4-3.FileOutputStream  
###### -바이트 단위로 데이터를 파일에 저장할 때 사용하는 바이트 기반 출력 스트림  
###### -주의할 점은 FileOutputStream 변수에 파일을 담을 때마다 파일이 추가되는게 아니라 덮어쓰는 형식으로 저장되기 때문에 기존  파일 끝에 데이터를 추가할 경우엔 생성사 두번째 매개값에 true를 추가해준다.  
###### -FileOutputStream은 OutputStream의 하위 클래스이기 때문에 사용방법이 동일하다.  
###### (flush를 통해 버퍼에 남은 데이터 출력 및 버퍼 비워주고 close로 파일을 닫아준다)  
```java
	FileOutputStream fo = new FileOutputStream("경로");

	File file = new File("경로");
	FileOutputStream fo = new FileOutputStream(file);


	FileOutputStream fo = new FileOutputStream("경로",true);
```

##### 4-4.FileReader
###### -텍스트 파일을 읽을 때 사용하는 문자 기반 스트림  
###### -문자 기반의 스트림이기 때문에 그림, 오디오 등은 읽을 수 없음  
```java
	FileReader fr = new FileReader("경로");

	File file = new File("경로"); // 파일 객체 생성
	FileReader fr = new FileReader(file); // 파일 객체를 통해 FileReader를 생성
```

##### 4-5.FileWriter  
###### -텍스트 데이터를 파일에 저장할 때 사용하는 문자 기반 스트림  
###### -FileWriter 역시 FileOutputStream처럼 기존 파일이 있을 경우 덮어쓰기 되므로 내용 끝에 데이터를 추가할 경우 FileWriter 두번째 매개값에 true를 넣어준다.
```java
	FileWriter fw = new FileWriter("경로");

	File file = new File("경로"); // 파일 객체 생성
	FileWriter fw = new FileWriter (file); // 파일 객체를 통해 FileWriter를 생성

	FileWriter fw = new FileWriter("경로",true);
```

#### 5.보조 스트림  
###### -보조 스트림이란 다른 스트림과 연결해서 여러 기능을 제공하는 스트림  
###### -자체적으로 입출력을 할 수 없어서 입력 소스와 연결되는 InputStream, FileInputStream, Reader 등과 연결하여 작업 진행  
###### -보조 스트림은 문자 변환, 입출력 성능 향상, 객체 입출력 등의 기능 제공  
```java
	보조스트림 변수 = new 보조스트림(연결스트림);

	InputStream is = System.in;
	InputStreamReader reader = new InputStreamReader(is);
```

##### 5-1.문자 변환 보조 스트림  
###### -입출력 데이터가 문자일 때 Reader, Writer로 변환해주는 보조 스트림  
###### -InputStreamReader, OutputStreamWriter  

##### 5-2.성능 향상 보조 스트림
###### -메모리 버퍼를 제공하여 프로그램의 실행 성능을 향상 시켜주는 보조 스트림  
###### -입력 소스로부터 자신의 내부 버퍼 크기만큼 데이터를 미리 읽고 버퍼에 저장, 버퍼는 데이터가 꽉차게 되면 한번에 데이터를 하드 디스크로 보냄으로서 출력 횟수를 줄인다.  
###### -바이트 기반 스트림에는 BufferedInputStream, BufferedOutputStream, 문자 기반 스트림에는 BufferedReader, BufferedWriter가 있다.  

##### (A)BufferedInputStream & BufferedReader  
###### -입력 소스로부터 자신의 내부 버퍼 크기만큼 데이터를 미리 읽고 버퍼에 저장, 이 때 프로그램은 데이터를 직접 읽는 대신 버퍼로부터 읽음으로서 읽기 성능 향상  
###### -그래서 Scanner를 통해 입력하는 것보다 BufferedReader를 통해 읽고 출력하는게 빠름  
```java
	BufferedInputStream bs = new BufferedInputStream(바이트입력스트림);
	BufferedReader br = new BufferedReader(문자입력스트림);
```

##### (B)BufferedOutputStream & BufferedWriter  
###### -프로그램에서 전송한 데이터를 내부 버퍼에 쌓아 두었다가 버퍼가 꽉 차면 버퍼의 데이터를 한번에 보내주는 보조 스트림  
###### -참고로 버퍼가 가득 찼을 때만 출력하기 때문에 마지막 자투리 데이터가 버퍼에 남아있을 수 있기 때문에 fluse() 메서드를 호출하여 버퍼에 잔류하는 데이터를 모두 보내준다.  
```java
	BufferedOutputStream bos = new BufferedOutputStream(바이트출력스트림);
```

##### 5-3.프린터 보조 스트림  
###### -PrintStream과 PrintWriter는 print(), println() 메서드를 가지고 있는 보조 스트림
###### -System.out 역시 PrintStream 타입
```java
	PrintStream ps = new PrintStream(바이트출력스트림);
	PrintWriter pw = new PrintWriter(문자출력스트림);
```

##### 5-4.객체 입출력 보조 스트림
###### -메모리에 생성된 객체 출력이 가능하나 객체는 문자가 아니기 때문에 바이트 기반 스트림으로 출력  
###### -객체를 출력하기 위해 객체의 데이터를 연속의 바이트로 변경해야하는데 이를 직렬화라고 부름  
###### -반대로 파일에 저장된 객체, 네트워크에서 전송된 연속적인 바이트를 객체로 복원하는 것은 역직렬화  
###### -객체 출력 보조 스트림으로는 ObjectInputStream과 ObjectOutputStream이 있다.  

#### 6.네트워크 기초  
###### -네트워크란, 여러 대의 컴퓨터를 통신회선으로 연결한 것  
###### -각 방의 컴퓨터를 통신 회선으로 연결한 것은 홈네트워크, 회사 및 건물같이 특정 영역에 존재하는 컴퓨터를 통신 회선으로 연결한 것은 지역 네트워크, 지역 네트워크를 통신 회선으로 연결한 것을 인터넷이라 한다  

##### 6-1.서버&클라이언트&IP주소&포트(Port)  
##### (A)Server  
###### -서비스를 제공하는 프로그램  
##### (B)Client  
###### -서비스를 받는 프로그램  
##### (C)IP  
###### -각 네트워크 어댑터마다 할당되는 고유의 주소  
###### -IP는 0~255사이의 정수로 할당되며 연결할 컴퓨터의 IP주소를 모르면 프로그램 통신 불가능  
##### (D)포트(Port)  
###### -한 대의 컴퓨터로 Web, DBMS, FTP 서버등이 실행될 경우 IP만으로 어떤 서버와 통신할 지 결정할 수 없다. 이 때 포트 번호를 통해 실행하는 서버를 선택할 수 있다.  
###### -서버는 시작할 때 고정적인 포트 번호를 가지는데 이를 포트 바인딩이라 한다.  
###### (웹서버는 80, ftp는 21)  

##### 6-2.자바 내에서 IP주소 가져오기
###### -자바는 IP주소를 java.net.InetAddress 객체로 표현  
###### -InetAddress는 로컬 IP 주소뿐 아니라 DNS(Domain Name System)에서 검색하여 IP주소를 가져오는 기능 제공  
```java
	InetAddress ia = InetAddress.getLocalHost();
```

#### 7.TCP 네트워킹  
###### -TCP(transmission Control Protocol)은 <b>연결 지향적 프로토콜</b>
###### *연결 지향적 프로토콜 : 클라이언트와 서버가 연결된 상태에서 데이터를 주고받는 프로토콜  
###### -장점 : 데이터는 고정된 통신 선로를 통해서 전달하기 때문에 안전하고 정확하게 전달  
###### -단점 : 연결까지 시간이 오래 걸리며 UDP보다 데이터 전송 속도가 느림  
###### -신뢰성이 중요한 프로그램에서 사용  

#### 8.UDT 네트워킹  
###### -UDT(User Datagram Protocol)은 <b>비연결 지향적 프로토콜</b>  
###### *비연결 지향적 프로토콜 : 연결 절차 없이 발신자가 일방적으로 데이터를 발신하는 방식  
###### -장점 : 연결 과정이 없기 때문에 속도가 빠름  
###### -단점 : 연결 유무를 알 수 없기 때문에 데이터 누락 가능성이 있으며 신뢰성이 떨어짐  
###### -속도가 중요한 프로그램에서 사용  

