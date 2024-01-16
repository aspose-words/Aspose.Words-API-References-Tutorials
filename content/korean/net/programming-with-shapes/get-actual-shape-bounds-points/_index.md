---
title: 실제 모양 경계 포인트 가져오기
linktitle: 실제 모양 경계 포인트 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 포인트(측정 단위)로 모양의 실제 경계를 검색하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/get-actual-shape-bounds-points/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 포인트(측정 단위)로 모양의 실제 경계를 검색하는 방법을 설명합니다. 경계는 문서 내 도형의 크기와 위치를 나타냅니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 새 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 이미지 모양 삽입
 사용`InsertImage` 의 방법`DocumentBuilder` 문서에 이미지 모양을 삽입하는 개체입니다. 이미지 파일의 경로를 매개변수로 제공합니다.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 3단계: 실제 모양 경계 지점 검색
 셰이프에 액세스`ShapeRenderer` 사용하여`GetShapeRenderer` 방법. 그런 다음 다음을 사용하여 점 단위로 모양의 실제 경계를 검색합니다.`BoundsInPoints` 재산.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### .NET용 Aspose.Words를 사용하여 실제 모양 경계 점 가져오기에 대한 예제 소스 코드 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 점 단위로 모양의 실제 경계를 성공적으로 검색했습니다.