---
title: Word 문서에서 서명 공급자 ID 설정
linktitle: Word 문서에서 서명 공급자 ID 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 서명 공급자 ID를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/set-signature-provider-id/
---
이 튜토리얼에서는 .NET용 Aspose.Words와 함께 서명 공급자 ID 설정 기능을 사용하는 단계를 안내합니다. 이 기능을 사용하면 Word 문서의 서명란에 대한 서명 공급자 ID를 지정할 수 있습니다. 아래 단계를 따르십시오.

## 1단계: 문서 로드 및 서명란에 액세스

서명란이 포함된 문서를 업로드하여 시작하세요.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## 2단계: 서명 옵션 설정

SignOptions 클래스의 인스턴스를 만들고 공급자 ID를 포함한 서명 옵션을 설정합니다.

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## 3단계: 문서에 서명하기

문서에 서명하려면 DigitalSignatureUtil 클래스를 사용하고 서명 인증서를 지정해야 합니다.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

문서, 인증서 및 서명된 문서에 대한 올바른 경로를 지정하십시오.

### .NET용 Aspose.Words를 사용하여 서명 공급자 ID 설정에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 서명 공급자 ID를 설정하는 전체 소스 코드입니다.

```csharp

	// 문서 디렉터리의 경로입니다.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

.NET용 Aspose.Words를 사용하여 Word 문서에서 서명 공급자 ID를 완성하세요.


## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 서명란에 서명 공급자 ID를 설정하는 방법을 배웠습니다. 제공된 단계를 따르면 쉽게 문서를 로드하고, 서명란에 액세스하고, 공급자 ID를 설정하고, 문서에 서명할 수 있습니다. 서명 공급자 ID를 설정하는 기능은 서명자의 신원과 신뢰성을 확립하여 Word 문서의 보안과 무결성을 향상시키는 데 도움이 됩니다. Aspose.Words for .NET은 디지털 서명이 포함된 강력한 단어 처리용 API를 제공하므로 서명 프로세스를 쉽게 사용자 정의하고 관리할 수 있습니다.

### Word 문서의 서명 공급자 ID 설정에 대한 FAQ

#### Q: Word 문서의 서명 공급자 ID란 무엇입니까?

A: Word 문서의 서명 공급자 ID는 디지털 서명 공급자를 지정하는 고유 식별자입니다. 이는 디지털 서명 생성 및 관리를 담당하는 엔터티 또는 조직을 식별하는 데 도움이 됩니다.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 서명란에 대한 서명 공급자 ID를 어떻게 설정할 수 있습니까?

A: .NET용 Aspose.Words를 사용하여 Word 문서의 서명란에 대한 서명 공급자 ID를 설정하려면 다음 단계를 따르세요.
1.  다음을 사용하여 문서를 로드합니다.`Document` 클래스를 선택하고 문서 파일의 경로를 지정합니다.
2.  적절한 방법이나 속성을 사용하여 서명란에 액세스합니다. 예를 들어 다음을 사용할 수 있습니다.`GetChild` 서명란 모양을 검색하는 방법입니다.
3. 서명란에서 공급자 ID를 검색합니다.
4.  인스턴스를 생성합니다.`SignOptions` 클래스를 설정하고`ProviderId` 속성을 검색된 공급자 ID에 추가합니다.
5.  사용`DigitalSignatureUtil.Sign` 문서에 서명하는 방법을 포함하여 필요한 매개변수를 제공합니다.`SignOptions` 물체.

#### Q: Aspose.Words for .NET을 사용하여 Word 문서의 서명란에 어떻게 액세스합니까?

 A: .NET용 Aspose.Words를 사용하여 Word 문서의 서명란에 액세스하려면 적절한 메서드나 속성을 사용하여 문서 구조에서 서명란 모양을 검색할 수 있습니다. 예를 들어 다음을 사용할 수 있습니다.`GetChild` 원하는 서명란 모양을 얻으려면 적절한 매개변수를 사용하는 방법을 사용하세요.

#### 질문: Word 문서의 여러 서명 줄에 서명 공급자 ID를 설정할 수 있습니까?

 A: 예, Word 문서의 여러 서명 줄에 서명 공급자 ID를 설정할 수 있습니다. 문서의 서명란 컬렉션을 반복하고 다음을 사용하여 각 서명란에 대한 공급자 ID를 개별적으로 설정할 수 있습니다.`SignOptions.ProviderId` 재산.

#### Q: Word 문서에서 서명 공급자 ID의 용도는 무엇입니까?

A: Word 문서의 서명 공급자 ID는 디지털 서명 생성 및 관리를 담당하는 엔터티 또는 조직을 식별하는 데 사용됩니다. 디지털 서명을 특정 공급자와 연결하여 디지털 서명의 진위성과 신뢰성을 확립하는 데 도움이 됩니다.

#### Q: Word 문서에서 서명 공급자 ID를 설정하는 데 어떤 유형의 디지털 인증서를 사용할 수 있습니까?

A: 적절한 공급자 정보와 함께 X.509 디지털 인증서를 사용하여 Word 문서에 서명 공급자 ID를 설정할 수 있습니다. 디지털 인증서는 신뢰할 수 있는 인증 기관(CA)에서 발급해야 하며 공급자를 식별하는 데 필요한 메타데이터를 포함해야 합니다.