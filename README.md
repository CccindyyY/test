## LinkedIn-adtech-system-redesign
---

### 目標：作為DSP，透過自然語言處理重新定義使用者，並提供各產業公司廣告投放策略與受眾建議。

### 背景：廣告商雖然可以直接設定目標族群的人口統計條件，但該條件下的使用者並不一定符合廣告商需求，且條件的設定也導致受眾人數產生損耗。

### 方法：提出 Lookalike 模型，透過分析現有目標群體的使用者行為，尋找相似的潛在客戶，進行瞄準性廣告投放。
### 流程：
1. 進行`關鍵字分析`：透過斷詞、過濾停用詞、統一詞性、並賦予各字詞分數，進而找出關鍵字。
   >計算指標：comment（文章評論數）, reaction（文章回應數）, follower（追蹤人數）作為計算分數的三個指標，以衡量互動、聲量成效。
   >1. comment（文章評論數）表示發文所引起的興趣和參與程度。更多的評論意味著你的內容激發了討論和交流。
   >2. reaction（文章回應數）指的是對發文內容進行點讚、讚賞、喜歡、關心等互動操作。更多的反應代表著你的內容引起了讀者的共鳴和興趣；
   >以上兩個指標顯示該LinkedIn用戶是否有真實受眾，且當忠誠度、互動皆良好時，社群號召力較強。
   >3. follower（追蹤人數）反映了使用者在LinkedIn上的認知度和影響力。為使品牌或商品能在短時間獲得較大的網路曝光，廣告主可能選擇紛絲數量高的LinkedIn用戶就有機會提升網路聲量，近一步提升市場認知度。
   >計算方法：使用簡單平均算出各字詞的三個分數（comment, reaction, follower）並標準化消除量級差異。

2. `聚類`：將分數相近的詞組合找出lookalike audience。
   >聚類方法：使用K-means和Hierarchical clustering model。

3. `Cosine similarity`：將分群後各群中的字詞和產業、興趣及行為特徵等自訂指標比對，去進行更精準的廣告投放。

### 結論：建立新廣告投放機制。
在 `廣告開始前`，使用Lookalike model進行客戶選擇、產品設計和整體品牌策略。
>幫助廣告主更好地理解他們的現有受眾，並擴展到與現有受眾相似的潛在客戶，有助於提高廣告的準確性、效果和回報率，並促進業務增長。
>擴大潛在客戶基礎：廣告LOOKALIKE模型可以根據現有受眾的特徵和行為模式，識別並選擇與其相似的潛在客戶。
>提高廣告的精準度：通過使用LOOKALIKE模型，廣告主可以更準確地定位具有相似特徵的潛在客戶，減少廣告浪費，並增加轉換率。

在`廣告開始後`，使用LinkedIn原有的segmentation model，幫助企業確定如何細分市場，如使用不同的標準和變數像是地理位置、年齡、性別、興趣等，以更好地了解目標受眾並制定相應的營銷策略。
