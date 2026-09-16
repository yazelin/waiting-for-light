# Waiting For Light

線上播放：https://yazelin.github.io/waiting-for-light/

一首寫給系統故障與等待微光的情歌，附中英對照動態歌詞。單頁播放器，零依賴、零 build step。

## 內容

- `index.html` — 播放器本體：封面隨低頻脈動、頻譜環、飄向微光的粒子、動態歌詞
- `assets/waiting-for-light.mp3` — 歌曲音檔
- `assets/lyrics.json` — 逐行英文歌詞＋中文對照，時間軸
- `images/cover.webp` — 封面（Codex `$imagegen` 生成）

## 歌詞時間軸怎麼做的

本機 `whisper-cli`（`ggml-large-v3-turbo`）跑一次語音轉錄拿逐字時間戳，再用
`SequenceMatcher` 把時間戳對回官方歌詞文字（只取時間、文字一律用官方版）。
對齊品質 98.7%（英文歌詞比中文歌詞好對齊很多）。

## 開發

純靜態頁面，本機起個 http server 就能看：

```bash
python3 -m http.server 8998
```

## 授權

見 [LICENSE.md](LICENSE.md)：CC BY-NC 4.0，禁止商用。
