---
title: 머리글 바닥글 만들기
linktitle: 머리글 바닥글 만들기
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서에 머리글과 바닥글을 만드는 방법을 알아보세요. 각 페이지의 머리글과 바닥글을 사용자 정의합니다.
type: docs
weight: 10
url: /ko/net/working-with-headers-and-footers/create-header-footer/
---

다음은 .NET 기능용 Aspose.Words를 사용하여 머리글과 바닥글을 생성하는 다음 C# 소스 코드를 설명하는 단계별 가이드입니다. 이 코드를 사용하기 전에 프로젝트에 Aspose.Words 라이브러리를 포함했는지 확인하세요.

## 1단계: 문서 디렉터리 경로 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

편집된 문서가 저장될 문서 디렉토리의 올바른 경로를 지정하십시오.

## 2단계: 문서 및 문서 생성기 만들기

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 여기서 우리는`Document` 클래스와 인스턴스`DocumentBuilder` 문서를 조작하고 요소를 추가할 수 있는 클래스입니다.

## 3단계: 페이지 매개변수 및 첫 번째 헤더 설정

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// 첫 번째 페이지의 머리글/바닥글을 다른 페이지와 다르게 할지 지정합니다.
// PageSetup.OddAndEvenPagesHeaderFooter 속성을 사용하여 지정할 수도 있습니다.
// 홀수 페이지와 짝수 페이지의 머리글/바닥글이 다릅니다.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

헤더 거리를 포함한 페이지 매개변수를 설정한 다음 기본 헤더(`HeaderPrimary`). 문서 생성기를 사용하여 텍스트를 추가하고 헤더 형식을 지정합니다.

## 4단계: 기본 헤더에 이미지와 텍스트 삽입

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

문서 생성기를 사용하여 기본 헤더의 왼쪽 상단에 이미지를 삽입한 다음 오른쪽 정렬된 텍스트를 추가합니다.

## 5단계: 기본 바닥글에 표 삽입

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

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

builder.MoveToDocumentEnd();
```

## 6단계: 새 페이지 추가 및 머리글/바닥글 설정

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// 이 섹션에서는 첫 번째 페이지에 다른 머리글/바닥글이 필요하지 않으며 문서의 제목 페이지 하나만 필요합니다.
//이 페이지의 머리글/바닥글은 이전 섹션에서 이미 정의되었습니다.
pageSetup.DifferentFirstPageHeaderFooter = false;

// 이 섹션은 기본적으로 이전 섹션의 머리글/바닥글을 표시합니다. 이 링크를 끊으려면 currentSection.HeadersFooters.LinkToPrevious(false)를 호출하세요.
// 새 섹션의 페이지 너비가 다르기 때문에 바닥글 테이블의 셀 너비를 다르게 설정해야 합니다.
currentSection.HeadersFooters.LinkToPrevious(false);

// 이 섹션에 이미 존재하는 머리글/바닥글을 사용하려면,
//그러나 몇 가지 사소한 변경 사항을 적용하면 머리글/바닥글을 복사하는 것이 합리적일 수 있습니다.
// 이전 섹션에서 원하는 곳에 필요한 변경 사항을 적용합니다.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// 문서 저장
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 페이지 나누기와 섹션 나누기를 추가하여 기본 머리글/바닥글이 표시되는 새 페이지를 만듭니다. 새 섹션에 대한 매개변수를 설정한 다음`CopyHeadersFootersFromPreviousSection` 이전 섹션의 머리글/바닥글을 복사하는 방법입니다. 마지막으로 기본 바닥글 테이블에 적절한 셀 너비를 설정하고 문서를 저장합니다.

### .NET용 Aspose.Words를 사용하여 머리글과 바닥글을 생성하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// 첫 번째 페이지의 머리글/바닥글을 다른 페이지와 다르게 할지 지정합니다.
// PageSetup.OddAndEvenPagesHeaderFooter 속성을 사용하여 지정할 수도 있습니다.
// 홀수 페이지와 짝수 페이지의 머리글/바닥글이 다릅니다.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

pageSetup.HeaderDistance = 20;
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// 헤더의 상단/왼쪽 모서리에 위치가 지정된 이미지를 삽입합니다.
// 페이지 상단/왼쪽 가장자리로부터의 거리는 10포인트로 설정됩니다.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// 두 개의 셀이 있는 표를 사용하여 줄에 있는 텍스트의 한 부분을 만듭니다(페이지 번호 매기기 포함).
// 왼쪽으로 정렬하고 텍스트의 다른 부분(저작권 포함)을 오른쪽으로 정렬합니다.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// PAGE 및 NUMPAGES 필드를 사용하여 현재 페이지 번호와 많은 페이지를 자동 계산합니다.
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

builder.MoveToDocumentEnd();

// 페이지 나누기를 만들어 기본 머리글/바닥글이 표시되는 두 번째 페이지를 만듭니다.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// 이 섹션에는 다른 첫 페이지 머리글/바닥글이 필요하지 않으며 문서에 제목 페이지 하나만 있으면 됩니다.
//이 페이지의 머리글/바닥글은 이전 섹션에서 이미 정의되었습니다.
pageSetup.DifferentFirstPageHeaderFooter = false;

// 이 섹션에는 이전 섹션의 머리글/바닥글이 표시됩니다.
// 기본적으로 이 페이지 너비를 취소하려면 currentSection.HeadersFooters.LinkToPrevious(false)를 호출하세요.
// 새 섹션에서는 다르기 때문에 바닥글 테이블에 대해 다른 셀 너비를 설정해야 합니다.
currentSection.HeadersFooters.LinkToPrevious(false);

// 이 섹션에 대해 기존 머리글/바닥글 세트를 사용하려는 경우.
// 그러나 약간의 수정을 가하면 머리글/바닥글을 복사하는 것이 편리할 수 있습니다.
// 이전 섹션에서 원하는 곳에 필요한 수정 사항을 적용합니다.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### FAQ

#### Q: Aspose.Words에서 내 문서에 헤더를 어떻게 추가할 수 있나요?

 A: Aspose.Words에서 문서에 헤더를 추가하려면 다음을 사용할 수 있습니다.`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` 방법. 이 방법은 문서의 첫 번째 섹션에 기본 제목을 추가합니다.

#### Q: Aspose.Words에서 내 문서에 바닥글을 어떻게 추가할 수 있나요?

 A: Aspose.Words에서 문서에 바닥글을 추가하려면`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`방법. 이 방법은 문서의 첫 번째 섹션에 기본 바닥글을 추가합니다.

#### Q: Aspose.Words의 머리글이나 바닥글에 텍스트를 어떻게 추가할 수 있나요?

 A: Aspose.Words의 머리글이나 바닥글에 텍스트를 추가하려면 다음을 사용할 수 있습니다.`HeaderFooter.Paragraphs` 속성을 사용하여 머리글이나 바닥글의 단락 컬렉션을 가져온 다음`ParagraphCollection.Add` 방법.

#### Q: Aspose.Words에서 이미지와 페이지 번호로 머리글이나 바닥글 콘텐츠를 사용자 정의할 수 있나요?

 A: 예, Aspose.Words에서 이미지와 페이지 번호로 머리글이나 바닥글 내용을 사용자 정의할 수 있습니다. 다음과 같은 객체를 사용할 수 있습니다.`Shape` 다음과 같은 이미지와 개체를 추가하려면`Field` 머리글이나 바닥글에 페이지 번호를 추가하려면

#### Q: Aspose.Words에서 머리글이나 바닥글의 텍스트 글꼴, 크기, 색상을 변경할 수 있나요?

 A: 예, Aspose.Words에서 머리글이나 바닥글의 텍스트 글꼴, 크기 및 색상을 변경할 수 있습니다. 다음과 같은 텍스트 서식 속성에 액세스할 수 있습니다.`Font` 글꼴을 변경하려면,`Size` 크기를 조절하고,`Color`텍스트 색상을 설정합니다.