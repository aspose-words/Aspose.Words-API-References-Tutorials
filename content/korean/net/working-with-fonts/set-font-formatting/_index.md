---
title: 글꼴 서식 설정
linktitle: 글꼴 서식 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 글꼴 서식을 설정하고 매력적인 문서를 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-font-formatting/
---
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 서식을 설정하는 방법을 보여줍니다. 굵게, 색상, 기울임꼴, 글꼴, 크기, 간격, 밑줄 등의 스타일을 적용하는 방법을 알아봅니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
Word 문서 위치에 대한 디렉터리 경로를 설정하여 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 만들기 및 서식 지정
 인스턴스를 생성합니다.`Document` 수업과`DocumentBuilder`문서를 작성하는 클래스입니다. 사용`Font` 의 재산`DocumentBuilder` 글꼴 서식 속성에 액세스합니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## 3단계: 문서 저장
 사용`Save` 글꼴 서식이 적용된 문서를 저장하는 방법입니다. 바꾸다`"WorkingWithFonts.SetFontFormatting.docx"` 원하는 파일명으로

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### .NET용 Aspose.Words를 사용하여 글꼴 서식 설정에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## 결론
축하합니다! 이제 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 서식을 설정하는 방법을 알았습니다. 더 많은 글꼴 서식 옵션을 탐색하고 개인화되고 매력적인 Word 문서를 만들 수 있습니다.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서의 글꼴에 굵은 스타일을 적용하려면 어떻게 해야 합니까?

A: Aspose.Words를 사용하여 Word 문서의 글꼴에 굵은 스타일을 적용하려면 API를 사용하여 원하는 글꼴로 이동하고 해당 스타일을 "굵게"로 설정하면 됩니다. 그러면 지정된 글꼴에 굵은 스타일이 적용됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서의 특정 텍스트 부분에 기울임꼴 스타일을 적용할 수 있나요?

A: 예, Aspose.Words를 사용하면 Word 문서 텍스트의 특정 부분에 기울임꼴 스타일을 적용할 수 있습니다. API를 사용하여 원하는 텍스트 범위를 선택하고 스타일을 "기울임꼴"로 설정할 수 있습니다.

#### Q: Aspose.Words를 사용하여 Word 문서의 글꼴 색상을 어떻게 변경할 수 있나요?

A: Aspose.Words를 사용하여 Word 문서의 글꼴 색상을 변경하려면 API를 사용하여 원하는 글꼴에 액세스하고 색상을 원하는 색상으로 설정할 수 있습니다. 그러면 문서의 글꼴 색상이 변경됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서의 글꼴 크기를 변경할 수 있나요?

A: 예, Aspose.Words를 사용하여 Word 문서의 글꼴 크기를 변경할 수 있습니다. API를 사용하면 글꼴에 액세스하고 필요에 따라 글꼴 크기를 포인트 또는 배율 포인트로 설정할 수 있습니다.

#### Q: Word 문서의 동일한 텍스트에 굵게, 기울임꼴 등 여러 글꼴 형식을 적용할 수 있나요?

A: 예, Aspose.Words를 사용하면 Word 문서의 동일한 텍스트에 굵게 및 기울임꼴과 같은 다양한 글꼴 형식을 적용할 수 있습니다. API를 사용하여 텍스트의 다양한 부분에 대해 원하는 다양한 글꼴 스타일을 설정할 수 있습니다.