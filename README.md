




# mBART-translation-demo

近年、自然言語処理(NLP)の分野において事前学習モデルの単語埋め込みはNLPの様々なタスクで有用であることが証明されている。しかし、機械翻訳においては事前学習モデルを用いることはそこまで多くない。事前学習モデルを利用するモデルとゼロから学習させた翻訳モデルでは学習にかかる時間やデータの量、学習の際の工夫、翻訳の品質、エラーの種類など、具体的にどのような違いがあるのかを調べるため日本語を含めた25言語で事前学習されたmBARTを利用して英日の翻訳モデルを構築し、翻訳の品質を評価、分析を実施した。

使用技術：Python,Pytorch,fairseq,weights＆biases


mBARTを英日の言語対でファインチューニングした翻訳モデルの出力結果を確認するデモ動画です。このモデルは比較的高品質な翻訳が可能ですが、エラー分析の結果から、入力テキストが長い場合や、文構造が複雑な場合、翻訳漏れなどの問題が発生し、品質が低下することが確認できました。そのため、現在は長文や文構造が複雑な文の翻訳精度改善に取り組んでいます。


デモ動画の3番目の翻訳の例では、

input : 'The motion for summary judgment, filed Thursday in the U.S. District Court for the Southern District of New York by the Electronic Frontier Foundation (EFF) and Durie Tangri LLP, explains that our Controlled Digital Lending (CDL) program is a lawful fair use that preserves traditional library lending in the digital world.

output :  電子フロンティア基金(EFF)とデリー・タンリ LLPが米国南区で提出した「概要判決」は、当社の制御デジタル貸出(CDL)プログラムは、デジタル世界における伝統的な図書館貸出を保護する法的公正な利用であると説明しています。

となっており、一見完璧に訳せているようですが、[Thursday],[New York]の単語の訳抜けが発生してしまっています。


![ezgif com-gif-maker](https://user-images.githubusercontent.com/77151911/197336031-ed2513c6-c30f-4850-9adb-7edc8f953820.gif)

