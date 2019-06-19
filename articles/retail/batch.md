---
title: Manuseio aprimorado de itens de lote rastreados
description: Este tópico descreve os aprimoramentos feitos no manuseio de lotes para itens de lote rastreados durante o processo de lançamento de demonstrativo de varejo.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4456fc3d5bc4547fa8211642b11ca6df455fa187
ms.sourcegitcommit: aec1dcd44274e9b8d0770836598fde5533b7b569
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2019
ms.locfileid: "1617380"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="542fa-103">Manuseio aprimorado de itens de lote rastreados</span><span class="sxs-lookup"><span data-stu-id="542fa-103">Improved handling of batch-tracked items</span></span>

<span data-ttu-id="542fa-104">No ponto de venda (PDV) do Microsoft Dynamics 365 for Retail, os números de lotes não podem ser capturados para itens de lote rastreados no momento da venda.</span><span class="sxs-lookup"><span data-stu-id="542fa-104">In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="542fa-105">No entanto, para configurações específicas, quando as vendas lançadas na matriz por meio de ordens de cliente ou lançamento de demonstrativo, o sistema do Microsoft Dynamics espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.</span><span class="sxs-lookup"><span data-stu-id="542fa-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="542fa-106">Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="542fa-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="542fa-107">Caso contrário, processo de faturamento da ordem do cliente não poderá fazer o lançamento e o usuário do PDV receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="542fa-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="542fa-108">O lançamento do demonstrativo entrará então em um estado de erro.</span><span class="sxs-lookup"><span data-stu-id="542fa-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="542fa-109">Esse estado de erro ocorrerá mesmo quando o estoque negativo tiver sido ativado para os produtos.</span><span class="sxs-lookup"><span data-stu-id="542fa-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="542fa-110">Os aprimoramentos feitos no Microsoft Dynamics for Retail versão 10.0.4 e posterior ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="542fa-110">Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="542fa-111">A nova funcionalidade usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="542fa-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="542fa-112">Para definir a ID padrão do lote usada para ordens de cliente, na página **Parâmetros de varejo** , na guia **Ordens do cliente**, na FastTab **Ordem**, defina o campo **ID de lote padrão**.</span><span class="sxs-lookup"><span data-stu-id="542fa-112">To define the default batch ID that is used for customer orders, on the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="542fa-113">Para definir a ID de lote padrão usada para o faturamento da ordem do cliente por meio do lançamento de demonstrativo, na página **Parâmetros de varejo**, na guia **Lançamento**, na FastTab **Atualização de estoque**, defina o campo **ID de lote padrão**.</span><span class="sxs-lookup"><span data-stu-id="542fa-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Retail parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="542fa-114">Esta funcionalidade ficará disponível somente quando o armazenamento avançado for ativado para os depósitos e o itens de específicos da loja.</span><span class="sxs-lookup"><span data-stu-id="542fa-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="542fa-115">Em uma versão posterior, a funcionalidade também terá suporte para cenários em que o gerenciamento de armazenamento não é usado.</span><span class="sxs-lookup"><span data-stu-id="542fa-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>
