---
title: 잘린 모서리 추가
linktitle: 잘린 모서리 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 모서리가 잘린 모양을 추가하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/add-corners-snipped/
---

 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에 모서리가 잘린 모양을 추가하는 방법을 설명합니다. 모서리 잘린 모양은 다음을 사용하여 사용자 정의하고 삽입할 수 있습니다.`InsertShape` 방법.

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

## 3단계: 모서리 잘린 모양 삽입
 사용`InsertShape` 의 방법`DocumentBuilder` 모서리가 잘린 모양을 삽입하는 개체입니다. 도형 유형을 지정합니다(이 경우`ShapeType.TopCornersSnipped`) 모양에 원하는 크기를 제공합니다.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 4단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.AddCornersSnipped.docx"로 저장합니다.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### .NET용 Aspose.Words를 사용하여 잘라낸 모서리 추가에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

그게 다야! Aspose.Words for .NET을 사용하여 Word 문서에 모서리 잘린 모양을 성공적으로 추가했습니다.