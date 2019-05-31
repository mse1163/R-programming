###데이터 분석
1. 패키지 설치 및 로드
- foreign : SPSS, SAS, STATA등 다양한 통계분석 소프트웨어 파일 불러올수있음
-library(foreign)             -> SPSS 파일 불러오기 
-library(dplyr)               -> 전처리 
-library(ggplot2)             -> 시각화 
-library(readxl)              -> 엑셀 파일 불러오기

2. 데이터 불러오기
- read.spss(file="파일경로", to.data.frame=T)
- to.data.frame=T는 SPSS파일을 데이터프레임 형태로 기능을 함.

3. 변수명 바꾸기
- welfare <- rename(welfare, sex=h10_g3, ......, )

4. 데이터 분석 절차
	1) 변수 검토 및 전처리
		- 변수의 특성 파악하고 이상치 정제한 다음 파생변수 만듬
	2) 변수 간 관계분석
		- 변수 간 관계를 파익하는 분석 
		- 데이터를 요약한 표를 만든 후 분석 결과를 쉽게 이해할 수 있는 그래프 만듬
5. 변수 검토하기
	- 범주 변수 :  table() 각 범주의 빈도 확인하여 특징 파악가능 -> 성별
	- 연속 변수 : summary()로 요약통계량을 확인해야 특징 파악할수잇다. -> 월급
* left_join(, , id="공통변수") -> 테이블에 결합
* coord_filp() : 막대를 오른쪽으로 90도 회전
* 반올림이 적용되지 않으면?
-dplyr은 출력 결과를 데이터 프레임의 업그레이드 버전인 tibble 형태로 만들어 줍니다. tibble은 콘 솔 창에 출력할 소수점 자릿수를 가독성이 높은 위치까지 자동으로 결정하기 때문에 round()를 이용해 반올림하더라도 다른 값이 출력될 수 있습니다. dplyr 구문 뒤에 %>% as.data.frame()을 추가하면 round()가 적용된 값을 확인할 수 있습니다.
* count() : 집단별 빈도를 구하는 함수
* fill= 변수명 : 막대 색깔을 다르게 표현
* position = "dodge" : 막대 분리
