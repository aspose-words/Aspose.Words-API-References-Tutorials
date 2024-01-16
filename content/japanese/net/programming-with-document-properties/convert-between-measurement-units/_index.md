---
title: 測定単位間の変換
linktitle: 測定単位間の変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内の測定単位を変換するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-document-properties/convert-between-measurement-units/
---

このチュートリアルでは、Aspose.Words for .NET を使用して測定単位間を変換するための C# ソース コードを説明します。この機能を使用すると、マージン、ヘッダーとフッターの距離などをさまざまな測定単位で指定できます。

## ステップ 1: プロジェクトのセットアップ

まず、お気に入りの IDE で新しい C# プロジェクトを作成します。 Aspose.Words for .NET ライブラリがプロジェクトで参照されていることを確認してください。

## ステップ 2: ドキュメントとコンストラクターの作成

このステップでは、新しいドキュメントを作成し、コンストラクターを初期化します。次のコードを使用します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: 測定単位を構成する

次に、余白、ヘッダーとフッターの距離などの値をさまざまな測定単位に変換します。特定の測定単位で値を指定するには、次のコードを使用します。

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

このコードでは、`ConvertUtil` Aspose.Words のクラスを使用して、指定された値をインチに変換します (`InchToPoint` ）。で利用可能な他の変換方法を使用することもできます。`ConvertUtil`値を他の測定単位に変換するクラス。

### Aspose.Words for .NET を使用した測定単位間の変換のソース コードの例

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Aspose.Words for .NET を使用してドキュメント内で余白、ヘッダーとフッターの距離などを指定するときに測定単位を変換する方法を学習しました。このチュートリアルで提供されるステップバイステップのガイドに従うことで、独自のドキュメント内で目的の測定単位の値を簡単に指定できます。