---
title: Word 문서에 Bidi 마크 추가
linktitle: Word 문서에 Bidi 마크 추가
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 Bidi 표시를 추가하고 전문적인 다국어 문서를 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words for .NET은 C# 애플리케이션에서 Word 문서를 생성, 편집 및 조작하기 위한 강력한 라이브러리입니다. Aspose.Words가 제공하는 기능 중에는 문서에 Bidi(양방향) 표시를 추가하는 기능이 있습니다. 이 가이드에서는 .NET용 Aspose.Words의 C# 소스 코드를 사용하여 문서에 Bidi 마크를 추가하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 Word 문서로 Words 처리를 쉽고 효율적으로 만들어주는 인기 있는 라이브러리입니다. Bidi 마크 추가를 포함하여 Word 문서를 생성, 편집 및 조작하기 위한 광범위한 기능을 제공합니다.

## 문서 작성 및 내용 추가

첫 번째 단계는 새 문서를 만들고 콘텐츠를 추가하는 것입니다. Document 클래스를 사용하여 새 문서 인스턴스를 만듭니다. 그런 다음 DocumentBuilder 클래스를 사용하여 문서에 텍스트를 추가합니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

이 예에서는 새 문서를 만들고 DocumentBuilder를 사용하여 텍스트를 추가합니다. 다양한 언어로 콘텐츠를 추가하는 방법을 보여주기 위해 세 줄의 텍스트(영어, 히브리어, 아랍어)를 추가했습니다.

## Bidi 마크 추가

콘텐츠가 추가되면 이제 문서에 Bidi 마크를 추가할 수 있습니다. 이를 위해 TxtSaveOptions 클래스를 사용하고 AddBidiMarks 속성을 true로 설정합니다. 방법은 다음과 같습니다.

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

이 예에서는 TxtSaveOptions의 인스턴스를 생성하고 AddBidiMarks 속성을 true로 설정합니다. 다음으로 Document 클래스의 Save 메서드를 사용하여 Bidi 표시가 있는 문서를 저장합니다.

### .NET용 Aspose.Words를 사용한 "Bidi 마크 추가" 기능에 대한 예제 소스 코드

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서 만들기 및 콘텐츠 추가
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Bidi 마크 추가
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## 결론

이 가이드에서는 Aspose.Words for .NET을 사용하여 제공된 C# 소스 코드를 사용하여 Word 문서에 Bidi 표시를 추가하는 방법을 설명했습니다. 제공된 단계를 따르면 C# 애플리케이션의 Word 문서에 Bidi 표시를 쉽게 추가할 수 있습니다. Aspose.Words는 텍스트 서식 및 언어 관리를 통해 단어 처리에 엄청난 유연성과 성능을 제공하므로 전문적으로 다국어 문서를 만들 수 있습니다.

### 자주 묻는 질문

#### Q: .NET용 Aspose.Words가 무엇인가요?
Aspose.Words for .NET은 C# 애플리케이션에서 Word 문서를 생성, 편집 및 조작하기 위한 강력한 라이브러리입니다. Bidi(양방향) 표시 추가를 포함하여 Word 문서로 단어 처리를 위한 다양한 기능을 제공합니다.

#### Q: Aspose.Words for .NET은 어떤 기능을 제공합니까?
Aspose.Words for .NET은 Word 문서 생성, 편집 및 조작을 위한 광범위한 기능을 제공합니다. 이러한 기능 중 일부에는 문서 만들기, 콘텐츠 추가, 텍스트 서식 지정, 테이블 관리, 문서 병합 및 분할, 문서 변환 등이 포함됩니다.

#### Q: .NET용 Aspose.Words를 사용하여 Word 문서에 Bidi 표시를 추가하려면 어떻게 해야 합니까?
다음 단계에 따라 Word 문서에 Bidi 표시를 추가할 수 있습니다.

 다음을 사용하여 새 문서를 만듭니다.`Document` 수업.

 사용`DocumentBuilder` 문서에 내용을 추가하는 클래스입니다.

 콘텐츠를 추가한 후 다음을 사용하세요.`TxtSaveOptions` 클래스를 설정하고`AddBidiMarks`재산`true`.

 다음을 사용하여 Bidi 표시가 있는 문서를 저장합니다.`Save` 의 방법`Document` 수업.

#### Q: Aspose.Words는 Bidi 마크 추가를 위해 여러 언어를 지원합니까?
예, Aspose.Words는 Bidi 마크 추가를 위해 여러 언어를 지원합니다. .NET용 Aspose.Words를 사용하여 영어, 히브리어, 아랍어 등 다양한 언어로 된 텍스트에 Bidi 표시를 추가할 수 있습니다.

#### Q: Bidi 마크가 포함된 문서를 저장할 수 있는 추가 옵션이 있나요?
 예, Bidi 마크가 있는 문서를 저장할 때 다음을 사용하여 다른 옵션을 지정할 수 있습니다.`TxtSaveOptions` 수업. 예를 들어 문서 저장 형식, 인코딩 옵션 등을 설정할 수 있습니다.