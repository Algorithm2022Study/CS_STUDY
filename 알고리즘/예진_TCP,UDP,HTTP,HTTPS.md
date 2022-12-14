## ๐ฅ Transport Layer

OSI 7 ๋ ์ด์ด์์ Transport Layer(4๊ณ์ธต)์๋ ์ ๋๋จ(End to end)์ ์ฌ์ฉ์๋ค์ด ์ ๋ขฐ์ฑ์๋ ๋ฐ์ดํฐ๋ฅผ ์ฃผ๊ณ  ๋ฐ์ ์ ์๋๋ก ํด ์ฃผ์ด, ์์ ๊ณ์ธต๋ค์ด ๋ฐ์ดํฐ ์ ๋ฌ์ ์ ํจ์ฑ์ด๋ ํจ์จ์ฑ์ ์๊ฐํ์ง ์๋๋ก ํด์ค๋ค. 

์ ์ก ๊ณ์ธต์ ์ธํฐ๋ท์ ๊ธฐ๋ฐ์ธ TCP/IP ์ฐธ์กฐ ๋ชจ๋ธ๊ณผ ์ผ๋ฐ์ ์ธ ๋คํธ์ํฌ ๋ชจ๋ธ์ธ ๊ฐ๋ฐฉํ ์์คํ ๊ฐ ์ํธ ์ ์ (Open Systems Interconnection, OSI) ๋ชจ๋ ํฌํจํ๊ณ  ์๋ค.

**์ ์ก ํ๋กํ ์ฝ ์ค ์ ์๋ ค์ง ๊ฒ์ด ๋ฐ๋ก TCP์ UDP**์ด๋ค.

### Transport Layer VS Network Layer

- Transport Layer :ย `Application ํ๋ก์ธ์ค`๋ค ๊ฐ์ย `๋ผ๋ฆฌ์ ์ธ ํต์ `์ ์ ๊ณต
- Network Layer :ย `host`ย ๊ฐ์ย `๋ผ๋ฆฌ์ ์ธ ํต์ `์ ์ ๊ณต
    - ๋ฐ์ดํฐ์ ์ ๋ฌ ๊ฒฝ๋ก๋ฅผ ์ค์ ํ๋ ์ญํ 

## ๐ฅ TCP์ UDP

- ํธ๋์คํฌํธ ๊ณ์ธต์ ํจํท์ "`์ธ๊ทธ๋จผํธ`"๋ผ๊ณ  ํ๋ค.
- UDP ์์๋ ์ข์ข ์ด๋ฅผ "`๋ฐ์ดํฐ๊ทธ๋จ`"์ด๋ผ๊ณ  ํ๊ธฐ๋ ํ๋ค.

## TCP (Transmission Control Protocol)

์ธํฐ๋ท์์์ ๋ฐ์ดํฐ๋ฅผ ๋ฉ์ธ์ง์ ํํ๋ก ๋ณด๋ด๊ธฐ ์ํด IP์ ํจ๊ป ์ฌ์ฉํ๋ ํ๋กํ ์ฝ

TCP๋ ์ ํ๋ฆฌ์ผ์ด์์๊ฒย **์ ๋ขฐ์ ์ด๊ณ  ์ฐ๊ฒฐ์งํฅ์ฑ**ย ์๋น์ค๋ฅผ ์ ๊ณตํ๋ค. ์ผ๋ฐ์ ์ผ๋ก TCP์ IP๋ ํจ๊ป ์ฌ์ฉ๋๋ฉฐย **IP๋ ๋ฐฐ๋ฌ์, TCP๋ย `ํจํท`์ ์ถ์  ๋ฐ ๊ด๋ฆฌ**๋ฅผ ํ๊ฒ ๋ฉ๋๋ค.

TCP๋ ์ฐ๊ฒฐํ ์๋น์ค๋ก, ์ ๋ขฐ์ ์ธ ์ ์ก์ ๋ณด์ฅํ๊ธฐ์ handshakingํ๊ณ  ๋ฐ์ดํฐ์ ํ๋ฆ์ ์ด์ ํผ์ก์ ์ด๋ฅผ ์ํํฉ๋๋ค. ํ์ง๋ง ์ด๋ฌํ ๊ธฐ๋ฅ์ผ๋ก ์ธํด TCP์ ์๋๋ ๋๋ฆฝ๋๋ค.

**TCP ํน์ง**

- 3-way handshaking ๊ณผ์ ์ ํตํด ์ฐ๊ฒฐ์ ์ค์ ํ๊ณ  4-way handshaking์ ํตํด ํด์ ํ๋ค.
- ํ๋ฆ ์ ์ด ๋ฐ ํผ์ก ์ ์ด.
- ๋์ ์ ๋ขฐ์ฑ์ ๋ณด์ฅํ๋ค.
- UDP๋ณด๋ค ์๋๊ฐ ๋๋ฆฌ๋ค.
- ์ ์ด์ค(Full-Duplex), ์ ๋์ (Point to Point) ๋ฐฉ์.

### UDP (User Datagram Protocol)

๋ฐ์ดํฐ๋ฅผ ๋ฐ์ดํฐ๊ทธ๋จ ๋จ์๋ก ์ฒ๋ฆฌํ๋ ํ๋กํ ์ฝ 
* ๋ฐ์ดํฐ๊ทธ๋จ์ด๋ย `๋๋ฆฝ`์ ์ธ ๊ด๊ณ๋ฅผ ์ง๋๋ ํจํท์ด๋ผ๋ ๋ป ์ด๋ค.

UDP๋ ๋น์ฐ๊ฒฐํ ํ๋กํ ์ฝ์ด๋ค. ์ฆ, ํ ๋น๋๋ ๋ผ๋ฆฌ์ ์ธ ๊ฒฝ๋ก๊ฐ ์๊ณ  ๊ฐ๊ฐ์ ํจํท์ด ๋ค๋ฅธ ๊ฒฝ๋ก๋ก ์ ์ก๋๊ณ  ์ด ๊ฐ๊ฐ์ ํจํท์ ๋๋ฆฝ์ ์ธ ๊ด๊ณ๋ฅผ ์ง๋๊ฒ ๋๋๋ฐ, ์ด๋ ๊ฒ ๋ฐ์ดํฐ๋ฅผ ์๋ก ๋ค๋ฅธ ๊ฒฝ๋ก๋ก ๋๋ฆฝ ์ฒ๋ฆฌํ๋ ํ๋กํ ์ฝ์ UDP ๋ผ๊ณ  ํ๋ค.

UDP๋ ์ฐ๊ฒฐ์ ์ค์ ํ๊ณ  ํด์ ํ๋ ๊ณผ์ ์ด ์กด์ฌํ์ง ์๋๋ค. ์๋ก ๋ค๋ฅธ ๊ฒฝ๋ก๋ก ๋๋ฆฝ์ ์ผ๋ก ์ฒ๋ฆฌํจ์๋ ํจํท์ ์์๋ฅผ ๋ถ์ฌํ์ฌ ์ฌ์กฐ๋ฆฝํ๊ฑฐ๋ ํ๋ฆ์ ์ด ๋ฐ ํผ์ก์ ์ด๋ฅผ ์ํํ์ง ์์ ์๋๊ฐ ๋น ๋ฅด๋ฉฐ ๋คํธ์ํฌ ๋ถํ๊ฐ ์ ๋ค๋ ์ฅ์ ์ด ์์ง๋ง ๋ฐ์ดํฐ ์ ์ก์ ์ ๋ขฐ์ฑ์ด ๋ฎ๋ค. **์ฐ์์ฑ์ด ์ค์ํ ์ค์๊ฐ ์๋น์ค(์คํธ๋ฆฌ๋ฐ)**์ ์ข๋ค.

**UDP ํน์ง**

- ๋น์ฐ๊ฒฐํ ์๋น์ค๋ก ๋ฐ์ดํฐ๊ทธ๋จย ๋ฐฉ์์ ์ ๊ณตํ๋ค
- ์ ๋ณด๋ฅผ ์ฃผ๊ณ  ๋ฐ์ ๋ ์ ๋ณด๋ฅผ ๋ณด๋ด๊ฑฐ๋ ๋ฐ๋๋ค๋ ์ ํธ์ ์ฐจ๋ฅผ ๊ฑฐ์น์ง ์๋๋ค.
- UDP ํค๋์ CheckSum ํ๋๋ฅผ ํตํด ์ต์ํ์ ์ค๋ฅ๋ง ๊ฒ์ถํ๋ค.
- ์ ๋ขฐ์ฑ์ด ๋ฎ๋ค
- TCP๋ณด๋ค ์๋๊ฐ ๋น ๋ฅด๋ค


[https://www.youtube.com/watch?v=ikDVGYp5dhg](https://www.youtube.com/watch?v=ikDVGYp5dhg)

# ๐ฅ 3-Way Handshake์ 4-Way Handshake

3-Way Handshake ๋ TCP์ ์ ์,4 -Way Handshake๋ TCP์ ์ ์ ํด์  ๊ณผ์ ์ด๋ค.

- ***ํฌํธ(PORT) ์ํ ์ ๋ณด***
    - CLOSED: ํฌํธ๊ฐ ๋ซํ ์ํ
    - LISTEN: ํฌํธ๊ฐ ์ด๋ฆฐ ์ํ๋ก ์ฐ๊ฒฐ ์์ฒญ ๋๊ธฐ ์ค
    - SYN_RCV: SYNC ์์ฒญ์ ๋ฐ๊ณ  ์๋๋ฐฉ์ ์๋ต์ ๊ธฐ๋ค๋ฆฌ๋ ์ค
    - ESTABLISHED: ํฌํธ ์ฐ๊ฒฐ ์ํ
    
- ***ํ๋๊ทธ ์ ๋ณด***
    - TCP Header์๋ CONTROL BIT(ํ๋๊ทธ ๋นํธ, 6bit)๊ฐ ์กด์ฌํ๋ฉฐ, ๊ฐ๊ฐ์ bit๋ "URG-ACK-PSH-RST-SYN-FIN"์ ์๋ฏธ๋ฅผ ๊ฐ์ง๋ค.
        - ์ฆ, ํด๋น ์์น์ bit๊ฐ 1์ด๋ฉด ํด๋น ํจํท์ด ์ด๋ ํ ๋ด์ฉ์ ๋ด๊ณ  ์๋ ํจํท์ธ์ง๋ฅผ ๋ํ๋ธ๋ค.
    - SYN(Synchronize Sequence Number) / 000010
        - ์ฐ๊ฒฐ ์ค์ . Sequence Number๋ฅผ ๋๋ค์ผ๋ก ์ค์ ํ์ฌ ์ธ์์ ์ฐ๊ฒฐํ๋ ๋ฐ ์ฌ์ฉํ๋ฉฐ, ์ด๊ธฐ์ Sequence Number๋ฅผ ์ ์กํ๋ค.
    - ACK(Acknowledgement) / 010000
        - ์๋ต ํ์ธ. ํจํท์ ๋ฐ์๋ค๋ ๊ฒ์ ์๋ฏธํ๋ค.
        - Acknowledgement Number ํ๋๊ฐ ์ ํจํ์ง๋ฅผ ๋ํ๋ธ๋ค.
        - ์๋จ ํ๋ก์ธ์ค๊ฐ ์ฌ์ง ์๊ณ  ๋ฐ์ดํฐ๋ฅผ ์ ์กํ๋ค๊ณ  ๊ฐ์ ํ๋ฉด ์ต์ด ์ฐ๊ฒฐ ์ค์  ๊ณผ์ ์์ ์ ์ก๋๋ ์ฒซ ๋ฒ์งธ ์ธ๊ทธ๋จผํธ๋ฅผ ์ ์ธํ ๋ชจ๋  ์ธ๊ทธ๋จผํธ์ ACK ๋นํธ๋ 1๋ก ์ง์ ๋๋ค๊ณ  ์๊ฐํ  ์ ์๋ค.
    - FIN(Finish) / 000001
        - ์ฐ๊ฒฐ ํด์ . ์ธ์ ์ฐ๊ฒฐ์ ์ข๋ฃ์ํฌ ๋ ์ฌ์ฉ๋๋ฉฐ, ๋ ์ด์ ์ ์กํ  ๋ฐ์ดํฐ๊ฐ ์์์ ์๋ฏธํ๋ค.
        
    
### โTCP ๊ด๋ จ ์ง๋ฌธ

**Q. ์ด๊ธฐ Sequence Number์ธ ISN์ 0๋ถํฐ ์์ํ์ง ์๊ณ  ๋์๋ฅผ ์์ฑํด์ ์ค์ ํ๋ ์ด์ ?**A. Connection์ ๋งบ์ ๋ ์ฌ์ฉํ๋ ํฌํธ(Port)๋ ์ ํ ๋ฒ์ ๋ด์์ ์ฌ์ฉํ๊ณ  ์๊ฐ์ด ์ง๋จ์ ๋ฐ๋ผ ์ฌ์ฌ์ฉ๋๋ค. ๋ฐ๋ผ์ ๋ ํต์  ํธ์คํธ๊ฐ ๊ณผ๊ฑฐ์ ์ฌ์ฉ๋ ํฌํธ ๋ฒํธ ์์ ์ฌ์ฉํ๋ ๊ฐ๋ฅ์ฑ์ด ์กด์ฌํ๋ค. ์๋ฒ ์ธก์์๋ ํจํท์ SYN์ ๋ณด๊ณ  ํจํท์ ๊ตฌ๋ถํ๊ฒ ๋๋๋ฐ ๋์๊ฐ ์๋ ์์ฒ์ ์ธ Number๊ฐ ์ ์ก๋๋ค๋ฉด ์ด์ ์ Connection์ผ๋ก๋ถํฐ ์ค๋ ํจํท์ผ๋ก ์ธ์ํ  ์ ์๋ค. ์ด๋ฐ ๋ฌธ์ ๊ฐ ๋ฐ์ํ  ๊ฐ๋ฅ์ฑ์ ์ค์ด๊ธฐ ์ํด์ ๋์๋ก ISN์ ์ค์ ํ๋ค.

[https://velog.io/@averycode/๋คํธ์ํฌ-TCPUDP์-3-Way-Handshake4-Way-Handshake](https://velog.io/@averycode/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-TCPUDP%EC%99%80-3-Way-Handshake4-Way-Handshake)


# HTTP ์์ฒญ ๋ฐฉ์ - GET, POST

# **HTTP**

HTTP๋ ์น์์์ ํด๋ผ์ด์ธํธ์ ์๋ฒ ๊ฐ์ ์์ฒญ/์๋ต์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ์ฃผ๊ณ  ๋ฐ์ ์ ์๋ ํ๋กํ ์ฝ์๋๋ค. ํด๋ผ์ด์ธํธ๊ฐ HTTP ํ๋กํ ์ฝ์ ํตํด ์๋ฒ์๊ฒ ์์ฒญ์ ๋ณด๋ด๋ฉด ์๋ฒ๋ ์์ฒญ์ ๋ง๋ ์๋ต์ ํด๋ผ์ด์ธํธ์๊ฒ ์ ์กํฉ๋๋ค. ์ด ๋, HTTP ์์ฒญ์ ํฌํจ๋๋ HTTP ๋ฉ์๋๋ ์๋ฒ๊ฐ ์์ฒญ์ ์ํํ๊ธฐ ์ํด ํด์ผํ  ํ๋์ ํ์ํ๋ ์ฉ๋๋ก ์ฌ์ฉํฉ๋๋ค. ์ด HTTP ๋ฉ์๋ ์ค GET๊ณผ POST์ ํน์ง๊ณผ ์ฐจ์ด์ ์ ์์๋ณด๊ฒ ์ต๋๋ค.

## **GET**

GET์ย **์๋ฒ๋ก๋ถํฐ ์ ๋ณด๋ฅผ ์กฐํํ๊ธฐ ์ํด**ย ์ค๊ณ๋ ๋ฉ์๋์๋๋ค. GET์ ์์ฒญ์ ์ ์กํ  ๋ ํ์ํ ๋ฐ์ดํฐ๋ฅผ Body์ ๋ด์ง ์๊ณ , ์ฟผ๋ฆฌ์คํธ๋ง์ ํตํด ์ ์กํฉ๋๋ค. URL์ ๋์ย `?`์ ํจ๊ป ์ด๋ฆ๊ณผ ๊ฐ์ผ๋ก ์์ ์ด๋ฃจ๋ ์์ฒญ ํ๋ผ๋ฏธํฐ๋ฅผ ์ฟผ๋ฆฌ์คํธ๋ง์ด๋ผ๊ณ  ๋ถ๋ฆ๋๋ค. ๋ง์ฝ, ์์ฒญ ํ๋ผ๋ฏธํฐ๊ฐ ์ฌ๋ฌ ๊ฐ์ด๋ฉดย `&`๋ก ์ฐ๊ฒฐํฉ๋๋ค. ์ฟผ๋ฆฌ์คํธ๋ง์ ์ฌ์ฉํ๊ฒ ๋๋ฉด URL์ ์กฐํ ์กฐ๊ฑด์ ํ์ํ๊ธฐ ๋๋ฌธ์ ํน์  ํ์ด์ง๋ฅผ ๋งํฌํ๊ฑฐ๋ ๋ถ๋งํฌํ  ์ ์์ต๋๋ค.

๊ทธ๋ฆฌ๊ณ  GET์ ๋ถํ์ํ ์์ฒญ์ ์ ํํ๊ธฐ ์ํด ์์ฒญ์ด ์บ์๋  ์ ์์ต๋๋ค. js, css, ์ด๋ฏธ์ง ๊ฐ์ ์ ์  ์ปจํ์ธ ๋ ๋ฐ์ดํฐ์์ด ํฌ๊ณ , ๋ณ๊ฒฝ๋  ์ผ์ด ์ ์ด์ ๋ฐ๋ณตํด์ ๋์ผํ ์์ฒญ์ ๋ณด๋ผ ํ์๊ฐ ์์ต๋๋ค. ์ ์  ์ปจํ์ธ ๋ฅผ ์์ฒญํ๊ณ  ๋๋ฉด ๋ธ๋ผ์ฐ์ ์์๋ ์์ฒญ์ ์บ์ํด๋๊ณ , ๋์ผํ ์์ฒญ์ด ๋ฐ์ํ  ๋ ์๋ฒ๋ก ์์ฒญ์ ๋ณด๋ด์ง ์๊ณ  ์บ์๋ ๋ฐ์ดํฐ๋ฅผ ์ฌ์ฉํฉ๋๋ค. ๊ทธ๋์ ํ๋ก ํธ์๋ ๊ฐ๋ฐ์ ํ๋ค๋ณด๋ฉด ์ ์  ์ปจํ์ธ ๊ฐ ์บ์๋ผ ์ปจํ์ธ ๋ฅผ ๋ณ๊ฒฝํด๋ ๋ด์ฉ์ด ๋ฐ๋์ง ์๋ ๊ฒฝ์ฐ๊ฐ ์ข์ข ๋ฐ์ํฉ๋๋ค. ์ด ๋๋ ๋ธ๋ผ์ฐ์ ์ ์บ์๋ฅผ ์ง์์ฃผ๋ฉด ๋ค์ ์ปจํ์ธ ๋ฅผ ์กฐํํ๊ธฐ ์ํด ์๋ฒ๋ก ์์ฒญ์ ๋ณด๋ด๊ฒ ๋ฉ๋๋ค.

## **POST**

POST๋ย **๋ฆฌ์์ค๋ฅผ ์์ฑ/๋ณ๊ฒฝํ๊ธฐ ์ํด ์ค๊ณ**๋์๊ธฐ ๋๋ฌธ์ GET๊ณผ ๋ฌ๋ฆฌ ์ ์กํด์ผ๋  ๋ฐ์ดํฐ๋ฅผ HTTP ๋ฉ์ธ์ง์ Body์ ๋ด์์ ์ ์กํฉ๋๋ค. HTTP ๋ฉ์ธ์ง์ Body๋ ๊ธธ์ด์ ์ ํ์์ด ๋ฐ์ดํฐ๋ฅผ ์ ์กํ  ์ ์์ต๋๋ค. ๊ทธ๋์ POST ์์ฒญ์ GET๊ณผ ๋ฌ๋ฆฌ **๋์ฉ๋ ๋ฐ์ดํฐ๋ฅผ ์ ์ก**ํ  ์ ์์ต๋๋ค. ์ด์ฒ๋ผ POST๋ ๋ฐ์ดํฐ๊ฐ Body๋ก ์ ์ก๋๊ณ  ๋ด์ฉ์ด ๋์ ๋ณด์ด์ง ์์ GET๋ณด๋ค ๋ณด์์ ์ธ ๋ฉด์์ ์์ ํ๋ค๊ณ  ์๊ฐํ  ์ ์์ง๋ง, POST ์์ฒญ๋ ํฌ๋กฌ ๊ฐ๋ฐ์ ๋๊ตฌ, Fiddler์ ๊ฐ์ ํด๋ก ์์ฒญ ๋ด์ฉ์ ํ์ธํ  ์ ์๊ธฐ ๋๋ฌธ์ ๋ฏผ๊ฐํ ๋ฐ์ดํฐ์ ๊ฒฝ์ฐ์๋ ๋ฐ๋์ ์ํธํํด ์ ์กํด์ผ ํฉ๋๋ค.

๊ทธ๋ฆฌ๊ณ  POST๋ก ์์ฒญ์ ๋ณด๋ผ ๋๋ ์์ฒญ ํค๋์ Content-Type์ ์์ฒญ ๋ฐ์ดํฐ์ ํ์์ ํ์ํด์ผ ํฉ๋๋ค. ๋ฐ์ดํฐ ํ์์ ํ์ํ์ง ์์ผ๋ฉด ์๋ฒ๋ ๋ด์ฉ์ด๋ URL์ ํฌํจ๋ ๋ฆฌ์์ค์ ํ์ฅ์๋ช ๋ฑ์ผ๋ก ๋ฐ์ดํฐ ํ์์ ์ ์ถํฉ๋๋ค. ๋ง์ฝ, ์ ์ ์๋ ๊ฒฝ์ฐ์๋ย `application/octet-stream`๋ก ์์ฒญ์ ์ฒ๋ฆฌํฉ๋๋ค.

## **GET๊ณผ POST์ ์ฐจ์ด**

GET์ Idempotent, POST๋ Non-idempotentํ๊ฒ ์ค๊ณ๋์์ต๋๋ค.Idempotent(๋ฉฑ๋ฑ)์ ์ํ์  ๊ฐ๋์ผ๋ก ๋ค์๊ณผ ๊ฐ์ด ๋ํ๋ผ ์ ์์ต๋๋ค.

> ์ํ์ด๋ ์ ์ฐํ์์ ์ฐ์ฐ์ ํ ์ฑ์ง์ ๋ํ๋ด๋ ๊ฒ์ผ๋ก, ์ฐ์ฐ์ ์ฌ๋ฌ ๋ฒ ์ ์ฉํ๋๋ผ๋ ๊ฒฐ๊ณผ๊ฐ ๋ฌ๋ผ์ง์ง ์๋ ์ฑ์ง
> 

์ฆ, ๋ฉฑ๋ฑ์ด๋ผ๋ ๊ฒ์ย **๋์ผํ ์ฐ์ฐ์ ์ฌ๋ฌ ๋ฒ ์ํํ๋๋ผ๋ ๋์ผํ ๊ฒฐ๊ณผ**๊ฐ ๋ํ๋์ผ ํฉ๋๋ค.์ฌ๊ธฐ์ GET์ด Idempotentํ๋๋ก ์ค๊ณ๋์๋ค๋ ๊ฒ์ GET์ผ๋กย **์๋ฒ์๊ฒ ๋์ผํ ์์ฒญ์ ์ฌ๋ฌ ๋ฒ ์ ์กํ๋๋ผ๋ ๋์ผํ ์๋ต์ด ๋์์์ผ ํ๋ค๋ ๊ฒ**์ ์๋ฏธํฉ๋๋ค. ์ด์ ๋ฐ๋ผ GET์ ์ค๊ณ์์น์ ๋ฐ๋ผ ์๋ฒ์ ๋ฐ์ดํฐ๋ ์ํ๋ฅผ ๋ณ๊ฒฝ์ํค์ง ์์์ผ Idempotentํ๊ธฐ ๋๋ฌธ์ย **์ฃผ๋ก ์กฐํ๋ฅผ ํ  ๋์ ์ฌ์ฉ**ํด์ผํฉ๋๋ค. ์๋ฅผ ๋ค์ด, ๋ธ๋ผ์ฐ์ ์์ ์นํ์ด์ง๋ฅผ ์ด์ด๋ณด๊ฑฐ๋ ๊ฒ์๊ธ์ ์ฝ๋ ๋ฑ ์กฐํ๋ฅผ ํ๋ ํ์๋ GET์ผ๋ก ์์ฒญํ๊ฒ ๋ฉ๋๋ค.

๋ฐ๋๋ก POST๋ Non-idempotentํ๊ธฐ ๋๋ฌธ์ย **์๋ฒ์๊ฒ ๋์ผํ ์์ฒญ์ ์ฌ๋ฌ ๋ฒ ์ ์กํด๋ ์๋ต์ ํญ์ ๋ค๋ฅผ ์ ์์ต๋๋ค**. ์ด์ ๋ฐ๋ผ POST๋ ์๋ฒ์ ์ํ๋ ๋ฐ์ดํฐ๋ฅผ ๋ณ๊ฒฝ์ํฌ ๋ ์ฌ์ฉ๋ฉ๋๋ค. ๊ฒ์๊ธ์ ์ฐ๋ฉด ์๋ฒ์ ๊ฒ์๊ธ์ด ์ ์ฅ์ด ๋๊ณ , ๊ฒ์๊ธ์ ์ญ์ ํ๋ฉด ํด๋น ๋ฐ์ดํฐ๊ฐ ์์ด์ง๋ ๋ฑ POST๋ก ์์ฒญ์ ํ๊ฒ ๋๋ฉด ์๋ฒ์ ๋ฌด์ธ๊ฐ๋ ๋ณ๊ฒฝ๋๋๋ก ์ฌ์ฉ๋ฉ๋๋ค. ์ด์ฒ๋ผ POST๋ ์์ฑ, ์์ , ์ญ์ ์ ์ฌ์ฉํ  ์ ์์ง๋ง, ์์ฑ์๋ POST, ์์ ์ PUT ๋๋ PATCH, ์ญ์ ๋ DELETE๊ฐ ๋ ์ฉ๋์ ๋ง๋ ๋ฉ์๋๋ผ๊ณ  ํ  ์ ์์ต๋๋ค.


GET๊ณผ POST๋ ์ด์ฒ๋ผ ํฐ ์ฐจ์ด๊ฐ ์๊ธฐ ๋๋ฌธ์ ์ค๊ณ์์น์ ๋ฐ๋ผ ์ ์ ํ ์ฉ๋๋ก ์ฌ์ฉํด์ผํฉ๋๋ค.



# HTTP ์ HTTPS

### **[ย HTTP(Hyper Text Transfer Protocol)๋?ย ]**

HTTP(Hyper Text Transfer Protocol)๋ย ์๋ฒ/ํด๋ผ์ด์ธํธ ๋ชจ๋ธ์ ๋ฐ๋ผ ๋ฐ์ดํฐ๋ฅผ ์ฃผ๊ณ  ๋ฐ๊ธฐ ์ํ ํ๋กํ ์ฝ์ด๋ค.

์ฆ, HTTP๋ ์ธํฐ๋ท์์ ํ์ดํผํ์คํธ๋ฅผ ๊ตํํ๊ธฐ ์ํ ํต์  ๊ท์ฝ์ผ๋ก, 80๋ฒ ํฌํธ๋ฅผ ์ฌ์ฉํ๊ณ  ์๋ค. ๋ฐ๋ผ์ HTTP ์๋ฒ๊ฐ 80๋ฒ ํฌํธ์์ ์์ฒญ์ ๊ธฐ๋ค๋ฆฌ๊ณ  ์์ผ๋ฉฐ, ํด๋ผ์ด์ธํธ๋ 80๋ฒ ํฌํธ๋ก ์์ฒญ์ ๋ณด๋ด๊ฒ ๋๋ค.

HTTP๋ 1989๋ ํ ๋ฒ๋์ค ๋ฆฌ(Tim Berners Lee)์ ์ํด ์ฒ์ ์ค๊ณ๋์์ผ๋ฉฐ, WWW(World-Wide-Web) ๊ธฐ๋ฐ์์ ์ธ๊ณ์ ์ธ ์ ๋ณด๋ฅผ ๊ณต์ ํ๋๋ฐ ํฐ ์ญํ ์ ํ์๋ค.

### **[ย HTTP์ ๊ตฌ์กฐย ]**

HTTP๋ ์ ํ๋ฆฌ์ผ์ด์ ๋ ๋ฒจ์ ํ๋กํ ์ฝ๋ก TCP/IP ์์์ ์๋ํ๋ค.ย HTTP๋ ์ํ๋ฅผ ๊ฐ์ง๊ณ  ์์ง ์๋ Stateless ํ๋กํ ์ฝ์ด๋ฉฐ Method, Path, Version, Headers, Body ๋ฑ์ผ๋ก ๊ตฌ์ฑ๋๋ค.

### **[ย HTTPS(Hyper Text Transfer Protocol Secure)๋?ย ]**

HyperText Transfer Protocol over Secure Socket Layer, HTTP over TLS, HTTP over SSL, HTTP Secure ๋ฑ์ผ๋ก ๋ถ๋ฆฌ๋ HTTPS๋ย HTTP์ ๋ฐ์ดํฐ ์ํธํ๊ฐ ์ถ๊ฐ๋ ํ๋กํ ์ฝ์ด๋ค. HTTPS๋ HTTP์ ๋ค๋ฅด๊ฒย 443๋ฒ ํฌํธ๋ฅผ ์ฌ์ฉํ๋ฉฐ, ๋คํธ์ํฌ ์์์ ์ค๊ฐ์ ์ 3์๊ฐ ์ ๋ณด๋ฅผ ๋ณผ ์ ์๋๋ก ์ํธํ๋ฅผ ์ง์ํ๊ณ  ์๋ค.

### **[ย ๋์นญํค ์ํธํ์ ๋น๋์นญํค ์ํธํย ]**

HTTPS๋ ๋์นญํค ์ํธํ ๋ฐฉ์๊ณผ ๋น๋์นญํค ์ํธํ ๋ฐฉ์์ ๋ชจ๋ ์ฌ์ฉํ๊ณ  ์๋ค. ๊ฐ๊ฐ์ ์ํธํ ๋ฐฉ์์ ๋ค์๊ณผ ๊ฐ๋ค.

- ๋์นญํค ์ํธํ
    - ํด๋ผ์ด์ธํธ์ ์๋ฒ๊ฐ ๋์ผํ ํค๋ฅผ ์ฌ์ฉํด ์ํธํ/๋ณตํธํ๋ฅผ ์งํํจ
    - ํค๊ฐ ๋ธ์ถ๋๋ฉด ๋งค์ฐ ์ํํ์ง๋ง ์ฐ์ฐ ์๋๊ฐ ๋น ๋ฆ
- ๋น๋์นญํค ์ํธํ
    - 1๊ฐ์ ์์ผ๋ก ๊ตฌ์ฑ๋ ๊ณต๊ฐํค์ ๊ฐ์ธํค๋ฅผ ์ํธํ/๋ณตํธํ ํ๋๋ฐ ์ฌ์ฉํจ
    - ํค๊ฐ ๋ธ์ถ๋์ด๋ ๋น๊ต์  ์์ ํ์ง๋ง ์ฐ์ฐ ์๋๊ฐ ๋๋ฆผ

๋์นญํค๋ ๋น๊ต์  ์ฌ์ด ๊ฐ๋์ด๋ฏ๋ก, ๋น๋์นญํค ์ํธํ์ ๋ํด ์กฐ๊ธ ์์ธํ ์ดํด๋ณด๋๋ก ํ์.

๋น๋์นญํค ์ํธํ๋ ๊ณต๊ฐํค/๊ฐ์ธํค ์ํธํ ๋ฐฉ์์ ์ด์ฉํด ๋ฐ์ดํฐ๋ฅผ ์ํธํํ๊ณ  ์๋ค. ๊ณต๊ฐํค์ ๊ฐ์ธํค๋ ์๋ก๋ฅผ ์ํ 1์์ ํค์ด๋ค.

- ๊ณต๊ฐํค: ๋ชจ๋์๊ฒ ๊ณต๊ฐ๊ฐ๋ฅํ ํค
- ๊ฐ์ธํค: ๋๋ง ๊ฐ์ง๊ณ  ์๊ณ  ์์ด์ผ ํ๋ ํค

์ํธํ๋ฅผ ๊ณต๊ฐํค๋ก ํ๋๋ ๊ฐ์ธํค๋ก ํ๋๋์ ๋ฐ๋ผ ์ป๋ ํจ๊ณผ๊ฐ ๋ค๋ฅธ๋ฐ, ๊ณต๊ฐํค์ ๊ฐ์ธํค๋ก ์ํธํํ๋ฉด ๊ฐ๊ฐ ๋ค์๊ณผ ๊ฐ์ ํจ๊ณผ๋ฅผ ์ป์ ์ ์๋ค.

- ๊ณต๊ฐํค ์ํธํ: ๊ณต๊ฐํค๋ก ์ํธํ๋ฅผ ํ๋ฉด ๊ฐ์ธํค๋ก๋ง ๋ณตํธํํ  ์ ์๋ค. -> ๊ฐ์ธํค๋ ๋๋ง ๊ฐ์ง๊ณ  ์์ผ๋ฏ๋ก, ๋๋ง ๋ณผ ์ ์๋ค.
- ๊ฐ์ธํค ์ํธํ: ๊ฐ์ธํค๋ก ์ํธํํ๋ฉด ๊ณต๊ฐํค๋ก๋ง ๋ณตํธํํ  ์ ์๋ค. -> ๊ณต๊ฐํค๋ ๋ชจ๋์๊ฒ ๊ณต๊ฐ๋์ด ์์ผ๋ฏ๋ก, ๋ด๊ฐ ์ธ์ฆํ ์ ๋ณด์์ ์๋ ค ์ ๋ขฐ์ฑ์ ๋ณด์ฅํ  ์ ์๋ค.
