```mermaid
graph TD
A[開始]
B[整数を入力]
C{10以上}
D[/loop start<br>i=0;i<10;i++\]
E[iの値を出力]
F[\loop end/]
G[終了]

A-->B
B-->C
C--はい-->D
C--いいえ-->G
D-->E
E-->F
F-->G
```