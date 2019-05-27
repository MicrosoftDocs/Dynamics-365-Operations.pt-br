---
title: Corrigir uma fatura de texto livre
description: Este artigo explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma nota fiscal corrigida.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c1b90b7b2c02a53e53cc13d70445a237b126d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559770"
---
# <a name="correct-a-free-text-invoice"></a><span data-ttu-id="4f115-103">Corrigir uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="4f115-103">Correct a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f115-104">Este artigo explica como corrigir uma nota fiscal de texto livre que foi lançada e emiti-la novamente como uma nota fiscal corrigida.</span><span class="sxs-lookup"><span data-stu-id="4f115-104">This article explains how to correct a free text invoice that has been posted and reissue it as a corrected invoice.</span></span>

<span data-ttu-id="4f115-105">Para corrigir uma fatura de texto livre que já foi lançada, abra a fatura de texto livre lançada.</span><span class="sxs-lookup"><span data-stu-id="4f115-105">To correct a free text invoice that has already been posted, open the posted free text invoice.</span></span> <span data-ttu-id="4f115-106">Na página **Fatura**, selecione **Cancelamento** e, em seguida, selecione **Corrigir fatura**.</span><span class="sxs-lookup"><span data-stu-id="4f115-106">On the **Invoice** page, select **Cancel**, and then select **Correct invoice**.</span></span> <span data-ttu-id="4f115-107">Selecione um código de motivo, adicione comentários, e selecione a data para a nova fatura corrigida.</span><span class="sxs-lookup"><span data-stu-id="4f115-107">Select a reason code, add comments, and select the date for new corrected invoice.</span></span> <span data-ttu-id="4f115-108">Você pode modificar a fatura corrigida e lançá-la.</span><span class="sxs-lookup"><span data-stu-id="4f115-108">You can modify the corrected invoice, and post it.</span></span> 

<span data-ttu-id="4f115-109">Ao lançar a fatura corrigida, uma fatura de cancelamento será criada para um valor de crédito que é igual ao valor da fatura original.</span><span class="sxs-lookup"><span data-stu-id="4f115-109">When you post the corrected invoice, a canceling invoice is created for a credit amount that equals the original invoice amount.</span></span> <span data-ttu-id="4f115-110">Sendo assim, o saldo combinado da fatura original e da fatura de cancelamento é igual a 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4f115-110">Therefore, the combined balance of the original invoice and the canceling invoice is 0 (zero).</span></span> <span data-ttu-id="4f115-111">A fatura de cancelamento é liquidada com relação à fatura original.</span><span class="sxs-lookup"><span data-stu-id="4f115-111">The canceling invoice is settled against the original invoice.</span></span> 

<span data-ttu-id="4f115-112">Depois de lançar a fatura corrigida, você terá três faturas:</span><span class="sxs-lookup"><span data-stu-id="4f115-112">After you post the corrected invoice, you will have three invoices:</span></span>

-   <span data-ttu-id="4f115-113">**Fatura original** – A fatura que inclui as informações que você está corrigindo.</span><span class="sxs-lookup"><span data-stu-id="4f115-113">**Original invoice** – The invoice that includes the information that you're correcting.</span></span>
-   <span data-ttu-id="4f115-114">**Fatura de cancelamento** – A fatura de crédito gerada pelo sistema, criada para cancelar a fatura que foi corrigida recentemente.</span><span class="sxs-lookup"><span data-stu-id="4f115-114">**Canceling invoice** – The system-generated credit invoice that was created to cancel the invoice that was most recently corrected.</span></span>
-   <span data-ttu-id="4f115-115">**Fatura corrigida** – A fatura que contém as informações da fatura corrigida.</span><span class="sxs-lookup"><span data-stu-id="4f115-115">**Corrected invoice** – The invoice that contains the corrected invoice information.</span></span>

<span data-ttu-id="4f115-116">Você pode identificar faturas de correção e cancelamento de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="4f115-116">You can identify canceling and correcting invoices in two ways:</span></span>

-   <span data-ttu-id="4f115-117">A página **Todas as faturas de texto livre** inclui uma coluna de **Correção**, onde você pode ver quais faturas são faturas de cancelamento e faturas corrigidas.</span><span class="sxs-lookup"><span data-stu-id="4f115-117">The **All free text invoices** page includes a **Correction** column, where you can see which invoices are canceling invoices and corrected invoices.</span></span>
-   <span data-ttu-id="4f115-118">O cabeçalho da fatura de texto livre exibe um status de **Fatura de cancelamento '\[número da fatura\]'** ou **Fatura corrigida '\[número da fatura\]'**.</span><span class="sxs-lookup"><span data-stu-id="4f115-118">The header of the free text invoice shows a status of **Cancelling invoice '\[invoice number\]'** or **Corrected invoice '\[invoice number\]'**.</span></span>

> [!NOTE]
> <span data-ttu-id="4f115-119">Este recurso está disponível somente se a chave de configuração **Correção de fatura de texto livre** estiver selecionada.</span><span class="sxs-lookup"><span data-stu-id="4f115-119">This feature is available only if the **Free text invoice correction** configuration key is selected.</span></span>



