---
title: Exibir resultados da automação de fatura de fornecedor (versão preliminar)
description: Este tópico explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: baa2f1f55dfb9bb93b4f27c45db563e39850dd37
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969717"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="ea60e-103">Exibir resultados da automação de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="ea60e-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea60e-104">Este tópico explica como exibir o status de faturas de fornecedor que estão no processo de envio para fluxo de trabalho automatizado.</span><span class="sxs-lookup"><span data-stu-id="ea60e-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="ea60e-105">Os detalhes do histórico de automação são mantidos para cada fatura de fornecedor importada.</span><span class="sxs-lookup"><span data-stu-id="ea60e-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="ea60e-106">Dependendo dos processos comerciais que você automatizou, a página **Faturas de fornecedor pendentes** mostra o **Status de correspondência automática de recibo** e o **Status de envio para fluxo de trabalho automatizado**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="ea60e-107">Você pode exibir os detalhes e fazer um plano para focar nas faturas que falharam em uma etapa automatizada.</span><span class="sxs-lookup"><span data-stu-id="ea60e-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="ea60e-108">Em seguida, depois de corrigir o problema, você poderá retomar o processo automatizado para a fatura importada.</span><span class="sxs-lookup"><span data-stu-id="ea60e-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="ea60e-109">Para poder editar uma fatura que foi enviada, você deve pausar o processamento automatizado.</span><span class="sxs-lookup"><span data-stu-id="ea60e-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="ea60e-110">Se uma fatura no processo de envio para fluxo de trabalho automatizado precisar ser pausada, defina o campo **Incluir no processamento automatizado** como **Não** na página **Faturas do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="ea60e-111">A automação não será executada até que a opção **Incluir no processamento automatizado** seja definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="ea60e-112">Uma fatura pode ser pausada da automação adicional, se ainda não estiver no sistema do fluxo de trabalho e não for usada pelo processo automatizado.</span><span class="sxs-lookup"><span data-stu-id="ea60e-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="ea60e-113">Se uma fatura importada estiver sujeita ao processo de envio para o fluxo de trabalho, você poderá exibir seu valor de **Status de automação** na página **Faturas do fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="ea60e-114">Os seguintes status são rastreados:</span><span class="sxs-lookup"><span data-stu-id="ea60e-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="ea60e-115">**Incluído** – os processos automatizados definidos na página **Parâmetros de contas a pagar** estão sendo executados corretamente, mas ainda não foram preenchidos.</span><span class="sxs-lookup"><span data-stu-id="ea60e-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="ea60e-116">**Pausado** – os processos automatizados definidos na página **Parâmetros de contas a pagar** foram executados, mas pelo menos uma etapa no processo falhou.</span><span class="sxs-lookup"><span data-stu-id="ea60e-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="ea60e-117">O status **Pausado** também é aplicado se o campo **Incluir no processamento automatizado** estiver definido como **Não**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="ea60e-118">Você pode exibir as falhas selecionando o botão **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="ea60e-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="ea60e-119">**No fluxo de trabalho** – a fatura importada foi enviada para o sistema de fluxo de trabalho, seja pelo processo de envio para fluxo de trabalho automatizado ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="ea60e-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="ea60e-120">**Fluxo de trabalho concluído** – o processo de fluxo de trabalho foi concluído para a fatura importada.</span><span class="sxs-lookup"><span data-stu-id="ea60e-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>
