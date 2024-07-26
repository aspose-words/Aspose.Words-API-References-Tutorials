---
title: 수직 앵커
linktitle: 수직 앵커
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words의 수직 앵커 기능을 사용하여 문서 내에서 모양을 수직으로 배치하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/vertical-anchor/
---

이 튜토리얼에서는 .NET용 Aspose.Words의 수직 앵커 기능을 사용하여 문서 내에서 모양을 수직으로 배치하는 방법을 설명합니다. 도형의 수직 앵커 속성을 설정하면 텍스트나 페이지를 기준으로 수직 정렬을 제어할 수 있습니다.

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
 새 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder` 문서 작업에 사용할 개체입니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 도형 삽입 및 구성
 다음을 사용하여 문서에 도형을 삽입합니다.`InsertShape` 의 방법`DocumentBuilder` 물체. 모양에 대해 원하는 크기를 설정합니다.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## 4단계: 수직 앵커 설정
도형의 수직 앵커 속성을 설정하여 수직 정렬을 제어합니다. 이 예에서는 도형을 텍스트나 페이지 하단에 고정하기 위해 "Bottom"으로 설정했습니다.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## 5단계: 도형에 콘텐츠 추가
 사용`MoveTo` 의 방법`DocumentBuilder` 도형의 첫 번째 단락으로 커서를 이동하려면 개체를 선택하세요. 그런 다음`Write` 도형에 콘텐츠를 추가하는 방법입니다.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 6단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.VerticalAnchor.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### .NET용 Aspose.Words를 사용하는 수직 앵커의 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

그게 다야! .NET용 Aspose.Words의 수직 앵커 기능을 성공적으로 사용하여 문서 내에서 모양을 수직으로 배치했습니다.