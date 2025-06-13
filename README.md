# 3Deye_ForAssistants
### 資料前處理格式:
![image](https://github.com/Poopogen/3Deye_ForAssistants/blob/main/image/Figure_r.png)
### 參考資料 :
#### OCR 字元辨識 : [Paddle OCR](https://github.com/PaddlePaddle/PaddleOCR)
#### 左右眼切分
![image](https://github.com/user-attachments/assets/b540ee12-cb7f-4943-b0c6-72abf9e7993d)

#### 沒有資訊欄的眼球手術影片
![image](https://github.com/user-attachments/assets/c541c1d7-6a55-474e-82be-d00e5cf4c132)
![image](https://github.com/user-attachments/assets/6eb25217-af69-4e25-9ae9-35ee672f0c69)

#### 我們認為沒有資訊欄的影片太多了，在後續的訓練模型，會有資料稀疏的問題，所以目前訓練一個classfiler 2分類的模型 去做 Anterior / Posterior 的分類
![image](https://github.com/user-attachments/assets/69eba28b-b768-4b57-9bdb-bb87dc5e0010)

#### 目前classfiler模型的相關參數
![image](https://github.com/user-attachments/assets/8b176e41-4fdb-4fe5-8136-72096b0aeb88)

