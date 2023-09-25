---
title: "구글 스프레드시트, 업비트, 텔레그램 API"
date: 2023-02-20 14:37:02 +0900
categories: [Developing, Python]
tags: [upbitAPI, telegramAPI]     # TAG names should always be lowercase

author: rouxist

---
&nbsp;&nbsp; 자산 내역을 구글 스프레드시트에 정리해둔 후, 매일 주기적으로 자산 내역을 핸드폰으로 간편히 확인하면서 변동 추이를 보고싶어 파이썬과 텔레그램 봇으로 구현했다.
<br/><br/>

## 할 일들
---  
- [ ] 은행 API로 입출금 내역 자동 업데이트
- [x] 업비트 API로 암호화폐 가격들과 보유 내역을 주기적으로 업데이트
- [x] 정해진 시각에 메신저(텔레그램)으로 자산 총액과 내역 보내기
- [x] 서버에 올리기
<br/><br/>

## 업비트 API  
---  
[https://www.upbit.com/service_center/open_api_guide](https://www.upbit.com/service_center/open_api_guide)  
&nbsp;&nbsp;업비트를 사용하고 있으니 암호화폐 가격들은 업비트 API를 사용해서 업데이트하고 있다. pyupbit 모듈로 내가 보유하고 있는 암호화폐들의 수량, 시장 가격 등을 불러온다.  
![11-24-1](/assets/post-img/developing/ram/upbit_api_ip.png){: width="600" height="150"}  
허용IP만 잘 관리해주면 별 여러움은 없었는데, ip들을 각각 넣고 빼는 게 아니라 수정할 때마다 전체를 csv처럼 콤마로 구분해서 넣는 건 조금 번거롭다.
<br/><br/>

## 텔레그램 API  
---  
&nbsp;&nbsp;텔레그램 봇을 만들고 telegram_send를 사용 중. 처음 쓸 때 $ telegram-send \-\-configure 로 연결할 봇의 토큰을 입력해서 연결해주면 바로 사용이 가능하다. [참고](https://medium.com/@robertbracco1/how-to-write-a-telegram-bot-to-send-messages-with-python-bcdf45d0a580)  

![11-24-1](/assets/post-img/developing/ram/telegram_send_version_error.png){: width="600" height="150"}  
다만 OCI로 옮길 때 문제가 있었는데, 그냥 버전을 낮춰서 해결했다. [참고](https://github.com/rahiel/telegram-send/issues/115)  
<br/><br/>

## OCI에 업로드  
---  
&nbsp;&nbsp;처음에는 [PythonAnywhere](https://www.pythonanywhere.com/)를 사용했는데, 과금을 하지 않는 이상 시간이 지나면 꺼져버리길래 24시간 내내 돌리려면 다른 서버에 업로드할 필요가 있었다. 일단 지금 사용 중인 OCI 서버에서 돌리고 있다.  
<br/><br/>

## 결과  
---  
![message_example](/assets/post-img/developing/ram/message_example.png){: width="200" height="150"}  
2023.02.20 현황. 이렇게 생긴 메세지가 3시간마다 오고 있다.
<br/><br/>

## 문제점  
---  
* Google Finance를 사용해 비트코인, 이더리움의 가격은 자동으로 불러올 수 있는데 다른 암호화폐들의 가격은 불러오지 못하는 것들이 많았다. (일단 솔라나도 안됐던..) 지금 보니 [유저가 만든 API를 사용해서](https://www.reddit.com/r/solana/comments/ppovly/sol_price_in_google_sheets/) 해결할 수도 있을 것 같다.
* 며칠간 갑자기 아래 사진과 같이 Google Finance에서 삼성전자의 주가를 불러오지 못하는 문제가 있었다. (2023.05.14에 발견) 시간이 지나니 다시 정상화되었지만 아직까지 원인은 미상.  
![05-14-1](/assets/post-img/developing/ram/problem_samsung_unavailable.png){: width="300" height="150"}  