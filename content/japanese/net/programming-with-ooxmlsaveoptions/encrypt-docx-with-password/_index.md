---
title: パスワードを使用して Docx を暗号化する
linktitle: パスワードを使用して Docx を暗号化する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して DOCX ファイルをパスワードで暗号化する方法を学習します。ドキュメントセキュリティに関する完全なチュートリアル。
type: docs
weight: 10
url: /ja/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
このチュートリアルでは、提供されている C# ソース コードを調べて、Aspose.Words for .NET を使用してパスワードで DOCX ファイルを暗号化します。この機能を使用すると、指定したパスワードでのみアクセスできるようにしてドキュメントを保護できます。

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

このステップでは、新しいファイルを作成して OOXML 保存オプションを構成します。`OoxmlSaveOptions`物体。を設定して、ドキュメントを暗号化するために必要なパスワードを指定します。`Password`プロパティをカスタムパスワードに追加します。

## ステップ 4: パスワードを使用して文書を暗号化する

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

この最後のステップでは、`Save`メソッドを使用し、出力ファイルへのパスを渡します。`.docx`拡張子と、指定された保存オプションを追加します。

これで、ソース コードを実行して、DOCX ドキュメントをパスワードで暗号化できるようになりました。結果のファイルは、指定されたディレクトリに「WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx」という名前で保存されます。パスワードは暗号化された文書を開くために必要となるため、必ず安全に保管してください。

### Aspose.Words for .NET を使用してパスワードで Docx を暗号化するためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して DOCX ファイルをパスワードで暗号化する機能を検討しました。私たちは、指定したパスワードでのみアクセスできるようにすることでドキュメントを保護する方法を学びました。

ドキュメントの暗号化は、機密情報を保護するために不可欠なセキュリティ対策です。 Aspose.Words for .NET のおかげで、この機能をアプリケーションに簡単に追加できます。

記載されている手順に従うことで、Aspose.Words for .NET プロジェクトにパスワード暗号化を統合し、ドキュメントの機密性を確保できます。

Aspose.Words for .NET が提供する他の機能を自由に試して、高度なドキュメント操作機能でアプリケーションを強化してください。
