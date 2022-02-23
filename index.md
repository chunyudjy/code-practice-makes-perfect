> import glob

紹介：[https://www.tech-teacher.jp/blog/python-glob/]

globは、pythonのモジュールの1つです。pythonでは、glob関数を使うことで特定のパターンにマッチするファイルを取得することができます。
- file = glob.glob(‘test/*.txt’)

test/ディレクトリの中にある「*.txt」というパターンに一致するファイルを取得する.はワイルドカード文字と呼ばれるもので「任意の文字列」を表します


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

> print(files)

> sheet_name = "Fee-Earnings"
