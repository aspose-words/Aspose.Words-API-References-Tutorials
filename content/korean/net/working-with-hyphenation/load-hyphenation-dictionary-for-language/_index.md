---
title: 언어에 대한 하이픈 넣기 사전 로드
linktitle: 언어에 대한 하이픈 넣기 사전 로드
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET에서 특정 언어에 대한 하이픈 사전을 로드하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

이 단계별 튜토리얼에서는 특정 언어에 대한 하이픈 넣기 사전을 Aspose.Words for .NET에 로드하는 방법을 보여줍니다. 제공된 C# 소스 코드를 설명하고 이를 자신의 프로젝트에 구현하는 방법을 보여 드리겠습니다.

 시작하려면 개발 환경에 Aspose.Words for .NET이 설치 및 구성되어 있는지 확인하세요. 아직 설치하지 않았다면 다음에서 라이브러리를 다운로드하여 설치하세요.[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1단계: 문서 로드

먼저 지정된 디렉터리에서 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## 2단계: 하이픈 넣기 사전 로드

그런 다음 하이픈 넣기 사전 파일에 대한 스트림을 열고 원하는 언어로 저장합니다. 이 예에서는 스위스 독일어(de-CH) 사전을 로드합니다.

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

데이터 디렉터리에 적절한 사전 파일이 있는지 확인하세요.

## 3단계: 수정된 문서 저장

마지막으로 수정된 문서를 저장합니다.

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

그래서 ! Aspose.Words for .NET에서 특정 언어에 대한 하이픈 사전을 성공적으로 로드했습니다.

### .NET용 Aspose.Words를 사용하는 언어의 하이픈 넣기 사전 로딩에 대한 예제 소스 코드

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

자신의 프로젝트에서 이 코드를 자유롭게 사용하고 특정 요구 사항에 맞게 수정하십시오.

### FAQ

#### Q: Aspose.Words에서 특정 언어에 대한 음절 사전을 로드하는 방법은 무엇입니까?

 A: Aspose.Words에서 특정 언어에 대한 음절 사전을 로드하려면 다음을 사용할 수 있습니다.`Hyphenation` 수업과`LoadDictionary()` 방법. 인스턴스를 생성합니다.`Hyphenation` 수업을 듣고 전화를 걸어`LoadDictionary()` 원하는 언어에 대한 음절 사전 파일의 경로를 지정하는 방법입니다. 그러면 Aspose.Words에 음절 사전이 로드됩니다.

#### Q: 다양한 언어에 대한 음절 사전 파일은 어디서 찾을 수 있나요?

A: 다양한 온라인 리소스에서 다양한 언어에 대한 음절 사전 파일을 찾을 수 있습니다. 이러한 파일은 일반적으로 XML 또는 TEX 형식입니다. 언어학 프로젝트 전용 웹사이트나 소스 코드 저장소에서 다양한 언어에 대한 오픈 소스 음절 사전을 찾을 수 있습니다.

#### Q: 로드된 음절 사전을 Aspose.Words의 문서에 어떻게 적용할 수 있나요?

 A: 로드된 음절화 사전을 Aspose.Words의 문서에 적용하려면 문서의 단어를 반복하고`Hyphenate()` 의 방법`Hyphenation`단어의 음절을 알아내는 수업입니다. 그런 다음 필요에 따라 음절 사이에 하이픈을 추가하여 음절 단어의 형식을 지정할 수 있습니다.

#### Q: Aspose.Words에서는 어떤 언어를 음절화에 지원합니까?

A: Aspose.Words는 영어, 프랑스어, 스페인어, 독일어, 이탈리아어, 네덜란드어, 러시아어, 포르투갈어, 스웨덴어, 노르웨이어, 덴마크어, 핀란드어, 폴란드어, 체코어 등을 포함한 여러 언어에 대한 음절화를 지원합니다. 음절 표기에 지원되는 언어의 전체 목록은 Aspose.Words 설명서를 확인하세요.