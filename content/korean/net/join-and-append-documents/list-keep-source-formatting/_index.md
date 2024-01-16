---
title: 목록 소스 형식 유지
linktitle: 목록 소스 형식 유지
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서를 결합하고 추가하는 동안 목록 서식을 유지하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/join-and-append-documents/list-keep-source-formatting/
---

이 튜토리얼은 .NET용 Aspose.Words의 List Keep Source Formatting 기능을 사용하는 과정을 안내합니다. 이 기능을 사용하면 목록의 원본 형식을 유지하면서 Word 문서를 결합하고 추가할 수 있습니다.

## 전제조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.Words가 설치되었습니다. Aspose 웹사이트에서 다운로드하거나 NuGet을 통해 설치할 수 있습니다.
2. Visual Studio 또는 기타 C# 개발 환경.

## 1단계: 문서 디렉터리 초기화

 먼저 문서 디렉터리의 경로를 설정해야 합니다. 값을 수정합니다.`dataDir` 문서가 있는 경로에 대한 변수입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 소스 및 대상 문서 로드

 다음으로 Aspose.Words를 사용하여 소스 및 대상 문서를 로드해야 합니다.`Document` 수업. 다음에서 파일 이름을 업데이트합니다.`Document` 문서 이름에 따른 생성자.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3단계: 원본 문서를 연속 흐름으로 설정

 대상 문서에 추가할 때 원본 문서의 콘텐츠가 계속 흐르도록 하려면 다음을 설정해야 합니다.`SectionStart` 소스 문서의 첫 번째 섹션 속성을`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4단계: 원본 문서를 대상 문서에 추가

 이제 다음을 사용하여 소스 문서를 대상 문서에 추가할 수 있습니다.`AppendDocument` 의 방법`Document` 수업. 그만큼`ImportFormatMode.KeepSourceFormatting`매개변수를 사용하면 목록 형식을 포함한 소스 형식이 추가 작업 중에 유지됩니다.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 5단계: 최종 문서 저장

 마지막으로, 다음을 사용하여 목록 유지 소스 서식 지정 기능을 활성화한 상태로 병합된 문서를 저장합니다.`Save` 의 방법`Document` 수업.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### .NET용 Aspose.Words를 사용한 List Keep Source Formatting의 예제 소스 코드 

다음은 .NET용 Aspose.Words를 사용하는 C#의 List Keep Source Formatting 기능에 대한 전체 소스 코드입니다.

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// 문서의 내용이 연속적으로 흐르도록 추가합니다.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

그게 다야! .NET용 Aspose.Words를 사용하여 List Keep Source Formatting 기능을 성공적으로 구현했습니다. 최종 문서에는 원본 문서의 목록 형식이 유지된 병합된 콘텐츠가 포함됩니다.