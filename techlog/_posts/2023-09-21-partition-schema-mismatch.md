---
layout: post
title: "Athena query 실행시 HIVE_PARTITION_SCHEMA_MISMATCH 에러를 해결하는 방법"
subtitle: "Athena query fail with the error HIVE_PARTITION_SCHEMA_MISMATCH"
category: techlog
tags: [aws,data engineering, athena, glue]
---

![Athena](/assets/img/techlog/amazon-athena.png){: width="320" height="212"}

최근에 AWS 환경에서 데이터 분석 환경을 만들면서, S3에 적재된 데이터를 Glue와 Athena를 이용하여 분석하도록 구성하고 있습니다.

그러다가 Glue crawler를 이용하여 스케줄을 실행하고 다음날 확인을 해보면, 아래와 같이 `HIVE_PARTITION_SCHEMA_MISMATCH`를 자주 만나고는 합니다.

![mismatch](/assets/img/techlog/hive-partition-schema-mismatch.png){: width="70%" height="70%"}

크롤링 하는 테이블과 파티션의 데이터 타입이 일치하지 않아서 발생하는 에러라고 하는데, 한 번 확인해 보겠습니다.
<!--more-->
