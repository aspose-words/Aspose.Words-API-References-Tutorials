---
title: 측정 단위 간 변환
linktitle: 측정 단위 간 변환
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서의 측정 단위 간 변환에 대한 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-document-properties/convert-between-measurement-units/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 측정 단위 간 변환을 위한 C# 소스 코드를 안내합니다. 이 기능을 사용하면 여백, 머리글 및 바닥글 거리 등을 다양한 측정 단위로 지정할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 및 생성자 만들기

이 단계에서는 새 문서를 만들고 생성자를 초기화합니다. 다음 코드를 사용하세요.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 측정 단위 구성

이제 여백, 머리글 및 바닥글 거리 등의 값을 다양한 측정 단위로 변환하겠습니다. 특정 측정 단위로 값을 지정하려면 다음 코드를 사용하십시오.

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 이 코드는`ConvertUtil` 지정된 값을 인치로 변환하는 Aspose.Words 클래스(`InchToPoint`). 다음에서 사용 가능한 다른 변환 방법을 사용할 수도 있습니다.`ConvertUtil` 값을 다른 측정 단위로 변환하는 클래스입니다.

### .NET용 Aspose.Words를 사용하여 측정 단위 간 변환에 대한 예제 소스 코드

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

이제 Aspose.Words for .NET을 사용하여 문서에서 여백, 머리글 및 바닥글 거리 등을 지정할 때 측정 단위 간에 변환하는 방법을 배웠습니다. 이 튜토리얼에서 제공되는 단계별 가이드를 따르면 자신의 문서에서 원하는 측정 단위로 값을 쉽게 지정할 수 있습니다.