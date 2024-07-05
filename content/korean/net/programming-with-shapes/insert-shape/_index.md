---
title: 모양 삽입
linktitle: 모양 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 도형을 삽입하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/insert-shape/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 모양을 삽입하는 방법을 설명합니다. 도형을 사용하면 문서의 시각적 모양과 레이아웃을 향상시킬 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 및 DocumentBuilder 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder`문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 도형 삽입
 사용`InsertShape` 의 방법`DocumentBuilder`문서에 도형을 삽입하는 개체입니다. 모양 유형, 상대 수평 및 수직 위치, 페이지 크기, 크기 및 배치 유형을 지정합니다. 원하는 경우 모양의 회전 각도를 설정할 수도 있습니다.

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## 4단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.InsertShape.docx"로 저장합니다.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### .NET용 Aspose.Words를 사용하여 도형 삽입에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에 도형을 성공적으로 삽입했습니다.