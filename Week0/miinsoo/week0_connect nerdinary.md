### 너디너리 홈페이지 접속 과정
1. 클라이어트가 너디너리 홈페이지에 접속하기 위해서, 웹 브라우저에 "https://neordinary.co.kr:443"를 입력합니다.
2. DNS(Domain Name System)에서 neordinary.co.kr을 ip주소로 변환합니다.
3. Network Edge에 있는 클라이언트는 너디너리 홈페이지 서버의 통신 가능 여부를 확인하기 위해, SYN 패킷을 너디너리 서버에게 보낸다. 패킷 안에는 서버의 위치 정보인 IP주소가 있다. 경로는 Network Edge(클라이언트) -> Access Network -> Network core(라우터) -> Access Network -> Network Edge(서버) 이다
4. syn 패킷을 받은 너디너리 홈페이지 서버는 통신 요청을 수락하는 응답인 ACK 패킷과 클라이언트의 통신 가능 여부를 알기 위해서 SYN 패킷을 클라이언트로 전송한다. 경로를 클라이언트에서 서버로의 경로의 역순이다.
5. 클라이언트가 정상적으로 ACK와 SYN 패킷을 받아, 서버가 통신 가능함을 알고 클라이언트도 통신 요청을 수락한다는 의사를 전달하기 위해서 ACK 패킷을 서버에게 전달한다.
6. 서버는 클라이언트가 보낸 ACK 패킷을 받아, 클라이언트가 통신 가능함을 인식한다.(TCP의 3 way-handshake)
7.  Network Edge에 있는 클라이언트가 ip주소와 Port 번호 등등을 담은 데이터를 패킷 형태로 Access Network(ex.공유기, 랜선)로 보냅니다.
8.  클라이언트는 동적 또는 정적 리소스를 요청하는 패킷들을 sequence number을 매겨서 순서를 보장한다. 서버가 만약 sequence number에 맞지 않는 패킷을 받으면 클라이언트에게 다시 순서대로 패킷을 보낼 것을 요청한다.
9.  서버가 정상적으로 패킷을 받으면 리소스와 ACK Number와 함께 패킷을 보내 데이터의 전달을 보증한다.
10. 클라이언트는 서버로부터 패킷에 담겨있는 리소스를 전달 받고, 이 리소스를 바탕으로 웹 브라우저가 화면을 출력해 홈페이지를 접속하게 된다.