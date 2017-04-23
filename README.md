# VGG16_Demo.py
VGG16のモデルで入力画像のクラス分類を行います。
`python VGG16_Demo.py input_image.jpg`

# ResNet50_Demo.py
ResNet50のモデルで入力画像のクラス分類を行います。
`python ResNet50_Demo.py input_image.jpg`

# Fine Tuning
VGG16のモデルでfine tuningを行います。
学習済みのネットワークを別のクラス分類のタスク用にチューニングします。
ゼロからVGG16を学習すると時間がかかりますが、特徴抽出部分は学習済みなので、新しいタスクに対しても短時間で学習できます。特徴抽出部分のネットワークはタスクが違ってもある程度共通しているという性質を利用しています。
## データ準備
クラス分類したい画像をクラス別のディクレクトリに分け、data/に入れます。訓練用と検証用に分ける必要があります。
## 学習
適宜、コードのパラメータ（学習回数など）を書き換えてから実行してください。
`python ft_VGG16_yorkie.py`
3クラス各50画像, 500 epoch, MBPで8時間かかりました。
学習結果はresult/に保存されます。
## 推定
fine tuning完了後、画像の分類を実行します。
`python pred_ft_VGG16.py input_image.jpg`
