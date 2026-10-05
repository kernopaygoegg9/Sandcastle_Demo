# Sandcastle_Demo

沙堡網頁版：在熱帶海灘上堆沙堡的 3D 沙盒遊戲。挖護城河、刻城垛、收集寶物，看潮水和海浪慢慢把城堡沖垮。還有會引來海嘯的末日模式。

非官方粉絲致敬作品，靈感來自 Bubblebird Studio 的《Sandcastle》。所有程式與 3D 造型皆為原創，未使用原作素材。

## 遊玩

純靜態網頁，不需要編譯。用任一靜態伺服器開啟專案根目錄：

```bash
python -m http.server 5173
```

然後打開 http://localhost:5173 。直接雙擊 `index.html` 無法執行（瀏覽器不允許從本機檔案載入 ES 模組）。

## 操作

- 左鍵：使用工具 / 撿起寶物
- 右鍵拖曳，或按住空白鍵 / Alt 再用左鍵拖曳：旋轉視角
- 滾輪：縮放；Q / E 轉向；R 重設視角
- 1–6：切換工具；`[` `]`：筆刷大小；Ctrl+Z：復原
- 觸控：單指使用工具，雙指旋轉縮放
- 網址加上 `?debug` 或按 F3：效能面板

## 程式結構

| 檔案 | 內容 |
| --- | --- |
| `main.js` | 進入點、主迴圈、遊戲事件 |
| `src/config.js` | 世界常數、海灘地形、寶物、工具、海浪模式 |
| `src/sim.js` | 沙與淺水模擬（不依賴 Three.js） |
| `src/ocean.js` | 潮汐、浪組、海嘯排程 |
| `src/render.js` | Three.js 場景、網格增量更新、鏡頭 |
| `src/items.js` | 寶物與裝飾 |
| `src/tools.js` | 工具、拾取、復原、輸入 |
| `src/ui.js` | 介面、任務 |
| `src/audio.js` | 程序化音效 |
| `src/save.js` | localStorage 存檔 |
