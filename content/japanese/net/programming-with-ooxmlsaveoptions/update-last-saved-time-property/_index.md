---
title: 最終保存時刻プロパティの更新
linktitle: 最終保存時刻プロパティの更新
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントを保存するときに、最終保存時刻プロパティを自動的に更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに、最終保存時刻プロパティを更新するための C# ソース コードについて説明します。この機能を使用すると、生成されたドキュメントの最終保存時刻プロパティを自動的に更新できます。

## ステップ1: 環境の設定

始める前に、Aspose.Words for .NET を使用して開発環境をセットアップしていることを確認してください。必要な参照を追加し、適切な名前空間をインポートしたことを確認してください。

## ステップ2: ドキュメントの読み込み

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

このステップでは、`Document`メソッドを呼び出して、読み込む DOCX ファイルへのパスを渡します。

## ステップ3: OOXMLバックアップオプションの設定

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

このステップでは、OOXML保存オプションを設定します。`OoxmlSaveOptions`クラス。設定により、最終保存時刻プロパティの自動更新が有効になります。`UpdateLastSavedTimeProperty`に`true`.

## ステップ4: 更新されたプロパティでドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを`.docx`拡張子と指定された保存オプションを指定します。

これで、ソース コードを実行して、ドキュメントを保存するときに最終保存時刻プロパティを自動的に更新できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx」という名前で保存されます。

### Aspose.Words for .NET を使用して最終保存時刻プロパティを更新するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに、最終保存時刻プロパティを自動的に更新する機能について説明しました。OOXML 保存オプションでこの機能を有効にすると、生成されたドキュメントで最終保存時刻プロパティが自動的に更新されるようになります。

最終保存時刻プロパティを更新すると、ドキュメントの変更やバージョンを追跡するのに役立ちます。また、ドキュメントが最後に保存された日時も追跡されるため、さまざまなシナリオで役立ちます。

Aspose.Words for .NET では、柔軟で強力なバックアップ オプションが提供され、最終バックアップ時刻プロパティの自動更新が簡単になります。この機能をプロジェクトに統合して、生成されたドキュメントに正確なバックアップ情報が含まれるようにすることができます。