# onigiri war ルール
※ルールは基本的な部分は決定しましたが、
障害物の配置やポイント配分など当日までに微調整をする場合があります。
変更があった場合はなるべく早くお知らせいたします。

## 基本ルール

ロボットを自律移動させ１対１で打ち合うゲームです。

主砲の代わりに正面のカメラでターゲット(ARマーカー)を読み取ります.

ターゲットを読み取ったIDを審判サーバーに提出すると、その的を撃ち落としたということになります。

ロボットは完全自律とし、スタート後に手動でのいかなる操作も禁止します。

## フィールド
**ターゲット配置**
![demo](onigiri_war_target.gif)

フィールドは**3.5m**四方の壁で囲われた空間です。お弁当箱をモチーフにしています。

フィールドにはおかず型の障害物が設置されています。設置初期位置は常に同じです。障害物は簡単には動きにくいよう設置していますが、動いた場合も試合は続行します。壁はロボットで押しても動かないように固定しています。

床は会場の板張りの床をそのまま使用します。

## 勝敗の決定方法
ターゲットを撃ちぬくとポイントを獲得できます。
また、相手背後のターゲットは撃ちぬいた瞬間に勝利が確定します。（１本勝ち）

配点
- 背後    ： 勝利確定
- 左右    ： 5ポイント
- フィールド ：１ポイント

＊＊制限時間３分間＊＊以内に１本勝ちまたは終了時にポイントが多い方の勝利となります。両者同点の場合は、最終ポイントを獲得した時刻の早い方の勝利となります。両者ポイント無しのまま終了した場合は.じゃんけんで勝敗を決めます。

審判へのターゲットIDの提出を10回間違えるとその時点で失格とします。

ドクターストップあり.機体に著しい負担がかかり故障や事故が予想されるなど危険と審判が判断した場合は試合を中断し、失格とする場合があります。

## リトライ
開始15秒は各チーム1回づつ再スタートの権利があります。これは、トラブルによりマシンが全く動かないや初期化のミスなどへの救済措置です。
**3分間**のインターバルの後、試合を再開します。

## ターゲット

**ターゲット画像**
![demo](onigiri_war_target.gif)

**ターゲット配置**
![demo](onigiri_war_target.gif)

ターゲットは直径12ｃｍの円形です.

中心にARマーカーが印刷されています。

機体に取り付けるターゲットと、フィールどに設置されたターゲットがあり、機体のターゲットは緑、フィールドのターゲットは青色をしています。

**機体のターゲット**は上の画像のように左右１枚づつ、背後１枚の計**3枚**。**フィールドのターゲット**は点対称に**12枚**設置します。

## 開始シーケンス
開始地点にロボットをセットした状態を開始待ち状態とします。
開始待ち状態から、審判の開始の合図のあと機体が動いた段階で開始完了とします。
開始の合図を前に機体を動かした場合は再度両者を開始待ち状態に戻します。(フライング)
フライング3回で失格とみなします。フライングの判断は審判が行います。
開始完了までは、スイッチの押下、SSH接続による操作などの手動での操作を許可します。

審判の開始の合図の後、すみやかにロボットを開始させてください。
ロボットが動いた段階で開始完了みなし、それ以降の手動での操作を禁止します。

開始待ちの状態で、ロボットの電源を入れ、プログラムの起動、初期化、パラメータの読み込み、審判サーバーへの接続確認などの処理を行うことを許可します。
審判の開始の合図まで移動すること(フライング)がないようにご注意ください。

## ロボット
ロボットはONIGIRI_BOT使用します。

使用可能なセンサは以下です。
- カメラ：realsense r200 
- Lidar ：日立LG　Lidar
- 左右斜め前方赤外線測距センサ 2個
- 前方バンパースイッチ　2個

## 外部PCの使用
ロボットにはJetsonTX1が搭載されており、単体でROSを動かすことが出来ます。
それに加えて、計算負荷分散やモニタリングのためにロボット以外の外部PCを試合で使用することを許可します。
各チームに割り当てられたIPを使用することをくれぐれもお守りください。
ネットワークに著しい負荷をかける行為も控えるようお願いします。

ex)/imgae_raw トピックの転送. commpressed imgageなどサイズの小さい画像をお使いください。

##　ネットワーク
各チームに固定のIPを3(個程度の予定)振り分けます。ロボットや、外部PCは割当のIPで使用してください。
全チームがネットワークを共有する予定なので、重たい生動画の転送などネットワークに著しく負荷をかける行為は控えるようお願いします。
