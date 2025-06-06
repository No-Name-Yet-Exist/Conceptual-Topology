我々は単語に動詞だったり名詞だったり品詞があると思っていますが、むしろ単語の持つ関係性が動詞である、名詞であるといったほうが自然に見えます。
関係性が品詞を生むとすることで、今まで存在しなかった単語、例えば動詞として使われなかった単語も別の動詞になることができます。
「昨日車運転してて、車急に出てきてやばっちゃったんだよね。向こうは許してくれたけどショックから立ち直れない」
膠着語はタグ付けが明示的なので英語のほうがいいかもしれません。"I got bloomberged. Man, I'm a billionaire! The world is looking at me!"bloombergは名詞ですが、ここでの単語の関係性が動詞的なので動詞的に機能します(受動態)
以下品詞分類です
名詞: 単語それ自体で成り立つ identity morphism
love → love | love //愛は愛
動詞: 射の関係性を記述するラベル
I → you | love // 私からみてあなたは愛している関係性
他動詞と自動詞の区別
他動詞 (mediator morphism)
二つの対象の関係性を記述しますhe → me | Lovef: subject → object | Verb
自動詞 (terminal morphism)
射が閉じていますhe → sleep | Sleep
Terminal object に到達する morphismid_sleep: sleep → Sleep
自然言語の例I'm sleepingWhat are you doing?I'm sleepingWhat are you doing? I couldnt hear you.Sleeping! // 名詞的孤立状態 id_sleep
SVOCは 自然変換：
例： "I gave you a book"η: Hom(I, book) → Hom(book, you)
わかりやすく書くとgive = η: Possession(I, book) → Possession(you, book)
解釈:"I gave" → "transfer event""you a book" → "new ownership state"
Diagram:
I → book | Ownership_before
   |
   | η
   ↓
book → you | Ownership_after

展開するとI → book | Ownership_beforeη: Ownership_before → Ownership_afterbook → you | Ownership_after
命令形は subject が暗示されている：
Implicit_subject → verb | Z
例： "Shut up"you (implicit) → shut up| Shut up
動名詞の主語
英語ではなぜme/my doingというのでしょうか。通時的分析は少しそばに置いておいて、単純に現代英語だけ見てみます。
"Me doing this homework looks awful.""My doing this homework looks awful."
射の方向としてみるとわかります。
doing → me 動詞として見れば折り返し構造です。
doing → me → doing → homeworkη: me → me | doingmy doingは包括構造として読めますid_doing | Me
最後に:
この思考の何が良いのかというと、LLMがなぜ品詞タグなしで学習できるかわかります。LLMはその単語が動詞であるのかを学んでいるのではなく、関係性が動詞であるのかを学んでいると解釈すれば自然です。また誤った文法、学習データにない独自の用法で語彙を使用しても理解するのはここに起因していると理解できます。
