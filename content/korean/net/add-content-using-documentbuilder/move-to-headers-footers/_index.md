---
title: Word 문서에서 머리글 바닥글로 이동
linktitle: Word 문서에서 머리글 바닥글로 이동
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서의 머리글과 바닥글을 탐색하고 수정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/add-content-using-documentbuilder/move-to-headers-footers/
---
이 예에서는 .NET용 Aspose.Words의 머리글 바닥글로 이동 기능을 살펴보겠습니다. Aspose.Words는 개발자가 프로그래밍 방식으로 Word 문서를 생성, 수정 및 변환할 수 있는 강력한 문서 조작 라이브러리입니다. 머리글/바닥글로 이동 기능을 사용하면 문서 내의 다양한 머리글과 바닥글로 이동하여 콘텐츠를 추가할 수 있습니다.

.NET용 Aspose.Words를 사용하여 머리글/바닥글로 이동 기능을 사용하는 방법을 이해하기 위해 소스 코드를 단계별로 살펴보겠습니다.

## 1단계: 문서 및 문서 작성기 초기화

먼저 Document 및 DocumentBuilder 객체를 초기화합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2단계: 머리글 및 바닥글 구성

문서의 머리글/바닥글 설정을 지정합니다. 이 예에서는 첫 번째 페이지와 홀수/짝수 페이지의 머리글과 바닥글을 다르게 설정합니다.

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## 3단계: 다양한 페이지에 대한 헤더 만들기

각 헤더 유형으로 이동하여 내용을 추가합니다. 이 예에서는 첫 번째 페이지, 심지어 페이지 및 기타 모든 페이지에 대한 헤더를 만듭니다.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## 4단계: 문서에 페이지 만들기
여러 페이지를 만들려면 문서에 콘텐츠를 추가하세요. 예를 들어:

```csharp
// 문서에 두 페이지를 만듭니다.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## 5단계: 문서 저장

수정된 문서를 원하는 위치에 저장합니다.

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

적절한 파일 경로와 형식(예: DOCX)을 지정했는지 확인하세요.

### .NET용 Aspose.Words를 사용하여 머리글/바닥글로 이동에 대한 예제 소스 코드

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 첫 번째 페이지, 짝수 페이지, 홀수 페이지에 대해 머리글과 바닥글을 다르게 지정하도록 지정합니다.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// 헤더를 생성합니다.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// 문서에 두 페이지를 만듭니다.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## 결론

이 예에서는 .NET용 Aspose.Words의 머리글/바닥글로 이동 기능을 살펴보았습니다. Word 문서 내의 다양한 머리글과 바닥글을 탐색하고 DocumentBuilder 클래스를 사용하여 콘텐츠를 추가하는 방법을 배웠습니다. 이 기능을 사용하면 개발자는 특정 페이지나 섹션에 대한 머리글과 바닥글을 사용자 정의할 수 있어 전문적이고 구조화된 문서를 만드는 데 유연성을 제공합니다. Aspose.Words for .NET은 Word 문서를 프로그래밍 방식으로 조작하기 위한 강력한 도구 세트를 제공하므로 문서 처리 애플리케이션을 위한 필수 라이브러리가 됩니다.

### Word 문서의 머리글 바닥글로 이동에 대한 FAQ

#### Q: Aspose.Words for .NET의 머리글/바닥글로 이동 기능의 목적은 무엇입니까?

A: .NET용 Aspose.Words의 머리글/바닥글로 이동 기능을 사용하면 개발자는 Word 문서 내의 다양한 머리글과 바닥글을 탐색하고 프로그래밍 방식으로 콘텐츠를 추가할 수 있습니다. 문서의 여러 페이지나 섹션에 대한 머리글과 바닥글을 사용자 정의해야 할 때 유용합니다.

#### 질문: 문서의 페이지마다 머리글과 바닥글을 다르게 지정할 수 있나요?

A: 예, PageSetup.DifferentFirstPageHeaderFooter 및 PageSetup.OddAndEvenPagesHeaderFooter 속성을 각각 사용하여 첫 번째 페이지, 짝수 페이지, 홀수 페이지에 서로 다른 머리글과 바닥글을 지정할 수 있습니다.

#### Q: 특정 머리글과 바닥글에 콘텐츠를 추가하려면 어떻게 해야 합니까?

A: 특정 머리글과 바닥글에 콘텐츠를 추가하려면 DocumentBuilder 클래스의 MoveToHeaderFooter 메서드를 사용하세요. 요구 사항에 따라 HeaderFirst, HeaderEven 및 HeaderPrimary 헤더나 FooterFirst, FooterEven 및 FooterPrimary 바닥글로 이동할 수 있습니다.

#### Q: 문서의 특정 섹션에 대한 머리글과 바닥글을 만들 수 있나요?

A: 예, DocumentBuilder 클래스의 MoveToSection 메서드를 사용하여 문서의 특정 섹션으로 이동한 다음 해당 섹션 내에 머리글과 바닥글을 만들 수 있습니다.

#### Q: Aspose.Words for .NET을 사용하여 수정된 문서를 파일로 어떻게 저장할 수 있나요?

A: Document 클래스의 Save 메서드를 사용하면 수정된 문서를 원하는 위치와 형식으로 저장할 수 있습니다. 적절한 파일 경로와 파일 형식(예: DOCX)을 지정했는지 확인하세요.