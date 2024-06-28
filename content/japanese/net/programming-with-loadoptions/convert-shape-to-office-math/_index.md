---
title: 形状を Office Math に変換
linktitle: 形状を Office Math に変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをアップロードするときに、図形を Office の数式に変換する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-loadoptions/convert-shape-to-office-math/
---
C# アプリケーションで数式図形を含むドキュメントをワード処理する場合、互換性とプレゼンテーションを向上させるために、ドキュメントを Office 数式に変換する必要がある場合があります。 .NET 用の Aspose.Words ライブラリを使用すると、ドキュメントの読み込み中に図形を Office の数式に簡単に変換できます。このステップバイステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、LoadOptions を使用して図形を Office 数式に変換しながらドキュメントを読み込む方法を説明します。

## Aspose.Words ライブラリについて

コードに入る前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。 Aspose.Words は、.NET を含むさまざまなプラットフォームで Word ドキュメントを作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式設定の変更、セクションの追加など、ドキュメントを操作するための多くの機能を提供します。

## 読み込みオプションの構成

最初のステップは、ドキュメントの読み込みオプションを設定することです。 LoadOptions クラスを使用して、読み込みパラメータを指定します。この例では、図形を Office の数式に変換したいので、ConvertShapeToOfficeMath プロパティを true に設定する必要があります。その方法は次のとおりです。

```csharp
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };
```

新しい LoadOptions オブジェクトを作成し、ConvertShapeToOfficeMath プロパティを true に設定して、ドキュメントの読み込み時に図形を Office 数式に変換できるようにします。

## 図形を Office の数式に変換してドキュメントを読み込む

ロード オプションを設定したので、Document クラスを使用してドキュメントをロードし、ロード オプションを指定できます。以下に例を示します。

```csharp
Document doc = new Document(dataDir + "Office math.docx", loadOptions);
```

この例では、指定されたロード オプションを使用して、ドキュメント ディレクトリにあるドキュメント「Office math.docx」をロードします。

## 文書の登録

図形を Office 数式に変換してドキュメントを読み込んだ後、Document クラスの Save メソッドを使用して目的の形式で保存できます。たとえば、ドキュメントを .docx 形式で保存するには、次のようにします。

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

### Aspose.Words for .NET を使用した「図形を Office Math に変換」機能を備えた LoadOptions のソース コードの例

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//「形状の変換」機能を使用した読み込みオプションの構成

  To Office Math"
LoadOptions loadOptions = new LoadOptions { ConvertShapeToOfficeMath = true };

//指定されたオプションを使用してドキュメントをロードします
Document doc = new Document(dataDir + "Office math.docx", loadOptions);

//ドキュメントを希望の形式で保存します
doc.Save(dataDir + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.Docx);
```

## 結論

このガイドでは、.NET 用 Aspose.Words ライブラリを使用して図形を Office 数式に変換しながらドキュメントを読み込む方法について説明しました。提供された手順に従い、提供された C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。図形を Office の数式に変換すると、互換性が向上し、数式要素を含むドキュメントの表示が向上します。


### よくある質問

#### Q: 図形を Office の数式に変換する必要があるのはなぜですか?

A: 図形を Office の数式に変換することは、互換性を向上させ、C# アプリケーションの Word 文書内の数学的要素をより適切に表示するために不可欠です。

#### Q: Aspose.Words は複雑な数式を処理できますか?

A: もちろんです！ Aspose.Words は幅広い数式や数式を処理できるため、複雑な数学的内容の処理にも適したツールです。

#### Q: Aspose.Words は .NET プラットフォームのみに限定されますか?

A: Aspose.Words は .NET 向けに最適化されていますが、Java や Android などの他のプラットフォームのサポートも提供しており、ドキュメント処理のための多用途なソリューションとなっています。

#### Q: 他の目的のために読み込みオプションをカスタマイズできますか?

A：確かに！ Aspose.Words は、特定の要件に合わせてカスタマイズできるさまざまな読み込みオプションを提供し、ライブラリをアプリケーションにシームレスに統合します。

#### Q: Aspose.Words は Word 以外のドキュメント形式をサポートしていますか?

A: はい、Aspose.Words は Word ドキュメントに加えて、PDF、HTML、EPUB などの幅広い形式をサポートしており、ドキュメント操作のための包括的なソリューションとなっています。