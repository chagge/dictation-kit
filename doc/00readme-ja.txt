======================================================================
                  Large Vocabulary Continuous Speech
                          Recognition Engine

                                Julius

						(Rev 4.4.1 2016/09/07)
						(Rev 4.4   2016/08/30)
                                                (Rev 4.3.1 2014/01/15)
                                                (Rev 4.3   2013/12/25)
                                                (Rev 4.2.3 2013/06/30)
                                                (Rev 4.2.2 2012/08/01)
                                                (Rev 4.2.1 2011/12/25)
                                                (Rev 4.2   2011/05/01)
                                                (Rev 4.1.5 2010/06/04)
                                                (Rev 4.1   2008/10/03)
                                                (Rev 4.0.2 2008/05/27)
                                                (Rev 4.0   2007/12/19)
                                                (Rev 3.5.3 2006/12/29)
                                                (Rev 3.4.2 2004/04/30)
                                                (Rev 2.0   1999/02/20)
                                                (Rev 1.0   1998/02/20)

 Copyright (c) 1991-2016 京都大学 河原研究室
 Copyright (c) 1997-2000 情報処理振興事業協会(IPA)
 Copyright (c) 2000-2005 奈良先端科学技術大学院大学 鹿野研究室
 Copyright (c) 2005-2016 名古屋工業大学 Julius開発チーム
 All rights reserved
======================================================================

Julius について
=================

Julius は，音声認識システムの開発・研究のためのオープンソースの高性能
な汎用大語彙連続音声認識エンジンです．数万語彙の連続音声認識を一般のPC
上でほぼ実時間で実行できます．また，高い汎用性を持ち，発音辞書や言語モ
デル・音響モデルなどの音声認識の各モジュールを組み替えることで，様々な
幅広い用途に応用できます． 動作プラットフォームは Linux, Windows，
その他 Unix 環境です．


GitHub への移行について
========================

Juliusは2016年より GitHub へ移行しました．
最新のソースコード・各種実行キット・開発情報の公開・共有および
開発者向けのフォーラム運営は GitHub にて行っていきます．

        Julius on GitHub
        https://github.com/julius-speech/julius

旧ホームページには 4.3.1 以前の情報が掲載されています．
こちらもご活用下さい．

        旧 Julius Web サイト
        http://julius.osdn.jp/


Julius-4.4/4.4.1
=================

バージョン 4.4 では DNN-HMM 仕様時の DNN 計算を組み込み、単体で
DNN-HMMを用いたオンライン音声認識が行えるようになりました。
詳細は 00readme-DNN.txt をご覧ください。

新ツールとして adintool の GUI バージョンである "adintool-gui" と
バイナリN-gramを ARPA 形式に逆変換する "binlm2arpa" が追加されました．
また，"mkbingram" でバイナリN-gramを直接文字コード変換できます。
モジュールモードでクライアント切断時に落ちずに次のクライアント接続を
待つようになりました．また，いくつかのバグが修正され，最近のOSでの
コンパイルエラーを修正しました．

変更点の詳細な一覧は Release-ja.txt をご覧ください．
"configure --help=recursive" を実行することで configure に与えられる
全てのオプションを出力することができます．また，"julius --help" を
実行することで実行時オプションの全リストが出力されます。

4.4.1 は 4.4 のバグ修正バージョンです。多くのバグを修正しました。


Julius-4.4.1のファイルの構成
=============================

	00readme-ja.txt		最初に読む文書（このファイル）
	LICENSE.txt		ライセンス条項
	Release-ja.txt		リリースノート/変更履歴
	00readme-DNN.txt	DNN-HMM の使い方説明
	configure		configureスクリプト
	configure.in		
	Sample.jconf		jconf 設定ファイルサンプル
	Sample.dnnconf		DNN 設定ファイルのサンプル
	julius/			Julius ソース
	libjulius/		JuliusLib コアエンジンライブラリ ソース
	libsent/		JuliusLib 汎用ライブラリ ソース
	adinrec/		録音ツール adinrec
	adintool/		音声録音/送受信ツール adintool
	generate-ngram/		N-gram文生成ツール
	gramtools/		文法作成ツール群
	jcontrol/		サンプルネットワーククライアント jcontrol
	mkbingram/		バイナリN-gram作成ツール mkbingram
	mkbinhmm/		バイナリHMM作成ツール mkbinhmm
	mkgshmm/		GMS用音響モデル変換ツール mkgshmm
	mkss/			ノイズ平均スペクトル算出ツール mkss
	support/		開発用スクリプト
	jclient-perl/		A simple perl version of module mode client
	plugin/			プラグインソースコードのサンプルと仕様文書
	man/			マニュアル類
	msvc/			Microsoft Visual Studio 2013 用ファイル
	dnntools/		Sample programs for dnn and vecnet client
	binlm2arpa/		バイナリN-gramからARPAへの変換ツール



使用方法・ドキュメント
=======================

本アーカイブに付属しているのはソースコード，バージョン遍歴，サンプルの
jconf 設定ファイルおよび各種オンラインマニュアル(.man)のみです．

ドキュメントの多くは下記の JuliusBook に統合されました。JuliusBook を含め、
多くのドキュメントは Julius の Web ページにて最新版を見ることができま
す．すべてのオプションの説明やコンパイル方法，チュートリアルから様々な
使用方法，各機能の紹介，制限事項等の資料がありますので，そちらを御覧下
さい．

    ホームページ：http://julius.osdn/


ライセンス
===========

Julius はオープンソースソフトウェアです．
学術用途・商用を含め，利用に関して特に制限はありません．
利用許諾については，同梱の文書 "LICENSE.txt" をお読み下さい．

また以下のファイルやディレクトリ内の Copyright もご参照下さい。

  gramtools/gram2sapixml/gram2sapixml.pl.in
  libsent/src/wav2mfcc/wav2mfcc-*.c
  libsent/src/adin/pa/
  msvc/portaudio/
  msvc/zlib/


連絡先
===========

Julius 開発に関するご質問・お問い合わせは GitHub で承っております。

        Julius on GitHub
        https://github.com/julius-speech/julius

あるいは下記のメールアドレスまでお問い合わせ下さい
('at' を '@' に読み替えてください)

	julius-info at lists.sourceforge.jp

以上
