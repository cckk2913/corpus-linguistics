---

### IgPost

1. 以模型預測 IgPost 的類別(1: 廣告, 0: 生活貼文)
2. 將文本前處理並以 ckip-transformers 進行中文斷詞、詞性標註
3. 使用 Text length, lexical diversity, POS diversity, Hashtag_n 作為 features
4. 使用 Logistic Regression model 進行 classification task

---

### Puyuma

且哥半年前修了田野調查課，但她記性不好，已經忘記除了 takesiyan （學校）以外的其他詞彙了。又因為知本卑南語有其特殊的詞根、詞綴，無法透過英文、中文等斷詞系統進行斷詞，能不能請你以且哥依照田調課 transcription 格式的 WORD 檔建立一個小規模的語料庫，並以此語料庫訓練一個 FastText 模型提取 word embedding，並使用 K-means cluster analysis 進行詞彙分類呢？

1. 用田調課格式儲存的 docx.檔，提取出知本卑南語 transcription 語料
2. 建立 Fasttext word embeddings
3. 再利用 PCA 降維、K-means cluster analysis 看詞類分布狀況

---

### BullyTweet

且哥期末最喜歡滑手機了，不過她常看到推特上有些人會用尖酸苛薄的文字辱罵、霸凌他人；因此，且哥想要做一個網路霸凌偵測器，來辨識推文是否有霸凌，並分類該推文的主題（e.g., 宗教、年齡、種族、性別、其他、無霸凌）。

不過她不確定用哪種方式來提取文本特徵比較有效，也不確定要用哪個模型作為分類器，於是想請你利用已標記的推文資料集，**比較 [TfidfTransformer & Naive Bayes] 和 [Word2Vec & SVM] 兩個 [embedding&模型] 的組合**，告訴她哪一組的 wordembedding 和 classifier 能較好地預測推文是否與網絡霸凌相關。

1. 使用英文推文資料集，進行前處理（斷詞、去除停用詞、去除標點符號、去除數字、去除網址、去除 emoji、去除 @標註人）
2. 使用 TfidfTransformer >> Naive Bayes 進行推文分類預測
3. 使用 Word2Vec >> SVM 進行推文分類預測

