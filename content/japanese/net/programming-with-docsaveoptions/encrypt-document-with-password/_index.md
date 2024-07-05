---
title: パスワードで文書を暗号化する
linktitle: パスワードで文書を暗号化する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントをパスワードで暗号化する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
C# アプリケーションでファイルを処理する場合は、ドキュメントのセキュリティが不可欠です。Aspose.Words ライブラリ for .NET を使用すると、パスワードで暗号化してドキュメントを簡単に保護できます。このステップ バイ ステップ ガイドでは、Aspose.Words for .NET C# ソース コードを使用して、DocSaveOptions 保存オプションでドキュメントを暗号化する方法について説明します。

## Aspose.Words ライブラリを理解する

コードに進む前に、.NET 用の Aspose.Words ライブラリを理解することが重要です。Aspose.Words は、.NET を含むさまざまなプラットフォームで Word 文書を作成、編集、変換、保護するための強力なライブラリです。テキストの挿入、書式の変更、セクションの追加など、文書を操作するための多くの機能を提供します。

## ステップ1: ドキュメントディレクトリの定義

最初のステップは、暗号化されたドキュメントを保存するディレクトリを設定することです。完全なディレクトリ パスを指定する必要があります。例:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ2: ドキュメントの作成と編集

次に、ドキュメントを作成し、コンテンツを追加できます。Aspose.Words が提供する DocumentBuilder クラスを使用して、ドキュメントのコンテンツを構築します。例:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

この例では、新しい空白のドキュメントを作成し、DocumentBuilder を使用して「Hello World!」というテキストを書き込みます。

## ステップ3: 録画オプションを設定する

次に、ドキュメントの保存オプションを設定しましょう。保存設定を指定するには、DocSaveOptions クラスを使用します。例:

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

この例では、新しい DocSaveOptions オブジェクトを作成し、Password プロパティを "password" に設定して、このパスワードでドキュメントを暗号化します。

## ステップ4: 「パスワードで文書を暗号化」機能を有効にする

すでにオプションを設定しています

指定されたパスワードで登録すると、「パスワードで文書を暗号化」機能が自動的に有効になります。これにより、文書は保存時に指定されたパスワードで暗号化されます。

## ステップ5: ドキュメントを保存する

最後に、Document クラスの Save メソッドを使用してドキュメントを保存できます。ファイルへのフル パスと希望のファイル名を指定します。例:

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

必ず「dataDir」をドキュメントへのディレクトリ パスに置き換えてください。

### Aspose.Words for .NET を使用した「パスワードでドキュメントを暗号化」機能を備えた DocSaveOptions 保存オプションのサンプル ソース コード

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントの作成と編集
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

//「パスワードでドキュメントを暗号化」機能を使用して保存オプションを設定します
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

//指定されたオプションでドキュメントを保存します
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## 結論

このガイドでは、.NET 用の Aspose.Words ライブラリを使用して、DocSaveOptions 保存オプションでドキュメントをパスワードで暗号化する方法について説明しました。提供されている手順に従い、提供されている C# ソース コードを使用すると、この機能を C# アプリケーションに簡単に適用できます。ドキュメントをパスワードで暗号化すると、ドキュメントを扱う際の機密性とセキュリティが保証されます。