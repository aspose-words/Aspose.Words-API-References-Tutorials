---
title: Aspose.Words for Java でのドキュメントの印刷
linktitle: 文書を印刷する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメントを印刷する方法を学びます。 Java アプリケーションでシームレスに印刷するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/java/printing-documents/printing-documents/
---

Aspose.Words for Java を使用してドキュメントを印刷したい場合は、ここが正しい場所です。このステップバイステップ ガイドでは、提供されたソース コードを使用して、Aspose.Words for Java でドキュメントを印刷するプロセスについて説明します。

## 導入

ドキュメントの印刷は、多くのアプリケーションで一般的なタスクです。 Aspose.Words for Java は、Word ドキュメントを操作するための強力な API (印刷機能など) を提供します。このチュートリアルでは、Word 文書を印刷するプロセスを段階的に説明します。

## 環境のセットアップ

コードに入る前に、次の前提条件が満たされていることを確認してください。

- Java 開発キット (JDK) がインストールされている
- Aspose.Words for Java ライブラリがダウンロードされ、プロジェクトに追加されました

## ドキュメントをロードする

まず、印刷する Word 文書をロードする必要があります。交換する`"Your Document Directory"`ドキュメントへのパスと`"Your Output Directory"`目的の出力ディレクトリを指定します。

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Rendering.docx");
```

## 印刷ジョブの作成

次に、読み込んだドキュメントを印刷するための印刷ジョブを作成します。以下のコード スニペットは、印刷ジョブを初期化し、必要なプリンター設定を設定します。

```java
//ドキュメントを印刷するための印刷ジョブを作成します。
PrinterJob pj = PrinterJob.getPrinterJob();
//ドキュメント内のページ数を使用して属性セットを初期化します。
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
//プリンター設定を他のパラメーターとともに印刷ドキュメントに渡します。
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
```

## 文書を印刷する

印刷ジョブの設定が完了したので、今度はドキュメントを印刷します。次のコード スニペットは、ドキュメントを印刷ジョブに関連付け、印刷プロセスを開始します。

```java
//印刷ジョブを使用して印刷するドキュメントを渡します。
pj.setPrintable(awPrintDoc);
pj.print();
```
## 完全なソースコード
```java
string dataDir = "Your Document Directory";
Document doc = new Document(dataDir + "Rendering.docx");
//ドキュメントを印刷するための印刷ジョブを作成します。
PrinterJob pj = PrinterJob.getPrinterJob();
//ドキュメント内のページ数を使用して属性セットを初期化します。
PrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
attributes.add(new PageRanges(1, doc.getPageCount()));
//プリンター設定を他のパラメーターとともに印刷ドキュメントに渡します。
MultipagePrintDocument awPrintDoc = new MultipagePrintDocument(doc, 4, true, attributes);
//印刷ジョブを使用して印刷するドキュメントを渡します。
pj.setPrintable(awPrintDoc);
pj.print();
```
MultipagePrintDocumentのソースコード
```java
class MultipagePrintDocument implements Printable
{
    private final Document mDocument;
    private final int mPagesPerSheet;
    private final boolean mPrintPageBorders;
    private final AttributeSet mAttributeSet;
    /// <概要>
    //カスタム PrintDocument クラスのコンストラクター。
    // / </概要>
    public MultipagePrintDocument(Document document, int pagesPerSheet, boolean printPageBorders,
                                  AttributeSet attributes) {
        if (document == null)
            throw new IllegalArgumentException("document");
        mDocument = document;
        mPagesPerSheet = pagesPerSheet;
        mPrintPageBorders = printPageBorders;
        mAttributeSet = attributes;
    }
    public int print(Graphics g, PageFormat pf, int page) {
        //属性セットで定義されているページの開始インデックスと終了インデックス。
        int[][] pageRanges = ((PageRanges) mAttributeSet.get(PageRanges.class)).getMembers();
        int fromPage = pageRanges[0][0] - 1;
        int toPage = pageRanges[0][1] - 1;
        Dimension thumbCount = getThumbCount(mPagesPerSheet, pf);
        //次にレンダリングされるページのインデックスを計算します。
        int pagesOnCurrentSheet = (int) (page * (thumbCount.getWidth() * thumbCount.getHeight()));
        //ページ インデックスが合計ページ範囲を超える場合は、何もありません。
        //さらにレンダリングする必要があります。
        if (pagesOnCurrentSheet > (toPage - fromPage))
            return Printable.NO_SUCH_PAGE;
        //各サムネイル プレースホルダーのサイズをポイント単位で計算します。
        Point2D.Float thumbSize = new Point2D.Float((float) (pf.getImageableWidth() / thumbCount.getWidth()),
                (float) (pf.getImageableHeight() / thumbCount.getHeight()));
        //この用紙に印刷される最初のページの番号を計算します。
        int startPage = pagesOnCurrentSheet + fromPage;
        //この用紙に印刷する最後のページの番号を選択します。
        int pageTo = Math.max(startPage + mPagesPerSheet - 1, toPage);
        //保存されている現在のページから計算されたページまで、選択したページをループします。
        //最後のページ。
        for (int pageIndex = startPage; pageIndex <= pageTo; pageIndex++) {
            //列と行のインデックスを計算します。
            int rowIdx = (int) Math.floor((pageIndex - startPage) / thumbCount.getWidth());
            int columnIdx = (int) Math.floor((pageIndex - startPage) % thumbCount.getWidth());
            //サムネイルの位置をワールド座標 (この場合はポイント) で定義します。
            float thumbLeft = columnIdx * thumbSize.x;
            float thumbTop = rowIdx * thumbSize.y;
            try {
                //左と上の開始位置を計算します。
                int leftPos = (int) (thumbLeft + pf.getImageableX());
                int topPos = (int) (thumbTop + pf.getImageableY());
                //計算された座標を使用して、ドキュメント ページを Graphics オブジェクトにレンダリングします。
                //サムネイルのプレースホルダーのサイズ。
                //有用な戻り値は、ページがレンダリングされたスケールです。
                float scale = mDocument.renderToSize(pageIndex, (Graphics2D) g, leftPos, topPos, (int) thumbSize.x,
                        (int) thumbSize.y);
                //ページの境界線を描画します (ページのサムネイルはサムネイルよりも小さい場合があります)
                //プレースホルダーのサイズ)。
                if (mPrintPageBorders) {
                    //ページの実際の 100% サイズをポイント単位で取得します。
                    Point2D.Float pageSize = mDocument.getPageInfo(pageIndex).getSizeInPoints();
                    //既知の倍率を使用して、拡大縮小されたページの周囲に境界線を描画します。
                    g.setColor(Color.black);
                    g.drawRect(leftPos, topPos, (int) (pageSize.x * scale), (int) (pageSize.y * scale));
                    //サムネイル プレースホルダーの周囲に境界線を描きます。
                    g.setColor(Color.red);
                    g.drawRect(leftPos, topPos, (int) thumbSize.x, (int) thumbSize.y);
                }
            } catch (Exception e) {
                //レンダリング中にエラーが発生した場合は、何もしません。
                //レンダリング中にエラーが発生した場合、空白のページが描画されます。
            }
        }
        return Printable.PAGE_EXISTS;
    }
    private Dimension getThumbCount(int pagesPerSheet, PageFormat pf) {
        Dimension size;
        //シート上の列と行の数を定義します。
        //横向きの紙。
        switch (pagesPerSheet) {
            case 16:
                size = new Dimension(4, 4);
                break;
            case 9:
                size = new Dimension(3, 3);
                break;
            case 8:
                size = new Dimension(4, 2);
                break;
            case 6:
                size = new Dimension(3, 2);
                break;
            case 4:
                size = new Dimension(2, 2);
                break;
            case 2:
                size = new Dimension(2, 1);
                break;
            default:
                size = new Dimension(1, 1);
                break;
        }
        //用紙が縦向きの場合は、幅と高さを入れ替えます。
        if ((pf.getWidth() - pf.getImageableX()) < (pf.getHeight() - pf.getImageableY()))
            return new Dimension((int) size.getHeight(), (int) size.getWidth());
        return size;
	}
}
```

## 結論

おめでとう！ Aspose.Words for Java を使用して Word 文書を正常に印刷できました。このステップバイステップのガイドは、ドキュメントの印刷を Java アプリケーションにシームレスに統合するのに役立ちます。

## よくある質問

### Q1: Aspose.Words for Java を使用してドキュメントの特定のページを印刷できますか?

はい、文書を印刷するときにページ範囲を指定できます。コード例では、`attributes.add(new PageRanges(1, doc.getPageCount()))`すべてのページを印刷します。必要に応じてページ範囲を調整できます。

### Q2: Aspose.Words for Java はバッチ印刷に適していますか?

絶対に！ Aspose.Words for Java は、バッチ印刷タスクに適しています。同様のコードを使用して、ドキュメントのリストを反復処理し、1 つずつ印刷できます。

### Q3: 印刷エラーや例外はどのように処理すればよいですか?

印刷プロセス中に発生する可能性のある例外には対処する必要があります。例外の処理については、Aspose.Words for Java のドキュメントを確認してください。

### Q4: 印刷設定をさらにカスタマイズできますか?

はい、特定の要件に合わせて印刷設定をカスタマイズできます。利用可能な印刷オプションの詳細については、Aspose.Words for Java ドキュメントを参照してください。

### Q5: Aspose.Words for Java に関するヘルプとサポートはどこで入手できますか?

追加のサポートと支援が必要な場合は、次のサイトにアクセスしてください。[Aspose.Words for Java フォーラム](https://forum.aspose.com/).

---

Aspose.Words for Java を使用してドキュメントを印刷する方法を学習したので、Java アプリケーションにこの機能の実装を開始できます。コーディングを楽しんでください!