
# 東吳知識王 — AR 互動問答遊戲

[![Unity](https://img.shields.io/badge/Unity-2022.3+-000000?style=flat&logo=unity&logoColor=white)](https://unity.com/)
[![AR Foundation](https://img.shields.io/badge/AR_Foundation-5.x-00ADEF?style=flat&logo=unity&logoColor=white)](https://docs.unity3d.com/Packages/com.unity.xr.arfoundation@5.0/manual/index.html)
[![Platform](https://img.shields.io/badge/Platform-iOS%20%7C%20Android-lightgrey?style=flat&logo=apple&logoColor=white)](https://github.com/BoRenCheng)
[![Language](https://img.shields.io/badge/Language-C%23-239120?style=flat&logo=csharp&logoColor=white)](https://github.com/BoRenCheng)

以東吳大學校園知識為題材的 **AR 擴增實境互動問答遊戲**。

掃描圖片卡觸發幽靈角色登場，完成對話後進入限時問答關卡，答對 3 題即可「畢業」！

 **專案介紹影片**: [點此觀看 YouTube](https://www.youtube.com/watch?v=ZDuq2qpmftc) 

---

##  遊戲流程

```
掃描 AR 圖片卡
      ↓
幽靈角色出現 + 對話劇情
      ↓
進入問答關卡（每題 5 秒倒數）
      ↓
答對 ≥ 3 題 → 🎓 畢業快樂！
答對 ＜ 3 題 → 📚 學分不夠，請重補修！
```
---

## 功能特色

- **AR 圖片辨識**：使用 AR Foundation 掃描實體圖片卡，即時生成 3D 幽靈角色
- **劇情對話系統**：幽靈逐行播放對話，帶入問答情境
- **四選一問答**：支援多題題庫、自動切換、答案即時回饋（綠色/紅色）
- **倒數計時**：每題限時 5 秒，增加緊張感
- **音效系統**：答對、答錯、背景音樂、勝利音效全覆蓋
- **跨平台支援**：支援 iOS / Android，Editor 模式可用滑鼠模擬點擊

---

## 腳本架構

| 腳本 | 功能 |
|------|------|
| `ARManager.cs` | AR 平面偵測、幽靈生成、流程控制 |
| `TrackedImageSpawner.cs` | 圖片辨識追蹤、Prefab 動態生成 |
| `GhostSpawner.cs` | 在攝影機前方生成幽靈 |
| `GhostDialogue.cs` | 幽靈對話劇情播放，結束後啟動問答 |
| `QuestionManager.cs` | 題庫管理、答案驗證、題目切換 |
| `UIManager.cs` | UI 更新、倒數計時、答題結果處理 |
| `AnswerButton.cs` | 選項方塊點擊事件處理 |
| `AudioManager.cs` | 背景音樂與音效播放 |

---

## 如何執行

1. Clone 此 repo
2. 以 Unity Hub 開啟專案（建議版本：Unity 2022.3 LTS）
3. 安裝套件：`Window → Package Manager` 確認 AR Foundation 已安裝
4. 匯入題庫資料至 `QuestionManager` Inspector
5. 設定 XR Plugin Management（iOS / Android）
6. Build 至手機即可執行

> **Editor 模式測試**：在 `ARManager.cs` 中已內建 Editor 滑鼠點擊模擬，可直接在編輯器中測試問答流程。

---

## 👤 作者

**Bo-Ren Cheng（鄭博仁）** — Soochow University, Taiwan
