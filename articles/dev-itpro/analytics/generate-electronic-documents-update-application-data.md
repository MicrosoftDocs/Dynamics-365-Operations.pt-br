---
title: "Gerar documentos eletrônicos e atualizar dados de aplicativos usando ER"
description: "Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo do Finance and Operations para gerar documentos eletrônicos de saída. Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: 2a989b0000766478c71b243d7793b2fc8c4ece28
ms.contentlocale: pt-br
ms.lasthandoff: 08/13/2018

---

# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="81bd5-104">Gerar documentos eletrônicos e atualizar dados de aplicativos usando ER</span><span class="sxs-lookup"><span data-stu-id="81bd5-104">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81bd5-105">Você pode criar os formatos de Relatório eletrônico (ER) que podem ser usados no aplicativo do Finance and Operations para gerar documentos eletrônicos de saída.</span><span class="sxs-lookup"><span data-stu-id="81bd5-105">You can design Electronic reporting (ER) formats that can be used in the Finance and Operations application to generate outgoing electronic documents.</span></span> <span data-ttu-id="81bd5-106">Você também pode criar os formatos de ER que analisam documentos eletrônicos de entrada e usam o conteúdo desses documentos para atualizar dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81bd5-106">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="81bd5-107">Com esta funcionalidade, um único formato de ER pode ser usado para gerar documentos eletrônicos de saída e, em seguida, atualizar os dados de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81bd5-107">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="81bd5-108">Este recurso também pode ser usado nestes cenários:</span><span class="sxs-lookup"><span data-stu-id="81bd5-108">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="81bd5-109">Para evitar o uso repetido de dados de aplicativo em processos subsequentes você pode marcar os dados de aplicativo imediatamente após ser usado para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="81bd5-109">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="81bd5-110">Por exemplo, você pode marcar transações de pagamento como já processadas imediatamente após terem sido incluídas em uma mensagem de pagamento gerada.</span><span class="sxs-lookup"><span data-stu-id="81bd5-110">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="81bd5-111">Para armazenar os detalhes de processamento de documentos eletrônicos gerados usando a lógica de ER.</span><span class="sxs-lookup"><span data-stu-id="81bd5-111">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="81bd5-112">Por exemplo, uma identificação exclusiva da mensagem de pagamento gerada usando a expressão de ER.</span><span class="sxs-lookup"><span data-stu-id="81bd5-112">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="81bd5-113">A expressão é baseada nas informações inseridas na caixa de diálogo de ER quando o formato de ER é executado para gerar documentos.</span><span class="sxs-lookup"><span data-stu-id="81bd5-113">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="81bd5-114">Para saber mais sobre este recurso, execute o conjunto de Guias de tarefas do ER Gerar documentos com atualização de dados do aplicativo (parte do processo comercial do 7.5.4.3 Adquirir/Desenvolver componentes de solução/serviço de TI (10677)), que o acompanham pelos detalhes de relatório e arquivamento do intrastat.</span><span class="sxs-lookup"><span data-stu-id="81bd5-114">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="81bd5-115">Os arquivos a seguir são necessários para concluir determinadas etapas nessas Guias de tarefas.</span><span class="sxs-lookup"><span data-stu-id="81bd5-115">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="81bd5-116">Baixe os arquivos e salve-os no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="81bd5-116">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="81bd5-117">Configuração de modelo de dados de ER: Intrastat (modelo)</span><span class="sxs-lookup"><span data-stu-id="81bd5-117">ER data model configuration: Intrastat (model)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="81bd5-118">Configuração de mapeamento de modelo de ER: Intrastat (mapeamento)</span><span class="sxs-lookup"><span data-stu-id="81bd5-118">ER model mapping configuration: Intrastat (mapping)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)
- [<span data-ttu-id="81bd5-119">Configuração de formato de ER: Intrastat (formato)</span><span class="sxs-lookup"><span data-stu-id="81bd5-119">ER format configuration: Intrastat (format)</span></span>](https://go.microsoft.com/fwlink/?linkid=849038)

