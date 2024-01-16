---
title: 이미지 폴더 설정
linktitle: 이미지 폴더 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Markdown으로 내보낼 때 이미지 폴더를 설정하는 방법을 알아보세요. 더 나은 구성과 통합을 위해 이미지 배치를 사용자 정의하세요.
type: docs
weight: 10
url: /ko/net/programming-with-markdownsaveoptions/set-images-folder/
---

다음은 .NET용 Aspose.Words 라이브러리를 사용하여 Markdown 내보내기 옵션에 대한 이미지 폴더를 설정하는 데 도움이 되는 다음 C# 소스 코드를 설명하는 단계별 가이드입니다. 이 코드를 사용하기 전에 프로젝트에 Aspose.Words 라이브러리를 포함했는지 확인하세요.

## 1단계: 문서 디렉터리 경로 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

이미지가 포함된 문서가 있는 문서 디렉터리의 올바른 경로를 지정해야 합니다.

## 2단계: 이미지가 포함된 문서 로드

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Markdown 옵션을 사용하여 내보내려는 이미지가 포함된 지정된 문서를 로드합니다.

## 3단계: Markdown 내보내기 옵션을 위한 이미지 폴더 설정

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 우리는`MarkdownSaveOptions` 다음을 사용하여 이미지 폴더의 경로를 설정합니다.`ImagesFolder` 재산. 내보낸 이미지를 저장할 폴더의 올바른 경로를 지정했는지 확인하세요.

## 4단계: Markdown 내보내기 옵션을 사용하여 문서 저장

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

지정된 Markdown 내보내기 옵션을 사용하여 문서를 메모리 스트림에 저장합니다. 그런 다음 흐름을 사용하여 Markdown 콘텐츠를 파일에 저장하는 등의 다른 작업을 수행할 수 있습니다.

### .NET용 Aspose.Words를 사용하여 MarkdownSaveOptions에 대한 이미지 폴더를 설정하는 예제 소스 코드

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

이 소스 코드는 이미지가 포함된 문서를 로드한 다음 Markdown 내보내기 옵션에 대한 이미지 폴더를 설정하는 방법을 보여줍니다. 지정된 옵션을 사용하면 문서가 메모리 스트림에 저장됩니다. 이를 통해 Markdown 콘텐츠를 내보낼 때 이미지 폴더의 위치를 사용자 정의할 수 있습니다.