Media
=====

`Media` オブジェクトは、デバイス上でのオーディオファイルの再生や録音などといった機能をサポートします。


    var media = new Media(src, mediaSuccess, [mediaError]);


注意: 現在の実行環境はメディアキャプチャに関するW3Cの仕様要件を満たしていないため、便宜上のオブジェクトとして扱われます。
将来的には最新のW3C仕様に合わせるとともに、現在のAPIを破棄することも検討されています。

パラメータ
----------

- __src__: オーディオコンテンツを示すURIを指定します _(DOMString)_
- __mediaSuccess__: (オプション) `Media` オブジェクトが再生、録音、停止などのアクションを完了したときに呼ばれるコールバック関数を指定します _(Function)_
- __mediaError__: (オプション) エラーが発生時に呼ばれるコールバック関数を指定します _(Function)_

メソッド
-------

- media.getCurrentPosition: オーディオファイル内の現在の再生位置を返します。
- media.getDuration: オーディオファイルの再生時間を返します。
- media.play: オーディオファイルの再生を開始・再開します。
- media.pause: オーディオファイルの再生を停止します。
- media.release: OSのオーディオリソースを開放します。
- media.startRecord: オーディオファイルの録音を開始します。
- media.stopRecord: オーディオファイルの録音を停止します。
- media.stop: オーディオファイルの録音を中止します。

サポートされているプラットフォーム
-------------------

- Android
- iOS

iOS に関する注意点
----------
- コールバック関数の範囲は常にグローバルに設定してください。(version 0.9.4 以下).
- メディアコンストラクタ内で、iOSは再生の準備のためにiOS内に用意されたメソッドを利用してファイルをオーディオプレイヤーにロードします。
オプションとしてdownloadCompleteCallbackをパラメータとしてメディアコンストラクタに渡すことができます。このパラメータは呼び出しの準備が完了した際に呼び出されます。
