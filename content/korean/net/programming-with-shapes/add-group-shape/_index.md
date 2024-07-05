---
title: 그룹 모양 추가
linktitle: 그룹 모양 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 여러 도형이 포함된 그룹 도형을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/add-group-shape/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 여러 도형을 포함하는 그룹 도형을 Word 문서에 추가하는 방법을 설명합니다. 그룹 모양을 사용하면 여러 모양을 단일 엔터티로 결합하고 조작할 수 있습니다.

## 전제조건
이 튜토리얼을 따르려면 다음이 필요합니다.

- .NET 라이브러리용 Aspose.Words가 설치되었습니다.
- C# 및 Word 문서를 사용한 단어 처리에 대한 기본 지식.

## 1단계: 문서 디렉터리 설정
 문서 디렉터리 경로를 설정하는 것부터 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서를 저장하려는 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 및 GroupShape 만들기
 새 인스턴스를 생성합니다.`Document` 수업과`GroupShape`문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 3단계: GroupShape에 도형 생성 및 추가
 다음과 같은 개별 모양을 만듭니다.`accentBorderShape` 그리고`actionButtonShape` 사용하여`Shape` 수업. 원하는 대로 속성을 사용자 정의합니다. 이 모양을`groupShape` 물체.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## 4단계: GroupShape의 크기 설정
 너비, 높이, 좌표 크기를 설정합니다.`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## 5단계: 문서에 GroupShape 삽입
 만들기`DocumentBuilder` 개체를 삽입하고`groupShape` 을 사용하여 문서에`InsertNode` 방법.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 6단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save`방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.AddGroupShape.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### .NET용 Aspose.Words를 사용하여 그룹 모양 추가에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

그게 다야! Aspose.W를 사용하여 여러 도형을 포함하는 그룹 도형을 Word 문서에 성공적으로 추가했습니다.