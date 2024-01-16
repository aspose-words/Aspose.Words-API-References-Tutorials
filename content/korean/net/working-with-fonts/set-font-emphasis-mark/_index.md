---
title: 글꼴 강조 표시 설정
linktitle: 글꼴 강조 표시 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 글꼴 강조 스타일을 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-fonts/set-font-emphasis-mark/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 강조 스타일을 설정하는 방법을 보여줍니다. 글꼴 강조는 텍스트의 특정 단어나 문구를 강조하는 데 사용됩니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리

## 1단계: 문서 디렉터리 정의
 Word 문서 위치에 대한 디렉터리 경로를 설정하여 시작하세요. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 문서 만들기 및 사용자 지정
 인스턴스를 생성합니다.`Document` 클래스와 관련`DocumentBuilder` 문서 콘텐츠를 구축합니다. 사용`Font.EmphasisMark` 글꼴 강조 스타일을 설정하는 속성`EmphasisMark.UnderSolidCircle` . 그런 다음`Write` 그리고`Writeln` 방법`DocumentBuilder` 지정된 글꼴 강조로 텍스트를 추가합니다.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## 3단계: 문서 저장
 다음을 사용하여 문서를 저장합니다.`Save` 의 방법`Document` 적절한 경로와 파일 이름을 사용하십시오.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### .NET용 Aspose.Words를 사용하여 글꼴 강조 표시 설정의 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 글꼴 강조 스타일을 설정하는 방법을 배웠습니다. 다양한 강조 스타일을 시험해 보고 이 기능을 사용하여 문서에서 단어나 구문을 강조 표시하세요.

### FAQ

#### Q: Aspose.Words를 사용하여 Word 문서의 특정 글꼴에 악센트 표시를 어떻게 추가할 수 있나요?

A: Aspose.Words를 사용하여 Word 문서의 특정 글꼴에 악센트 표시를 추가하려면 API를 사용하여 원하는 글꼴로 이동하고 적절한 악센트 표시를 적용할 수 있습니다. 그러면 선택한 글꼴의 텍스트에 악센트 표시가 추가됩니다.

#### Q: Aspose.Words를 사용하여 Word 문서의 악센트 표시 스타일을 변경할 수 있나요?

A: 예, Aspose.Words를 사용하면 Word 문서의 악센트 표시 스타일을 변경할 수 있습니다. API를 사용하면 색상, 크기, 선종류 등과 같은 스타일 속성을 조정하여 악센트 표시의 모양을 사용자 정의할 수 있습니다.

#### Q: Aspose.Words를 사용하여 Word 문서에서 모든 악센트 표시를 제거하려면 어떻게 해야 합니까?

A: Aspose.Words를 사용하여 Word 문서에서 모든 악센트 표시를 제거하려면 API를 사용하여 문서를 탐색하고 기존 악센트 표시를 감지한 후 적절한 방법을 사용하여 제거할 수 있습니다. 그러면 문서에서 모든 강조 표시가 제거됩니다.

#### Q: Word 문서에서 텍스트의 특정 부분에 악센트 표시를 추가할 수 있나요?

A: 예, Aspose.Words를 사용하여 Word 문서 텍스트의 특정 부분에 악센트 표시를 추가할 수 있습니다. API를 사용하여 원하는 텍스트 범위를 선택하고 텍스트의 해당 부분에 적절한 강조 표시를 추가할 수 있습니다.

#### Q: 악센트 표시를 필요에 맞게 맞춤 설정할 수 있나요?

A: 예, Aspose.Words를 사용하여 필요에 따라 악센트 표시를 사용자 정의할 수 있습니다. 색상, 크기, 선종류 등과 같은 강조 표시의 스타일 속성을 서식 기본 설정에 맞게 조정할 수 있습니다.