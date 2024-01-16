---
title: 最終保存時刻プロパティを更新する
linktitle: 最終保存時刻プロパティを更新する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でドキュメントを保存するときに、最終保存時刻プロパティを自動的に更新する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに、最終保存時刻プロパティを更新するために提供されている C# ソース コードを調べます。この機能を使用すると、生成されたドキュメントの最終保存時刻プロパティを自動的に更新できます。

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

このステップでは、OOXML 保存オプションを使用して設定します。`OoxmlSaveOptions`クラス。設定により、最終保存時刻プロパティの自動更新を有効にします。`UpdateLastSavedTimeProperty`に`true`.

## ステップ 4: 更新されたプロパティを使用してドキュメントを保存する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.docx`拡張子と、指定された保存オプションを追加します。

これで、ソース コードを実行して、ドキュメントの保存時に最終保存時刻プロパティを自動的に更新できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx」という名前で保存されます。

### Aspose.Words for .NET を使用した「最終保存時刻プロパティを更新」のサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントを保存するときに、最終保存時刻プロパティを自動的に更新する機能を検討しました。 OOXML 保存オプションでこの機能を有効にすると、生成されたドキュメントで最終保存時刻プロパティが自動的に更新されるようになります。

最終保存時刻プロパティを更新すると、ドキュメントの変更とバージョンを追跡するのに役立ちます。また、ドキュメントが最後に保存された日時も追跡されるため、さまざまなシナリオで役立ちます。

Aspose.Words for .NET では、柔軟で強力なバックアップ オプションを提供することで、最終バックアップ時刻プロパティを簡単に自動的に更新できます。この機能をプロジェクトに統合すると、生成されたドキュメントに正確なバックアップ情報が含まれるようになります。