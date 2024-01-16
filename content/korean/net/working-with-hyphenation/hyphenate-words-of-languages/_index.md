---
title: 언어의 하이픈 넣기 단어
linktitle: 언어의 하이픈 넣기 단어
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 다양한 언어의 단어에 하이픈을 넣는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-hyphenation/hyphenate-words-of-languages/
---

이 단계별 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 다양한 언어의 단어에 하이픈을 넣는 방법을 안내합니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 공식 사이트에서 라이브러리를 다운로드하여 설치하세요.

## 1단계: 문서 개체 초기화

 먼저, 초기화`Document` 다양한 언어로 된 텍스트가 포함된 소스 문서의 경로를 지정하여 개체를 만듭니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2단계: 하이픈 넣기 사전 저장

다음으로, 처리하려는 다양한 언어에 대한 하이픈 넣기 사전을 저장하세요. 이 예에서는 미국 영어와 스위스 독일어에 대한 사전을 등록합니다.

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

데이터 디렉터리에 적절한 사전 파일이 있는지 확인하세요.

## 3단계: 하이픈으로 단어 처리

 이제 하이픈 넣기 기능을 사용하여 다양한 언어의 단어를 처리할 수 있습니다. 다양한 방법을 사용할 수 있습니다.`Document` 또는`DocumentBuilder` 귀하의 특정 요구에 따라.

```csharp
// 예: DocumentBuilder의 하이픈 넣기 방법 사용
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## 4단계: 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

그래서 ! Aspose.Words for .NET을 사용하여 Word 문서에서 다양한 언어로 단어에 하이픈을 넣어 성공적으로 처리했습니다.

### .NET용 Aspose.Words를 사용한 단어 하이픈 넣기용 샘플 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 맞게 수정하십시오.

### FAQ

#### Q: Aspose.Words를 사용하여 특정 언어의 단어를 어떻게 음절화할 수 있나요?

 A: Aspose.Words를 사용하여 특정 언어의 단어를 음절화하려면 다음을 사용할 수 있습니다.`Hyphenation` 수업과`Hyphenate()` 방법. 인스턴스를 생성합니다.`Hyphenation` 원하는 언어를 지정하는 클래스를 호출한 다음`Hyphenate()`음절화할 단어를 인수로 전달하는 메서드입니다. 그러면 지정된 언어로 된 단어의 음절이 제공됩니다.

#### Q: Aspose.Words에서 음절 언어를 지정하려면 어떤 언어 코드를 사용해야 합니까?

A: Aspose.Words에서 음절 언어를 지정하려면 적절한 언어 코드를 사용해야 합니다. 예를 들어 영어에는 "en", 프랑스어에는 "fr", 스페인어에는 "es", 독일어에는 "de" 등을 사용할 수 있습니다. 지원되는 언어 코드의 전체 목록은 Aspose.Words 설명서를 참조하세요.

#### Q: Aspose.Words의 모든 언어에 대해 음절 구분이 작동합니까?

A: Aspose.Words의 음절 표기는 언어별 음절 표기 규칙에 따라 다릅니다. Aspose.Words는 다양한 언어를 지원하지만 일부 언어는 지원되지 않거나 음절을 사용하지 못할 수 있습니다. Aspose.Words 문서를 확인하여 음절화에 지원되는 언어를 알아보세요.