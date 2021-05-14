---
title: Gerar documentos eletrônicos e atualizar dados de aplicativos usando ER
description: Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo para gerar documentos eletrônicos de saída.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f66a173c7d66f915a7802e42caf1a36f661eea1
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944308"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="0d8ce-103">Gerar documentos eletrônicos e atualizar dados do aplicativo usando ER</span><span class="sxs-lookup"><span data-stu-id="0d8ce-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0d8ce-104">Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo para gerar documentos eletrônicos de saída.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="0d8ce-105">Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="0d8ce-106">Com esta funcionalidade, um único formato de ER pode ser usado para gerar documentos eletrônicos de saída e, em seguida, atualizar os dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="0d8ce-107">Este recurso também pode ser usado nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="0d8ce-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="0d8ce-108">Para evitar o uso repetido de dados de aplicativo em processos subsequentes você pode marcar os dados de aplicativo imediatamente após ser usado para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="0d8ce-109">Por exemplo, você pode marcar transações de pagamento como já processadas imediatamente após terem sido incluídas em uma mensagem de pagamento gerada.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="0d8ce-110">Para armazenar os detalhes de processamento de documentos eletrônicos gerados usando a lógica de ER.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="0d8ce-111">Por exemplo, uma identificação exclusiva da mensagem de pagamento gerada usando a expressão de ER.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="0d8ce-112">A expressão é baseada nas informações inseridas na caixa de diálogo de ER quando o formato de ER é executado para gerar documentos.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="0d8ce-113">Para saber mais sobre este recurso, execute o conjunto de Guias de tarefas do ER Gerar documentos com atualização de dados do aplicativo (parte do processo comercial do 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)), que o acompanham pelos detalhes de relatório e arquivamento do intrastat.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="0d8ce-114">Os arquivos a seguir são necessários para concluir determinadas etapas nessas Guias de tarefas.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="0d8ce-115">Baixe os arquivos e salve-os no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="0d8ce-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="0d8ce-116">Configuração de modelo de dados de ER: Intrastat (modelo)</span><span class="sxs-lookup"><span data-stu-id="0d8ce-116">ER data model configuration: Intrastat (model)</span></span>](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [<span data-ttu-id="0d8ce-117">Configuração de mapeamento de modelo de ER: Intrastat (mapeamento)</span><span class="sxs-lookup"><span data-stu-id="0d8ce-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [<span data-ttu-id="0d8ce-118">Configuração de formato de ER: Intrastat (formato)</span><span class="sxs-lookup"><span data-stu-id="0d8ce-118">ER format configuration: Intrastat (format)</span></span>](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
