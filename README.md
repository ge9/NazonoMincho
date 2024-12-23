# 謎乃明朝
謎乃明朝(NazonoMincho)は[花園明朝](http://fonts.jp/hanazono/)と同じく[GlyphWiki](https://glyphwiki.org/wiki/GlyphWiki:%E3%83%A1%E3%82%A4%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8)に登録されている漢字データをもとに作成されたフリーフォントです。
オリジナルの花園明朝との主な違いは以下の通りです。
- 英数字、ひらがな、カタカナ、々〆〇等の非漢字の収録無し（一部の囲み記号など含めて現在検討中）
- 最新のUnicode15.0、IVDの2022-09-13改正などに対応
- 4つの書体を提供
  - 従来のKAGE engine（[kurgmさんのTypeScript版](https://github.com/kurgm/kage-engine)）を使用した"Classic"
    - （グリフの高さなどを除けば）従来の花園明朝と同様の形状
  - 改変したKAGE engine https://github.com/ge9/kage-engine-2 による"Light", "Regular", "Medium"の3ウェイト
    - 曲線部分のデータを折れ線ではなく3次ベジェ曲線で表現
    - ハネの曲線化、縦画のコブのサイズ増加など
    - いくつかのカスタマイズ部品の使用による見た目の改善（犭や氵や阝など）
    - DemiBoldの提供も検討しているが、ストロークが太くなるため見た目に課題があり準備中
- PostScriptアウトラインのOpenTypeフォントと、ヒント命令が付加されたTrueTypeフォントの2フォーマットで提供
  - 後者は小さいサイズでもビットマップフォントのようにくっきり表示されるが、サイズが大きい。基本的には前者を推奨。
# 字形変化の例

![](https://turgenev.cloudfree.jp/misc/nazomin.png)

# 収録グリフ
OpenTypeフォントの仕様上、1フォントに65535文字までしか入らないため、「謎乃明朝」「謎乃明朝+」の2つに分かれています。日本で通常使われる漢字のほとんどは「謎乃明朝」のほうに入っています。
またここで挙げたもの以外に、両者に共通して、notdef（いわゆる「豆腐」）、半角・全角スペース及び縦書き用スペースが収録されています。

#### 謎乃明朝…よく使われる漢字、異体字、第三漢字面の漢字
- CJK統合漢字
- CJK統合漢字拡張A, G, H
- 康煕部首・CJK部首補助
- CJK互換漢字・CJK互換漢字補助（SVSによる利用にも対応）
- IVDの異体字（IVSによる利用に対応）
- SVS・IVSが定義されている全てのCJK統合漢字
- [Source Han Sans](https://github.com/adobe-fonts/source-han-sans)（源ノ角ゴシック）に含まれる全てのCJK統合漢字

これはメイリオや源ノ明朝に収録されている全ての漢字を含みます。合計50000グリフ程度です。

#### 謎乃明朝+…第二漢字面のCJK統合漢字
- CJK統合漢字拡張B-F, I

一部、「謎乃明朝」と重複して収録されている文字があります。合計60000グリフ程度です。

# 使い方
[リリースページ](https://github.com/ge9/NazonoMincho/releases)からダウンロードできます。ライセンスは花園明朝に準じます（事実上のパブリックドメイン）。

漢字のみのフォントであるため、他の日本語フォントとの併用を主に想定しています。その際に役立つ情報などは今後追加予定です。

これは実験的なリリースであり、不具合が含まれている可能性があります。また、元になっているGlyphWikiのデータは誰でも編集可能であり、漢字データや生成プログラムの表現力の不足により不自然なデザインになっている字もあります。十分注意のうえご利用ください。

# 技術的情報
- 生成に用いたスクリプト群は[ge9/kage-afdko-toolkit: Building Fonts from KAGE Data with AFDKO](https://github.com/ge9/kage-afdko-toolkit)に公開してあります。
- パスの統合（Union）に[Inkscape](https://inkscape.org/)（Classic以外）と[js-angusj-clipper](https://github.com/xaviergonz/js-angusj-clipper)（Classic）、パスの単純化に[FontForge](https://fontforge.org/)（Classic以外）、フォントデータの生成には[AFDKO](https://github.com/adobe-type-tools/afdko)を使用しています。
