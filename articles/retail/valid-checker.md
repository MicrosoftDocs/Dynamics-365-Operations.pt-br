---
title: Verificador de consistência das transações de varejo
description: Este tópico descreve a funcionalidade do verificador de consistência das transações de varejo no Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 01/08/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: db01a12b92574b41f1f4fe7281c23992e0d36027
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "301919"
---
# <a name="retail-transaction-consistency-checker"></a><span data-ttu-id="01fad-103">Verificador de consistência das transações de varejo</span><span class="sxs-lookup"><span data-stu-id="01fad-103">Retail transaction consistency checker</span></span>


[!include [banner](includes/banner.md)]
[!include [preview banner](includes/preview-banner.md)]

<span data-ttu-id="01fad-104">Este tópico descreve a funcionalidade do verificador de consistência das transações de varejo introduzido no Microsoft Dynamics 365 for Finance and Operations versão 8.1.3.</span><span class="sxs-lookup"><span data-stu-id="01fad-104">This topic describes the retail transaction consistency checker functionality introduced in Microsoft Dynamics 365 for Finance and Operations version 8.1.3.</span></span> <span data-ttu-id="01fad-105">O verificador de consistência identifica e isola as transações inconsistentes antes que elas sejam coletadas pelo processo de lançamento de demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="01fad-105">The consistency checker identifies and isolates inconsistent transactions before they are picked up by the statement posting process.</span></span>

<span data-ttu-id="01fad-106">Quando um demonstrativo é lançado no Retail, o lançamento pode falhar devido a dados inconsistentes nas tabelas de transações de varejo.</span><span class="sxs-lookup"><span data-stu-id="01fad-106">When a statement is posted in Retail, posting can fail due to inconsistent data in the retail transaction tables.</span></span> <span data-ttu-id="01fad-107">O problema nos dados pode ser causado por imprevistos no aplicativo de ponto de venda (PDV) ou pela importação incorreta das transações de sistemas POS de terceiros.</span><span class="sxs-lookup"><span data-stu-id="01fad-107">The data issue may be caused by by unforeseen issues in the point of sale (POS) application, or if transactions were incorrectly imported from third-party POS systems.</span></span> <span data-ttu-id="01fad-108">Exemplos de como essas inconsistências podem ser exibidas:</span><span class="sxs-lookup"><span data-stu-id="01fad-108">Examples of how these inconsistencies may appear include:</span></span> 

  - <span data-ttu-id="01fad-109">O total da transação na tabela do cabeçalho não corresponde ao total da transação nas linhas.</span><span class="sxs-lookup"><span data-stu-id="01fad-109">The transaction total on the header table does not match the transaction total on the lines.</span></span>
  - <span data-ttu-id="01fad-110">A contagem de linhas na tabela do cabeçalho não corresponde ao número de linhas na tabela de transações.</span><span class="sxs-lookup"><span data-stu-id="01fad-110">The line count on the header table does not match with the number of lines in the transaction table.</span></span>
  - <span data-ttu-id="01fad-111">Os impostos na tabela do cabeçalho não correspondem ao valor do imposto nas linhas.</span><span class="sxs-lookup"><span data-stu-id="01fad-111">Taxes on the header table do not match the tax amount on the lines.</span></span> 
  
<span data-ttu-id="01fad-112">Quando transações inconsistentes são coletadas pelo processo de lançamento de demonstrativo, diários de pagamentos e faturas de vendas inconsistentes são criados e, consequentemente, o processo inteiro falha.</span><span class="sxs-lookup"><span data-stu-id="01fad-112">When inconsistent transactions are picked up by the statement posting process, inconsistent sales invoices and payment journals are created, and the entire statement posting process fails as a result.</span></span> <span data-ttu-id="01fad-113">Recuperar os demonstrativos desse estado envolve correções complexas de dados em várias tabelas de transações.</span><span class="sxs-lookup"><span data-stu-id="01fad-113">Recovering the statements from such a state involves complex data fixes across multiple transaction tables.</span></span> <span data-ttu-id="01fad-114">O verificador de consistência das transações de varejo evita esses problemas.</span><span class="sxs-lookup"><span data-stu-id="01fad-114">The retail transaction consistency checker prevents such issues.</span></span>

<span data-ttu-id="01fad-115">O gráfico a seguir ilustra o processo de lançamento com o verificador de consistência das transações.</span><span class="sxs-lookup"><span data-stu-id="01fad-115">The following chart illustrates the posting process with the transaction consistency checker.</span></span>

<span data-ttu-id="01fad-116">![Processo de lançamento de demonstrativo com o verificador de consistência das transações de varejo](./media/validchecker.png "Processo de lançamento de demonstrativo com o verificador de consistência das transações de varejo")</span><span class="sxs-lookup"><span data-stu-id="01fad-116">![Statement posting process with retail transaction consistency checker](./media/validchecker.png "Statement posting process with retail transsaction consistency checker")</span></span>

<span data-ttu-id="01fad-117">O processo em lote **Validar transações de loja** verifica a consistência das tabelas de transações de varejo para os seguintes cenários.</span><span class="sxs-lookup"><span data-stu-id="01fad-117">The **Validate store transactions** batch process checks the consistency of the retail transaction tables for the following scenarios.</span></span>

- <span data-ttu-id="01fad-118">Conta de cliente – valida que a conta de cliente nas tabelas de transações de varejo existe no cliente mestre da sede.</span><span class="sxs-lookup"><span data-stu-id="01fad-118">Customer account - Validates that the customer account in the retail transaction tables exists in the HQ customer master.</span></span>
- <span data-ttu-id="01fad-119">Contagem de linhas – valida que o número de linhas, como capturado na tabela do cabeçalho de transações, corresponde ao número de linhas nas tabelas de transações de vendas.</span><span class="sxs-lookup"><span data-stu-id="01fad-119">Line count - Validates that the number of lines, as captured on the transaction header table, matches the number of lines in the sales transaction tables.</span></span>

## <a name="set-up-the-consistency-checker"></a><span data-ttu-id="01fad-120">Configurar o verificador de consistência</span><span class="sxs-lookup"><span data-stu-id="01fad-120">Set up the consistency checker</span></span>
<span data-ttu-id="01fad-121">Configure o processo em lote "Validar transações de loja" em **Varejo \> TI de Varejo \> Lançamento do PDV** para execuções periódicas.</span><span class="sxs-lookup"><span data-stu-id="01fad-121">Configure the "Validate store transactions" batch process, at **Retail \> Retail IT \> POS posting**, for periodic runs.</span></span> <span data-ttu-id="01fad-122">O trabalho em lotes pode ser agendado com base na hierarquia da organização da loja, semelhante a como os processos "Calcular demonstrativos em lote" e "Lançar demonstrativos em lote" são configurados.</span><span class="sxs-lookup"><span data-stu-id="01fad-122">The batch job can be scheduled based on store organization hierarchy, similar to how the "Calculate statement in batch" and "Post statement in batch" processes are set up.</span></span> <span data-ttu-id="01fad-123">É recomendável configurar esse processo em lote para ser executado várias vezes em um dia e agendá-lo de forma que isso ocorra ao final de cada execução de trabalho P.</span><span class="sxs-lookup"><span data-stu-id="01fad-123">We recommend that you configure this batch process to run multiple times in a day and schedule it so that it runs at the end of every P-job execution.</span></span>

## <a name="results-of-validation-process"></a><span data-ttu-id="01fad-124">Resultados do processo de validação</span><span class="sxs-lookup"><span data-stu-id="01fad-124">Results of validation process</span></span>
<span data-ttu-id="01fad-125">Os resultados da verificação de validação pelo processo em lote são marcados na transação de varejo apropriada.</span><span class="sxs-lookup"><span data-stu-id="01fad-125">The results of the validation check by the batch process are tagged on the appropriate retail transaction.</span></span> <span data-ttu-id="01fad-126">O campo **Status de validação** do registro de transação de varejo é definido como **Êxito** ou **Erro** e a data da última execução de validação aparece no campo **Hora da última validação**.</span><span class="sxs-lookup"><span data-stu-id="01fad-126">The **Validation status** field on the retail transaction record is either set to **Successful** or **Error**, and the date of the last validation run appears on the **Last validation time** field.</span></span>

<span data-ttu-id="01fad-127">Para exibir um texto de erro mais descritivo referente a uma falha de validação, selecione o registro de transação de loja de varejo relevante e clique no botão **Erros de validação**.</span><span class="sxs-lookup"><span data-stu-id="01fad-127">To view more descriptive error text relating to a validation failure, select the relevant retail store transaction record and click the **Validation errors** button.</span></span>

<span data-ttu-id="01fad-128">As transações que forem reprovadas na verificação de validação e as que ainda não tiverem sido validadas não serão incluídas nos demonstrativos.</span><span class="sxs-lookup"><span data-stu-id="01fad-128">Transactions that fail the validation check and transactions that have not yet been validated will not be pulled into statements.</span></span> <span data-ttu-id="01fad-129">Durante o processo "Calcular demonstrativo", os usuários serão notificados se houver transações que poderiam ter sido incluídas no demonstrativo, mas não foram.</span><span class="sxs-lookup"><span data-stu-id="01fad-129">During the "Calculate statement" process, users will be notified if there are transactions that could have been included in the statement but weren't.</span></span>

<span data-ttu-id="01fad-130">Se um erro de validação for encontrado, a única maneira de corrigi-lo é entrar em contato com o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01fad-130">If a validation error is found, the only way to fix the error is to contact Microsoft Support.</span></span> <span data-ttu-id="01fad-131">Em uma versão futura, será adicionado um recurso para que os usuários possam corrigir os registros com falha por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="01fad-131">In a future release, capability will be added so that users can fix the records that failed through the user interface.</span></span> <span data-ttu-id="01fad-132">Recursos de registro e auditoria também serão disponibilizados para rastrear o histórico de modificações.</span><span class="sxs-lookup"><span data-stu-id="01fad-132">Logging and auditing capabilities will also be made available to trace the history of the modifications.</span></span>

> [!NOTE]
> <span data-ttu-id="01fad-133">Regras de validação adicionais para oferecer suporte a mais cenários serão adicionadas em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="01fad-133">Additional validation rules to support more scenarios will be added in a future release.</span></span>
