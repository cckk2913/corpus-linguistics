### Dcard

且哥之前在語法學的 term paper 使用 PTT 語料，分析了<strong>「V 看看」</strong> 和<strong>「VV 看」</strong>（e.g., 試看看 和 試試看）的動詞共現頻率和語境。
他發現

- <strong>「V 看看」</strong>出現的頻率更高、搭配的動詞種類也更多
- _試、問_ 等動詞明顯傾向與<strong>「V 看看」</strong>共現（2188 vs 5; 1539 vs 13）
- _瞧、攻_ 等動詞只有和<strong>「VV 看」</strong>共現的資料

不過且哥也想知道在 Dcard 論壇是不是也有相似的狀況，於是他想請你利用賦神爬取的 Dcard 貼文 raw data（197 個 folders，共 20069 個 json），找出

1. 在<strong>「V 看看」</strong>的 V-slot 最常出現的 10 個動詞和詞性（e.g., VC, VE, or VA)
2. 在<strong>「VV 看」</strong>的 V-slot 最常出現的 10 個動詞和詞性
3. 在兩個構式的 V-slot 出現次數總和最多的前 10 個動詞
4. 在兩個構式的 V-slot 出現次數差異最大的前 10 個動詞
5. 在兩個構式的 V-slot 都有出現的動詞

---

### IgPost

且哥每次瀏覽 Instagram hashtag #芋頭 的帖文，都會看到很多無關芋頭的廣告貼文，讓他覺得十分無語。而且他發現這些廣告貼文常夾帶高人氣的 hashtag（例如： #台北美食、#超商、#台灣 ）以增加曝光度，除此之外，這些貼文的內容中也常會出現毫不相干的名詞。

於是，且哥準備做一個廣告/一般貼文分類器，不過他需要先知道貼文長度、hashtag 數量、 lexical diversity、POS diversity 之中，哪些特徵對於分類器的準確度影響最大，因此他想請你利用 Derek 神提供的 5000 篇 Instagram 貼文資料集，

1. 將內文前處理並以 ckip-transformers 進行中文斷詞、詞性標註
2. 分別提取出每篇文的 4 種 features：文章長度, hashtag 數量, lexical diversity, POS diversity
3. 再使用 Logistic Regression model 作為 classifier (1: 廣告, 0: 生活貼文)，並依序測試 4 種 features, 4 選 3 種 features 的準確度，看哪一個特徵對於分類器的準確度影響最大

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
