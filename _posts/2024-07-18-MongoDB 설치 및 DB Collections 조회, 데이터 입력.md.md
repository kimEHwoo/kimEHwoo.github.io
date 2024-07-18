---
title: MongoDB 설치 및 DB Collections 조회, 데이터 입력
author: EHwoo
date: 2024-07-18 14:00:05 +0900
categories: [MongoDB]
tags:[MongoDB]
---

### show dbs
데이터베이스 검색해줌
(ex) admin, config, local

### 콜렉션이 있고 콜렉션 안에 document라는 것이 있음.
document가 저장된 data
SQL과 비교했을 때 테이블이라고 생각하면 쉬움.

1. use studydb
2. show dbs
3. db.firstcol.insertOne({a:1})
4. show dbs


MongoDB에서는 use studydb 명령어를 사용하여 데이터베이스를 전환할 수 있습니다. 그러나 데이터베이스가 처음 사용될 때까지는 실제로 데이터베이스 목록에 나타나지 않습니다. 데이터베이스가 목록에 나타나려면 최소한 하나의 컬렉션에 데이터를 삽입해야 합니다.

주어진 명령어를 순서대로 실행했을 때, 데이터베이스가 어떻게 추가되는지 설명하겠습니다.

명령어 실행 순서와 결과
use studydb
이 명령어는 studydb라는 이름의 데이터베이스를 사용하겠다는 의미입니다. 만약 studydb 데이터베이스가 존재하지 않으면, MongoDB는 새로운 데이터베이스를 생성하지는 않지만 사용 준비 상태로 전환합니다.
show dbs
현재 MongoDB 서버에 존재하는 데이터베이스 목록을 표시합니다. 이 시점에서는 아직 studydb가 실제로 생성되지 않았으므로 목록에 나타나지 않습니다.
db.firstcol.insertOne({a:1})
studydb 데이터베이스 내에 firstcol이라는 컬렉션을 생성하고 {a: 1}이라는 문서를 삽입합니다. 이로 인해 studydb 데이터베이스가 실제로 생성됩니다.
show dbs
다시 데이터베이스 목록을 표시합니다. 이제는 studydb 데이터베이스가 목록에 나타납니다.


5. show collections
6. db.firstcol.insertOne({name:"홍길동", age:10, t_f:true, assstr:[{국적:"한국", 도시: "서울"}, {직업: "육상선수", 경력: "500년"}]})