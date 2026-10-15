# untangle

자꾸 머릿속에 맴도는 생각을 쪽지에 적으면, 그렇게까지 붙들고 있을 일이 아니라는 한 줄을 듣고, 쪽지째 구겨 버리는 모바일 웹앱이에요. (앱 이름은 가칭 "사실은 별거 아냐")

## 구조
- `public/` 화면 (index.html 한 장 + 그림, 글꼴)
- `api/answer.js` 답 만들기. 화면이 보낸 글에 말투 지시문(`api/tone.json`)을 붙여 Claude API에 보낸다
- `api/tone.json` 답 말투 지시문. 말투를 고칠 땐 이 파일만 고치면 된다

## Vercel 환경 변수
- `ANTHROPIC_API_KEY` (필수) Anthropic 콘솔에서 만든 키
- `ANTHROPIC_MODEL` (선택) 기본 `claude-sonnet-5-5`
- `DAILY_LIMIT` (선택) 한 사람이 하루에 받을 수 있는 답 수, 기본 10

## 지금 하지 않는 것
- 적은 글은 저장하지 않는다 (서버 로그에도 남기지 않음)
- 하루 사용 제한은 서버 메모리 기준이라 대략적이다. 사람을 많이 받기 전에 저장소 기반으로 바꾼다
