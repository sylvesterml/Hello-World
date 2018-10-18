# Born Again Neural Networks  
2017 NIPS workshop  Tommaso Furlanello, Zachary C. Lipton, Michael Tschannen, Laurent Itti, Anima Anandkumar  
  
URL:http://export.arxiv.org/pdf/1805.04770  
  
## どんなもの？  
これまで，Knowledge Distillation（蒸留）はモデルの軽量化を図るための手段として扱われてきた．
提案手法であるBAN（Born Again Networks）はKnowledge Distillation（蒸留）をモデルの精度向上を図る手段として用いる．

## どうやって有効だと検証した？  
実験に使用したデータセット：CIFAR-10/100（画像データ），PTB（Penn Tree Bank）（英語コーパス）  
### CIFAR-10/100に関する実験  
■BANの精度に関する検証
使用したモデル  
- teacher model：DenseNet，student model：DenseNet  
→teacher modelとstudent modelが同等のモデルであるときの検証  
- teacher model：DenseNet，student model：ResNet  
→teacher modelが大規模モデルでstudent modelが小規模モデルであるときの検証  
- teacher model：DenseNet，student model：WideResNet or bottleneck-ResNet  
→teacher modelが大規模モデルでstudent modelが中規模モデルであるときの検証  
  
■Dark Knowledgeが提案手法に及ぼす効果に関する検証  
2種類の実験を行い，効果を検証  
- CWTM（Confidence-Weighted by Teacher Max）→Dark Knowledge内の値を全て0にしてstudent modelの学習を行う  
- DKPP（Dark Knowledge with Permuted Predictions）→Dark Knowledge内の値をシャッフルしてstudent modelの学習を行う  
  
### PTBに関する実験  
■BANの精度に関する検証  
使用したモデル
- a single layer LSTM  
→ユニット数が1500のモデル  
- CNN-LSTM  
→畳み込み層とハイウェイ層と2層のLSTMを組み合わせたもので，上のモデルよりも小さい  
  
## 技術や手法の肝は？
■
