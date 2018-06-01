# GLSL_Practice

GLSLの練習をしようかなと。

主にVertexShaderとFragmentShaderを編集・実行できるようにして、個人的な課題が出来たらシェーダーを追加するみたいな感じでやっていこうかなと。

# How to use

* `uniform float frame;`
    * 経過フレーム数。一応整数だがfloatでくる。
* `uniform vec2 mouse;`
    * マウス座標が帰ってくる。
    * 値の範囲は0～1
* `uniform vec2 resolution;`
    * 解像度。Canvasの大きさが入っている。
* `uniform sampler2D backbuffer;`
    * 前の描画内容。

# Memo

## バッファ切り替え

バックバッファを使いたいため、以下のようにやっている。

* まずバックバッファに真っ黒な状態を描画する
* バックバッファをシェーダーに転送し、フロントバッファに描画するようにする
* フロントバッファに描画結果が入るので、それを実際のCanvasに描画する
* バッファを入れ替える
* 上から2番目に戻る

この仕様上、勉強のために書いているシェーダーはバッファへの描画となり、実際の描画は全く別のシェーダーが必要になる。
バッファはテクスチャとして取得可能なので、完全にその中身を転写するシェーダーとなる。


# TODO

* テクスチャの指定
    * 何かに対するエフェクトとかフィルタの練習になるので。
