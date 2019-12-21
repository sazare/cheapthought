# Unification Theoryのメモ

## ソース
Unification theory
by Franz Baader, Wayne Snyder
Chapter 8 HANDBOOK OF AUTOMATED REASONING
Edited by Alan Robinson and Andrei Voronkov
(c) Elsevier Science Publishers B.V., 2001
url:http://www.cs.bu.edu/~snyder/publications/UnifChapter.pdf

## 感想
Unification Theoryだけで1章になっていて、話が絞り込まれているので読みやすい。
この章だけがpdfで拾えた。参照しているところに"?"とか書かれているので、下書きなのだろう。
2001年の本なので、比較的新しく、unification algorithmのいくつかのバリエーションであるとか
substitutionの表記方法/定義など知りたいことが書かれている。


## 概要
unificationの歴史から書かれていて、あらためて面白かった。
Shifting lemma(だったか)はHerbrandが考えたものであるとか
そのときHerbrand自身はunificationという言葉を与えなかったとか、
unificationという言葉自体はRobinsonが考えたとか。

## 定義の特徴
・全体として変数記号の集合Vとか関数記号の集合Fを決めていて、varsのようなものは考えない。
・つまり、termのある記号を変数とみたり定数とみたりという切替えはしない
・

### 代入に関する性質(?)としてidempotentをあげているが、
これはunificationのinside checkに相当するはず。

idempotentが代入の定義なのか、その一部に対する性質なのか??
これが定義なら、{x->f(y),y->g(z),z->a}というようなものは代入とみとめられない。


## 代入
表現は{x⇨t, y⇨s, ...}という形(⇨は'|->' を一文字にした矢印で、latexなら書けるけど直接入力できなかった)
{x⇨t;y⇨s;...}という書き方もある。

代入の意味は、tσの定義は漠然としていたが、σθの計算方法を見ると、そこでわかる。
1) σの右にθをかける => σ1
2) θからσの左(変数)への代入を全部消す => θ1
3) σ1から x=>xの形のものをすべて消す => σ2
4) σ2∪θ1 == σθ


