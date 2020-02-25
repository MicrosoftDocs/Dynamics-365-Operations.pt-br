---
title: Transferir razão auxiliar para a Contabilidade
description: Este tópico descreve recursos no Microsoft Dynamics 365 Finance relacionados ao processo de transferência do razão auxiliar na contabilidade.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1ae10f406148e213fd0272d1387f15606233be27
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000438"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="5d96d-103">Transferir razão auxiliar para a Contabilidade</span><span class="sxs-lookup"><span data-stu-id="5d96d-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d96d-104">Este tópico descreve os recursos no Microsoft Dynamics 365 Finance que estão relacionados às regras de transferência em lotes das entradas no diário-razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="5d96d-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="5d96d-105">Na versão 8.1, as alterações foram feitas para permitir a transferência de regras, o que substituiu a opção Síncrona.</span><span class="sxs-lookup"><span data-stu-id="5d96d-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the Synchronous option.</span></span> <span data-ttu-id="5d96d-106">Para obter mais informações, consulte [Recursos removidos ou substituídos do Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="5d96d-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="5d96d-107">As opções a seguir estão disponíveis para transferir lotes do razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="5d96d-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="5d96d-108">Assíncrona – Esta opção imediatamente agendará a transferência das entradas de contabilidade do razão auxiliar para a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5d96d-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="5d96d-109">O comprovante da contabilidade será registrado assim que os recursos estiverem livres para processar esta solicitação no servidor.</span><span class="sxs-lookup"><span data-stu-id="5d96d-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="5d96d-110">Lote agendado – Esta opção permitirá adicionar as entradas de contabilidade do razão auxiliar que estão sendo transferidas para a fila de processamento na contabilidade, na qual as entradas serão processadas na ordem em que forem recebidas.</span><span class="sxs-lookup"><span data-stu-id="5d96d-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="5d96d-111">O comprovante da contabilidade será registrado no horário agendado se os recursos estiverem livres para processar o trabalho em lotes no servidor.</span><span class="sxs-lookup"><span data-stu-id="5d96d-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="5d96d-112">Na versão 10.0.8, foram feitas melhorias para aprimorar o desempenho da opção Assíncrona.</span><span class="sxs-lookup"><span data-stu-id="5d96d-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchrounous option.</span></span> <span data-ttu-id="5d96d-113">Este recurso está habilitado com o nome **Transferência do razão auxiliar para a otimização do desempenho da Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="5d96d-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="5d96d-114">Esta funcionalidade aprimora a transferência de dados do razão auxiliar para a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5d96d-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="5d96d-115">Ela permite que o processo seja mais eficiente e agrupa conjuntos de transações menores para a transferência.</span><span class="sxs-lookup"><span data-stu-id="5d96d-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="5d96d-116">Isto permite um uso mais eficiente do servidor de lote.</span><span class="sxs-lookup"><span data-stu-id="5d96d-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="5d96d-117">Esta funcionalidade requer que o servidor de lote esteja configurado, conectado e funcionando para que a opção de transferência Assíncrona seja executada corretamente.</span><span class="sxs-lookup"><span data-stu-id="5d96d-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchrounous transfer option to work.</span></span> 
