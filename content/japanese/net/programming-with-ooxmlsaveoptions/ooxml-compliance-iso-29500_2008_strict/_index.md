---
title: Ooxml コンプライアンス ISO 29500_2008_Strict
linktitle: Ooxml コンプライアンス ISO 29500_2008_Strict
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でドキュメントを保存するときに Ooxml Iso 29500_2008_Strict に準拠していることを確認する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/ooxml-compliance-iso-29500_2008_strict/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに Ooxml Iso 29500_2008_Strict に準拠していることを確認するために提供されている C# ソース コードを調べます。この機能により、生成されたドキュメントが ISO 29500_2008_Strict 仕様に準拠していることが保証されます。

## ステップ 1: 環境をセットアップする

始める前に、Aspose.Words for .NET を使用して開発環境がセットアップされていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ 2: ドキュメントをロードする

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、`Document`メソッドを実行し、ロードする DOCX ファイルへのパスを渡します。

## ステップ 3: OOXML バックアップ オプションの構成

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions() { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
```

このステップでは、OOXML 保存オプションを設定します。`OptimizeFor`そして`OoxmlSaveOptions`方法。 Word 2016 バージョンに対するドキュメントの互換性を最適化するには、`OptimizeFor`そしてコンプライアンスを次のように設定します`Iso29500_2008_Strict`を使用して`Compliance`.

## ステップ 4: Ooxml Iso 29500_2008_Strict 準拠でドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.docx`拡張子と、指定された保存オプションを追加します。

ソース コードを実行して、ドキュメントを保存するときに Ooxml Iso 29500_2008_Strict に準拠していることを確認できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx」という名前で保存されます。

### Ooxml コンプライアンス ISO 29500 のサンプル ソース コード_ 2008_ Strict using Aspose.Words for .NET 
```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions() { Compliance = OoxmlCompliance.Iso29500_2008_Strict };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときの Ooxml Iso 29500_2008_Strict 準拠機能について調べました。 Ooxml 保存オプションで ISO29500_2008_Strict 準拠を指定することにより、生成されたドキュメントが ISO 29500_2008_Strict 標準に準拠していることが保証されます。

Ooxml Iso 29500_2008_Strict 準拠により、新しいバージョンの Microsoft Word との互換性が向上し、文書の書式設定、スタイル、機能が確実に保持されます。これは、他のユーザーとドキュメントを交換する場合、または長期間アーカイブする場合に特に重要です。

Aspose.Words for .NET は、柔軟で強力なバックアップ オプションを提供することで、Ooxml Iso 29500_2008_Strict への準拠を容易に保証します。この機能をプロジェクトに統合して、生成されたドキュメントが最新の標準を確実に満たすようにすることができます。

Aspose.Words for .NET が提供する他の機能を自由に探索して、ドキュメントの処理を改善し、ワークフローを最適化してください。