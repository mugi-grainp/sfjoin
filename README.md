# sfjoin - Sort-Free Join Command

## 説明

UNIX join コマンドと似た機能を提供。データ結合のためのソートが不要。

ただし、結合するファイルがともに巨大であるような場合はメモリを大量消費するおそれがある。

```
# sfjoin.rb
# Sort-Free Join Command
# データ行のソート無しで2つのテキストファイルを指定したフィールドで結合する
#
# Usage
#     ruby sfjoin.rb [options] FILE1 FILE2
# 引数
#     FILE1            結合するファイル1
#     FILE2            結合するファイル2
# オプション
#     -m JOIN_METHOD   結合の種類
#             'INNER'  内部結合 (デフォルト)
#             'LOUTER' 左外部結合
#     -1 FIELD         FILE1の結合キー (列番号で指定)
#     -2 FIELD         FILE2の結合キー (列番号で指定)
#     -t CHAR          フィールド区切り
#     -e EMPTY         空白フィールドを置き換える文字列
#     -j FIELD         '-1 FIELD -2 FIELD'と同値
# 出力
#     列の出力は、まずFILE1の全列を出力し、FILE2のうち結合キー列を除く全列を、
#     ファイル中に記載した順序で出力する。
# 注記
#     *1  FILE2の全行をメモリに載せるため、FILE2のサイズは小さい方が良い
#        (FILE1は1行ずつ処理するため、理論上どのようなサイズであっても良い)
```

## 今後の予定

- [ ] フィールド出力順序指定 (UNIX joinコマンドの o オプション) 実装の検討
