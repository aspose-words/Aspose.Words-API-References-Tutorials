---
title: 가로 세로 비율이 잠겼습니다.
linktitle: 가로 세로 비율이 잠겼습니다.
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 가로 세로 비율을 잠그거나 잠금 해제하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-shapes/aspect-ratio-locked/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 가로 세로 비율을 잠그거나 잠금 해제하는 방법을 설명합니다. 종횡비를 잠그면 크기를 조정할 때 모양의 원래 비율을 유지할 수 있습니다.

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

## 3단계: 이미지 모양 삽입
 사용`InsertImage` 의 방법`DocumentBuilder` 문서에 이미지 모양을 삽입하는 개체입니다. 이미지 파일의 경로를 매개변수로 제공합니다.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 4단계: 종횡비 잠금 또는 잠금 해제
 설정`AspectRatioLocked` 모양의 속성`true` 또는`false` 종횡비를 각각 잠그거나 잠금 해제합니다.

```csharp
shape.AspectRatioLocked = false; //종횡비 잠금 해제
```

## 5단계: 문서 저장
 다음을 사용하여 문서를 지정된 디렉터리에 저장합니다.`Save` 방법. 적절한 파일 확장자와 함께 원하는 파일 이름을 제공하십시오. 이 예에서는 문서를 "WorkingWithShapes.AspectRatioLocked.docx"로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### .NET용 Aspose.Words를 사용하여 종횡비 잠김에 대한 예제 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 Word 문서에서 도형의 가로 세로 비율을 성공적으로 잠그거나 잠금 해제했습니다.