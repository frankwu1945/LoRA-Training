# LoRA-Training LoRA 模型訓練實作
---
本專案旨在展示訓練一款能高度還原訓練角色之外表特色及其特定服飾的 LoRA 模型之變化過程。期盼透過精準的資料集處理與參數調校，在維持角色面部特徵與服裝一致性的同時，具備良好的動作與背景泛化能力。  
---
訓練角色：Eva  

角色來源：電腦遊戲 Eternal Return 永恆輪迴  

訓練基底模型：Illustrious XL 0.1 (https://civitai.com/models/795765/illustrious-xl)

訓練工具：本作品使用 Hollow Strawberry 開發的 kohya-colab (https://github.com/hollowstrawberry/kohya-colab) ，並依本專案需求進行資料集準備與訓練參數設定。感謝原作者提供此工具。

---

目的：透過較強的學習率來學習角色與服裝的基本特徵

訓練日期：2026 年 08 月 20 日

資料數量：72  

素材大小：1024*1024  

UNet 學習率：2e-4  

Text Encoder 學習率：2e-5  

結果：  
<table>
  <tr>
    <td align="center">
      <img src="simple/eva_default.jpg" width="100%" /><br>
      <b>Eva 的經典造型，保留改變手勢與頭戴花環等彈性</b>
    </td>
    <td align="center">
      <img src="simple/eva_default_2.jpg" width="100%" /><br>
      <b>Eva 的經典造型，能透過提詞改變角色的眼睛狀況</b>
    </td>
  </tr>
</table>

---

目的：為增加模型多樣性與泛化性，透過適當刪減與新增加訓練素材與修改訓練參數來取得更好的LoRA內容，並將經典造型與cadet造型放入同一個LoRA中進行訓練。

訓練日期：2026 年 09 月 01 日

資料數量：100 

素材大小：1024*1024  

UNet 學習率：8e-5  

Text Encoder 學習率：4e-5  

結果：  
<table>
  <tr>
    <td align="center">
      <img src="simple/eva_default(20260901).jpg" width="100%" /><br>
      <b>Eva 的 Cadet 造型，露出ya的手勢來確保手動作的可變性</b>
    </td>
    <td align="center">
      <img src="simple/eva_cadet(20260901).jpg" width="100%" /><br>
      <b>Eva 的 Cadet 造型，露出ya的手勢來確保手動作的可變性</b>
    </td>
  </tr>
</table>

---

目的：在訓練過程中將角色身份與服裝特徵分離，使角色能在服裝間進行切換時能維持原有的外觀特徵。

訓練日期：2026 年 09 月 02 日

資料數量：107 

素材大小：1024*1024  

UNet 學習率：1e-4  

Text Encoder 學習率：4e-5  

結果：  
<table>
  <tr>
    <td align="center">
      <img src="simple/eva_cadet(20260902).jpg" width="100%" /><br>
      <b>Eva 的 Cadet 造型</b>
    </td>
    <td align="center">
      <img src="simple/eva_cadet_nocapelet(20260902).jpg" width="100%" /><br>
      <b>將cadet造型中的白色披肩移除，確定衣服間的解耦足夠有效</b>
    </td>
  </tr>
</table>

