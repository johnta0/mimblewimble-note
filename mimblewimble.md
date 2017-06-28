# Mimblewimbleについてのメモ

## 概要
Bitcoinはtransactionsをpublic に公開することによって、trusted third party による検閲・検証なしに
その改竄不可能性を保っている。しかしそれは同時にプライバシーの問題や通貨のファンジビリティの問題
もはらんでいる。

そこで、Mimblewimbleが考え出された。サイドチェーンにそれを組み込むことでScalabilityとFungiilityの問題を解決できるらしい。

## Technical 概要

### 秘匿トランザクション

confidential transaction では、inputやoutputの値はblinding factorによって全て暗号化されるが、暗号文で行う計算と平文で行う計算が一致するように暗号化される。
すなわち暗号化はされるが、その暗号化されたoutputとinputの値を全部足し合わせるとゼロになり、トランザクションは有効だと示される。

transactionは、receiverが受け取った量を解読できるblinding factorが含まれているので、送信者と受信者は両方、金額を確認できる。

