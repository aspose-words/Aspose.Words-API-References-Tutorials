---
title: 図形をOffice Mathに変換する
linktitle: 図形をOffice Mathに変換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをアップロードするときに、図形を Office の数式に変換する方法について説明します。
type: docs
weight: 10
url: /ja/net/programming-with-loadoptions/convert-shape-to-office-math/
---
C# アプリケーションで数式図形を含むドキュメントを Words で処理する場合、互換性とプレゼンテーションを向上させるために、それらを Office 数式に変換する必要がある場合があります。Aspose.Words ライブラリ for .NET を使用すると、ドキュメントを読み込むときに図形を Office 数式に簡単に変換できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、LoadOptions を使用して図形を Office 数式に変換しながらドキュメントを読み込む方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## 読み込みオプションの設定

最初のステップは、ドキュメントの読み込みオプションを構成することです。読み込みパラメータを指定するには、LoadOptions クラスを使用します。この場合、図形を Office の数式に変換するため、ConvertShapeToOfficeMath プロパティを true に設定する必要があります。手順は次のとおりです。

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

新しい LoadOptions オブジェクトを作成し、ConvertShapeToOfficeMath プロパティを true に設定して、ドキュメントを読み込むときに図形を Office の数式に変換できるようにします。

## 図形を Office の数式に変換してドキュメントを読み込む

読み込みオプションを設定したので、Document クラスを使用してドキュメントを読み込み、読み込みオプションを指定できます。次に例を示します。

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

この例では、指定された読み込みオプションを使用して、ドキュメント ディレクトリにあるドキュメント「Office math.docx」を読み込みます。

## 文書の登録

図形を Office の数式に変換してドキュメントを読み込んだ後、Document クラスの Save メソッドを使用して目的の形式で保存できます。たとえば、ドキュメントを .docx 形式で保存するには、次のようにします。

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

### Aspose.Words for .NET を使用した「図形を Office Math に変換」機能を備えた LoadOptions のサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//「形状変換」機能による読み込みオプションの設定

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

//指定されたオプションでドキュメントをロードします
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//希望の形式で文書を保存する
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、図形を Office の数式に変換してドキュメントを読み込む方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。図形を Office の数式に変換すると、数式要素を含むドキュメントの互換性とプレゼンテーションが向上します。


### よくある質問

#### Q: 図形を Office の数式に変換する必要があるのはなぜですか?

A: 図形を Office の数式に変換することは、C# アプリケーションでの Word 文書内の数学要素の互換性の向上と表示の改善に不可欠です。

#### Q: Aspose.Words は複雑な数式を処理できますか?

A: もちろんです! Aspose.Words は幅広い数式や式を処理できるため、複雑な数学的コンテンツを処理するのにも適したツールです。

#### Q: Aspose.Words は .NET プラットフォームのみに限定されていますか?

A: Aspose.Words は .NET 向けに最適化されていますが、Java や Android などの他のプラットフォームもサポートしており、ドキュメント処理のための多目的ソリューションとなっています。

#### Q: 他の目的のために読み込みオプションをカスタマイズできますか?

A: そうです! Aspose.Words は、特定の要件に合わせてカスタマイズできるさまざまな読み込みオプションを提供し、ライブラリをアプリケーションにシームレスに統合します。

#### Q: Aspose.Words は Word 以外のドキュメント形式もサポートしていますか?

A: はい、Word 文書以外にも、Aspose.Words は PDF、HTML、EPUB など幅広い形式をサポートしており、文書操作のための包括的なソリューションとなっています。