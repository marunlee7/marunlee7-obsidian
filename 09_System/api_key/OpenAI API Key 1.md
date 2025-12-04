<%*
const fs = require("fs");
const path = require("path");
const OpenAI = require("openai");

// 파일 경로
const keyPath = path.join(tp.file.folder(true), "openai_key.md");

// 파일 읽기
const apiKey = fs.readFileSync(keyPath, "utf8").trim();

// OpenAI 클라이언트 설정
const client = new OpenAI({ apiKey });

// GPT 호출
const prompt = "옵시디언에서 GPT 호출 테스트";

const response = await client.chat.completions.create({
  model: "gpt-4o-mini",
  messages: [
    { role: "system", content: "친절한 조수 역할" },
    { role: "user", content: prompt }
  ],
  max_tokens: 100
});

// 결과 출력
tR += response.choices[0].message.content;
%>
