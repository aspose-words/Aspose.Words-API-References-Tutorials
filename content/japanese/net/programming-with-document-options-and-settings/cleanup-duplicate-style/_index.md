---
title: 重複したスタイルのクリーンアップ
linktitle: 重複したスタイルのクリーンアップ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の重複したスタイルをクリーンアップするためのステップ バイ ステップ ガイド。完全なソース コードが含まれています。
type: docs
weight: 10
url: /ja/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して重複するスタイルをクリーンアップするための C# ソース コードを段階的に説明します。この機能は、ドキュメントから重複するスタイルを削除するのに役立ちます。

## ステップ1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Words for .NET ライブラリが参照されていることを確認します。

## ステップ2: ドキュメントの読み込み

このステップでは、クリーンアップする Word 文書を読み込みます。次のコードを使用して文書を読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

交換する`"YOUR DOCUMENTS DIRECTORY"`ドキュメントが配置されているディレクトリの実際のパスを入力します。

## ステップ3: 掃除の前にスタイルを数える

クリーニングを進める前に、ドキュメント内に存在するスタイルの数をカウントします。スタイルの数を表示するには、次のコードを使用します。

```csharp
Console.WriteLine(doc.Styles.Count);
```

このステートメントは、ドキュメント内に存在するスタイルの数を表示します。

## ステップ4: 重複したスタイルをクリーンアップする

次に、ドキュメントから重複したスタイルをクリーンアップします。クリーンアップを実行するには、次のコードを使用します。

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

このコードは、指定されたオプションを使用してドキュメントから重複したスタイルを削除します。この例では、`DuplicateStyle`重複したスタイルをクリーンアップするオプション。

## ステップ5: クリーニング後のスタイルを数える

クリーニングを行った後、スタイルの数を再度カウントして、減少したかどうかを確認します。新しいスタイルの数を表示するには、次のコードを使用します。

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

このステートメントは、クリーニング後に残っているスタイルの数を表示します。

### Aspose.Words for .NET を使用して重複したスタイルをクリーンアップするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//クリーンアップ前のスタイルの数。
	Console.WriteLine(doc.Styles.Count);

	//ドキュメントから重複したスタイルを削除します。
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//クリーンアップ後のスタイルの数が減少しました。
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```