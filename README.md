11/22 회의

Q/A
1. 클러스터링을 선택하신 것은 광고등급으로 클러스터링 하기 위해서인가요?
예)광고회사의 역사별 광고등급(5,6,7,8) https://m.blog.naver.com/comma_ame/221250935964

-> 위의 역사별 광고등급은 이용객 수 총합에만 의존하는 것으로 보임
그러나 본 프로젝트에선 승객의 연령대 및 성별 "분포"에 초점을 둠

2. 모델이 잘 학습되었는지는 어떻게 테스트 할 수 있을까요?

-> 비지도학습이라서 테스트가 무의미한 듯??

3. K는 여러 번 클러스터링 해보면서 정하면 될까요? -> Yes

4. 제가 데이터를 보고도 잘 이해하지 못해서, 예시로 질문드립니다ㅠㅠ 예) 클러스터링을 할 떄, "강남역/20대/남성/10시" , "서울역/40대/여성/15시" 이렇게 두 오브젝트 사이 거리는 어떤 식으로 구하나요?

-> 오브젝트는 각 역들, 변수는 각 역별로 32개
연령대: 20대/30대/4-50대/6-70대, 성별: 남/여, 시간대: 출근(5-10)/낮(10-16)/퇴근(16-20)/밤(20-25)

5. 지하철 광고가 호선별, 종류별로 많은 회사들에게 나누어 맡겨져 있는 것 같은데, 우리가 이 회사 입장에서 효율을 높이려 하는 것인가요? 아니면 광고주로서 어디에 얼만큼 광고료 투자할지 결정하는 것인가요?

-> 처음에는 광고주 입장으로 접근하려 했으나, 결국 광고회사가 시간대별로 광고를 다르게 진행하지 않으면 무의미.
그러므로 광고회사 입장에서 전체적인 광고 효과를 증진하는 것을 목표로 삼기로.

6. 광고 형식과 종류가 다양해서 타겟마다 광고효과가 조금씩 다를 것 같은데, 어떤 광고를 메인으로 생각하면 좋을까요? 예)전동차-음성/문자, 역내-승강장안전문/음성/포스터/기둥조명 등등

-> 좀 더 고려해보면 좋을 듯.
같은 이유로 승차객과 하차객의 비중을 다르게 두어야 할 것 같다는 생각을 함.

7. 데이터 특성상 각 역이 어느 구에 속하는지 찾아 연결해주면 될 것 같은데 맞나요? -> Yes
_____

사실 각 역마다 광고를 다 따로 진행해도 됨. 이럴 경우 클러스터링이고 뭐고 불필요함.
그러나 데이터마이닝 기법을 하나 적용해야 하므로, 제일 적합해 보이는 클러스터링을 선택했음.
역들을 묶어서 관리하면 관리자 혹은 광고 의뢰자의 편의성이 높아진다는 것 등을 클러스터링 선택 이유로 삼을 수 있음.

-> 클러스터링 기법으로 하는 것 확정
_____

중간발표 할 일: 전처리, 시각화, Baseline 모델링
_____

역할분담
- 유나: 역과 구 매칭(1-4호선은 서울시 제공 데이터로, 5-9호선 및 분당선 등등은 수작업..)
http://data.seoul.go.kr/dataList/OA-12035/A/1/datasetView.do;jsessionid=5CCF18226C123C8289086F07BA82179D.new_portal-svr-11
- 민재: 역별로 32개 변수 계산하기
- 한결: 클러스터링 모델링
_____

기타
- 노선별로 묶는건 시각화 등에 필요할수도. 필요하면 하는걸로.
- 유동인구 데이터를 가공하는 것 필요? -> 그대로 사용하는 걸로.
- 연령대별 skt 가입률 고려 -> 정 데이터 없다면 그냥 가입률 동일하다고 가정해도 무방할 듯.
- 시간대를 네 개에서 더 세분화 -> 변수 개수가 너무 많아지는 것 같아 일단 네 개로 나눴는데, 결과가 이상하거나 하면 변경해볼만 함.