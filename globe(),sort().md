> import glob

# glob.glob()関数

紹介：[https://www.tech-teacher.jp/blog/python-glob/]

globは、pythonのモジュールの1つです。pythonでは、glob関数を使うことで特定のパターンにマッチするファイルを取得することができます。
- file = glob.glob(‘test/*.txt’)
## 正規表現
test/ディレクトリの中にある「*.txt」というパターンに一致するファイルを取得する.はワイルドカード文字と呼ばれるもので「任意の文字列」を表します

ここでの「*」は正規表現と呼ばれる書き方の1つです。正規表現とは、文字列のパターンを表現する表記法のことであり、glob関数内でも使うことができます。


> import pandas as pd

> files = sorted(glob.glob('datapath/*.csv'))

紹介：[https://note.nkmk.me/python-list-sort-sorted/]

1. リスト型のメソッド sort(): 元のリストをソート(自体が書き換えられる破壊的処理)

|例1|
|:---:|
|org_list = [3, 1, 4, 5, 2]|
|org_list.sort()|
|print(org_list)|
|[1, 2, 3, 4, 5]|

sort()が返すのはNoneなので注意。

|例2|
|:---:|
|print(org_list.sort())|
|'No return'|

2. 組み込み関数 sorted(): ソートした新たなリストを生成

引数にソートしたいリストを指定するとソートされたリストを返す。元のリストは変更されない非破壊的処理。

|例3|
|:---:|
|org_list = [3, 1, 4, 5, 2]|
|new_list = sorted(org_list)|
|print(org_list)|
|print(new_list)|
|[3, 1, 4, 5, 2]|
|[1, 2, 3, 4, 5]|

文字列、タプルはイミュータブル（更新不可）なので、元のオブジェクトを書き換えるsort()メソッドは用意されていない。

|例4|
|:---:|
|org_str = 'cebad'|
|new_str_list = sorted(org_str)|
|print(org_str)|
|print(new_str_list)|
|# cebad|
|# ['a', 'b', 'c', 'd', 'e']|

文字列のリストを連結して一つの文字列にするにはjoin()メソッドを使う。

|例5|
|:---:|
|new_str = ''.join(new_str_list)|
|print(new_str)|
|# abcde|

タプルとは、順序付けられた複数の要素で構成される組

|例6|
|:---:|
|org_tuple = (3, 1, 4, 5, 2)|
|new_tuple_list = sorted(org_tuple)|
|print(org_tuple)|
|print(new_tuple_list)|
|# (3, 1, 4, 5, 2)|
|# [1, 2, 3, 4, 5]|

> print(files)

'datapath\\CNS_CA_char curve.CSV', 'datapath\\CNS_CA_char curve_2.CSV', 'datapath\\CNS_CA_char curve_2_BaseValue.CSV', 'datapath\\CNS_CA_char curve_BaseValue.CSV'

> sheet_name = "Fee-Earnings"
