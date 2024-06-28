---
title: 머리글 바닥글 만들기
linktitle: 머리글 바닥글 만들기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 머리글과 바닥글을 추가하고 사용자 정의하는 방법을 알아보세요. 이 단계별 가이드는 전문적인 문서 형식을 보장합니다.
type: docs
weight: 10
url: /ko/net/working-with-headers-and-footers/create-header-footer/
---

문서에 머리글과 바닥글을 추가하면 문서의 전문성과 가독성을 높일 수 있습니다. .NET용 Aspose.Words를 사용하면 Word 문서의 머리글과 바닥글을 쉽게 만들고 사용자 지정할 수 있습니다. 이 튜토리얼에서는 이러한 기능을 원활하게 구현할 수 있도록 프로세스를 단계별로 안내합니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Words: 다음에서 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/words/net/).
- 개발 환경: Visual Studio와 같은 코드를 작성하고 실행합니다.
- C# 기본 지식: C# 및 .NET 프레임워크에 대한 이해.
- 샘플 문서: 튜토리얼에 나온 것처럼 머리글과 바닥글을 적용하거나 새로 만들기 위한 샘플 문서입니다.

## 네임스페이스 가져오기

먼저 Aspose.Words 클래스 및 메서드에 액세스하려면 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## 1단계: 문서 디렉터리 정의

문서가 저장될 디렉터리를 정의합니다. 이는 경로를 효과적으로 관리하는 데 도움이 됩니다.

```csharp
// 문서 디렉토리의 경로
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## 2단계: 새 문서 만들기

 새 문서를 만들고`DocumentBuilder` 콘텐츠 추가를 용이하게 합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 페이지 설정 구성

첫 번째 페이지에 다른 머리글/바닥글을 적용할지 여부를 포함하여 페이지 설정을 지정합니다.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## 4단계: 첫 페이지에 머리글 추가

첫 번째 페이지의 헤더 섹션으로 이동하여 헤더 텍스트를 구성합니다.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## 5단계: 기본 헤더 추가

기본 헤더 부분으로 이동하여 이미지와 텍스트를 삽입합니다.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// 헤더에 이미지 삽입
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## 6단계: 기본 바닥글 추가

기본 바닥글 섹션으로 이동하여 바닥글 내용의 서식을 지정할 테이블을 만듭니다.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// 페이지 번호 매기기 추가
builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();
```

## 7단계: 콘텐츠 및 페이지 나누기 추가

문서 끝으로 이동하고, 페이지 나누기를 추가하고, 다른 페이지 설정으로 새 섹션을 만듭니다.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## 8단계: 이전 섹션의 머리글 및 바닥글 복사

이전 섹션의 머리글과 바닥글을 재사용하려면 복사하고 필요한 수정 사항을 적용하세요.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## 결론

다음 단계를 수행하면 Aspose.Words for .NET을 사용하여 Word 문서에 머리글과 바닥글을 효과적으로 추가하고 사용자 지정할 수 있습니다. 이렇게 하면 문서의 모양과 전문성이 향상되어 읽기 쉽고 매력적입니다.

## 자주 묻는 질문

### Q1: .NET용 Aspose.Words란 무엇입니까?

Aspose.Words for .NET은 개발자가 .NET 애플리케이션 내에서 프로그래밍 방식으로 Word 문서를 생성, 편집 및 변환할 수 있게 해주는 라이브러리입니다.

### Q2: 머리글이나 바닥글에 이미지를 추가할 수 있나요?

 예, 다음을 사용하여 머리글이나 바닥글에 이미지를 쉽게 추가할 수 있습니다.`DocumentBuilder.InsertImage` 방법.

### Q3: 첫 페이지에 머리글과 바닥글을 다르게 설정하려면 어떻게 해야 합니까?

 다음을 사용하여 첫 번째 페이지에 다른 머리글과 바닥글을 설정할 수 있습니다.`DifferentFirstPageHeaderFooter` 의 재산`PageSetup` 수업.

### Q4: Aspose.Words에 대한 추가 문서는 어디서 찾을 수 있나요?

 다음에서 포괄적인 문서를 찾을 수 있습니다.[Aspose.Words API 문서 페이지](https://reference.aspose.com/words/net/).

### Q5: Aspose.Words에 대한 지원이 제공됩니까?

 예, Aspose는 다음을 통해 지원을 제공합니다.[지원 포럼](https://forum.aspose.com/c/words/8).
