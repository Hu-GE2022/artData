# BUSAN CRIME

## 부산 관할구별 5대 범죄 시각화

데이터 출처 : 부산시 관서별 5대 범죄 발생 현황 https://www.data.go.kr/data/15036510/fileData.do#layer_data_infomation

- 데이터 전처리
  - 2018~2021년도 부산시 5대범죄 데이터를 통합
  - 컬럼명 통일 및 합계 열과 행 생성
  
- 데이터 시각화
  - 5대 범죄별 연도별 범죄건수 추이를 막대 그래프로 시각화
  ![image](https://user-images.githubusercontent.com/108312150/185886648-576d4401-5198-45a3-8d30-827c7cd441aa.png)
  - 데이터 정규화 처리 후 4개년 관서별 범죄 수를 막대 그래프로 시각화
  ![image](https://user-images.githubusercontent.com/108312150/185886701-2c03cf77-1ba0-4569-9da9-ee5cabdfd778.png)
  ![image](https://user-images.githubusercontent.com/108312150/185886770-2657d372-d311-4d82-82cb-2671cc225a7c.png)

## 인구 만 명 당 5대 범죄 시각화

데이터 출처: ?

- 행정구역별 인구 수 데이터를 이용해, 행정구역별 인구 만 명 당 5대 범죄 시각화함
![image](https://user-images.githubusercontent.com/108312150/185887032-02efe7d0-6770-4c10-b2cb-4c4c3d410878.png)
![image](https://user-images.githubusercontent.com/108312150/185887067-e8d32e1e-7bf0-4c37-b9ea-c5b02876c81d.png)

## 장소별 시각화

데이터 출처 : https://www.data.go.kr/data/3074463/fileData.do

- 장소별 범죄 건수 데이터 조회 후 시각화
  - 범죄 건수가 가장 높은 장소 5개 선정(아파트, 숙박업소, 목욕탕, 유흥업소, 주차장)
![image](https://user-images.githubusercontent.com/108312150/185886119-0c58b3c9-efd2-41cd-87a6-9c18a3804c4b.png)

## 시간 및 요일별 시각화

데이터 출처 : https://www.data.go.kr/data/3074459/fileData.do

- 요일별 범죄 건수 데이터 조회 후 시각화
  - boxplot을 이용해 범죄 건수가 가장 많은 요일 선정
  ![image](https://user-images.githubusercontent.com/108312150/185885872-c56c30b9-c11f-44eb-900a-e241f199db3b.png)
(토요일)

- 시간별 범죄 건수 데이터 조회 후 시각화
  - 막대그래프를 이용해 범죄 건수가 가장 많은 시간 선정
  ![image](https://user-images.githubusercontent.com/108312150/185885957-74780b67-f918-4d8a-a74e-4704448737c8.png)
(절도는 6시~18시, 강력범죄와 폭력범죄는 15시 이후 증가)

  

## 장소별 클러스터링

<범죄 빈도가 높은 장소 5가지 : 아파트, 숙박업소, 목욕탕, 유흥주점, 주차장>

  - 아파트 위치 정보 출처 : https://www.data.go.kr/data/15007226/fileData.do
  - 숙박업소 위치 정보 출처: https://www.data.go.kr/data/15025544/fileData.do
  - 목욕탕 위치 정보 출처: https://www.data.go.kr/data/15025545/fileData.do 
  - 유흥주점 위치 정보 출처: https://data.busan.go.kr/dataSet/detail.nm?publicdatapk=15025547&contentId=10
  - 주차장 위치 정보 출처: https://data.busan.go.kr/dataSet/detail.nm?publicdatapk=15004683&contentId=10

- 선정된 장소를 범죄건수가 가장 많은 부산진구 지도에 클러스터링

![image](https://user-images.githubusercontent.com/108312150/185885751-1d3d95a8-52a6-4eff-a2ce-54edadede76c.png)

- 데이터 전처리
  - null값 해결 및 컬럼명 통일
  - 주소 값 통일

- 데이터를 지도로 시각화
  - import googlemaps : 구글맵을 이용해 데이터 프레임의 주소를 위도, 경도 값 추출
  - 추출된 위도,경도 값을 지도에 표시
  - 5개 구역의 값을 색을 다르게 해서 모두 표시
  --> 부산 진구의 인구 밀집 지역 표시 완료 

## Kmeans 클러스터링

![image](https://user-images.githubusercontent.com/108312150/185885634-a4291980-f4ee-4660-9099-1cf1d6ff2e1e.png)

범죄 우발 지역의 포화도를 구해내어, 주의가 필요한 지역을 Kmeans를 이용해 선정
--> 개금동, 양정동, 초읍동, 범일동 : 아파트, 다세대가 많은 주거지역
--> 부전동 : 유흥 지역이 많이 위치하는 지역

# 결론 : 개금동, 양정동, 초읍동, 범일동, 부전동에 토요일 18시 이후에 범죄 예방 인력 집중이 필요하다 
