# BUSAN CRIME

## 부산 관할구별 5대 범죄 시각화

출처 : 부산시 관서별 5대 범죄 발생 현황 https://www.data.go.kr/data/15036510/fileData.do#layer_data_infomation

- 데이터 전처리
  - 2018~2021년도 부산시 5대범죄 데이터를 통합
  - 컬럼명 통일 및 합계 열과 행 생성
  
- 데이터 시각화
  - 5대 범죄별 연도별 범죄건수 추이를 막대 그래프로 시각화
  - 데이터 정규화 처리 후 4개년 관서별 범죄 수를 막대 그래프로 시각화

## 장소별 시각화

## 시간 및 요일별 시각화

## 장소별 클러스터링

<범죄 빈도가 높은 장소 5가지 : 아파트, 숙박업소, 목욕탕, 유흥주점, 주차장>

  - 아파트 위치 정보 출처 : https://www.data.go.kr/data/15007226/fileData.do
  - 숙박업소 위치 정보 출처: https://www.data.go.kr/data/15025544/fileData.do
  - 목욕탕 위치 정보 출처: https://www.data.go.kr/data/15025545/fileData.do 
  - 유흥주점 위치 정보 출처: https://data.busan.go.kr/dataSet/detail.nm?publicdatapk=15025547&contentId=10
  - 주차장 위치 정보 출처: https://data.busan.go.kr/dataSet/detail.nm?publicdatapk=15004683&contentId=10

- 범죄가 가장 많이 일어나는 장소를 선정해 부산진구의 해당 장소 데이터를 수집

- 데이터 전처리
  - null값 해결 및 컬럼명 통일
  - 주소 값 통일

- 데이터를 지도로 시각화
  - import googlemaps : 구글맵을 이용해 데이터 프레임의 주소를 위도, 경도 값 추출
  - 추출된 위도,경도 값을 지도에 표시
  - 5개 구역의 값을 색을 다르게 해서 모두 표시
  --> 부산 진구의 인구 밀집 지역 표시 완료 

## Kmeans 클러스터링

범죄 우발 지역의 포화도를 구해내어, 주의가 필요한 지역을 선정
