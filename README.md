# Report integration

"뉴스펍"을 선택해 주셔서 감사합니다.<br>
통계를 요청하기 위해서는 key를 발급받아야 합니다.<br>
아래 메일을 통해 key를 발급 받으세요.<br>

> 메일 : <newspub@adxcorp.kr>

# 유의사항
> 통계는 매일 오전 11시 30분에 완료 됩니다.<br>
> 빈번한 요청은 계정이 Block 될 수 있습니다.<br>

# Request (Method : GET)

Status|URL
:---:|:---:
LIVE|http://my.newspub.kr/api/report

Parameter|Mandantory|Description
:---:|:---:|:---:
key|O|발급받은 아이디
sdate|O|통계 요청 시작일 (yyyyMMdd)
edate|O|통계 요청 종료일 (yyyyMMdd)

# Request sample
http://my.newspub.kr/api/report?key={발급받은KEY}&sdate={통계요청시작일}&edate={통계요청종료일}

# Response

```

# Response sample.

{
    "result": 0,
    "message": "success",
    "data": [
        {
            "ymd": "20220117",
            "media": [
                {
                    "mid": "607e5f007f88ba08cb651f93",
                    "clk": 1,
                    "revenue": 0.0
                }
            ]
        },
        {
            "ymd": "20220118",
            "media": [
                {
                    "mid": "607e5f007f88ba08cb651f93",
                    "clk": 1,
                    "revenue": 0.0
                }
            ]
        }
    ]
}

```

Key|Key|Mandantory|Description
:---:|:---:|:---:|:---:|:---
result|||O|응답 코드
message|||O|응답 메세지
data|||O|응답 데이터
||ymd|O|통계 대상일
||media|O|날짜별 매체 데이터
|||clk|O|클릭 수치
|||revenue|O|수익 (KRW)

# 응딥 코드 (result)
Code|Description
:---:|:---:
0|Success
400|Bad Request
401|Unathorized
