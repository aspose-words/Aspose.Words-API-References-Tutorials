---
title: 왕복 정보 내보내기
linktitle: 왕복 정보 내보내기
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 문서를 HTML로 저장할 때 왕복 정보를 내보내는 단계별 가이드입니다.
type: docs
weight: 10
url: /ko/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 문서에서 왕복 정보를 내보내는 C# 소스 코드를 안내합니다. 이 기능을 사용하면 내보낸 HTML 파일에 왕복 정보를 포함할 수 있으므로 원본 문서에 대한 변경 사항을 더 쉽게 검색할 수 있습니다.

## 1단계: 프로젝트 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 참조되는지 확인하세요.

## 2단계: 문서 로드

이 단계에서는 내보낼 문서를 로드합니다. 다음 코드를 사용하여 지정된 디렉터리에서 문서를 로드합니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 이 코드는`Document` 지정된 디렉토리에서 문서를 로드합니다.

## 3단계: HTML 백업 옵션 구성

이제 문서의 왕복 정보를 내보내도록 HTML 저장 옵션을 구성하겠습니다. 다음 코드를 사용하세요.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 이 코드는`HtmlSaveOptions` 그리고`ExportRoundtripInformation` 옵션`true` 내보낼 때 왕복 정보를 포함합니다.

## 4단계: 문서를 HTML로 변환 및 저장

마지막으로 앞서 구성한 HTML 저장 옵션을 사용하여 문서를 HTML로 변환하겠습니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

이 코드는 왕복 정보를 포함하여 문서를 HTML로 변환하고 내보낸 HTML 파일을 지정된 디렉터리에 저장합니다.

### .NET용 Aspose.Words를 사용하여 왕복 정보 내보내기에 대한 예제 소스 코드


```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 문서 디렉토리에 대한 올바른 경로를 지정하십시오.`dataDir` 변하기 쉬운.