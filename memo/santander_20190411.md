# Santander Customer Transaction Prediction

link: https://www.kaggle.com/c/santander-customer-transaction-prediction


- 効いた特徴量、jump upした特徴量はよく吟味する
  - count encodingが効いた -> count=1でのmaskが効く
  - count=1 => x, count>=2 => 0とか
- categorical feature(もしくはcategorical featureとみなせるfeature)のencodingは何が効くかわからない
  - いろいろ試してみて効いたものを吟味
- テーブルコンペでもheatmapでのEDAは結構わかりやすい
  - 特徴を2軸にプロット -> target value ratioとかわかりやすい
- num_leavesが小さい方が精度が良い場合交互作用が小さい
  - num_leaves=2 -> 交互作用がない
  - num_leaves=3 -> 特定のfeatureで交互作用がある
- 確率密度分布が特徴量ごとに相関が高い
  - 同じfeatureとみなせる
  - unstackでデータ量を水増し
  - shuffle augumentationで精度が変わらないことからもこれがわかる
- 自分の実験を信じる
