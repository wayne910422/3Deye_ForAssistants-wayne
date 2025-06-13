## 3Deye_ForAssistants
- 資料前處理格式:
![image](https://github.com/Poopogen/3Deye_ForAssistants/blob/main/image/Figure_r.png)
### 參考資料 :
#### OCR 字元辨識 : [Paddle OCR](https://github.com/PaddlePaddle/PaddleOCR)
## 左右眼切分
![image](https://github.com/user-attachments/assets/b540ee12-cb7f-4943-b0c6-72abf9e7993d)

## 沒有資訊欄的眼球手術影片
![image](https://github.com/user-attachments/assets/c541c1d7-6a55-474e-82be-d00e5cf4c132)
![image](https://github.com/user-attachments/assets/6eb25217-af69-4e25-9ae9-35ee672f0c69)

## 我們認為沒有資訊欄的影片太多了，在後續的訓練模型，會有資料稀疏的問題，所以目前訓練一個classfiler 2分類的模型 去做 Anterior / Posterior 的分類
![image](https://github.com/user-attachments/assets/69eba28b-b768-4b57-9bdb-bb87dc5e0010)

![classifier prediction result](https://github.com/user-attachments/assets/69eba28b-b768-4b57-9bdb-bb87dc5e0010)

---

## Classifier 模型參數（ResNet50）



### 訓練參數配置

#### 資料處理參數
- `IMAGE_SIZE`: (448, 448)
- `BATCH_SIZE`: 32
- `NUM_WORKERS`: 10

#### 模型設定
- `MODEL`: ResNet50（使用預訓練權重）
- `NUM_CLASSES`: 2（Anterior=0, Posterior=1）
- `PRETRAINED`: True

#### 訓練參數
- `EPOCHS`: 30
- `LEARNING_RATE`: 1e-4
- `OPTIMIZER`: Adam
- `LOSS_FUNCTION`: CrossEntropyLoss
- `EARLY_STOPPING_PATIENCE`: 5

#### 交叉驗證
- `K_FOLDS`: 5
- `SHUFFLE`: True
- `RANDOM_SEED`: 42

#### 資料增強（訓練時）
- `RandomHorizontalFlip`
- `RandomRotation`: ±10度
- `ColorJitter`:
  - brightness=0.2
  - contrast=0.2
  - saturation=0.2
- `Normalization`:
  - mean=[0.485, 0.456, 0.406]
  - std=[0.229, 0.224, 0.225]

#### 模型表現
- `F1-score`: **0.9924**


##  後續

- 有分好的  Anterior / Posterior ， 開始研究如何利用 cv 去辨識 眼球深度
- 目前有看到大腸鏡深度的相關實驗正在研究 
  

---

