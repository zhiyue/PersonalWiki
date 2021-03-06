## Dataflow	[Back](./../Style.md)
- Dataflow適用於基於**數據驅動**的系統, 數據處理是**分步驟**的.
- **拓撲結構**: 線性或有限循環
- 優點: 容易添加步驟
- 缺點: 難於修改步驟順序(交互性差)
- 組件: 處理數據過程
- 連接件: 數據

> Batch Sequential

> Pipe-Filter

> Procedure Control
>> Open Loop Control

>> Close Loop Control

### 1. Batch Sequential(批處理)
- 批處理指數據整體傳遞
- 優點: 對數據的整體訪問是可行的
- 缺點: 處理速度較慢, 因為上一步驟完全處理完數據後才能傳遞到下一步驟, 導致下一步驟的空閒

### 2. Pipe-Filter(管道-過濾)
- 管道過濾指數據流水式傳遞, 當處理好單個數據後立即傳遞到下一步驟(相當於流水線)
- 優點: 處理速度較快
- 缺點: 無法進行對數據的訪問性, 即很難找到數據當前處於哪個步驟

### 3. Procedure Control(過程控制)
- 當系統容易受到外界的影響(軟件不可控或不可見)時, 應考慮**過程控制**. (一般是**軟硬結合**的系統)
- 組件: 算法 + 控制結構
- 連接件: 數據
- Open Loop Control(開環控制): 由人來控制當前系統受到影響後其處理方法.
- Close Loop Control(閉環控制): 由系統自身根據當前狀態來決定處理方法.
	- 反饋閉環: 測量**受控變量**, 通過**預測值**與**實際值**的差異來決定控制
	- 前饋閉環: 測量其他變量進行**事先預測**

 

<a href="#" style="left:200px;"><img src="./../../../pic/gotop.png"></a>
=====
<a href="http://aleen42.github.io/" target="_blank" ><img src="./../../../pic/tail.gif"></a>
