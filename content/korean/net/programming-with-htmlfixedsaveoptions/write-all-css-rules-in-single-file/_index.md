---
title: 단일 파일에 모든 CSS 규칙 작성
linktitle: 단일 파일에 모든 CSS 규칙 작성
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 단일 파일에 모든 CSS 규칙을 작성하여 Word 문서를 고정 HTML로 변환하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

C# 응용 프로그램에서 Word 문서를 고정 HTML로 변환할 때 더 나은 구성과 이식성을 위해 모든 CSS 규칙을 단일 파일로 통합할 수 있습니다. .NET용 Aspose.Words 라이브러리를 사용하면 HtmlFixedSaveOptions 저장 옵션을 사용하여 이 기능을 쉽게 지정할 수 있습니다. 이 단계별 가이드에서는 저장 옵션 HtmlFixedSaveOptions를 사용하여 단일 파일에 모든 CSS 규칙을 작성하여 .NET C# 소스 코드용 Aspose.Words를 사용하여 Word 문서를 고정 HTML로 변환하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## Word 문서 로드

첫 번째 단계는 고정 HTML로 변환하려는 Word 문서를 로드하는 것입니다. Document 클래스를 사용하여 소스 파일에서 문서를 로드합니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

이 예에서는 문서 디렉터리에 있는 "Document.docx" 문서를 로드합니다.

## 백업 옵션 구성

다음 단계는 고정 HTML로 변환하기 위한 저장 옵션을 구성하는 것입니다. 모든 CSS 규칙을 단일 파일에 작성하려면 HtmlFixedSaveOptions 클래스를 사용하고 SaveFontFaceCssSeparately 속성을 false로 설정하세요. 수행 방법은 다음과 같습니다.

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

새로운 HtmlFixedSaveOptions 개체를 만들고 SaveFontFaceCssSeparately 속성을 false로 설정하여 모든 CSS 규칙을 단일 파일에 작성합니다.

## HTML 문서 변환 수정

이제 저장 옵션을 구성했으므로 문서를 고정 HTML로 변환할 수 있습니다. 저장 옵션을 지정하여 변환된 문서를 고정 HTML 형식으로 저장하려면 Document 클래스의 Save 메서드를 사용합니다. 예는 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

이 예에서는 지정된 저장 옵션을 사용하여 변환된 문서를 "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html"로 저장합니다.

### .NET용 Aspose.Words를 사용하여 "하나의 파일에 모든 CSS 규칙 작성" 기능이 있는 HtmlFixedSaveOptions의 예제 소스 코드

```csharp
// 문서 디렉터리에 대한 액세스 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word 문서 로드
Document doc = new Document(dataDir + "Document.docx");

// "모든 CSS 규칙을 하나의 파일에 작성" 기능으로 백업 옵션 구성
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// 문서를 고정 HTML로 변환
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리와 함께 HtmlFixedSaveOptions를 사용하여 단일 파일에 모든 CSS 규칙을 작성하여 Word 문서를 고정 HTML로 변환하는 방법을 다루었습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. 모든 CSS 규칙을 단일 파일에 작성하면 문서 변환 중에 생성된 HTML 코드를 더 쉽게 구성하고 관리할 수 있습니다.