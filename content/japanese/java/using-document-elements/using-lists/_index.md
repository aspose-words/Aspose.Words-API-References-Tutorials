---
title: Aspose.Words for Java でのリストの使用
linktitle: リストの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: このステップバイステップのチュートリアルで、Aspose.Words for Java でのリストの使用方法を学習します。文書を効果的に整理し、書式設定します。
type: docs
weight: 18
url: /ja/java/using-document-elements/using-lists/
---

この包括的なチュートリアルでは、Microsoft Word ドキュメントをプログラムで操作するための強力な API である Aspose.Words for Java でリストを効果的に使用する方法を説明します。リストは、ドキュメント内のコンテンツを構造化および整理するために不可欠です。リストの操作に関する 2 つの重要な側面、つまり各セクションでのリストの再開とリスト レベルの指定について説明します。飛び込んでみましょう！

## Aspose.Words for Java の概要

リストの操作を始める前に、Aspose.Words for Java について理解しましょう。この API は、Java 環境で Word ドキュメントを作成、変更、操作するためのツールを開発者に提供します。これは、単純なドキュメント生成から複雑な書式設定やコンテンツ管理まで、さまざまなタスクに対応する多用途のソリューションです。

### 環境のセットアップ

まず、Aspose.Words for Java が開発環境にインストールされ、設定されていることを確認してください。ダウンロードできます[ここ](https://releases.aspose.com/words/java/). 

## 各セクションのリストを再開する

多くのシナリオでは、文書の各セクションでリストを再開する必要がある場合があります。これは、レポート、マニュアル、学術論文など、複数のセクションからなる構造化文書を作成する場合に役立ちます。

Aspose.Words for Java を使用してこれを実現する方法のステップバイステップ ガイドを次に示します。

### ドキュメントを初期化します。 
まず、新しいドキュメント オブジェクトを作成します。

```java
Document doc = new Document();
```

### 番号付きリストを追加します。 
番号付きリストを文書に追加します。デフォルトの番号付けスタイルを使用します。

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### リスト設定を構成します。 
\各セクションでリストを再開できるようにします。

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### DocumentBuilder のセットアップ: 
DocumentBuilder を作成して、ドキュメントにコンテンツを追加します。

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### リスト項目を追加します。 
ループを使用してリスト項目をドキュメントに追加します。 15 番目の項目の後にセクション区切りを挿入します。

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### ドキュメントを保存します。 
必要なオプションを指定してドキュメントを保存します。

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

これらの手順に従うことで、各セクションから再開するリストを含むドキュメントを作成し、明確で整理されたコンテンツ構造を維持できます。

## リストレベルの指定

Aspose.Words for Java ではリスト レベルを指定できます。これは、ドキュメント内で異なるリスト形式が必要な場合に特に便利です。これを行う方法を見てみましょう。

### ドキュメントを初期化します。 
新しいドキュメント オブジェクトを作成します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 番号付きリストを作成します。 
Microsoft Word から番号付きリストのテンプレートを適用します。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### リスト レベルを指定します。 
さまざまなリスト レベルを反復処理し、コンテンツを追加します。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 箇条書きリストを作成します。 
それでは、箇条書きリストを作成してみましょう。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### 箇条書きリストのレベルを指定します。 
番号付きリストと同様に、レベルを指定してコンテンツを追加します。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 停止リストのフォーマット: 
リストの書式設定を停止するには、リストを null に設定します。

```java
builder.getListFormat().setList(null);
```

### ドキュメントを保存します。 
文書を保存します。

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

これらの手順に従うと、カスタム リスト レベルを使用してドキュメントを作成し、ドキュメント内のリストの書式設定を制御できるようになります。

## 完全なソースコード
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        // IsRestartAtEachSection は、コンプライアンスが OoxmlComplianceCore.Ecma376 よりも高い場合にのみ書き込まれます。
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Microsoft Word リスト テンプレートの 1 つに基づいて番号付きリストを作成します。
        //そしてそれをドキュメントビルダーの現在の段落に適用します。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        //このリストには 9 つのレベルがあります。すべて試してみましょう。
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        // Microsoft Word リスト テンプレートの 1 つに基づいて箇条書きリストを作成します。
        //そしてそれをドキュメントビルダーの現在の段落に適用します。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        //これはリストの書式設定を停止する方法です。
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //テンプレートに基づいてリストを作成します。
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        //最初のリストを再利用するには、元のリストの書式設定のコピーを作成して、番号付けをやり直す必要があります。
        List list2 = doc.getLists().addCopy(list1);
        //新しい開始番号の設定など、任意の方法で新しいリストを変更できます。
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## 結論

おめでとう！ Aspose.Words for Java でリストを効果的に操作する方法を学習しました。リストは、ドキュメント内のコンテンツを整理して表示するために非常に重要です。各セクションでリストを再開する必要がある場合でも、リスト レベルを指定する必要がある場合でも、Aspose.Words for Java はプロフェッショナルな外観のドキュメントを作成するために必要なツールを提供します。

これらの機能を自信を持って使用して、ドキュメントの生成と書式設定のタスクを強化できるようになりました。ご質問がある場合、またはさらにサポートが必要な場合は、お気軽にお問い合わせください。[Aspose コミュニティ フォーラム](https://forum.aspose.com/)サポートのための。

## よくある質問

### Aspose.Words for Java をインストールするにはどうすればよいですか?
 Aspose.Words for Java は次からダウンロードできます。[ここ](https://releases.aspose.com/words/java/)ドキュメントのインストール手順に従ってください。

### リストの番号付け形式をカスタマイズできますか?
はい、Aspose.Words for Java には、リストの番号付け形式をカスタマイズするための広範なオプションが用意されています。詳細については、API ドキュメントを参照してください。

### Aspose.Words for Java は、最新の Word ドキュメント標準と互換性がありますか?
はい、ISO 29500 を含むさまざまな Word ドキュメント標準に準拠するように Aspose.Words for Java を構成できます。

### Aspose.Words for Java を使用して、表や画像を含む複雑なドキュメントを生成できますか?
絶対に！ Aspose.Words for Java は、表、画像などを含む高度なドキュメント書式設定をサポートしています。例についてはドキュメントを確認してください。

### Aspose.Words for Java の一時ライセンスはどこで入手できますか?
仮免許を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
