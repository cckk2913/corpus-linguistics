## Puyuma_FastText

1. 用田調課格式儲存的 docx.檔，提取出知本卑南語語料 transcription
2. 為其建立 Fasttext word embeddings
3. 再利用 PCA 降維度、K-means cluster analysis 看卑南語料的詞類分布狀況

## IgPost_LR

1. 以模型預測 IgPost 的類別(1: 廣告, 0: 生活貼文)
2. 將文本前處理並以 ckip-transformers 進行中文斷詞、詞性標註
3. 使用 Text length, lexical diversity, POS diversity, Hashtag_n 作為 features
4. 使用 Logistic Regression model 進行 classification task
