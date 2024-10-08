# RAID의 정의 (Redundant Array of Independent Disks)
- 여러 개의 물리적 보조기억장치를 마치 하나의 논리적 보조기억장치처럼 사용하는 기술

# RAID의 종류
- RAID를 구성하는 방법에는 여러가지가 있고, RAID 구성 방법을 'RAID 레벨'이라고 표현함
- RAID 레벨에는 RAID1, 2, 3, 4, 5, 6, 10, 50 등이 있음

# RAID 0
- 여러 개의 보조기억장치에 데이터를 단순히 나누어 저장하는 구성 방식
- 1TB 하드 디스크 네 개로 RAID 0을 구성하면 데이터를 번갈아가면서 저장함 <br>
  이때, 줄무늬처럼 분산되어 저장된 데이터를 '스트라이프' 이라 하고, <br>
  분산하여 저장하는 것을 '스트라이핑' 이라고 함

![image](https://github.com/user-attachments/assets/52ec610f-eba4-4d70-8cbb-12b355233059)

- 데이터가 분산되어 저장되면(스프라이핑되면), 저장된 데이터를 읽고 쓰는 속도가 빨라짐
- 이론상 4TB 저장 장치 한 개 보다 RAID 0으로 구성된 1TB 저장 장치 네 개의 속도가 네 배가량 빠름
- 하지만, RAID0에는 구성된 하드디스크 하나에 문제가 생기면 다른 모든 하드디스크의 정보를 읽는데 <br>
  문제가 생길 수 있다는 단점이 있음. 이를 예방하기 위해 등장한 것이 RAID 1임

![image](https://github.com/user-attachments/assets/3484491f-450e-4955-8512-4b7a807d6e26)

# RAID 1
- RAID 1는 복사본을 만드는 방식임. 거울처럼 완전한 복사본을 만들기 때문에 미러링이라고도 부름
- RAID 0과 달리 네 개의 하드디스크에 대해 2개에는 원본 데이터를 나머지 2개에는 백업(복사본) 데이터를 저장함

![image](https://github.com/user-attachments/assets/cf655d2f-b990-48cc-8ab4-a46feed86400)

- RAID 1 방식은 복구가 매우 간단하는 장점이 있음 <br>
  똑같은 디스크가 2개 있는 것과 같으니, 하나에 문제가 발생해도 잃어버린 정보를 쉽게 되찾을 수 있기 때문
- 하지만 RAID 1 방식은 한정된 하드디스크에서는 사용 가능한 용량이 적어진다는 단점이 있음 <br>
  RAID 0에서는 4TB의 데이터를 저장할 수 있는 반면, RAID 1에서는 2TB의 데이터만 저장할 수 있음 <br>
  결국, 많은 양의 하드디스크가 필요하게 되고, 비용이 증가하게 됨

# RAID 4
- RAID 4는 RAID 1과 같이 완전한 복사본을 만드는 대신 <br>
  오류를 검출하고 복구하기 위한 정보를 저장하는 디스크를 두는 방식임
- 오류를 검출하고 복구하기 위한 정보를 '패리티 비트' 라고 부름
- RAID 4에서는 '패리티 비트'를 저장한 디스크를 이용해 <br>
  다른 디스크들의 오류를 검출하고, 오류가 있다면 복구함

  ![image](https://github.com/user-attachments/assets/592aeff1-cea2-4482-a5d5-e6391378f613)

- RAID 4에서는 새로운 데이터가 저장될 때마다 <br>
  패리티를 저장하는 디스크에도 데이터를 쓰게 되어 <br>
  패리티를 저장하는 디스크에 병목 현상이 발생한다는 단점이 있음 <br>
  이를 해소하기 위해 만들어진 방식이 RAID 5임

![image](https://github.com/user-attachments/assets/ba3bd6a2-0453-457e-8150-b9c89e173844)

# RAID 5
- RAID 5는 패리티 정보를 분산하여 저장하는 방식으로 RAID 4의 문제인 병목 현상을 해소함

![image](https://github.com/user-attachments/assets/a694e784-9428-4c35-88cd-b73781463a51)

# RAID 6
- RAID 6의 구성방식은 기본적으로 RAID 5와 같으나 서로 다른 두 개의 패리티를 두는 방식임 <br>
  오류를 검출하고 복구할 수 있는 수단이 두 개 생긴 것과 같음 <br>
  결론적으로 RAID 6는 RAID 4, RAID 5보다 안전한 구성이라고 볼 수 있음 <br>

- 물론, 새로운 데이터를 저장할 때마다 저장해야하는 패리티가 두 개이므로, <br>
  RAID 5보다 쓰기 속도는 느리지만, 저장 속도를 조금 희생하더라도 데이터를 더욱 안전하게 보관하고 싶을 때 쓰는 방식임

![image](https://github.com/user-attachments/assets/5dd17b0d-9231-4fb8-be76-08db1143edec)
