# mrchypark/N2H4 로 이전합니다.
패키지 식으로 변경한 N2H4 패키지로 이전합니다.<br>
https://github.com/mrchypark/N2H4

# 사용법
getwd()로 확인한 작업공간에 getnavernews.R파일을 저장합니다.<br>
R 콘솔에 source("getnavernews.R",encoding="UTF-8")을 입력하면 시작합니다.<br>
처음에 크롤링을 시작할 날짜와 마지막 날짜를 물어보면 yyy-mm-dd 양식으로 입력합니다.<br>
8개 카테고리 모두 긁어올 것인지 물어봅니다. 1을 입력하면 모두 이고 나머지는 각 카테고리를 다시 질문합니다.<br>
코드 관련 내용은 맨 하단에 있습니다.<br>
*최종 작업하신 결과물에 https://github.com/mrchypark/naverNewsParser/ 가 사용 출처임을 밝혀주시면 정말 감사하겠습니다.<br>
*최종 결과물도 보내주시면 특히 보람찰 것 같습니다.(문의도 환영) mrchypark@gmail.com<br>
<br>
# v0.33<br>
IT/과학 카테고리를 IT와 과학 카테고리로 분리하였습니다..<br>
Fast mode의 딜레이시간을 0으로 변경하였습니다.<br>
<br>
# v0.32<br>
날씨 링크중에 EUC-KR 인코딩을 사용하는 페이지를 대응했습니다.<br>
날짜와 시간을 파악하는 정규식을 개선했습니다.<br>
<>로 둘러쌓인 제목이 제거되는 문제가 파악되어 개선이 필요합니다.<br>
<br>
# v0.31<br>
링크 에러를 우회했습니다.<br>
<br>
# v0.3<br>
날씨 부분을 추가하였습니다.<br>
크롤링 속도를 조절할 수 있습니다. fast mode(0.01초 딜레이)와 safe mode(0.5초 딜레이)가 있습니다. <br>
<br>
# v0.21<br>
TV연애 부분 에러를 수정했습니다.<br>
<br>
# v0.2<br>
8번째 카테고리인 TV연애를 추가했습니다. TV연애는 2014년 1월 1일부터 네이버가 시작했습니다.<br>
중간에 에러가 나면 그냥 멈추던 문제를 개선해서 5번 재 시도 해보고 안되면 다음 링크로 넘기게 우회처리했습니다.<br>
코드가 끝나면 errorURL 변수에 수집이 안된 url이 저장됩니다.<br>
<br>
# v0.1<br>
여전히 매우 느리지만 얼마나 진행중인지 표시하도록 했습니다.<br>
중간에 아무 문제 없이 멈추는 경우가 있는데 그 에러가 발생하면 조금 기다렸다가 계속 진행할 수 있게 고칠 계획입니다.<br>
중간에 멈췄을 때 tt 변수를 확인해서 url 모양에 이상이 있을시 mrchypark@gmail.com로 메일을 보내주세요.<br>
<br>
# v0.001<br>
readLinse 명령어로 html을 무식하게 긁어옵니다.<br>
grep로 필요한 위치를 찾고(같은 줄을 찾아야 해서 네이버 뉴스에 맞는 마구잡이 규칙이 난무합니다.)<br>
gsub로 필요없는 글자를 버립니다.<br>
for 문과 while 문으로 단순 반복 시킵니다.<br>
<br>
긁어온 주소가 모두 같은 구조를 가지지 않아서 예외 조건을 계속 추가하는 중입니다.<br>
주소 긁는데만 2~3일 걸렸는데 내용 다 긁는데는 20배 쯤 걸릴꺼라고 생각하고 있습니다....<br>
<br>
# naverNewsParser
<br>
2012년부터 2014년까지 3개년 네이버에 게시된 뉴스를 불러옵니다.<br>
(참고로 그냥 실행시키시면 일주일도 더 걸릴껍니다.)<br>
<br>
1단계는 네이버에 직접 게시된 링크를 불러옵니다.<br>
7개 카테고리(정치, 경제, 사회, 생활/문화, 세계, IT/과학, 스포츠)의 뉴스를 불러옵니다.<br>
2단계는 링크를 불러서 6개 콜론(카테고리, 제목, 신문사, 게제시간, 수정시간, 내용)으로 정리해서 저장합니다.<br>
네이버의 블락을 피하기 위해 매 요청마다 0.5초의 딜레이를 주었습니다.<br>
0.5초보다 빠르게 설정하지 않는 것을 권장합니다. 이 방법이 막히면 우울할 꺼 같아요.<br>
본 코드는 R로 제작되었습니다.<br>
코드 효율 및 최적화는 고려하지 않았습니다.<br>
수정요청 대환영입니다.<br>
<br>
뉴스의 저작권은 상업목적으로는 불허(돈을 내야함)하며 연구의 목적을 위해 수집하였습니다.<br>
한국온라인신문협회(KONA) http://www.kona.or.kr/ (국민일보, 동아닷컴, 디지틀조선일보, 매경인터넷, 미디어칸, 세계닷컴,
전자신문인터넷, 조인스닷컴, 한겨레엔, 한경닷컴, 한국아이닷컴)의 뉴스는 ③ 영리를 목적으로 하지 아니하고 개인적으로 이용하는 경우 복제를 허가하고 있습니다.<br>
다른 신문사도 같은 저작권 정책을 따르는 것으로 간주하였습니다.<br>
하지만 데이터 자체를 계시하는 경우를 불법으로 간주하므로 수집하는 코드만을 공개합니다.<br>
감사합니다.<br>
<br>
This source code is to parse naver news in Korea.<br>
As you can see this code is by R.<br>
Naver news categories are 8(politics, economy, society, culture, world news, IT/science, sports, entertainment).<br>
Always welcome your participation.<br>



 
