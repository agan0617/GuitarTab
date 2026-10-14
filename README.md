# 吉他譜架

彈吉他時邊彈邊看譜的網頁：<https://agan0617.github.io/GuitarTab/>

- 譜是 [alphaTex](https://www.alphatab.net/docs/alphatex/introduction) 純文字檔，由 [alphaTab](https://www.alphatab.net/) 畫成六線譜（含和弦名與和弦圖）並播放
- 譜存在**私有** repo（預設 `agan0617/CloudSave` 的 `saves/guitartab/`），網頁用 fine-grained token 讀取，這個公開 repo 裡沒有任何譜
- 跟 [K書吧](https://github.com/agan0617/KBookBar) 在同一個網域，瀏覽器連過 K書吧就自動沿用那組 token；沒連過就按「連線設定」貼一次
- 譜架照這台裝置最近彈的排序；看過的譜存在瀏覽器裡，離線也能開
- Android App 在 [GuitarTabApp](https://github.com/agan0617/GuitarTabApp)（WebView 開這個網頁）

## 看譜

- **播放**：游標照譜上的速度一拍一拍走，譜自動捲到正在彈的地方；點譜上任一小節從那裡開始
- **聲音**：關掉（🔇）就只剩游標在走，當作自動捲譜；節拍器可以另外開
- **速度**：用百分比放慢或加快（30%～150%），練習時從慢的開始
- **譜大小**：A− A＋ 縮放；速度、聲音、節拍器、大小每首各自記住
- 看譜時螢幕不會自動關閉；播放中工具列幾秒後自動收起，點譜面叫出來

鍵盤與藍牙翻頁踏板：

| 按鍵 | 動作 |
|---|---|
| 空白鍵 | 播放／暫停 |
| → ↓ PageDown Enter | 往下捲一頁 |
| ← ↑ PageUp | 往上捲一頁 |
| Home | 回到開頭 |
| － ＋ | 慢一點／快一點 |
| M／K | 聲音開關／節拍器開關 |
| F | 全螢幕 |
| Esc | 回譜架 |

## 譜的格式

`saves/guitartab/library.json`：

```json
{
  "tabs": [
    {
      "id": "g20261015001000",
      "title": "卡農",
      "artist": "帕海貝爾",
      "tempo": 82,
      "bars": 69,
      "file": "tabs/卡農.tex",
      "addedAt": "2026-10-15T00:10:00+08:00",
      "updatedAt": "2026-10-15T00:50:00+08:00"
    }
  ]
}
```

- `file` 是相對於 `saves/guitartab/` 的路徑，內容是 alphaTex；`tempo`、`bars` 只用在譜架上顯示，播放速度以譜檔裡的 `\tempo` 為準
- 改了譜檔要更新 `updatedAt`，瀏覽器才會重抓
