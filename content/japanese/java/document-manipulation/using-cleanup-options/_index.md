---
title: Aspose.Words for Java でのクリーンアップ オプションの使用
linktitle: クリーンアップ オプションの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java クリーンアップ オプションを使用してドキュメントの明瞭さを強化します。空の段落や未使用の領域などを削除する方法を学びます。
type: docs
weight: 10
url: /ja/java/document-manipulation/using-cleanup-options/
---

## Aspose.Words for Java でのクリーンアップ オプションの使用の概要

このチュートリアルでは、Aspose.Words for Java のクリーンアップ オプションを使用して、差し込み印刷プロセス中にドキュメントを操作およびクリーンアップする方法を説明します。クリーンアップ オプションを使用すると、空の段落や未使用領域の削除など、ドキュメントのクリーンアップのさまざまな側面を制御できます。

## 前提条件

始める前に、Aspose.Words for Java ライブラリがプロジェクトに統合されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).

## ステップ 1: 空の段落を削除する

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//差し込みフィールドを挿入する
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

//クリーンアップ オプションを設定する
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

//句読点を使用したクリーンアップ段落を有効にする
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

//差し込み印刷を実行する
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

//文書を保存する
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

この例では、新しい文書を作成し、差し込みフィールドを挿入し、空の段落を削除するクリーンアップ オプションを設定します。さらに、句読点のある段落を削除できるようにしました。差し込み印刷を実行すると、指定したクリーンアップが適用された状態で文書が保存されます。

## ステップ 2: マージされていない領域の削除

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

//未使用の領域を削除するクリーンアップ オプションを設定する
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

//地域を指定して差し込み印刷を実行する
doc.getMailMerge().executeWithRegions(data);

//文書を保存する
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

この例では、差し込み領域のある既存の文書を開き、未使用の領域を削除するようにクリーンアップ オプションを設定してから、空のデータで差し込み印刷を実行します。このプロセスにより、未使用の領域がドキュメントから自動的に削除されます。

## ステップ 3: 空のフィールドを削除する

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//空のフィールドを削除するクリーンアップ オプションを設定する
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

//差し込み印刷を実行する
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//文書を保存する
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

この例では、差し込みフィールドのある文書を開き、空のフィールドを削除するクリーンアップ オプションを設定し、データを使用して差し込み印刷を実行します。結合後、空のフィールドはドキュメントから削除されます。

## ステップ 4: 未使用フィールドの削除

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//未使用のフィールドを削除するクリーンアップ オプションを設定する
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

//差し込み印刷を実行する
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//文書を保存する
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

この例では、差し込みフィールドのある文書を開き、未使用のフィールドを削除するクリーンアップ オプションを設定し、データを使用して差し込み印刷を実行します。結合後、未使用のフィールドはドキュメントから削除されます。

## ステップ 5: 含まれるフィールドの削除

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//クリーンアップ オプションを設定して、含まれるフィールドを削除する
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

//差し込み印刷を実行する
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//文書を保存する
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

この例では、差し込みフィールドを含む文書を開き、含まれるフィールドを削除するクリーンアップ オプションを設定し、データを使用して差し込み印刷を実行します。結合後、フィールド自体はドキュメントから削除されます。

## ステップ 6: 空のテーブル行の削除

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//空のテーブル行を削除するクリーンアップ オプションを設定します。
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

//差し込み印刷を実行する
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//文書を保存する
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

この例では、テーブルと差し込みフィールドを含む文書を開き、空のテーブル行を削除するクリーンアップ オプションを設定し、データを使用して差し込み印刷を実行します。マージ後、空のテーブル行はドキュメントから削除されます。

## 結論

このチュートリアルでは、Aspose.Words for Java のクリーンアップ オプションを使用して、差し込み印刷プロセス中にドキュメントを操作およびクリーンアップする方法を学習しました。これらのオプションを使用すると、ドキュメントのクリーンアップをきめ細かく制御できるため、洗練されたカスタマイズされたドキュメントを簡単に作成できます。

## よくある質問

### Aspose.Words for Java のクリーンアップ オプションとは何ですか?

Aspose.Words for Java のクリーンアップ オプションは、差し込み印刷プロセス中にドキュメントのクリーンアップのさまざまな側面を制御できるようにする設定です。これにより、空の段落や未使用の領域などの不必要な要素を削除して、最終的な文書が適切に構造化され、洗練されたものになるようにすることができます。

### 文書から空の段落を削除するにはどうすればよいですか?

 Aspose.Words for Java を使用して文書から空の段落を削除するには、`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS`オプションを true に設定します。これにより、内容のない段落が自動的に削除され、文書がよりきれいになります。

### の目的は何ですか`REMOVE_UNUSED_REGIONS` cleanup option?

の`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS`このオプションは、差し込み印刷プロセス中に対応するデータがない文書内の領域を削除するために使用されます。未使用のプレースホルダーを削除することで、文書を整理整頓した状態に保つことができます。

### Aspose.Words for Java を使用してドキュメントから空のテーブル行を削除できますか?

はい、`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`クリーンアップ オプションを true に設定します。これにより、データが含まれていない表の行が自動的に削除され、文書内の表が適切に構造化されます。

### を設定するとどうなるか`REMOVE_CONTAINING_FIELDS` option?

の設定`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS`このオプションを使用すると、差し込み印刷プロセス中に、差し込みフィールドを含む段落を含む差し込みフィールド全体が文書から削除されます。これは、差し込みフィールドとそれに関連するテキストを削除する場合に便利です。

### 未使用の差し込みフィールドを文書から削除するにはどうすればよいですか?

ドキュメントから未使用の差し込みフィールドを削除するには、`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS`オプションを true に設定します。これにより、差し込み印刷中に入力されなかった差し込みフィールドが自動的に削除され、文書がよりきれいになります。

### 違いは何ですか`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

の`REMOVE_EMPTY_FIELDS`このオプションは、差し込み印刷プロセス中にデータがないか空の差し込みフィールドを削除します。一方、`REMOVE_UNUSED_FIELDS`このオプションは、結合中にデータが入力されていない差し込みフィールドを削除します。どちらを選択するかは、コンテンツのないフィールドを削除するか、特定のマージ操作で使用されないフィールドを削除するかによって異なります。

### 句読点のある段落の削除を有効にするにはどうすればよいですか?

句読点のある段落の削除を有効にするには、`cleanupParagraphsWithPunctuationMarks`オプションを true に設定し、クリーンアップの対象となる句読点を指定します。これにより、不要な句読点のみの段落を削除して、より洗練された文書を作成できます。

### Aspose.Words for Java のクリーンアップ オプションをカスタマイズできますか?

はい、特定のニーズに応じてクリーンアップ オプションをカスタマイズできます。適用するクリーンアップ オプションを選択し、ドキュメントのクリーンアップ要件に応じて構成することで、最終ドキュメントが希望の基準を確実に満たすようにすることができます。