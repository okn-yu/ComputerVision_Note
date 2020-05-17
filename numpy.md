### Numpy配列の基礎
* np.ndarrayはN次元配列を扱うためのクラス
* Numpyを利用しない場合は、Pythonでは多重リストを用いてN次元配列を表す
* 多重リストよりも高速に処理ができる
* 1次元の場合はベクトルに、2次元の場合は行列に、3次元の場合はテンソルに該当する
* np.ndarrayは、np.arrayの引数にarray_like型のオブジェクトを与えて生成する
* ベクトルはリスト、行列は2重にネストしたリストで表す

### ndarrayの次元
* size：ndarrayの全要素数
* shape：ndarrayの形状をタプルで表したもの
* axis：shapeのインデックス（多次元配列の次元）に対応
* ndim：ndarrayの次元数（= len(shape)）
* reshape：size数が同じとなる範囲内においてreshapeで形状が変換できる

### 行ベクトル・列ベクトルの具体例
* ndarrayの本質は多次元配列（ネストしたリスト）である
* ネストの数はndimと一致する
* 全て以下の組み合わせである
* R次元の行ベクトルの形状は(R,)、つまりネストがないリスト
* R次元の列ベクトルの形状は(R, 1)、つまり二重にネストしたリスト

```
In [15]: a = np.array([1,2,3,4,5]) # ただの１次元配列
In [16]: a
Out[16]: array([1, 2, 3, 4, 5])
In [17]: a.shape
Out[17]: (5,)
In [18]:a.ndim
Out[18]: 1

In [17]: b = np.array([[1], [2], [3], [4], [5]]) # 縦ベクトルのようにすると(R,1)の形になる。
In [18]: b  
Out[18]:
array([[1],
       [2],
       [3],
       [4],
       [5]])
In [19]: b.shape
Out[19]: (5, 1)
In [20]: b.ndim
Out[60]: 2
```

### テンソルの積
* "A * B"と"numpy.multiply(A, B)"はどちらも対応する要素毎に積を取る
* そのため演算前後でshapeは変化しない
* "np.matmul"は行列積を計算する
* そのため演算前後でshapeは変化する

* 参照：http://segafreder.hatenablog.com/entry/2017/01/09/203811
