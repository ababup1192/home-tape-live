# 素材の出典とライセンス

『よその子』

## シナリオ

- 藻屑

このゲームの背景は画像生成で作った物、BGM・効果音は外のフリー素材と合成の音、フォントは SIL OFL の物を使っています。
ゲームの中のクレジット（タイトル画面の「クレジット」と、物語を読み終えた後）には、このうち出典の表記が要る物を短くして流します（`assets/novel.credits.json`。背景の場面・合成した音の種類・BGM の曲名は並べない。甘茶の音楽工房と効果音ラボの規約はクレジットも曲名も任意）。
絵や音を差し替えたら、ここと `assets/novel.credits.json` の両方を書き直してください。

## 背景（画像生成）

どれも画像生成（Codex CLI の built-in image_gen・OpenAI の画像生成）で、このゲームのために作った物です。
縦の画面（スマホ）向けに、横で作った絵（`art/bg/gen.sh`）を中身と画風の参考に渡して縦の構図（約 9:19.5）で生成し直し（`art/bg/gen_tall.sh`）、720×1560 に切り抜いた（`art/bg/prepare_tall.sh`）。

| ファイル | 中身 |
|---|---|
| `assets/bg/my_room_tall.jpg` | 私の部屋（夜。弁当とスマホの載った低い机） |
| `assets/bg/house_ext_tall.jpg` | 須藤の家の外観（郊外の新しい二階建て・子ども用の自転車） |
| `assets/bg/hallway_tall.jpg` | 須藤の家の廊下（子どもの写真の額） |
| `assets/bg/sudo_room_tall.jpg` | 須藤の部屋（モニター 2 枚・外付けのハードディスク・古いビデオデッキ） |
| `assets/bg/tape_yard_tall.jpg` | 1996 年のホームビデオの一コマ風の運動会の園庭（フェンスの前に黒いワンピースの少女） |
| `assets/bg/park_tall.jpg`・`park_slide_tall.jpg`・`park_sand_tall.jpg`・`park_bench_tall.jpg`・`park_entrance_tall.jpg` | 公園（広場・滑り台・砂場・ベンチ・入口） |

背景はゲームの中でさらに、シェーダーで少しぼかし、時間帯の色（昼・夜・夕方・ホームビデオ）に色を変えて表示します（`src/Backdrop.flix`・数は `assets/novel.backdrops.json`）。
`assets/cast/_sample_plain.png` はテスト用の単色の形（`art/cast/sample.py` が作る）で、物語には出しません。

## フォント

- **しっぽり明朝**（`assets/ShipporiMincho-Regular.subset.ttf`）— Copyright 2021 The Shippori Mincho Project Authors
  （https://github.com/fontdasu/ShipporiMincho）。[SIL Open Font License 1.1](assets/OFL.txt)。
  JIS 第 1 水準の漢字・かな・英数と、シナリオに出てくる字だけを残した部分集合（サブセット）です。
  第 2 水準の字をシナリオに足した時は、元のフォントから字を足して作り直してください（作り直すまで、その字は表示されません）。
  このゲームのシナリオの第 2 水準の字（几・呟・曖・棘・頷・颯）は、`make font-subset FONT_DIR=<元のフォントのフォルダ>`（`art/font_subset.py`）で足して作り直した。
- **M PLUS 1p**（Bold。`assets/MPLUS1p-Bold.subset.ttf`）— Copyright 2016 The M+ Project Authors。[SIL Open Font License 1.1](assets/OFL-MPLUS1p.txt)。
  ホームビデオとビデオカメラの画面の英数字（REC・日付・録画の経過時間）だけに使う。シナリオ・Doc・ソースの字と英数・かなを残した部分集合（`make font-subset` で作り直す）。

## 音

| ファイル | 元の音 | 出典 | 規約 |
|---|---|---|---|
| `assets/sfx/se_intercom.wav` | 「ドアチャイム1」（玄関のピンポン） | [効果音ラボ](https://soundeffect-lab.info/) | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/sfx/se_door_open.wav` | 「ドアを開ける1」 | [効果音ラボ](https://soundeffect-lab.info/) | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/sfx/se_door_close.wav` | 「ドアを閉める1」（木のドア） | [効果音ラボ](https://soundeffect-lab.info/) | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/sfx/se_tape_insert.wav` | 「ビデオディスクをケースに入れる」を 0.72 倍速（遅く低く）にして、合成の ガチャ を重ねた物 | [効果音ラボ](https://soundeffect-lab.info/) ＋ 合成 | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/sfx/se_pistol_far.wav` | 「拳銃を撃つ」を高域を削り・歪ませ・こだまを足して遠くの音にした物 | [効果音ラボ](https://soundeffect-lab.info/) | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/sfx/se_tape_cut.wav` | ブツッ（合成） | 合成（ffmpeg と Python で生成） | 自作の合成音。規約なし |
| `assets/sfx/se_static.wav` | 砂嵐（ホワイトノイズの合成） | 合成（ffmpeg と Python で生成） | 自作の合成音。規約なし |
| `assets/sfx/se_deck_load.wav` | デッキに テープを取り込む ガチャン・モーター・カタカタ（合成） | 合成（ffmpeg と Python で生成） | 自作の合成音。規約なし |
| `assets/sfx/amb_deck_run.wav` | デッキの駆動音（モーターのうなりとカタカタ・合成。輪にして 22050 Hz モノラル） | 合成（ffmpeg と Python で生成） | 自作の合成音。規約なし |
| `assets/sfx/amb_tape_hiss.wav` | テープの回転音とザーというノイズ（合成。輪にして 22050 Hz モノラル） | 合成（ffmpeg と Python で生成） | 自作の合成音。規約なし |
| `assets/sfx/amb_sportsday.wav` | 「公園2」の子どもの声と「スタジアムのざわめき」（[効果音ラボ](https://soundeffect-lab.info/)）に、New Post Horn Galop（United States Navy Band・パブリックドメイン）を重ね、スピーカーで割れた古い録音のように帯域を 280〜5200 Hz に狭め歪ませた物（62 秒の輪・22050 Hz モノラル） | [効果音ラボ](https://soundeffect-lab.info/) ＋ United States Navy Band | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） ／ パブリックドメイン（米国政府の著作物）。クレジットは任意 |
| `assets/sfx/amb_sportsday_warped.wav` | 上の `amb_sportsday` を 0.93 倍速（遅く低く）にし、ピッチの揺れと音量の波を足した物 | [効果音ラボ](https://soundeffect-lab.info/) ＋ United States Navy Band | 上と同じ |
| `assets/sfx/amb_park.wav` | 「公園2」と「自然公園1」を重ねて輪にした物（42 秒・32000 Hz モノラル） | [効果音ラボ](https://soundeffect-lab.info/) | [効果音ラボの利用規約](https://soundeffect-lab.info/agreement/)（クレジットは任意。音のファイルの再配布・音を自由に鳴らせる画面は不可。AI の学習に使わない） |
| `assets/bgm/bgm_daily.wav` | 「3月の澄んだ空」の頭から 95 秒を切り、末尾を頭へ重ねて輪にした物（90 秒・22050 Hz ステレオ） | [甘茶の音楽工房](https://amachamusic.chagasi.com/)（甘茶） | [甘茶の音楽工房の利用規約](https://amachamusic.chagasi.com/terms.html)（クレジットは任意。加工は自由。音楽だけの再配布・Content ID への登録は不可） |
| `assets/bgm/bgm_daily_calm.wav` | 「秋うらら」の頭から 95 秒を同じく輪にした物 | [甘茶の音楽工房](https://amachamusic.chagasi.com/)（甘茶） | [甘茶の音楽工房の利用規約](https://amachamusic.chagasi.com/terms.html)（クレジットは任意。加工は自由。音楽だけの再配布・Content ID への登録は不可） |
| `assets/bgm/bgm_quiet.wav` | 「プルキンエ・フェノミナン」の頭から 100 秒を同じく輪にした物（95 秒） | [甘茶の音楽工房](https://amachamusic.chagasi.com/)（甘茶） | [甘茶の音楽工房の利用規約](https://amachamusic.chagasi.com/terms.html)（クレジットは任意。加工は自由。音楽だけの再配布・Content ID への登録は不可） |

返事の音（`ui_*`）は、`art/sfx.snd.star` から `bin/fge snd build` で合成した物です。
