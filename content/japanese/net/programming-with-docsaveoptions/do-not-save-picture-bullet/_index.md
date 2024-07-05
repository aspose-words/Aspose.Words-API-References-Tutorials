---
title: 画像を保存しない
linktitle: 画像を保存しない
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の画像の箇条書きの保存を無効にする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

画像行頭記号は、Word 文書でカスタム行頭記号を追加するためによく使用される機能です。ただし、Aspose.Words Library for .NET を使用して文書を操作するときに、画像行頭記号の登録を無効にする必要がある場合があります。このステップ バイ ステップ ガイドでは、Aspose.Words C# ソース コード for .NET を使用して、DocSaveOptions 保存オプションで画像行頭記号の保存を無効にする方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## ステップ1: ドキュメントディレクトリの設定

最初のステップは、ドキュメントが保存されているディレクトリを定義することです。完全なディレクトリ パスを指定する必要があります。例:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ2: イメージ箇条書き付きのドキュメントを読み込む

次に、イメージ箇条書きを含むドキュメントを読み込む必要があります。Document クラスを使用して、ファイルからドキュメントを読み込みます。例:

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

この例では、「Image bullet points.docx」ファイルからドキュメントを読み込んでいます。

  ドキュメントディレクトリにあります。

## ステップ3: 録画オプションを設定する

次に、ドキュメントの保存オプションを設定しましょう。保存設定を指定するには、DocSaveOptions クラスを使用します。例:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

この例では、新しい DocSaveOptions オブジェクトを作成し、SavePictureBullet プロパティを false に設定して、画像の箇条書きの保存を無効にします。

## ステップ4: 「画像の箇条書きを保存しない」機能を有効にする

「画像の箇条書きを保存しない」機能を有効にするために、SavePictureBullet を false に設定して保存オプションを既に構成しています。これにより、画像の箇条書きが最終文書に保存されなくなります。

## ステップ5: ドキュメントを保存する

最後に、Document クラスの Save メソッドを使用してドキュメントを保存できます。ファイルへのフル パスと希望のファイル名を指定します。例:

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

## Aspose.Words for .NET を使用した「画像の箇条書きを保存しない」機能を備えた DocSaveOptions 保存オプションのサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//イメージ箇条書き付きの文書を読み込む
Document doc = new Document(dataDir + "Image bullet points.docx");

//「画像の箇条書きを保存しない」機能を使用して保存オプションを設定します
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

//指定されたオプションでドキュメントを保存します
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、ドキュメント内の画像の箇条書きの保存を無効にする方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。画像の箇条書きの保存を無効にすると、画像の箇条書きを保存せずにドキュメントの構造と書式設定を保持できるため、状況によっては便利です。