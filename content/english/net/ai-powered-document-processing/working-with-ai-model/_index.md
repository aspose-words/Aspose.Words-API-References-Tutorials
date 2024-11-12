---
title: Working with AI Model
linktitle: Working with AI Model
second_title: Aspose.Words Document Processing API
description: 
type: docs
weight: 10
url: /net/ai-powered-document-processing/working-with-ai-model/
---

```csharp
using System.Text;
using Aspose.Words;
using System;
using Aspose.Words.AI;

// Working with AI Model

// Your Document Directory
string MyDir = "YOUR_DOCUMENT_DIRECTORY";
// Your ArtifactsDir Directory
string ArtifactsDir = "YOUR_ARTIFACTS_DIRECTORY";

Document firstDoc = new Document(MyDir + "Big document.docx");
Document secondDoc = new Document(MyDir + "Document.docx");

string apiKey = Environment.GetEnvironmentVariable("API_KEY");
// Use OpenAI or Google generative language models.
IAiModelText model = (IAiModelText)AiModel.Create(AiModelType.Gpt4OMini).WithApiKey(apiKey);

Document oneDocumentSummary = model.Summarize(firstDoc, new SummarizeOptions() { SummaryLength = SummaryLength.Short });
oneDocumentSummary.Save(ArtifactsDir + "AI.AiSummarize.One.docx");

Document multiDocumentSummary = model.Summarize(new Document[] { firstDoc, secondDoc }, new SummarizeOptions() { SummaryLength = SummaryLength.Long });
multiDocumentSummary.Save(ArtifactsDir + "AI.AiSummarize.Multi.docx");

```
