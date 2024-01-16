---
title: 重複スタイルのクリーンアップ
linktitle: 重複スタイルのクリーンアップ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の重複スタイルをクリーンアップするためのステップバイステップ ガイド。完全なソースコードが含まれています。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して重複したスタイルをクリーンアップするための C# ソース コードを段階的に説明します。この機能は、ドキュメントから重複したスタイルを削除するのに役立ちます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントをロードする

このステップでは、クリーンアップする Word 文書を読み込みます。次のコードを使用してドキュメントをロードします。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが置かれているディレクトリの実際のパスに置き換えます。

## ステップ 3: クリーニング前にスタイルを数える

クリーニングに進む前に、ドキュメント内に存在するスタイルの数を数えます。スタイル数を表示するには、次のコードを使用します。

```csharp
Console.WriteLine(doc.Styles.Count);
```

このステートメントは、ドキュメント内に存在するスタイルの数を表示します。

## ステップ 4: 重複したスタイルをクリーンアップする

次に、ドキュメントから重複したスタイルをクリーンアップしましょう。クリーンアップを実行するには、次のコードを使用します。

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

このコードは、指定されたオプションを使用してドキュメントから重複したスタイルをクリーンアップします。この例では、`DuplicateStyle`重複したスタイルをクリーンアップするオプション。

## ステップ 5: クリーニング後にスタイルを数える

クリーニングを行った後、再度スタイル数をカウントし、減っているかどうかを確認します。新しいスタイルの数を表示するには、次のコードを使用します。

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

このステートメントは、クリーニング後に残っているスタイルの数を表示します。

### Aspose.Words for .NET を使用した重複スタイルのクリーンアップのソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//クリーンアップ前のスタイルの数。
	Console.WriteLine(doc.Styles.Count);

	//重複したスタイルをドキュメントから削除します。
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//クリーンアップ後のスタイルの数が減少しました。
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```