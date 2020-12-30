---
title: Declaração de imposto do SPED-Reinf (Brasil)
description: Este tópico fornece informações sobre a configuração de eventos do SPED-Reinf usando Livros fiscais e a estrutura de registro de relatórios SII no Microsoft Dynamics 365 Finance para o Brasil.
author: sndray
manager: AnnBe
ms.date: 01/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 399e30597628c91ccb4d896b899f6152a12caffd
ms.sourcegitcommit: e544c51a68ad5daf748c0e877bdbde094ad40bd2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4408499"
---
# <a name="sped-reinf-tax-statement-brazil"></a><span data-ttu-id="b0e47-103">Declaração de imposto do SPED-Reinf (Brasil)</span><span class="sxs-lookup"><span data-stu-id="b0e47-103">SPED-Reinf tax statement (Brazil)</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b0e47-104">O SPED-Reinf é um novo relatório de declaração de imposto que coleta informações sobre imposto retido na fonte e outras informações fiscais de interesse da Receita Federal do Brasil (RFB) e da Previdência Social.</span><span class="sxs-lookup"><span data-stu-id="b0e47-104">The SPED-Reinf is a new tax statement report that gathers information about withholding tax and other tax information that is of interest from the Brazilian Internal Revenue Service (RFB) and Social Security.</span></span> <span data-ttu-id="b0e47-105">(Reinf significa "Retenções e Outras Informações Fiscais".) A declaração consiste em um conjunto de eventos que devem ser entregues, em layouts específicos, por meio do ambiente do Sistema Público de Escrituração Digital (SPED).</span><span class="sxs-lookup"><span data-stu-id="b0e47-105">(In Brazilian Portuguese, Reinf stands for "Retenções e Outras Informações Fiscais.") The statement consists of a set of events that must be delivered, in specific layouts, through the environment of the public digital bookkeeping system (SPED).</span></span> <span data-ttu-id="b0e47-106">Além disso, eles devem ser entregues usando um certificado digital válido, emitido por uma entidade credenciada pela Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil).</span><span class="sxs-lookup"><span data-stu-id="b0e47-106">Additionally, they must be delivered by using a valid digital certificate that is issued by an entity that is accredited by the Brazilian Public Key Infrastructure (ICP-Brasil).</span></span> <span data-ttu-id="b0e47-107">A declaração será considerada válida após a confirmação do recebimento e a validação do conteúdo dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-107">The statement will be considered valid after receipt is confirmed and the contents of the files are validated.</span></span>

<span data-ttu-id="b0e47-108">O SPED-Reinf foi criado para apurar impostos federais retidos, para fins de imposto de renda e Previdência Social, em atividades que não estão relacionadas ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0e47-108">The SPED-Reinf was created to assess federal taxes that are withheld, for Social Security and income taxes purposes, for activities that aren't related to labor.</span></span> <span data-ttu-id="b0e47-109">Exemplos dessas atividades incluem notas fiscais, pagamentos e outros eventos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-109">Examples of these activities include fiscal documents, payments, and other events.</span></span>

<span data-ttu-id="b0e47-110">O Microsoft Dynamics oferece suporte à geração de eventos do SPED-Reinf por meio do módulo **Livros fiscais** e da estrutura de registro de relatórios SII.</span><span class="sxs-lookup"><span data-stu-id="b0e47-110">Microsoft Dynamics supports the generation of SPED-Reinf events through the **Fiscal books** module and the SII reporting register framework.</span></span> <span data-ttu-id="b0e47-111">Os usuários podem trocar mensagens XML para cada evento exigido pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-111">Users can exchange XML messages for every event that is required by the tax authority.</span></span>

<span data-ttu-id="b0e47-112">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="b0e47-112">**Scope**</span></span>

-   <span data-ttu-id="b0e47-113">Versão do SPED-Reinf compatível: 1.3.</span><span class="sxs-lookup"><span data-stu-id="b0e47-113">Supported SPED-Reinf version: 1.3.</span></span>

-   <span data-ttu-id="b0e47-114">Versões com suporte: Microsoft Dynamics AX 2012 R3 e Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b0e47-114">Supported versions: Microsoft Dynamics AX 2012 R3 and Microsoft Dynamics 365 for Finance and Operations.</span></span>

-   <span data-ttu-id="b0e47-115">A procuração eletrônica não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="b0e47-115">Electronic power of attorney (procuração eletronica) isn't supported.</span></span>

<span data-ttu-id="b0e47-116">**Tabela de eventos**</span><span class="sxs-lookup"><span data-stu-id="b0e47-116">**Table of events**</span></span>

| <span data-ttu-id="b0e47-117">Evento</span><span class="sxs-lookup"><span data-stu-id="b0e47-117">Event</span></span> | <span data-ttu-id="b0e47-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="b0e47-118">Description</span></span>                                                   | <span data-ttu-id="b0e47-119">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="b0e47-119">Event type</span></span>             | <span data-ttu-id="b0e47-120">Com suporte no Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="b0e47-120">Supported in Microsoft Dynamics</span></span> | <span data-ttu-id="b0e47-121">Comentários</span><span class="sxs-lookup"><span data-stu-id="b0e47-121">Comments</span></span>                                                                                                                                                                |
|-----------|-------------------------------------------------------------------|----------------------------|-------------------------------------|----------------------------------------|
| <span data-ttu-id="b0e47-122">R-1000</span><span class="sxs-lookup"><span data-stu-id="b0e47-122">R-1000</span></span>    | <span data-ttu-id="b0e47-123">Informações do contribuinte</span><span class="sxs-lookup"><span data-stu-id="b0e47-123">Taxpayer information</span></span>                                              | <span data-ttu-id="b0e47-124">Inicial</span><span class="sxs-lookup"><span data-stu-id="b0e47-124">Initial</span></span>                    | <span data-ttu-id="b0e47-125">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-125">**Yes**</span></span>                             | <span data-ttu-id="b0e47-126">Suporte para contribuintes como entidades legais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-126">Support for taxpayers as legal entities.</span></span>   |
| <span data-ttu-id="b0e47-127">R-1070</span><span class="sxs-lookup"><span data-stu-id="b0e47-127">R-1070</span></span>    | <span data-ttu-id="b0e47-128">Processo administrativo e judicial</span><span class="sxs-lookup"><span data-stu-id="b0e47-128">Administrative and Judicial process</span></span>                               | <span data-ttu-id="b0e47-129">Quando um processo está em vigor</span><span class="sxs-lookup"><span data-stu-id="b0e47-129">When a process is in place</span></span> | <span data-ttu-id="b0e47-130">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-130">**Yes**</span></span>                             |                                              |
| <span data-ttu-id="b0e47-131">R-2010</span><span class="sxs-lookup"><span data-stu-id="b0e47-131">R-2010</span></span>    | <span data-ttu-id="b0e47-132">Serviços adquiridos</span><span class="sxs-lookup"><span data-stu-id="b0e47-132">Acquired services</span></span>                                                 | <span data-ttu-id="b0e47-133">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-133">Periodic event</span></span>             | <span data-ttu-id="b0e47-134">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-134">**Yes**</span></span>                             | <span data-ttu-id="b0e47-135">Sem suporte para estabelecimentos fiscais compradores como construções civis.</span><span class="sxs-lookup"><span data-stu-id="b0e47-135">No support for acquirer fiscal establishments as civil constructions.</span></span> <span data-ttu-id="b0e47-136">(As construções civis exigem um CNO em vez de um CNPJ.)</span><span class="sxs-lookup"><span data-stu-id="b0e47-136">(Civil constructions require a CNO instead of a CNPJ.)</span></span>                                                |
| <span data-ttu-id="b0e47-137">R-2020</span><span class="sxs-lookup"><span data-stu-id="b0e47-137">R-2020</span></span>    | <span data-ttu-id="b0e47-138">Serviços fornecidos</span><span class="sxs-lookup"><span data-stu-id="b0e47-138">Provided services</span></span>                                                 | <span data-ttu-id="b0e47-139">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-139">Periodic event</span></span>             | <span data-ttu-id="b0e47-140">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-140">**Yes**</span></span>                             | <span data-ttu-id="b0e47-141">Sem suporte para tomadores de serviço (clientes) como construções civis.</span><span class="sxs-lookup"><span data-stu-id="b0e47-141">No support for service takers (customers) as civil constructions.</span></span> <span data-ttu-id="b0e47-142">(As construções civis exigem um CNO em vez de um CNPJ.)</span><span class="sxs-lookup"><span data-stu-id="b0e47-142">(Civil constructions require a CNO instead of a CNPJ.)</span></span>                                                    |
| <span data-ttu-id="b0e47-143">R-2030</span><span class="sxs-lookup"><span data-stu-id="b0e47-143">R-2030</span></span>    | <span data-ttu-id="b0e47-144">Valores recebidos por associações esportivas</span><span class="sxs-lookup"><span data-stu-id="b0e47-144">Amounts received by sport associations</span></span>                            | <span data-ttu-id="b0e47-145">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-145">Periodic event</span></span>             | <span data-ttu-id="b0e47-146">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-146">**No**</span></span>                              |                                              |
| <span data-ttu-id="b0e47-147">R-2040</span><span class="sxs-lookup"><span data-stu-id="b0e47-147">R-2040</span></span>    | <span data-ttu-id="b0e47-148">Valores pagos a associações esportivas</span><span class="sxs-lookup"><span data-stu-id="b0e47-148">Amounts paid to sport associations</span></span>                                | <span data-ttu-id="b0e47-149">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-149">Periodic event</span></span>             | <span data-ttu-id="b0e47-150">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-150">**No**</span></span>                              |                                              |
| <span data-ttu-id="b0e47-151">R-2050</span><span class="sxs-lookup"><span data-stu-id="b0e47-151">R-2050</span></span>    | <span data-ttu-id="b0e47-152">Comércio da produção rural por entidades legais rurais ou pelo agronegócio</span><span class="sxs-lookup"><span data-stu-id="b0e47-152">Trade of rural production by rural legal entities or agribusiness</span></span> | <span data-ttu-id="b0e47-153">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-153">Periodic event</span></span>             | <span data-ttu-id="b0e47-154">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-154">**No**</span></span>                              |                                               |
| <span data-ttu-id="b0e47-155">R-2060</span><span class="sxs-lookup"><span data-stu-id="b0e47-155">R-2060</span></span>    | <span data-ttu-id="b0e47-156">Apuração do INSS-CPRB</span><span class="sxs-lookup"><span data-stu-id="b0e47-156">INSS-CPRB assessment</span></span>                                              | <span data-ttu-id="b0e47-157">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-157">Periodic event</span></span>             | <span data-ttu-id="b0e47-158">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-158">**Yes**</span></span>                             | <span data-ttu-id="b0e47-159">Sem suporte para apuração do imposto CPRB das operações do Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0e47-159">No support for CPRB tax assessment from Commerce operations.</span></span>  |
| <span data-ttu-id="b0e47-160">R-2070</span><span class="sxs-lookup"><span data-stu-id="b0e47-160">R-2070</span></span>    | <span data-ttu-id="b0e47-161">Retenção em pagamentos (IR, CSLL, PIS, COFINS)</span><span class="sxs-lookup"><span data-stu-id="b0e47-161">Withholding on payments (IR, CSLL, PIS, COFINS)</span></span>                   | <span data-ttu-id="b0e47-162">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-162">Periodic event</span></span>             | <span data-ttu-id="b0e47-163">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-163">**No**</span></span>                              | <span data-ttu-id="b0e47-164">O suporte será incluído como um recurso separado na próxima versão.</span><span class="sxs-lookup"><span data-stu-id="b0e47-164">Support will be included as a separate feature in the next release.</span></span> <span data-ttu-id="b0e47-165">Para obter mais informações, consulte **Sped REINF - evento R-2070** no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b0e47-165">For more information, see **Sped REINF - event R-2070** in Microsoft Dynamics Lifecycle Services (LCS).</span></span> |
| <span data-ttu-id="b0e47-166">R-2098</span><span class="sxs-lookup"><span data-stu-id="b0e47-166">R-2098</span></span>    | <span data-ttu-id="b0e47-167">Reabertura de atividades periódicas</span><span class="sxs-lookup"><span data-stu-id="b0e47-167">Reopening of periodic</span></span>                                             | <span data-ttu-id="b0e47-168">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-168">Periodic event</span></span>             | <span data-ttu-id="b0e47-169">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-169">**Yes**</span></span>                             |                                                |
| <span data-ttu-id="b0e47-170">R-2099</span><span class="sxs-lookup"><span data-stu-id="b0e47-170">R-2099</span></span>    | <span data-ttu-id="b0e47-171">Fechamento</span><span class="sxs-lookup"><span data-stu-id="b0e47-171">Closing</span></span>                                                           | <span data-ttu-id="b0e47-172">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-172">Periodic event</span></span>             | <span data-ttu-id="b0e47-173">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-173">**Yes**</span></span>                             |                                              |
| <span data-ttu-id="b0e47-174">R-3010</span><span class="sxs-lookup"><span data-stu-id="b0e47-174">R-3010</span></span>    | <span data-ttu-id="b0e47-175">Receita de espetáculo de esporte</span><span class="sxs-lookup"><span data-stu-id="b0e47-175">Sport spectacle revenue</span></span>                                           | <span data-ttu-id="b0e47-176">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-176">Non-periodic event</span></span>         | <span data-ttu-id="b0e47-177">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-177">**No**</span></span>                              |                                                |
| <span data-ttu-id="b0e47-178">R-5001</span><span class="sxs-lookup"><span data-stu-id="b0e47-178">R-5001</span></span>    | <span data-ttu-id="b0e47-179">Base de cálculo de impostos consolidada por contribuinte</span><span class="sxs-lookup"><span data-stu-id="b0e47-179">Consolidated tax calculation basis by taxpayer</span></span>                    | <span data-ttu-id="b0e47-180">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-180">Non-periodic event</span></span>         | <span data-ttu-id="b0e47-181">**Não**</span><span class="sxs-lookup"><span data-stu-id="b0e47-181">**No**</span></span>                              |                                               
| <span data-ttu-id="b0e47-182">R-5011</span><span class="sxs-lookup"><span data-stu-id="b0e47-182">R-5011</span></span>    | <span data-ttu-id="b0e47-183">Base consolidada e valor do imposto</span><span class="sxs-lookup"><span data-stu-id="b0e47-183">Consolidated base and tax amount</span></span>                                  | <span data-ttu-id="b0e47-184">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-184">Non-periodic event</span></span>         | <span data-ttu-id="b0e47-185">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-185">**Yes**</span></span>                             | <span data-ttu-id="b0e47-186">Este evento é usado para consultar o status do evento de fechamento R-2099.</span><span class="sxs-lookup"><span data-stu-id="b0e47-186">This event is used to inquire about the status of closing event R-2099.</span></span> |
| <span data-ttu-id="b0e47-187">R-9000</span><span class="sxs-lookup"><span data-stu-id="b0e47-187">R-9000</span></span>    | <span data-ttu-id="b0e47-188">Exclusão </span><span class="sxs-lookup"><span data-stu-id="b0e47-188">Deletion</span></span>                                                          | <span data-ttu-id="b0e47-189">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="b0e47-189">Non-periodic event</span></span>         | <span data-ttu-id="b0e47-190">**Sim**</span><span class="sxs-lookup"><span data-stu-id="b0e47-190">**Yes**</span></span>                             |                                                |

-   <span data-ttu-id="b0e47-191">Somente os contribuintes em conformidade com o SPED-ECD têm suporte.</span><span class="sxs-lookup"><span data-stu-id="b0e47-191">Only taxpayers that comply with SPED-ECD are supported.</span></span>

-   <span data-ttu-id="b0e47-192">Sem suporte para contribuintes como departamentos públicos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-192">No support for taxpayers as public departments.</span></span>

-   <span data-ttu-id="b0e47-193">Sem suporte para serviços fornecidos em projetos de construções civis.</span><span class="sxs-lookup"><span data-stu-id="b0e47-193">No support for services that are provided on civil constructions projects.</span></span>

-   <span data-ttu-id="b0e47-194">Sem suporte para tomadores de serviço em projetos de construções civis.</span><span class="sxs-lookup"><span data-stu-id="b0e47-194">No support for service takers on civil constructions projects.</span></span>

-   <span data-ttu-id="b0e47-195">Escrituração manual do pagamento para liquidação do valor de CPRB devido.</span><span class="sxs-lookup"><span data-stu-id="b0e47-195">Manual bookkeeping of the payment for settlement of the CPRB amount that is due.</span></span>

-   <span data-ttu-id="b0e47-196">O pagamento do valor de CPRB devido está fora do escopo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-196">Payment of the CPRB amount that is due are out of scope.</span></span>

<span data-ttu-id="b0e47-197">**Configuração do SPED-Reinf**</span><span class="sxs-lookup"><span data-stu-id="b0e47-197">**SPED-Reinf setup**</span></span>

<span data-ttu-id="b0e47-198">Esta seção descreve a configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="b0e47-198">This section describes the configuration that is required.</span></span>

### <a name="set-up-electronic-messages-functionality"></a><span data-ttu-id="b0e47-199">**Configurar a funcionalidade Mensagens eletrônicas**</span><span class="sxs-lookup"><span data-stu-id="b0e47-199">**Set up Electronic messages functionality**</span></span>

<span data-ttu-id="b0e47-200">A funcionalidade Mensagens eletrônicas é nova no Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b0e47-200">Electronic messages functionality is new in Dynamics 365 Finance.</span></span> <span data-ttu-id="b0e47-201">Ela permite manter e acompanhar vários processos de mensagens eletrônicas quando há uma troca de informações entre o Finance e os serviços Web da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-201">It lets you maintain and track various processes for electronic messages when there is an exchange of information between Finance and tax authority web services.</span></span>

<span data-ttu-id="b0e47-202">Antes de entregar eventos do SPED-Reinf ao site do governo, use a configuração predefinida que a Microsoft preparou para atender aos requisitos do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="b0e47-202">Before you issue SPED-Reinf events to government website, use the predefined configuration that Microsoft has prepared to meet SPED-Reinf requirements.</span></span> <span data-ttu-id="b0e47-203">Essa configuração é fornecida como uma entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-203">This configuration is delivered as a data entity.</span></span> <span data-ttu-id="b0e47-204">Depois de importada para o Finance, os usuários poderão gerar, validar e entregar todos os eventos descritos no escopo do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="b0e47-204">After it's imported into Finance, users will able to generate, validate, and deliver all events that are described in the SPED-Reinf scope.</span></span>

#### <a name="import-the-configuration-from-the-data-entity"></a><span data-ttu-id="b0e47-205">Importar a configuração da entidade de dados</span><span class="sxs-lookup"><span data-stu-id="b0e47-205">Import the configuration from the data entity</span></span>

<span data-ttu-id="b0e47-206">Para configurar a funcionalidade Mensagens eletrônicas para comunicações de eventos do SPED-Reinf, use a configuração predefinida disponível no LCS.</span><span class="sxs-lookup"><span data-stu-id="b0e47-206">To set up Electronic messages functionality for SPED-Reinf event communications, use the predefined configuration that is available in LCS.</span></span>

1.  <span data-ttu-id="b0e47-207">Ir para <https://lcs.dynamics.com>.</span><span class="sxs-lookup"><span data-stu-id="b0e47-207">Go to <https://lcs.dynamics.com>.</span></span>

2.  <span data-ttu-id="b0e47-208">Entre.</span><span class="sxs-lookup"><span data-stu-id="b0e47-208">Sign in.</span></span>

3.  <span data-ttu-id="b0e47-209">Selecione **Biblioteca de ativos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-209">Select **Shared asset library**.</span></span>

4.  <span data-ttu-id="b0e47-210">Na guia **Pacote de dados**, selecione as entidades de dados de comunicações de eventos do SPED Reinf e salve o arquivo no local onde as entidades de dados devem ser armazenadas.</span><span class="sxs-lookup"><span data-stu-id="b0e47-210">On the **Data package** tab, select the SPED Reinf events communications data entities, and save the file in the location where data entities should be stored.</span></span>

5.  <span data-ttu-id="b0e47-211">Entre no Finance.</span><span class="sxs-lookup"><span data-stu-id="b0e47-211">Sign in to Finance.</span></span>

6.  <span data-ttu-id="b0e47-212">Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Importar**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-212">Go to **Workspaces \> Data management**, and then select the **Import** tile.</span></span>

7.  <span data-ttu-id="b0e47-213">Insira uma descrição e um nome para identificar o trabalho, como **SpedReinf**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-213">Enter a description and a name to identify the job, such as **SpedReinf**.</span></span>

8.  <span data-ttu-id="b0e47-214">No campo **Formato de dados de origem**, selecione **Pacote**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-214">In the **Source data format** field, select **Package**.</span></span>

9.  <span data-ttu-id="b0e47-215">Selecione **Carregar** e, em seguida, selecione o arquivo que você salvou do LCS (**SPEDReinf_EMSettings.zip**).</span><span class="sxs-lookup"><span data-stu-id="b0e47-215">Select **Upload**, and then select the file that you saved from LCS (**SPEDReinf_EMSettings.zip**).</span></span>

10. <span data-ttu-id="b0e47-216">Selecione **Salvar** e aguarde até que todas as entidades de dados sejam exibidas na página.</span><span class="sxs-lookup"><span data-stu-id="b0e47-216">Select **Save** and wait until all data entities are shown on the page.</span></span>

11. <span data-ttu-id="b0e47-217">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-217">Select **Import**.</span></span>

    <span data-ttu-id="b0e47-218">Você receberá uma notificação sobre o processo de importação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-218">You receive a notification about the import process.</span></span> <span data-ttu-id="b0e47-219">Também é possível atualizar a página manualmente para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-219">You can also manually refresh the page to see the progress of the import process.</span></span> <span data-ttu-id="b0e47-220">Quando o processo for concluído, você poderá visualizar a página **Resumo de execução**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-220">When the process is completed, you can view the **Execution summary** page.</span></span>

    ![Página Resumo de execução](media/bra-execution-summary-page.png)

#### <a name="structure-of-electronic-messages"></a><span data-ttu-id="b0e47-222">Estrutura de mensagens eletrônicas</span><span class="sxs-lookup"><span data-stu-id="b0e47-222">Structure of electronic messages</span></span>

<span data-ttu-id="b0e47-223">Cada evento criado, entregue e recebido é representado por uma mensagem e um item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0e47-223">Every event that is created, delivered, and received is represented by a message and a message item.</span></span>

![Estrutura de mensagens eletrônicas](media/bra-electronic-messages-structure.png)

<span data-ttu-id="b0e47-225">O item de mensagem é representado pela mensagem de evento XML e também inclui as seguintes informações adicionais que são armazenadas na mensagem ou atualizadas no Microsoft Dynamics:</span><span class="sxs-lookup"><span data-stu-id="b0e47-225">The message item is represented by the XML event message, and it also includes the following additional information that is stored in the message or updated in Microsoft Dynamics:</span></span>

-   <span data-ttu-id="b0e47-226">O CNPJ do estabelecimento fiscal (número completo)</span><span class="sxs-lookup"><span data-stu-id="b0e47-226">The CNPJ of the fiscal establishment (full number)</span></span>

-   <span data-ttu-id="b0e47-227">O CNPJ raiz</span><span class="sxs-lookup"><span data-stu-id="b0e47-227">The root CNPJ</span></span>

-   <span data-ttu-id="b0e47-228">O período de escrituração</span><span class="sxs-lookup"><span data-stu-id="b0e47-228">The booking period</span></span>

-   <span data-ttu-id="b0e47-229">A data inicial do período para o qual a mensagem é válida</span><span class="sxs-lookup"><span data-stu-id="b0e47-229">The start date of the period that the message is valid for</span></span>

-   <span data-ttu-id="b0e47-230">O número do protocolo de recebimento</span><span class="sxs-lookup"><span data-stu-id="b0e47-230">The receipt protocol number</span></span>

-   <span data-ttu-id="b0e47-231">Um valor que indica se a mensagem está registrada no Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="b0e47-231">A value that indicates whether the message is registered in Microsoft Dynamics</span></span>

<span data-ttu-id="b0e47-232">Você pode encontrar essa configuração em **Imposto \> Configuração \> Mensagens eletrônicas \> Campos adicionais**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-232">You can find this configuration at **Tax \> Setup \> Electronic messages \> Additional fields**.</span></span>

![Campos adicionais de mensagens eletrônicas](media/bra-electronic-messaging-additional-fields.png)

> [!NOTE]
> <span data-ttu-id="b0e47-234">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-234">Don't remove this configuration.</span></span> <span data-ttu-id="b0e47-235">Essa configuração está incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="b0e47-235">This configuration is included in the package.</span></span>

<span data-ttu-id="b0e47-236">Os tipos de item de mensagem são classificados pelo tipo de evento em **Imposto \> Configuração \> Mensagens eletrônicas \> Tipos de item de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-236">The message item types are classified by the type of event at **Tax \> Setup \> Electronic messages \> Message item types**.</span></span>

![Message-types](media/bra-message-types.png)

> [!NOTE]
> <span data-ttu-id="b0e47-238">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-238">Don't remove this configuration.</span></span> <span data-ttu-id="b0e47-239">A configuração desses tipos está incluída no pacote.\*</span><span class="sxs-lookup"><span data-stu-id="b0e47-239">These types configuration are included in the package.\*</span></span>

<span data-ttu-id="b0e47-240">Vá para **Imposto \> Configuração \> Parâmetros \> Parâmetros da contabilidade** e, em seguida, na guia **Sequências numéricas**, selecione **Mensagem** e **Item de mensagem** para configurar a sequência numérica para itens de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0e47-240">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Number sequences** tab, select **Message** and **Message item** to set up the sequence number for message items.</span></span>

![Sequências numéricas de mensagens eletrônicas](media/bra-electronic-messages-number-sequences.png)

> [!NOTE]
> <span data-ttu-id="b0e47-242">A sequência numérica deve ser definida como não contínua.</span><span class="sxs-lookup"><span data-stu-id="b0e47-242">The number sequence must be defined as non-continuous.</span></span>

#### <a name="certificates"></a><span data-ttu-id="b0e47-243">Certificados</span><span class="sxs-lookup"><span data-stu-id="b0e47-243">Certificates</span></span>

<span data-ttu-id="b0e47-244">Certificados confiáveis devem ser configurados e usados pelo Microsoft Dynamics, pois o SPED-Reinf deve ser sempre assinado por um certificado e-CNPJ autorizado pela entidade ICP-Brasil, independentemente de quaisquer outras assinaturas.</span><span class="sxs-lookup"><span data-stu-id="b0e47-244">Trusted certificates must be configured and used by Microsoft Dynamics, because the SPED-Reinf should always be signed by an e-CNPJ certificate that is authorized by the ICP-Brazil entity, regardless of any other signatures.</span></span> <span data-ttu-id="b0e47-245">Esse certificado e-CNPJ deve corresponder aos oito primeiros dígitos do CNPJ do estabelecimento fiscal matriz, pois o relatório é enviado por esse estabelecimento e pelos estabelecimentos fiscais relacionados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-245">This e-CNPJ certificate should match the first eight digits of the root fiscal establishment's CNPJ, because the report is issued by the root fiscal establishment and the related fiscal establishments.</span></span>

<span data-ttu-id="b0e47-246">No Finance, você deve registrar o certificado do Key Vault no Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b0e47-246">In Finance, you must register the Key Vault certificate in Microsoft Azure.</span></span>

<span data-ttu-id="b0e47-247">Para obter informações sobre como configurar um cliente do Key Vault, consulte [Configuração do Cliente do Azure Key Vault](https://support.microsoft.com/help/4040305).</span><span class="sxs-lookup"><span data-stu-id="b0e47-247">For information about how to set up a Key Vault client, see [Setting up Azure Key Vault Client](https://support.microsoft.com/help/4040305).</span></span>

1.  <span data-ttu-id="b0e47-248">Vá para **Administração do sistema \> Configuração \> Parâmetros do Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-248">Go to **System administration \> Setup \> Key Vault parameters**.</span></span>

2.  <span data-ttu-id="b0e47-249">Digite as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b0e47-249">Enter the following information:</span></span>

    -  <span data-ttu-id="b0e47-250">URL do Key Vault</span><span class="sxs-lookup"><span data-stu-id="b0e47-250">Key Vault URL</span></span>

    -  <span data-ttu-id="b0e47-251">Cliente do Key Vault</span><span class="sxs-lookup"><span data-stu-id="b0e47-251">Key Vault client</span></span>

    -  <span data-ttu-id="b0e47-252">Chave secreta do Key Vault</span><span class="sxs-lookup"><span data-stu-id="b0e47-252">Key Vault secret key</span></span>

    -  <span data-ttu-id="b0e47-253">ID secreta do Key Vault</span><span class="sxs-lookup"><span data-stu-id="b0e47-253">Key vault secret ID</span></span>

<span data-ttu-id="b0e47-254">Após o registro, associe o certificado nos parâmetros de configuração para a ação **Geração de relatório**, conforme descrito na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0e47-254">After registration, associate the certificate in the setup parameters for the **Report generation** action, as described in the next section.</span></span>

#### <a name="setup-parameters"></a><span data-ttu-id="b0e47-255">Parâmetros de configuração</span><span class="sxs-lookup"><span data-stu-id="b0e47-255">Setup parameters</span></span> 

<span data-ttu-id="b0e47-256">Sempre que uma mensagem é criada, preparada, validada, entregue ou recebida, a ação relacionada deve ser identificada por meio de uma classe X++ em **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de classe executável**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-256">Every time that a message is created, prepared, validated, delivered, or received, the related action must be identified through a X++ class at **Tax \> Setup \> Electronic messages \> Executable class settings**.</span></span>

-   <span data-ttu-id="b0e47-257">**Preparação dos eventos –** Esta ação é usada para criar e preparar a mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="b0e47-257">**Preparation items (Preparacao dos eventos) –** This action is used to create and prepare the XML message.</span></span> <span data-ttu-id="b0e47-258">Ela solicita parâmetros adicionais, como **Data de escrituração**, **CNPJ** e **CNPJ raiz**, pois os eventos são gerados com base nessas informações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-258">It requests additional parameters, such as **Booking date**, **CNPJ**, and **CNPJ root**, because the events are generated based on this information.</span></span>

    ![Itens de preparação](media/bra-preparation-items.png)

-   <span data-ttu-id="b0e47-260">**Processo de resposta** – Esta ação é usada para atualizar a mensagem entregue quando ela for aprovada pelo governo usando um número de protocolo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-260">**Process response (Processo de reposta)** – This action is used to update the delivered message when it's approved by the government by using a protocol number.</span></span> <span data-ttu-id="b0e47-261">Além disso, a mensagem é atualizada conforme registrado no site do governo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-261">Additionally, the message is updated as registered on the     government website.</span></span>

    ![Resposta ao processo de itens de preparação](media/bra-preparation-items-process-response.png)

-   <span data-ttu-id="b0e47-263">**Geração de relatório** – Esta ação é usada para enviar e receber o item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0e47-263">**Report generation (Geracao de relatório)** – This action is used to send and receive the message item.</span></span>

    ![Gerar parâmetros de relatórios](media/bra-generate-reports-parameters.png)

> [!NOTE]
> <span data-ttu-id="b0e47-265">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-265">Don't remove this configuration.</span></span> <span data-ttu-id="b0e47-266">Essa configuração está incluída no pacote.</span><span class="sxs-lookup"><span data-stu-id="b0e47-266">This configuration is included in the package.</span></span>

#### <a name="specific-actions"></a><span data-ttu-id="b0e47-267">Ações específicas</span><span class="sxs-lookup"><span data-stu-id="b0e47-267">Specific actions</span></span>

<span data-ttu-id="b0e47-268">Antes que uma mensagem seja entregue, você deve configurar a validação do esquema XML para evitar rejeições do site do governo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-268">Before a message is delivered, you must set up XML schema validation to prevent rejections from the government website.</span></span>

<span data-ttu-id="b0e47-269">Vá para **Administração da organização \> Gerenciamento de documentos \> Parâmetros de gerenciamento de documentos** e habilite arquivos XSD adicionando **XSD** como um novo tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-269">Go to **Organization administration \> Document management \> Document management parameters**, and enable XSD files by adding **XSD** as a new file type.</span></span>

![Parâmetros de gerenciamento de documentos](media/bra-document-management-parameters.png)

<span data-ttu-id="b0e47-271">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens** e selecione **Novo \> Arquivo** para anexar os esquemas (arquivos .xsd) para as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b0e47-271">Go to **Tax \> Setup \> Electronic messages \> Message processing actions**, and select **New \> File** to attach the schemas (.xsd files) for the following actions:</span></span>

-   <span data-ttu-id="b0e47-272">Validar</span><span class="sxs-lookup"><span data-stu-id="b0e47-272">Verify (Validar)</span></span>

-   <span data-ttu-id="b0e47-273">Re-Validar</span><span class="sxs-lookup"><span data-stu-id="b0e47-273">Re-Verify (Re-Validar)</span></span>

-   <span data-ttu-id="b0e47-274">Exclusão-Validar</span><span class="sxs-lookup"><span data-stu-id="b0e47-274">Cancel-Verify (Exclusão-Validar)</span></span>

<span data-ttu-id="b0e47-275">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens**, selecione a ação **Preencher** (**Incluir**) e, em seguida, no campo **Ação de preencher registros**, selecione **Registrar transações**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-275">Go to **Tax \> Setup \> Electronic messages \> Message processing actions**, select the **Populate** (**Incluir**) action, and then, in the **Populate records action** field, select **Registrar transacões**.</span></span>

![Ações de Processamento de Mensagens](media/bra-message-processing-actions.png)

<span data-ttu-id="b0e47-277">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de serviço Web** e configure uma conexão de serviços Web e certificados para enviar e consultar eventos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-277">Go to **Tax \> Setup \> Electronic messages \> Web service settings**, and set up a web services connection and certificates for issuing and inquiring about events.</span></span>

![Configurações de serviços Web](media/bra-web-service-settings.png)

> [!NOTE]
> <span data-ttu-id="b0e47-279">Nas configurações do **SPED Reinf assíncrono**, inclua o endereço do serviço Web para consultar o evento R-5011.</span><span class="sxs-lookup"><span data-stu-id="b0e47-279">In the settings for **SPED Reinf asynchronous (SPED Reinf – assíncrono)**, include the web service address for inquire event R-5011.</span></span>

### <a name="set-up-service-types"></a><span data-ttu-id="b0e47-280">Configurar tipos de serviço</span><span class="sxs-lookup"><span data-stu-id="b0e47-280">Set up service types</span></span>

<span data-ttu-id="b0e47-281">A tabela de tipos de serviço representa a tabela 06 que as autoridades fiscais estabeleceram para classificar os serviços fornecidos, com base na atribuição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b0e47-281">The service type table represents table 06 that the tax authorities have established to classify the services that are provided, based on assignment of labor.</span></span> <span data-ttu-id="b0e47-282">Uma lista detalhada de valores disponíveis está à disposição no site do SPED.</span><span class="sxs-lookup"><span data-stu-id="b0e47-282">A detailed list of available values is available on the SPED website.</span></span>

1.  <span data-ttu-id="b0e47-283">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Tipos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-283">Go to **Fiscal books \> Setup \> SPED Reinf \> Service types**.</span></span>

2.  <span data-ttu-id="b0e47-284">Selecione **Novo**, insira um código de classificação que tenha sido estabelecido pelas autoridades fiscais e insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b0e47-284">Select **New**, enter a classification code that has been established by the tax authorities, and enter a description.</span></span>

    ![Tipos de serviço](media/bra-service-type-setup.png)

<span data-ttu-id="b0e47-286">Depois que a lista de tipos de serviço for criada, eles devem ser atribuídos a códigos de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0e47-286">After the list of service types is created, the service types must be assigned to service codes.</span></span> <span data-ttu-id="b0e47-287">Vá para **Gerenciamento de estoque \> Configuração \> Informações fiscais \> Código de serviço** e, em seguida, para cada serviço, atribua o tipo de serviço relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-287">Go to **Inventory management \> Setup \> Fiscal information \> Service code**, and then, for each service, assign the related service type.</span></span>

<span data-ttu-id="b0e47-288">**Configurar códigos de classificação de imposto**</span><span class="sxs-lookup"><span data-stu-id="b0e47-288">**Set up tax classification codes**</span></span>

<span data-ttu-id="b0e47-289">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Códigos de classificação de imposto** e insira os tipos de classificação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b0e47-289">Go to **Fiscal books \> Setup \> SPED Reinf \> Tax classification codes** and enter the available classification types.</span></span>

![Classificação de imposto](media/bra-tax-classification-codes.png)

<span data-ttu-id="b0e47-291">Essa informação é atribuída à organização fiscal na FastTab **Geral** em **Livros fiscais \> Configuração \> Organização fiscal**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-291">This information is assigned to the fiscal organization on the **General** FastTab at **Fiscal books \> Setup \> Fiscal organization**.</span></span>

![Organização fiscal](media/bra-fiscal-organization-setup.png)

### <a name="set-up-codes-explanation-suspension"></a><span data-ttu-id="b0e47-293">Configurar suspensão da explicação de códigos</span><span class="sxs-lookup"><span data-stu-id="b0e47-293">Set up codes explanation suspension</span></span>

<span data-ttu-id="b0e47-294">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Suspensão da explicação de códigos** e configure os códigos que são usados no evento R-1070 quando a suspensão da retenção se aplica.</span><span class="sxs-lookup"><span data-stu-id="b0e47-294">Go to **Fiscal books \> Setup \> SPED Reinf \> Codes explanation suspension**, and set up the codes that are used in event R-1070 when suspension of withholding applies.</span></span> <span data-ttu-id="b0e47-295">Esses códigos são atribuídos em **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-295">These codes are assigned at **Fiscal books \> Periodic \> SPED Reinf \> Administrative and judicial process**.</span></span>

![Códigos de explicação](media/bra-codes-explanation-suspension.png)

### <a name="set-up-fiscal-books-parameters"></a><span data-ttu-id="b0e47-297">Configurar parâmetros de livros fiscais</span><span class="sxs-lookup"><span data-stu-id="b0e47-297">Set up fiscal books parameters</span></span>

<span data-ttu-id="b0e47-298">Vá para **Livros fiscais \> Configuração \> Parâmetros de livros fiscais** e configure a sequência numérica para os eventos R-2010 e R-2020.</span><span class="sxs-lookup"><span data-stu-id="b0e47-298">Go to **Fiscal books \> Setup \> Fiscal books parameters**, and set up the number sequence for events R-2010 and R-2020.</span></span>

![Parâmetros de livros fiscais](media/bra-sped-fiscal-books-parameters.png)

> [!NOTE]
> <span data-ttu-id="b0e47-300">Se as sequências numéricas não tiverem sido inicializadas durante a lista de verificação da configuração para a instalação de KB, você poderá gerá-las usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-300">If the number sequences weren't initialized during the setup checklist for KB installation, you can generate them by using a wizard.</span></span> <span data-ttu-id="b0e47-301">Para iniciar o assistente, vá para **Administração da organização \> Sequências numéricas \> Sequências numéricas** e selecione **Gerar**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-301">To start the wizard, go to **Organization administration \> Number sequences \> Number sequences**, and select **Generate**.</span></span> <span data-ttu-id="b0e47-302">Assim você poderá configurar a sequência numérica relacionada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-302">You will then be able to configure the related number sequence.</span></span>

-   <span data-ttu-id="b0e47-303">**Área:** Livros fiscais</span><span class="sxs-lookup"><span data-stu-id="b0e47-303">**Area:** Fiscal books</span></span>

-   <span data-ttu-id="b0e47-304">**Referência**: ID de evento do SPED-Reinf</span><span class="sxs-lookup"><span data-stu-id="b0e47-304">**Reference:** SPED-Reinf event ID</span></span>

<span data-ttu-id="b0e47-305">**Eventos do SPED-Reinf**</span><span class="sxs-lookup"><span data-stu-id="b0e47-305">**SPED-Reinf events**</span></span>

<span data-ttu-id="b0e47-306">Todas as informações que o SPED-Reinf fornece sobre impostos e contribuições em um determinado período de apuração são conhecidas como uma *movimentação*.</span><span class="sxs-lookup"><span data-stu-id="b0e47-306">All the information that the SPED-Reinf provides about taxes and contributions in a given assessment period is known as a *movement*.</span></span> <span data-ttu-id="b0e47-307">Portanto, cada movimentação pode conter um ou mais eventos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-307">Therefore, every movement can contain one or more events.</span></span>

<span data-ttu-id="b0e47-308">Para encerrar a transmissão de eventos periódicos para uma determinada movimentação em um período de apuração específico, você deve enviar o evento R-2099 "Fechamento de evento periódico”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-308">To close the transmission of periodic events for a given movement in a specific assessment period, you must send event R-2099, "Closure of periodic event."</span></span> <span data-ttu-id="b0e47-309">Depois que o evento de fechamento é processado e validado, ele é aceito.</span><span class="sxs-lookup"><span data-stu-id="b0e47-309">After the closure event is processed and validated, it's accepted.</span></span> <span data-ttu-id="b0e47-310">A aceitação do evento de fechamento finaliza a soma das bases de cálculo incluídas na movimentação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-310">Acceptance of the closure event finalizes the sum of the calculation bases that are included in the movement.</span></span> <span data-ttu-id="b0e47-311">O crédito de imposto poderá então ser calculado e o DARF poderá ser gerado para coletar os impostos e as contribuições devidos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-311">The tax credit can then be calculated, and the DARF can be generated to collect taxes and contributions that are owed.</span></span>

<span data-ttu-id="b0e47-312">Se for necessário enviar uma correção ou novos eventos para uma movimentação que já foi fechada, você deverá reabri-la enviando o evento R-2098, “Reabertura de evento periódico”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-312">If a correction or new events must be sent for a movement that has already been closed, you must reopen the movement by sending event R-2098, "Reopening of periodic event."</span></span> <span data-ttu-id="b0e47-313">Após a reabertura de uma movimentação, você deve enviar um novo evento de fechamento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-313">After a movement is reopened, you must send a new closing event.</span></span>

<span data-ttu-id="b0e47-314">**Quando não há movimentações no período de apuração**</span><span class="sxs-lookup"><span data-stu-id="b0e47-314">**When there is no movement in the assessment period**</span></span>

<span data-ttu-id="b0e47-315">A situação “sem movimentação” para um contribuinte ocorre somente quando não há informações a serem enviadas ao grupo de eventos periódicos do evento R-2010 ao evento R-2070.</span><span class="sxs-lookup"><span data-stu-id="b0e47-315">The "no movement" situation for a taxpayer occurs only when there is no information to send to the periodic event group from event R-2010 to event R-2070.</span></span> <span data-ttu-id="b0e47-316">Nesse caso, o evento R-2099, "Fechamento de evento periódico”, que fornece as informações para o fechamento, declara a não ocorrência de transações no primeiro período de apuração do ano em que essa situação ocorre.</span><span class="sxs-lookup"><span data-stu-id="b0e47-316">In this case, event R-2099, "Closure of periodic event," which provides the information for closure, declares the non-occurrence of transactions in the first assessment period of the year that this situation occurs in.</span></span> <span data-ttu-id="b0e47-317">Se a situação “sem movimentação” persistir nos anos seguintes, o contribuinte deverá repetir esse procedimento no mês de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="b0e47-317">If the "no movement" situation persists in the following years, the taxpayer must repeat this procedure in January of each year.</span></span>

<span data-ttu-id="b0e47-318">**Protocolo de recebimento**</span><span class="sxs-lookup"><span data-stu-id="b0e47-318">**Receiving protocol**</span></span>

<span data-ttu-id="b0e47-319">O protocolo de recebimento confirma que as informações enviadas foram validadas e entregues com êxito ao ambiente do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="b0e47-319">The receiving protocol confirms that the information that was sent was successfully delivered and validated to the SPED-Reinf environment.</span></span> <span data-ttu-id="b0e47-320">O protocolo de recebimento é o ponto inicial para corrigir ou excluir um determinado evento, se a correção e a exclusão forem permitidas.</span><span class="sxs-lookup"><span data-stu-id="b0e47-320">The receiving protocol is the starting point for correcting or deleting a given event, if correction and deletion are allowed.</span></span>

<span data-ttu-id="b0e47-321">Cada evento transmitido tem um protocolo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-321">Every event that is transmitted has a receiving protocol.</span></span> <span data-ttu-id="b0e47-322">Para corrigir um evento, é necessário inserir o número do protocolo de recebimento dele.</span><span class="sxs-lookup"><span data-stu-id="b0e47-322">To correct an event, you must enter the number of the event's receiving protocol.</span></span>

<span data-ttu-id="b0e47-323">A quantidade de tempo que os protocolos de recebimento são mantidos no banco de dados do governo não é definida.</span><span class="sxs-lookup"><span data-stu-id="b0e47-323">The amount of time that receiving protocols are kept in the government database isn't defined.</span></span> <span data-ttu-id="b0e47-324">Portanto, como precaução, é importante que o contribuinte os guarde, pois eles comprovam que a obrigação tributária acessória foi entregue e cumprida.</span><span class="sxs-lookup"><span data-stu-id="b0e47-324">Therefore, as a precaution, it's important that the taxpayer retain them, because they provide proof that the ancillary tax obligation has been delivered and met.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-325">O protocolo de entrega consiste em informações transitórias que comprovam que o evento foi transmitido e que a validação apropriada será processada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-325">The delivery protocol is transient information that provides proof that the event has been transmitted, and that the appropriate validation will be processed.</span></span> <span data-ttu-id="b0e47-326">Ele não demonstra conformidade com a obrigação acessória.</span><span class="sxs-lookup"><span data-stu-id="b0e47-326">It doesn't demonstrate compliance with the ancillary obligation.</span></span>

<span data-ttu-id="b0e47-327">**Aditamento e correção**</span><span class="sxs-lookup"><span data-stu-id="b0e47-327">**Amendment and correction**</span></span>

<span data-ttu-id="b0e47-328">O procedimento para aditar as informações enviadas ao SPED-Reinf ocorre somente nos eventos R-1000, “Informações do contribuinte” e R-1070, "Tabela legal e administrativa".</span><span class="sxs-lookup"><span data-stu-id="b0e47-328">The procedure for amending information that is sent to the SPED-Reinf occurs only in events R-1000, "Taxpayer information," and R-1070, "Administrative and lawsuits table."</span></span>

<span data-ttu-id="b0e47-329">Em todos os outros casos em que as informações enviadas devem ser corrigidas, o procedimento para a correção ou exclusão deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-329">In all other cases where the information that was sent must be amended, the procedure for correction or deletion must be used.</span></span>

<span data-ttu-id="b0e47-330">**Eventos de exclusão**</span><span class="sxs-lookup"><span data-stu-id="b0e47-330">**Deletion events**</span></span>

<span data-ttu-id="b0e47-331">Para excluir eventos que foram aprovados pela autoridade fiscal, mas entregues incorretamente, você deve enviar o evento R-9000, "Evento de exclusão".</span><span class="sxs-lookup"><span data-stu-id="b0e47-331">To exclude events that were approved by the tax authority but incorrectly delivered, you must send event R-9000, "Deletion event."</span></span> <span data-ttu-id="b0e47-332">Nesse evento, é necessário identificar o evento a ser excluído preenchendo a marca **Tipo de evento** (**TpEvento**).</span><span class="sxs-lookup"><span data-stu-id="b0e47-332">In this event, you must identify the event to delete by filling in the **Event Type** tag (**TpEvento**).</span></span> <span data-ttu-id="b0e47-333">Você também deve preencher o **Número de recebimento do evento** (**NRRECEVT**), que especifica o número do protocolo de recebimento do arquivo que foi enviado e deve ser excluído.</span><span class="sxs-lookup"><span data-stu-id="b0e47-333">You must also fill in **Event Receipt Number** (**NRRECEVT**), which specifies the receipt protocol number of the file that was sent and must be deleted.</span></span>

<span data-ttu-id="b0e47-334">**Assinatura digital**</span><span class="sxs-lookup"><span data-stu-id="b0e47-334">**Digital signature**</span></span>

<span data-ttu-id="b0e47-335">O certificado digital usado no SPED-Reinf deve ser emitido por uma autoridade de certificação credenciada pela ICP-Brasil.</span><span class="sxs-lookup"><span data-stu-id="b0e47-335">The digital certificate that is used in the SPED-Reinf must be issued by a certification authority that is accredited by ICP-Brasil.</span></span>

<span data-ttu-id="b0e47-336">O certificado digital deve pertencer à série ”A”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-336">The digital certificate must belong to the "A" series.</span></span> <span data-ttu-id="b0e47-337">Os certificados podem pertencer a duas séries: série ”A” e série “S”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-337">Certificates can belong to two series: the "A" series and the "S" series.</span></span> <span data-ttu-id="b0e47-338">A série ”A” inclui os certificados de assinatura digital usados para confirmação de identidade na Web em emails, redes virtuais privadas (VPNs) e documentos eletrônicos, com verificação da integridade de suas informações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-338">The "A" series includes the digital signature certificates that are used for web identity confirmation on emails, virtual private networks (VPNs), and electronic documents, with verification of the integrity of its information.</span></span> <span data-ttu-id="b0e47-339">A série “S” inclui os certificados de confidencialidade usados na codificação de documentos, bancos de dados, mensagens e outras informações eletrônicas confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-339">The "S" series includes the confidentiality certificates that are used in the encoding of documents, databases, messages, and other sensitive electronic information.</span></span>

<span data-ttu-id="b0e47-340">O certificado digital deve ser do tipo “A1” ou “A3”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-340">The digital certificate must be of the "A1" or "A3" type.</span></span> <span data-ttu-id="b0e47-341">Certificados digitais do tipo “A1” são armazenados no computador em que são usados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-341">Digital certificates of the "A1" type are stored on the computer that they are used from.</span></span> <span data-ttu-id="b0e47-342">Certificados digitais do tipo “A3” são armazenados em um dispositivo portátil à prova de adulterações com um chip capaz de realizar a assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="b0e47-342">Digital certificates of the "A3" type are stored in a tamper-resistant portable device that contains a chip that can do the digital signing.</span></span> <span data-ttu-id="b0e47-343">Exemplos desses dispositivos incluem cartões inteligentes e tokens.</span><span class="sxs-lookup"><span data-stu-id="b0e47-343">Examples of these devices include smart cards and tokens.</span></span> <span data-ttu-id="b0e47-344">Esses dispositivos são razoavelmente seguros porque cada operação é feita pelo chip no dispositivo e não há nenhum acesso externo à chave privada do certificado digital.</span><span class="sxs-lookup"><span data-stu-id="b0e47-344">These devices are reasonably secure, because every operation is done by the chip on the device, and there is no external access to the private key of the digital certificate.</span></span>

<span data-ttu-id="b0e47-345">Os certificados digitais são necessários em dois momentos:</span><span class="sxs-lookup"><span data-stu-id="b0e47-345">The digital certificates are required at two moments:</span></span>

-   <span data-ttu-id="b0e47-346">**Para ações de entrega**: antes da solicitação de entrega ao SPED-Reinf ser iniciada, o certificado digital do solicitante é usado para ajudar a garantir a segurança do tráfego de informações na Internet.</span><span class="sxs-lookup"><span data-stu-id="b0e47-346">**For delivery actions**: Before the request for delivery to the SPED-Reinf is started, the requestor's digital certificate is used to help guarantee the safety of the information traffic on the internet.</span></span> <span data-ttu-id="b0e47-347">Para que o certificado digital seja aceito como uma função de transmissor, ele deve ser do tipo e-CNPJ.</span><span class="sxs-lookup"><span data-stu-id="b0e47-347">For the digital certificate to be accepted as a transmitter function, it must be of the e-CNPJ type.</span></span>

-   <span data-ttu-id="b0e47-348">**Para assinatura de documentos**: os eventos podem ser gerados por qualquer estabelecimento fiscal da entidade legal ou seu proxy.</span><span class="sxs-lookup"><span data-stu-id="b0e47-348">**For document signing**: The events can be generated by any fiscal establishment of the legal entity or its proxy.</span></span> <span data-ttu-id="b0e47-349">No entanto, o assinante digital desses eventos deve pertencer ao estabelecimento fiscal principal (matriz), seu representante legal ou um advogado concedido por meio de proxy eletrônico e não eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b0e47-349">However, the digital subscriber of those events must belong to the main fiscal establishment (headquarters), its legal representative, or an attorney that is granted by means of electronic and non-electronic proxy.</span></span>

<span data-ttu-id="b0e47-350">Os certificados digitais que são usados para assinar os eventos enviados ao SPED-Reinf devem ser habilitados para a função de assinatura digital de acordo com a política de certificação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-350">The digital certificates that are used to sign the events that are sent to the SPED-Reinf must be enabled for the digital signature function in accordance with the certificate policy.</span></span>

<span data-ttu-id="b0e47-351">Os eventos no SPED-Reinf devem ser transmitidos usando um certificado digital válido.</span><span class="sxs-lookup"><span data-stu-id="b0e47-351">The events in the SPED-Reinf must be transmitted by using a valid digital certificate.</span></span> <span data-ttu-id="b0e47-352">No entanto, uma exceção será feita para micro e pequenas empresas (ME e EPP) que atendam aos critérios do Simples Nacional e possuam sete funcionários ou menos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-352">However, an exception is made for micro and small businesses (ME and EPP) that meet the Simple Nacional criteria and have seven or fewer employees.</span></span> <span data-ttu-id="b0e47-353">Essas empresas podem transmitir seus eventos usando um código de acesso.</span><span class="sxs-lookup"><span data-stu-id="b0e47-353">These businesses can transmit their events by using an access code.</span></span>

### <a name="general-process"></a><span data-ttu-id="b0e47-354">Processo geral</span><span class="sxs-lookup"><span data-stu-id="b0e47-354">General process</span></span>

1.  <span data-ttu-id="b0e47-355">Use uma mensagem eletrônica para criar, validar e entregar o evento ou lote de eventos por meio de itens de mensagem eletrônica.</span><span class="sxs-lookup"><span data-stu-id="b0e47-355">Use an electronic message to create, validate, and deliver the event or batch of events through electronic message items.</span></span>

2.  <span data-ttu-id="b0e47-356">O serviço Web da autoridade fiscal recebe o lote e valida seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-356">The tax authority web service receives the batch and validates its contents.</span></span>

3.  <span data-ttu-id="b0e47-357">O serviço Web retorna o resultado do processamento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-357">The web service returns the result of processing.</span></span> <span data-ttu-id="b0e47-358">Se os eventos ou o lote de eventos forem recebidos com êxito, um protocolo de recebimento será retornado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-358">If the events or batch of events is successfully received, a receiving protocol is returned.</span></span> <span data-ttu-id="b0e47-359">Caso contrário, uma mensagem de erro será retornada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-359">Otherwise, an error message is returned.</span></span> <span data-ttu-id="b0e47-360">Nesse caso, o contribuinte pode resolver os erros e renviar o evento por meio de um novo lote.</span><span class="sxs-lookup"><span data-stu-id="b0e47-360">In that case, the taxpayer can resolve the errors and resubmit the event through a new batch.</span></span>

![<span data-ttu-id="b0e47-361">Texto alternativo gerado por máquina: Contribuinte Eventos Gera Evento XML Assina Digitalmente & 80 T rata Rsultados Lote de Ev Clialte Notificaqäo de Retomo EFD-REINF Rec.cäo e Val idacäo (Lotede Eventosi BD Controle</span><span class="sxs-lookup"><span data-stu-id="b0e47-361">Machine generated alternative text: Contribuinte Eventos Gera Evento XML Assina Digitalmente & 80 T rata Rsultados Lote de Ev Clialte Notificaqäo de Retomo EFD-REINF Rec.cäo e Val idacäo (Lotede Eventosi BD Controle</span></span> ](media/bra-general-process.png)

<span data-ttu-id="b0e47-362">Os eventos são transmitidos às autoridades fiscais usando a funcionalidade Mensagens eletrônicas para estabelecer um relacionamento bidirecional, automatizado e instantâneo entre o contribuinte e os serviços Web do governo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-362">The events are transmitted to tax authorities by using Electronic messages functionality to establish a two-way, automated, and instantaneous relationship between the government web services and the taxpayer.</span></span>

<span data-ttu-id="b0e47-363">As ilustrações a seguir mostram as ações que são realizadas e os status de itens de mensagem que causam a aprovação ou rejeição de cada evento ao ser entregue pela primeira vez (Inserção), atualizado (Aditamento/Atualização) ou cancelado ou excluído (Cancelamento/Exclusão).</span><span class="sxs-lookup"><span data-stu-id="b0e47-363">The following illustrations show the actions that are performed and the status of message items that causes each event to be approved or rejected when it's delivered for the first time (Insertion), updated (Amendment/Update), or canceled or deleted (Cancel/Delete).</span></span>

![Ações de fluxo](media/bra-flow-actions.png)

#### <a name="insertion"></a><span data-ttu-id="b0e47-365">Inserção</span><span class="sxs-lookup"><span data-stu-id="b0e47-365">Insertion</span></span>

<span data-ttu-id="b0e47-366">Este fluxo é usado para entregar qualquer evento pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="b0e47-366">This flow is used to deliver any event for the first time.</span></span>

![Inserção](media/bra-insertion-flow.png)

#### <a name="amendmentupdate"></a><span data-ttu-id="b0e47-368">Aditamento/Atualização</span><span class="sxs-lookup"><span data-stu-id="b0e47-368">Amendment/Update</span></span>

![Atualização](media/bra-amendment-update-flow.png)

#### <a name="canceldelete"></a><span data-ttu-id="b0e47-370">Cancelamento/Exclusão</span><span class="sxs-lookup"><span data-stu-id="b0e47-370">Cancel/Delete</span></span>

![Cancelar](media/bra-cancel-delete-flow.png)

#### <a name="inquire-event-5011-from-event-r-2099"></a><span data-ttu-id="b0e47-372">Consultar evento 5011 (do evento R-2099)</span><span class="sxs-lookup"><span data-stu-id="b0e47-372">Inquire event 5011 (from event R-2099)</span></span>

![Consultar evento 5011](media/bra-inquire-event-5011.png)

#### <a name="manage-electronic-messages"></a><span data-ttu-id="b0e47-374">Gerenciar mensagens eletrônicas</span><span class="sxs-lookup"><span data-stu-id="b0e47-374">Manage electronic messages</span></span> 

<span data-ttu-id="b0e47-375">Todos os eventos são gerenciados e controlados em **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-375">All events are managed and controlled at **Tax \> Inquiries and reports \> Electronic messages \> Electronic message items**.</span></span>

| <span data-ttu-id="b0e47-376">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="b0e47-376">Field name</span></span>      | <span data-ttu-id="b0e47-377">Descrição do campo</span><span class="sxs-lookup"><span data-stu-id="b0e47-377">Field description</span></span>                                                                                                                                         |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b0e47-378">Tipo de item de mensagem</span><span class="sxs-lookup"><span data-stu-id="b0e47-378">Message item type</span></span>   | <span data-ttu-id="b0e47-379">O tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="b0e47-379">The type of event:</span></span>                                                                                                                                            |
| <span data-ttu-id="b0e47-380">Status de item de mensagem</span><span class="sxs-lookup"><span data-stu-id="b0e47-380">Message item status</span></span> | <span data-ttu-id="b0e47-381">O status atual do evento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-381">The current status of the event.</span></span> <span data-ttu-id="b0e47-382">Este campo é automaticamente preenchido e atualizado, com base na troca de mensagens entre a autoridade fiscal e o contribuinte.</span><span class="sxs-lookup"><span data-stu-id="b0e47-382">This field is automatically filled in and updated, based on the exchange of messages between the tax authority and taxpayer.</span></span> |

-   <span data-ttu-id="b0e47-383">Processo administrativo e judicial (R-1070)</span><span class="sxs-lookup"><span data-stu-id="b0e47-383">Administrative and judicial process (R-1070)</span></span>

-   <span data-ttu-id="b0e47-384">Serviços adquiridos (R-2010)</span><span class="sxs-lookup"><span data-stu-id="b0e47-384">Acquired services (R-2010)</span></span>

-   <span data-ttu-id="b0e47-385">Apuração do INSS-CPRB (R-2060)</span><span class="sxs-lookup"><span data-stu-id="b0e47-385">INSS-CPRB assessment (R-2060)</span></span>

-   <span data-ttu-id="b0e47-386">Serviços fornecidos (R-2020)</span><span class="sxs-lookup"><span data-stu-id="b0e47-386">Provided services (R-2020)</span></span>

-   <span data-ttu-id="b0e47-387">Informações do contribuinte (R-1000)</span><span class="sxs-lookup"><span data-stu-id="b0e47-387">Taxpayer information (R-1000</span></span>

-   <span data-ttu-id="b0e47-388">Fechamento (R-2099)</span><span class="sxs-lookup"><span data-stu-id="b0e47-388">Closing (R-2099)</span></span>

-   <span data-ttu-id="b0e47-389">**Criado** – O evento foi adicionado ao registro, mas ainda não foi enviado aos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="b0e47-389">**Created** – The event was added to the register but hasn't yet been sent to the web services.</span></span>

-   <span data-ttu-id="b0e47-390">**Rejeitado** – O evento foi enviado aos serviços Web, mas foi rejeitado pelo sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-390">**Rejected** – The event was sent to the web services, but it was rejected by the tax authority system.</span></span> <span data-ttu-id="b0e47-391">Um grupo de marcas específico no arquivo XML que é retornado pelo governo especifica o código de erro e fornece uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b0e47-391">A specific tag group in the XML file that is returned by the government specifies the error code and provides a description.</span></span>

-   <span data-ttu-id="b0e47-392">**Aceito** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-392">**Accepted** – The event was sent to the web services and was accepted by the tax authority system.</span></span>

-   <span data-ttu-id="b0e47-393">**Aceito com erros** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal, apesar de haver erros.</span><span class="sxs-lookup"><span data-stu-id="b0e47-393">**Accepted with errors** – The event was sent to the web services and was accepted by the tax authority system, even though there were errors.</span></span>


### <a name="event-r-1000-taxpayer-information"></a><span data-ttu-id="b0e47-394">Evento R-1000, "Informações do contribuinte"</span><span class="sxs-lookup"><span data-stu-id="b0e47-394">Event R-1000, "Taxpayer information"</span></span>

<span data-ttu-id="b0e47-395">O evento R-1000 é usado para entregar informações sobre a empresa.</span><span class="sxs-lookup"><span data-stu-id="b0e47-395">Event R-1000 is used to delivery information about the company.</span></span> <span data-ttu-id="b0e47-396">Esse evento deve ser entregue apenas uma vez para registrar as informações no site do governo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-396">This event must be delivered only one time to register the information on the government site.</span></span> <span data-ttu-id="b0e47-397">No entanto, após esse registro inicial de informações, pode ser entregue quantas vezes for necessário para ações de manutenção como atualizações e exclusões de dados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-397">However, after this initial registration of information, it can be delivered as many times as required for maintenance actions such as updates and deletions of data.</span></span>

<span data-ttu-id="b0e47-398">Portanto, sempre que qualquer atributo do contribuinte ou a data válida de informações que foi fornecida anteriormente precisarem ser alterados, o evento R-1000 deve ser entregue novamente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-398">Therefore, whenever any taxpayer attribute or the valid date of information that was provided earlier must be changed, event R-1000 must be delivered again.</span></span> <span data-ttu-id="b0e47-399">Quando for entregue novamente, o grupo de marcas correto para a ação desejada deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-399">When it's redelivered, the correct group of tags for the desired action must be specified.</span></span>

<span data-ttu-id="b0e47-400">Como as comunicações podem falhar devido a problemas técnicos, como tempo limite ou falhas de Internet, o contador tributário deve ser capaz de renviar o evento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-400">Because communications can fail for technical reasons, such as a time-out or an internet shortage, the tax accountant must be able to resubmit the event.</span></span> <span data-ttu-id="b0e47-401">Além disso, como a validação do arquivo pelo serviço Web pode falhar, o contador tributário deve ser capaz de visualizar os detalhes e corrigir os erros relacionados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-401">Additionally, because validation of the file by the web service can fail, the tax accountant must be able to view the details and fix the related errors.</span></span> <span data-ttu-id="b0e47-402">Após a validação do arquivo, o protocolo de recebimento que é retornado pelo serviço Web deve ser salvo e o contador tributário deve ser capaz de visualizar seus detalhes, como o número e o carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="b0e47-402">After the file is validated, the receiving protocol that is returned by the web service must be saved, and the tax accountant must be able to view its details, such as the number and time stamp.</span></span>

#### <a name="repro-step--insertion"></a><span data-ttu-id="b0e47-403">Etapa de reprodução – Inserção</span><span class="sxs-lookup"><span data-stu-id="b0e47-403">Repro step – Insertion</span></span>

1.  <span data-ttu-id="b0e47-404">Vá para **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-404">Go to **Tax \> Inquiries and reports \> Electronic messages \> Electronic message items**.</span></span>

2.  <span data-ttu-id="b0e47-405">No Painel de Ação, selecione **Executar processamento**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-405">On the Action Pane, select **Run processing**.</span></span> <span data-ttu-id="b0e47-406">Em seguida, na caixa de diálogo **Executar processamento**, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-406">Then, in the **Run processing** dialog box, in the **Processing** field select **SPED Reinf**.</span></span>

3.  <span data-ttu-id="b0e47-407">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Incluir**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-407">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Incluir**.</span></span>

    ![Executar processamento](media/bra-run-processing.png)

4.  <span data-ttu-id="b0e47-409">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-409">Select **OK** to confirm the settings.</span></span>

    <span data-ttu-id="b0e47-410">Um item de mensagem do tipo **Informações do contribuinte** é criado e seu status é definido como **Anexado**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-410">A message item of **Informações do contribuinte** type is created, and the status of the message item is set to **Anexado**.</span></span>

    ![Inserção de itens de mensagem eletrônica](media/bra-electronic-message-items-insertion.png)

5.  <span data-ttu-id="b0e47-412">Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-412">Select **Run processing** again, and then, in the dialog box, in the **Processing** field, select **SPED Reinf**.</span></span>

6.  <span data-ttu-id="b0e47-413">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Parâmetros adicionais** para atualizar as informações relacionadas nos campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-413">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Parâmetros adicionais** to update the related information in additional fields.</span></span>

    ![Executar parâmetros adicionais de processamento](media/bra-run-processing-additional-parameters.png)

    ![Itens de preparação](media/bra-preparation-items.png)

7.  <span data-ttu-id="b0e47-416">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-416">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="b0e47-417">O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Preparado**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-417">The message item of **Informações do contribuinte** type is updated, and the status of the message item is changed to **Preparado**.</span></span>

    ![Status de itens de mensagem eletrônica](media/bra-electronic-message-items-status.png)

8.  <span data-ttu-id="b0e47-419">Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-419">Select **Run processing** again, and then, in the dialog box, in the **Processing** field, select **SPED Reinf**.</span></span>

9.  <span data-ttu-id="b0e47-420">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Gerar** para gerar o XML.</span><span class="sxs-lookup"><span data-stu-id="b0e47-420">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Gerar** to generate the XML.</span></span>

10.  <span data-ttu-id="b0e47-421">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-421">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="b0e47-422">A caixa de diálogo **Gerar relatórios** aparece automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-422">The **Generate reports** dialog box automatically appears.</span></span> <span data-ttu-id="b0e47-423">Na FastTab **Registros a serem incluídos**, nas opções de filtro, a ID do tipo de item de mensagem que está solicitando a geração de um arquivo XML é selecionada no campo **Item de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-423">On the **Records to include** FastTab, in the filter options, the ID of the message item type that is requesting generation of an XML file is selected in the **Message item** field.</span></span>

     ![Gerar relatórios](media/bra-generate-reports.png)

11.  <span data-ttu-id="b0e47-425">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-425">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="b0e47-426">O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Gerado**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-426">The message item of the **Informações do contribuinte** type is updated, and the status of the message item is changed to **Gerado**.</span></span>

12.  <span data-ttu-id="b0e47-427">Repita essas etapas até concluir todas as ações no fluxo [Inserção](#insertion).</span><span class="sxs-lookup"><span data-stu-id="b0e47-427">Repeat these steps until you've complete all the actions in the [Insertion](#insertion) flow.</span></span>

#### <a name="repro-step--amendment"></a><span data-ttu-id="b0e47-428">Etapa de reprodução – Aditamento</span><span class="sxs-lookup"><span data-stu-id="b0e47-428">Repro step – Amendment</span></span> 

<span data-ttu-id="b0e47-429">Se algum dado da organização fiscal foi alterado ou se for necessário excluir o evento por algum motivo, o evento R-1010 deve ser transmitido novamente, mas o status deve ser diferente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-429">If any data of the fiscal organization has been changed, or if the event must be excluded for some reason, event R-1010 must be transmitted again, but the status must be different.</span></span>

<span data-ttu-id="b0e47-430">Use o mesmo processo descrito na seção “Etapa de reprodução – Inserção” e conclua todas as ações no fluxo [Aditamento/Atualização](#amendmentupdate).</span><span class="sxs-lookup"><span data-stu-id="b0e47-430">Use the same process that is described in the "Repro step – Insertion" section, and complete all the actions in the [Amendment/Update](#amendmentupdate) flow.</span></span>

<span data-ttu-id="b0e47-431">O Microsoft Dynamics AX detectará quaisquer diferenças entre as informações no último evento e as informações atuais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-431">Microsoft Dynamics AX will detect any differences between the information in the last event and the current information.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-432">Se as alterações não afetarem o evento R-1010 relacionado, você receberá a seguinte mensagem: “0 registros foram adicionados”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-432">If changes don't affect the related R-1010 event, you will receive the following message: "0 records have been added."</span></span>

#### <a name="repro-step--cancel"></a><span data-ttu-id="b0e47-433">Etapa de reprodução – Cancelamento</span><span class="sxs-lookup"><span data-stu-id="b0e47-433">Repro step – Cancel</span></span>

<span data-ttu-id="b0e47-434">Se, por algum motivo, o contribuinte quiser cancelar/excluir um evento aceito, selecione **Cancelar** e confirme a operação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-434">If for some many reason, the taxpayer wants to cancel/exclude an event that has accepted, select **Cancel**, and confirm the operation.</span></span> <span data-ttu-id="b0e47-435">O status do evento será atualizado para **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-435">The status of the event will be updated to **Excluded**.</span></span> <span data-ttu-id="b0e47-436">Conclua todas as ações no fluxo [Cancelamento/Exclusão](#canceldelete).</span><span class="sxs-lookup"><span data-stu-id="b0e47-436">Complete all the actions in the [Cancel/Delete](#canceldelete) flow.</span></span>

### <a name="event-r-1070-administrative-and-judicial-process"></a><span data-ttu-id="b0e47-437">Evento R-1070, "Processo administrativo e judicial"</span><span class="sxs-lookup"><span data-stu-id="b0e47-437">Event R-1070, "Administrative and judicial process"</span></span>

<span data-ttu-id="b0e47-438">O evento R-1070 é usado para relatar informações sobre os processos legais e administrativos ao sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-438">Event R-1070 is used to report information about the administrative and lawsuits process to tax authority system.</span></span>

<span data-ttu-id="b0e47-439">Os processos legais e administrativos podem ser iniciados pelo contribuinte ou pelo trabalhador quando valores da previdência social forem contestados.</span><span class="sxs-lookup"><span data-stu-id="b0e47-439">The administrative and lawsuits process can be started by either the taxpayer or by the worker when the amounts in the social security are disputed.</span></span> <span data-ttu-id="b0e47-440">Os procedimentos (judiciais ou administrativos) são realizados pelo tribunal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-440">The proceedings (either judicial or administrative) are carried out by the court.</span></span> <span data-ttu-id="b0e47-441">Após o juiz chegar a um veredito, ele terá o poder de suspender (ou não) os valores que foram retidos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-441">After the judge reaches a final decision, they have the power to suspend (or not) the amounts that were retained.</span></span>

<span data-ttu-id="b0e47-442">A finalidade desse evento é comunicar a existência de procedimentos desse tipo ao banco de dados do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="b0e47-442">The purpose of this event is to communicate the existence of proceedings of this type to the SPED-Reinf database.</span></span> <span data-ttu-id="b0e47-443">Depois que os procedimentos recebem a decisão final do tribunal que suspende a elegibilidade da retenção de valores, o evento se refere a essa decisão para explicar por que os valores foram relatados como suspensos nos eventos periódicos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-443">After the proceedings have a final court decision that suspends the eligibility of withholding amounts, the event refers to that decision to explain why the amounts have been reported as suspended in the periodic events.</span></span>

<span data-ttu-id="b0e47-444">Além das informações típicas que identificam o contribuinte e o evento, o evento R-1070 contém os seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="b0e47-444">Besides the typical information that identifies the taxpayer and the event, event R-1070 contains the following groups:</span></span>

-   <span data-ttu-id="b0e47-445">Identificador do processo ou dos procedimentos</span><span class="sxs-lookup"><span data-stu-id="b0e47-445">Identifier of the process or proceedings</span></span>

-   <span data-ttu-id="b0e47-446">Informações da suspensão</span><span class="sxs-lookup"><span data-stu-id="b0e47-446">Suspension information</span></span>

-   <span data-ttu-id="b0e47-447">Informações complementares sobre os procedimentos</span><span class="sxs-lookup"><span data-stu-id="b0e47-447">Complementary information about the proceedings</span></span>

<span data-ttu-id="b0e47-448">Antes da entrega do evento R-1070, você deve criar o processo relacionado e incluir todas as informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b0e47-448">Before event R-1070 can be delivered, you must create the related process and include all related information.</span></span>

#### <a name="repro-step--create-process"></a><span data-ttu-id="b0e47-449">Etapa de reprodução – Criar processo</span><span class="sxs-lookup"><span data-stu-id="b0e47-449">Repro step – Create process</span></span>

1.  <span data-ttu-id="b0e47-450">Vá para **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-450">Go to **Fiscal books \> Periodic \> SPED Reinf \> Administrative and judicial process**.</span></span>

    ![Processo judicial administrativo](media/bra-administrative-judicial-process.png)

1.  <span data-ttu-id="b0e47-452">Selecione **Novo** e defina os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0e47-452">Select **New**, and set the following fields.</span></span>

    | <span data-ttu-id="b0e47-453">**Campo**</span><span class="sxs-lookup"><span data-stu-id="b0e47-453">**Field**</span></span>                    | <span data-ttu-id="b0e47-454">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b0e47-454">**Description**</span></span>        |
    |------------------------------|-----------------------|
    | <span data-ttu-id="b0e47-455">Número do processo</span><span class="sxs-lookup"><span data-stu-id="b0e47-455">Number of the process</span></span>        | <span data-ttu-id="b0e47-456">Insira o número do processo atribuído pelas autoridades competentes.</span><span class="sxs-lookup"><span data-stu-id="b0e47-456">Enter the process number that was assigned by the competent authorities.</span></span> <span data-ttu-id="b0e47-457">O sistema da autoridade fiscal valida o formato, pois há uma regra específica a ser considerada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-457">The tax authority system validates the format, because there is a specific rule to consider.</span></span> |
    | <span data-ttu-id="b0e47-458">Autor do processo</span><span class="sxs-lookup"><span data-stu-id="b0e47-458">Author of process</span></span>            | <span data-ttu-id="b0e47-459">Selecione a origem do processo:</span><span class="sxs-lookup"><span data-stu-id="b0e47-459">Select the source that the process originated from:</span></span>                                                                                                                   |
    | <span data-ttu-id="b0e47-460">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="b0e47-460">Type of process</span></span>              | <span data-ttu-id="b0e47-461">Selecione o tipo de processo:</span><span class="sxs-lookup"><span data-stu-id="b0e47-461">Select the type of process:</span></span>                                                                                                                                           |
    | <span data-ttu-id="b0e47-462">Cidade da vara judicial</span><span class="sxs-lookup"><span data-stu-id="b0e47-462">City of the judicial section</span></span> | <span data-ttu-id="b0e47-463">Selecione a cidade relacionada onde o processo foi originado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-463">Select the related city where the process originated.</span></span>                                                                                                                 |
    | <span data-ttu-id="b0e47-464">Código da vara judicial</span><span class="sxs-lookup"><span data-stu-id="b0e47-464">Code of the judicial section</span></span> | <span data-ttu-id="b0e47-465">Insira o código da vara judicial.</span><span class="sxs-lookup"><span data-stu-id="b0e47-465">Enter the code for the judicial section.</span></span>                                                                                                                              |

    -   <span data-ttu-id="b0e47-466">Contribuinte</span><span class="sxs-lookup"><span data-stu-id="b0e47-466">Taxpayer</span></span>

    -   <span data-ttu-id="b0e47-467">Outros terceiros</span><span class="sxs-lookup"><span data-stu-id="b0e47-467">Other third party</span></span>

    -   <span data-ttu-id="b0e47-468">Administrativo</span><span class="sxs-lookup"><span data-stu-id="b0e47-468">Administrative</span></span>

    -   <span data-ttu-id="b0e47-469">Judicial</span><span class="sxs-lookup"><span data-stu-id="b0e47-469">Judicial</span></span>

1.  <span data-ttu-id="b0e47-470">Na seção **Detalhes**, insira os detalhes das notas fiscais registradas no Microsoft Dynamics e que são afetadas pelo processo registrado, pois algumas delas podem ter exceções nos impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="b0e47-470">In the **Details** section, enter details of the fiscal documents that are registered in Microsoft Dynamics, and that are affected by the registered process, because some of them might have exceptions in withholding taxes.</span></span> <span data-ttu-id="b0e47-471">Você pode adicionar notas fiscais ou remover as que foram adicionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-471">You can add fiscal documents or remove fiscal documents that were previously added.</span></span>

    | <span data-ttu-id="b0e47-472">**Campo**</span><span class="sxs-lookup"><span data-stu-id="b0e47-472">**Field**</span></span>                        | <span data-ttu-id="b0e47-473">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b0e47-473">**Description**</span></span>                                                                                           |
    |----------------------------------|-----------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="b0e47-474">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="b0e47-474">Reference</span></span>                        | <span data-ttu-id="b0e47-475">O identificador exclusivo da relação entre o número do processo e a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-475">The unique identifier of the relation between the process number and the fiscal document.</span></span>                 |
    | <span data-ttu-id="b0e47-476">Código</span><span class="sxs-lookup"><span data-stu-id="b0e47-476">Code</span></span>                             | <span data-ttu-id="b0e47-477">Selecione o código de suspensão da explicação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-477">Select the explanation suspension code.</span></span>                                                                   |
    | <span data-ttu-id="b0e47-478">Tipo de serviço</span><span class="sxs-lookup"><span data-stu-id="b0e47-478">Service type</span></span>                     | <span data-ttu-id="b0e47-479">Selecione o tipo de serviço relacionado que é aplicável à nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-479">Select the related service type that is applicable for the fiscal document.</span></span>                               |
    | <span data-ttu-id="b0e47-480">Nota fiscal</span><span class="sxs-lookup"><span data-stu-id="b0e47-480">Fiscal document</span></span>                  | <span data-ttu-id="b0e47-481">Selecione a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-481">Select the fiscal document.</span></span>                                                                               |
    | <span data-ttu-id="b0e47-482">Data da decisão</span><span class="sxs-lookup"><span data-stu-id="b0e47-482">Date of decision</span></span>                 | <span data-ttu-id="b0e47-483">A data da decisão, da sentença ou do despacho administrativo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-483">The date of the decision, sentence, or administrative dispatch.</span></span>                                           |
    | <span data-ttu-id="b0e47-484">Valor da retenção</span><span class="sxs-lookup"><span data-stu-id="b0e47-484">Amount of withholding</span></span>            | <span data-ttu-id="b0e47-485">O valor da retenção que foi suspenso devido a um processo legal ou administrativo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-485">The amount of withholding that was suspended because of an administrative or lawsuits process.</span></span>            |
    | <span data-ttu-id="b0e47-486">Valor da retenção adicional</span><span class="sxs-lookup"><span data-stu-id="b0e47-486">Amount of additional withholding</span></span> | <span data-ttu-id="b0e47-487">O valor adicional da retenção que foi suspenso devido a um processo legal ou administrativo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-487">The additional amount of withholding that was suspended because of an administrative or lawsuits process.</span></span> |

    > [!NOTE]
    > <span data-ttu-id="b0e47-488">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-488">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

### <a name="event-r-2010-acquired-services"></a><span data-ttu-id="b0e47-489">Evento R-2010, "Serviços adquiridos"</span><span class="sxs-lookup"><span data-stu-id="b0e47-489">Event R-2010, "Acquired services"</span></span>

<span data-ttu-id="b0e47-490">O evento periódico R-2010 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço recebidas pelo estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-490">Periodic event R-2010 is used to report, to the tax authority system, information about the withholding amounts for social security that are present in service fiscal documents that were received by the fiscal establishment.</span></span> <span data-ttu-id="b0e47-491">Esse evento não tem nenhuma outra finalidade além de relatar essas notas fiscais para o governo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-491">This event has no other purpose but to report those fiscal documents to the government.</span></span>

<span data-ttu-id="b0e47-492">Esse evento deve ser enviado até o décimo quinto dia do mês seguinte.</span><span class="sxs-lookup"><span data-stu-id="b0e47-492">This event must be sent until the fifteenth day of the next month.</span></span> <span data-ttu-id="b0e47-493">Por ser um evento periódico, não é recomendável enviá-lo apenas uma vez, próximo à data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-493">Because it's a periodic event, we don't recommend that you send the event just one time, near the due date.</span></span> <span data-ttu-id="b0e47-494">Em vez disso, você deve enviá-lo regularmente e com frequência durante o período.</span><span class="sxs-lookup"><span data-stu-id="b0e47-494">Instead, you should send it regularly and frequently during the period.</span></span>

<span data-ttu-id="b0e47-495">Além disso, a geração desse evento requer a adoção de novas semânticas para o tratamento de eventos em livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-495">Additionally, generation of this event requires the adoption of new semantics for handling events in fiscal books.</span></span> <span data-ttu-id="b0e47-496">As novas semânticas são desacopladas de uma apuração de imposto, mas ainda estão no contexto do período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-496">The new semantics are decoupled from a tax assessment but are still in the context of the booking period.</span></span> <span data-ttu-id="b0e47-497">Depois que todas as notas fiscais no módulo **Livros fiscais** estiverem no contexto de um período de escrituração, o evento R-2010 também deverá ser gerado por período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-497">After every fiscal document in the **Fiscal books** module is in the context of a booking period, event R-2010 must also be generated by booking period.</span></span>


<span data-ttu-id="b0e47-498">Somente o imposto INSS Retido e o imposto sobre serviços devem ser selecionados para gerar esse evento no período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-498">Only service and retained INSS tax type must be selected to generate this event in the booking period.</span></span>

<span data-ttu-id="b0e47-499">**Principais critérios**</span><span class="sxs-lookup"><span data-stu-id="b0e47-499">**Main criteria**</span></span>

-   <span data-ttu-id="b0e47-500">As notas fiscais são registradas e sincronizadas no estabelecimento fiscal e no período relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-500">The fiscal documents are booked and synced in the related period and fiscal establishment.</span></span>

-   <span data-ttu-id="b0e47-501">As notas fiscais têm o status de **Aprovada** ou **Cancelada**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-501">The fiscal documents have a status of **Approved** or **Canceled**.</span></span>

-   <span data-ttu-id="b0e47-502">O modelo da nota fiscal é **SE**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-502">The fiscal document model is **SE**.</span></span>

-   <span data-ttu-id="b0e47-503">O tipo de imposto é **INSS** e ele é retido (a caixa de seleção **Imposto retido/recuperável** é marcada).</span><span class="sxs-lookup"><span data-stu-id="b0e47-503">The tax type is **INSS**, and it's retained (the **Retained tax/to recuperate** check box is selected).</span></span>

![Impostos brasileiros](media/bra-brazilian-taxes.png)

> [!NOTE]
> <span data-ttu-id="b0e47-505">Nunca use o tipo de imposto **INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-505">Never use the **INSS-CPRB** tax type.</span></span>

<span data-ttu-id="b0e47-506">O relatório é agrupado por um valor **Tipo de código de serviço** (tabela 06 da documentação do SPED-Reinf).</span><span class="sxs-lookup"><span data-stu-id="b0e47-506">The report is grouped by a **Type of service code** value (table 06 from the SPED-Reinf documentation).</span></span> <span data-ttu-id="b0e47-507">Portanto, você deve modificar o lançamento de notas fiscais de serviço para habilitar a captura dessas informações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-507">Therefore, you must modify the posting of service fiscal documents to enable the capture of this information.</span></span> <span data-ttu-id="b0e47-508">Caso contrário, não é possível gerar o evento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-508">Otherwise, the event can't be generated.</span></span>

<span data-ttu-id="b0e47-509">O evento envia quatro tipos de valores para o banco de dados do governo:</span><span class="sxs-lookup"><span data-stu-id="b0e47-509">The event sends four types of amounts to the government database:</span></span>

-   <span data-ttu-id="b0e47-510">**Retenção** – O tipo de imposto INSS Retido calculado que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-510">**Withholding** – The calculated retained INSS tax type that is linked to the fiscal document line.</span></span>

-   <span data-ttu-id="b0e47-511">**Retenção adicional** – Uma variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-511">**Additional withholding** – A variation of the INSS tax type that is linked to the fiscal document line.</span></span>

-   <span data-ttu-id="b0e47-512">**Retenção suspensa** – O valor do tipo de imposto INSS Retido suspenso.</span><span class="sxs-lookup"><span data-stu-id="b0e47-512">**Suspended withholding** – The amount of the suspended retained INSS tax type.</span></span>

-   <span data-ttu-id="b0e47-513">**Retenção adicional suspensa** – O valor suspenso da variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-513">**Suspended additional withholding** – The suspended amount on the variation of the INSS tax type that is linked to the fiscal document line.</span></span>

<span data-ttu-id="b0e47-514">Sempre que uma suspensão de valores ocorrer, o processo legal ou administrativo associado deve ser especificado no evento para oferecer suporte aos motivos da suspensão ou explicá-los.</span><span class="sxs-lookup"><span data-stu-id="b0e47-514">Whenever a suspension of amounts occurs, the associated administrative or lawsuits process must be specified in the event to support (or explain) the reasons for the suspension.</span></span> <span data-ttu-id="b0e47-515">Essas informações devem ser inseridas manualmente nos campos **Valor da retenção** e **Valor da retenção adicional** na página **Processo administrativo e judicial** que é descrita na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="b0e47-515">This information must be manually entered in the **Amount of withholding** and **Additional amount of withholding** fields on the **Administration and judicial process** page that is described in the previous section.</span></span>

<span data-ttu-id="b0e47-516">O evento R-2010 usa o conceito de fechamento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-516">Event R-2010 uses the concept of closing.</span></span> <span data-ttu-id="b0e47-517">Depois que esse evento for fechado, o serviço Web recusará quaisquer novas entradas ou modificações nele, a menos que seja reaberto manualmente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-517">After this event is closed, the web service will refuse any new entries or modifications for it, unless it's manually reopened.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-518">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-518">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

### <a name="event-r-2020-provided-services"></a><span data-ttu-id="b0e47-519">Evento R-2020, "Serviços fornecidos"</span><span class="sxs-lookup"><span data-stu-id="b0e47-519">Event R-2020, "Provided services"</span></span>

<span data-ttu-id="b0e47-520">O evento periódico R-2020 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço emitidas pelos estabelecimentos fiscais de uma organização fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-520">Periodic event R-2020 is used to report, to the tax authority system, information about the withholdings amounts for social security that are present in service fiscal documents that were issued by the fiscal establishments of a fiscal organization.</span></span>

<span data-ttu-id="b0e47-521">Esse evento funciona como o evento R-2010, mas você deve considerar as contas de cliente e o modelo de nota fiscal SE (saída) que é emitido pelo estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-521">This event works like event R-2010, but you must consider customer accounts and fiscal document model SE (outgoing) that is issued by the fiscal establishment.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-522">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-522">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

### <a name="event-r-2060-inss-cprb"></a><span data-ttu-id="b0e47-523">Evento R-2060, "INSS CPRB"</span><span class="sxs-lookup"><span data-stu-id="b0e47-523">Event R-2060, "INSS CPRB"</span></span>

<span data-ttu-id="b0e47-524">O evento periódico R-2060 é usado para enviar informações sobre a apuração de imposto da retenção para a previdência social ao SPED-Reinf quando a organização fiscal escolher calcular a previdência social com base na receita bruta em vez da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-524">Periodic event R-2060 is used to send information about the tax assessment of the withholding for social security to the SPED-Reinf when the fiscal organization has chosen to calculate the social security based on the gross revenue instead of the payroll.</span></span>

<span data-ttu-id="b0e47-525">Portanto, antes de gerar o evento, você deve realizar a apuração de imposto por organização fiscal no módulo **Livros fiscais**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-525">Therefore, before you generate the event, you must do the tax assessment by fiscal organization in the **Fiscal books** module.</span></span> <span data-ttu-id="b0e47-526">Quando essa opção é estabelecida nos parâmetros do SPED-Reinf, os usuários podem criar a apuração de imposto para o INSS-CPRB e os impostos são calculados automaticamente com base nos critérios definidos nos Parâmetros de livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-526">When this option is established in the SPED-Reinf parameters, users can create the tax assessment for INSS-CPRB, and taxes are automatically calculated based on the criteria that are defined in the Fiscal books parameters.</span></span>

<span data-ttu-id="b0e47-527">O Microsoft Dynamics pegará todas as notas fiscais que estão registradas no período relacionado e que representam a receita e aplicará a alíquota de imposto ao valor base.</span><span class="sxs-lookup"><span data-stu-id="b0e47-527">Microsoft Dynamics will pick up all fiscal documents that are booked in the related period and that represents revenue, and it will apply the tax rate to the base amount.</span></span> <span data-ttu-id="b0e47-528">A alíquota de imposto aplicada pode variar, dependendo do produto ou serviço que gerou a receita.</span><span class="sxs-lookup"><span data-stu-id="b0e47-528">The tax rate that is applied can vary, depending on the product or service that generated the revenue.</span></span> <span data-ttu-id="b0e47-529">O resultado será o valor de CPRB.</span><span class="sxs-lookup"><span data-stu-id="b0e47-529">The result will be the amount of CPRB.</span></span>

<span data-ttu-id="b0e47-530">Para essa finalidade, um novo tipo de imposto brasileiro, o **INSS-CPRB**, foi criado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-530">For this purpose, a new Brazilian tax type, **INSS-CPRB**, was created.</span></span> <span data-ttu-id="b0e47-531">Esse tipo de imposto só é usado na apuração do imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="b0e47-531">This tax type is used only in the generation of the INSS-CPRB tax assessment.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-532">Não use o tipo de imposto **INSS-CPRB** para outras finalidades.</span><span class="sxs-lookup"><span data-stu-id="b0e47-532">Don't use the **INSS-CPRB** tax type for other purposes.</span></span>

<span data-ttu-id="b0e47-533">Como a apuração do imposto INSS-CPRB é um tipo de apuração de imposto, ajustes podem ser necessários.</span><span class="sxs-lookup"><span data-stu-id="b0e47-533">Because the INSS-CPRB tax assessment is a type of tax assessment, adjustments might become necessary.</span></span> <span data-ttu-id="b0e47-534">Esses ajustes devem ser inseridos manualmente como adições ou reduções.</span><span class="sxs-lookup"><span data-stu-id="b0e47-534">These adjustments must be manually entered as either additions or reductions.</span></span>

<span data-ttu-id="b0e47-535">Por fim, a apuração do imposto e os ajustes determinam o valor de CPRB que deve ser pago.</span><span class="sxs-lookup"><span data-stu-id="b0e47-535">Finally, the tax assessment and the adjustments determine the amount of CPRB that must be paid.</span></span> <span data-ttu-id="b0e47-536">No entanto, a geração do diário de pagamento e o registro nesse pagamento não são o escopo desse recurso.</span><span class="sxs-lookup"><span data-stu-id="b0e47-536">However, generation of the payment journal and registration on this payment isn't in the scope of this feature.</span></span>

<span data-ttu-id="b0e47-537">Os períodos nessa nova apuração de imposto devem ser gerenciados da mesma forma que em outras apurações.</span><span class="sxs-lookup"><span data-stu-id="b0e47-537">Periods for this new tax assessment must be managed in the same way as other tax assessments.</span></span> <span data-ttu-id="b0e47-538">Em outras palavras, a apuração de imposto pode ser criada ou atualizada somente enquanto estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="b0e47-538">In other words, the tax assessment can be created or updated only while it's open.</span></span> <span data-ttu-id="b0e47-539">Após ser finalizada, não poderá mais ser alterada a menos que seja reaberta.</span><span class="sxs-lookup"><span data-stu-id="b0e47-539">After it's finalized, it can no longer be touched unless it's reopened.</span></span>

<span data-ttu-id="b0e47-540">Após a criação da apuração de imposto e a realização dos ajustes necessários, o evento periódico R-2060 pode ser gerado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-540">After the tax assessment is created and any required adjustments are made, periodic event R-2060 can be generated.</span></span>

<span data-ttu-id="b0e47-541">O evento R-2060 inclui os totais da apuração de impostos e detalhes dos cálculos de impostos por código de atividade econômica, ajustes (adições e reduções, quando aplicável) e referências a processos legais e administrativos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-541">Event R-2060 includes the totals of the tax assessment and details of the tax calculations by economic activity code, adjustments (additions and reductions, when applicable), and references to administrative and lawsuits processes.</span></span>

#### <a name="repro-step--setup"></a><span data-ttu-id="b0e47-542">Etapa de reprodução – Configuração</span><span class="sxs-lookup"><span data-stu-id="b0e47-542">Repro step – Setup</span></span>

1.  <span data-ttu-id="b0e47-543">Vá para **Livros fiscais \> Configuração \> Organização fiscal**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-543">Go to **Fiscal books \> Setup \> Fiscal organization**.</span></span>

2.  <span data-ttu-id="b0e47-544">Defina a opção **CPRB** como **Sim** para habilitar a criação da apuração do INSS-CPRB e a transmissão do evento R-2060.</span><span class="sxs-lookup"><span data-stu-id="b0e47-544">Set the **CPRB** option to **Yes** to enable creation of the INSS-CPRB assessment and transmission of event R-2060.</span></span>

3.  <span data-ttu-id="b0e47-545">Vá para **Livros fiscais \> Configuração \> Sped Reinf \> Códigos de atividades econômicas**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-545">Go to **Fiscal books \> Setup \> Sped Reinf \> Economic activity codes**.</span></span> <span data-ttu-id="b0e47-546">Os códigos de atividades econômicas devem ser configurados para habilitar o cálculo automático dos valores do imposto INSS-CPRB, pois a nota fiscal não possui informações relacionadas sobre esse imposto.</span><span class="sxs-lookup"><span data-stu-id="b0e47-546">Economic activity codes must be configured to enable automatic calculation of INSS-CPRB tax amounts, because the fiscal document has no related information about this tax.</span></span> <span data-ttu-id="b0e47-547">Essa abordagem foi implementada para facilitar a configuração da matriz de impostos.</span><span class="sxs-lookup"><span data-stu-id="b0e47-547">This approach was implemented to facilitate the configuration of the tax matrix.</span></span>

4.  <span data-ttu-id="b0e47-548">Selecione **Novo** para criar um código de atividade econômica e insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="b0e47-548">Select **New** to create an economic activity code, and enter a description.</span></span> <span data-ttu-id="b0e47-549">Você deve verificar a Tabela 09 do Sped REINF no site da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="b0e47-549">You must check the Sped REINF Table 09 on the tax authority website.</span></span>

5.  <span data-ttu-id="b0e47-550">Selecione o código de imposto que contém a alíquota de imposto para aplicar ao produto ou serviço.</span><span class="sxs-lookup"><span data-stu-id="b0e47-550">Select the tax code that contains the tax rate to apply for the product or service.</span></span> <span data-ttu-id="b0e47-551">Você deve criar um tipo de imposto INSS Retido.</span><span class="sxs-lookup"><span data-stu-id="b0e47-551">You must create a Retained INSS tax type.</span></span>

6.  <span data-ttu-id="b0e47-552">Na guia **Linha**, insira os produtos ou serviços que estão relacionados pela atividade econômica.</span><span class="sxs-lookup"><span data-stu-id="b0e47-552">On the **Line** tab, enter the products or services that are related by the economic activity.</span></span> <span data-ttu-id="b0e47-553">Os produtos são identificados pelo código de classificação fiscal e os serviços pelo código de serviço (federal).</span><span class="sxs-lookup"><span data-stu-id="b0e47-553">Products are identified by the fiscal classification code and services are identified by the service code (federal).</span></span>

#### <a name="repro-step--create-tax-assessment-option-1"></a><span data-ttu-id="b0e47-554">Etapa de reprodução – Criar apuração de imposto (opção 1)</span><span class="sxs-lookup"><span data-stu-id="b0e47-554">Repro step – Create tax assessment (option 1)</span></span>

1.  <span data-ttu-id="b0e47-555">Vá para **Livros fiscais \> Comum \> Período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-555">Go to **Fiscal books \> Common \> Booking period**.</span></span>

2.  <span data-ttu-id="b0e47-556">Selecione um período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-556">Select a booking period.</span></span>

3.  <span data-ttu-id="b0e47-557">No Painel de Ação, selecione **INSS-CPRN** e, em seguida, selecione **Novo** para criar uma apuração de imposto.</span><span class="sxs-lookup"><span data-stu-id="b0e47-557">On the Action Pane, select **INSS-CPRN**, and then select **New** to create a tax assessment.</span></span> <span data-ttu-id="b0e47-558">O Microsoft Dynamics automaticamente cria a apuração de imposto para o período de escrituração selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-558">Microsoft Dynamics automatically creates the tax assessment for the selected booking period.</span></span>

#### <a name="repro-step--create-tax-assessment-option-2"></a><span data-ttu-id="b0e47-559">Etapa de reprodução – Criar apuração de imposto (opção 2)</span><span class="sxs-lookup"><span data-stu-id="b0e47-559">Repro step – Create tax assessment (option 2)</span></span>

1.  <span data-ttu-id="b0e47-560">Vá para **Livros fiscais \> Comum \> Apuração de imposto \> INSS-CPRB** e, em seguida, selecione **Apuração do imposto INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-560">Go to **Fiscal books \> Common \> Tax assessment \> INSS-CPRB**, and then select **INSS-CPRB tax assessment**.</span></span>

2.  <span data-ttu-id="b0e47-561">Selecione o período de escrituração e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-561">Select the booking period, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-562">Você poderá receber o seguinte aviso: “Linha XXXX: não foi possível identificar o código da atividade econômica”.</span><span class="sxs-lookup"><span data-stu-id="b0e47-562">You might receive the following warning: "Line XXXX: unable to identify the economic activity code."</span></span> <span data-ttu-id="b0e47-563">Esse aviso indica que o Microsoft Dynamics não encontrou o código da atividade econômica para a linha e a nota fiscal relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b0e47-563">This warning indicates that Microsoft Dynamics didn't find the economic activity code for the related fiscal document and line.</span></span> <span data-ttu-id="b0e47-564">Nesse caso, você deve concluir a configuração que é descrita na etapa de reprodução anterior.</span><span class="sxs-lookup"><span data-stu-id="b0e47-564">In this case, you must complete the setup that is described in the previous repro step.</span></span>

<span data-ttu-id="b0e47-565">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="b0e47-565">**Delete**</span></span>

<span data-ttu-id="b0e47-566">Você poderá excluir uma apuração do imposto INSS-CPRB existente se o status for **Aberto**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-566">You can delete an existing INSS-CPRB tax assessment if the status is **Opened**.</span></span>

<span data-ttu-id="b0e47-567">**Notas fiscais e operações não fiscais**</span><span class="sxs-lookup"><span data-stu-id="b0e47-567">**Fiscal documents and Non-fiscal operations**</span></span>

<span data-ttu-id="b0e47-568">Quando os impostos INSS-CPRB são apurados, o valor tributável da nota fiscal é considerado e classificado durante o processo de apuração.</span><span class="sxs-lookup"><span data-stu-id="b0e47-568">When INSS-CPRB taxes are assessed, the taxable amount of the fiscal document is considered and classified during the assessment process.</span></span> <span data-ttu-id="b0e47-569">Você pode visualizar as operações não fiscais e as notas fiscais relacionadas que fazem parte do cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="b0e47-569">You can view the related fiscal documents and non-fiscal operations that are part of the tax calculation.</span></span>

<span data-ttu-id="b0e47-570">**Transações de imposto**</span><span class="sxs-lookup"><span data-stu-id="b0e47-570">**Tax transactions**</span></span>

<span data-ttu-id="b0e47-571">Quando os impostos INSS-CPRB são apurados, você pode visualizar os detalhes das transações de imposto que são gerados pelo processo.</span><span class="sxs-lookup"><span data-stu-id="b0e47-571">When INSS-CPRB taxes are assessed, you can view the tax transactions details that are generated by the process.</span></span>

<span data-ttu-id="b0e47-572">**Ajuste**</span><span class="sxs-lookup"><span data-stu-id="b0e47-572">**Adjustment**</span></span>

<span data-ttu-id="b0e47-573">Você pode inserir transações de ajuste adicionais para ajustar (aumentar ou diminuir) o valor do INSS-CPRB calculado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-573">You can enter additional adjustment transactions to adjust (increase or decrease) the amount of INSS-CPRB that is calculated.</span></span> <span data-ttu-id="b0e47-574">Configure os códigos de ajuste em **Livros fiscais \> Configuração \> Códigos de ajuste de imposto \> Tabela de códigos de ajustes de INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-574">You configure the adjustment codes at **Fiscal books \> Setup \> Tax adjustment codes \> INSS-CPRB adjustments codes table**.</span></span>

1.  <span data-ttu-id="b0e47-575">Selecione **Ajuste** para adicionar uma transação de ajuste que diminuirá ou aumentará o valor do imposto (débito) que é calculado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-575">Select **Adjustment** to add an adjustment transaction that will decrease or increase the tax amount (debit) that is calculated.</span></span>

2.  <span data-ttu-id="b0e47-576">Selecione o código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="b0e47-576">Select the adjustment code.</span></span>

3.  <span data-ttu-id="b0e47-577">Insira uma descrição da transação relacionada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-577">Enter a description of the related transaction.</span></span>

4.  <span data-ttu-id="b0e47-578">Especifique o valor do ajuste e a atividade econômica.</span><span class="sxs-lookup"><span data-stu-id="b0e47-578">Specify the adjustment amount and the economic activity.</span></span>

5.  <span data-ttu-id="b0e47-579">Especifique a data do ajuste.</span><span class="sxs-lookup"><span data-stu-id="b0e47-579">Specify the adjustment date.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0e47-580">Os ajustes de INSS-CPRB estão disponíveis apenas por meio desse procedimento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-580">Adjustments for INSS-CPRB are available only through this procedure.</span></span> <span data-ttu-id="b0e47-581">Esse tipo de ajuste não está disponível em **Livros fiscais \> Diários \> Ajuste geral de imposto/benefício/incentivo**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-581">This type of adjustment isn't available at **Fiscal books \> Journals \> General tax adjustment/benefit/incentive**.</span></span>

<span data-ttu-id="b0e47-582">**Finalizar e reabrir**</span><span class="sxs-lookup"><span data-stu-id="b0e47-582">**Finalize and Reopen**</span></span>

<span data-ttu-id="b0e47-583">Você pode finalizar ou reabrir a apuração do imposto INSS-CPRB relacionada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-583">You can finalize or reopen the related INSS-CPRB tax assessment.</span></span>

<span data-ttu-id="b0e47-584">Quando uma apuração do imposto INSS-CPRB é finalizada, nenhuma modificação é permitida nessa apuração para esse período, a menos que ela seja reaberta.</span><span class="sxs-lookup"><span data-stu-id="b0e47-584">When an INSS-CPRB tax assessment is finalized, no modifications to the tax assessment are allowed for that period, unless the tax assessment is reopened.</span></span> <span data-ttu-id="b0e47-585">Um comprovante é criado para lançar o imposto INSS-CPRB para coleta e as contas contábeis são definidas no lançamento contábil para o imposto INSS em **Imposto \> Configuração \> Imposto sobre vendas \> Grupos de lançamento contábil**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-585">A voucher is created to post the INSS-CPRB tax to collect, and the ledger accounts are defined in the ledger posting for INSS tax at **Tax \> Setup \> Sales tax \> Ledger posting groups**.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-586">Na atual arquitetura do SPED-Reinf definida pelo governo, o processo de pagamento e liquidação do passivo criado pela apuração de imposto será relatado a outro sistema chamado de DCTF Web.</span><span class="sxs-lookup"><span data-stu-id="b0e47-586">In the current SPED-Reinf architecture that is defined by the government, the process for payment and settlement of the liability that is created by the tax assessment will be reported to another system that is named DCTF web.</span></span> <span data-ttu-id="b0e47-587">Esse sistema consome a saída não apenas do SPED-Reinf, mas também de outros sistemas, como o eSocial e o PER/DCOMP.</span><span class="sxs-lookup"><span data-stu-id="b0e47-587">This system consumes the output from not only the SPED-Reinf but also the other systems, such as eSocial and PER/DCOMP.</span></span> <span data-ttu-id="b0e47-588">Portanto, o processo de pagamento atualmente está fora do escopo e é entregue por meio de outro recurso do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="b0e47-588">Therefore, the payment process is currently out of scope and is delivered through another Microsoft Dynamics feature.</span></span>

<span data-ttu-id="b0e47-589">A ação de reabertura estará disponível se o evento R-2060 já tiver sido fechado para o estabelecimento fiscal matriz e se a apuração de imposto já estiver finalizada.</span><span class="sxs-lookup"><span data-stu-id="b0e47-589">The reopen action is available if event R-2060 has already been closed for the root fiscal establishment, and if the tax assessment is already finalized.</span></span> <span data-ttu-id="b0e47-590">A ação de reabertura reverte o comprovante anterior que foi gerado pela ação de fechamento.</span><span class="sxs-lookup"><span data-stu-id="b0e47-590">The reopen action reverses the previous voucher that was generated by the closing action.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e47-591">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-591">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

### <a name="events-r-2090-closing-and-r-2098-reopen"></a><span data-ttu-id="b0e47-592">Eventos R-2090, "Fechamento" e R-2098, "Reabertura"</span><span class="sxs-lookup"><span data-stu-id="b0e47-592">Events R-2090, "Closing," and R-2098, "Reopen"</span></span>

<span data-ttu-id="b0e47-593">**Fechamento**</span><span class="sxs-lookup"><span data-stu-id="b0e47-593">**Closing**</span></span>

<span data-ttu-id="b0e47-594">Os eventos periódicos R-2010, R-2010 e R-2060 devem ser fechados ao final de um período, quando não houver mais nenhuma transação a ser relatada nesse período.</span><span class="sxs-lookup"><span data-stu-id="b0e47-594">Periodic events R-2010, R-2010, and R-2060 must be closed at the end of a period, when there are no more transactions to report in that period.</span></span>

#### <a name="repro-step"></a><span data-ttu-id="b0e47-595">Etapa de reprodução</span><span class="sxs-lookup"><span data-stu-id="b0e47-595">Repro step</span></span>

1.  <span data-ttu-id="b0e47-596">Finalize a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="b0e47-596">Finalize the INSS-CPRB tax assessment, even if you don't assess INSS-CPRB tax.</span></span>

2.  <span data-ttu-id="b0e47-597">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-597">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

<span data-ttu-id="b0e47-598">**Reabrir**</span><span class="sxs-lookup"><span data-stu-id="b0e47-598">**Reopen**</span></span>

<span data-ttu-id="b0e47-599">Depois que os eventos periódicos R-2010, R-2010 e R-2060 forem fechados por meio de um evento R-2099, eles poderão ser reabertos por meio de um evento R-2098.</span><span class="sxs-lookup"><span data-stu-id="b0e47-599">After periodic events R-2010, R-2010, and R-2060 are closed through an event R-2099, they can be reopened through an event R-2098.</span></span> <span data-ttu-id="b0e47-600">Você poderá então relatar novas transações ou modificar transações existentes para o período.</span><span class="sxs-lookup"><span data-stu-id="b0e47-600">You can then report new transactions or modify existing transactions for the period.</span></span>

#### <a name="repro-step"></a><span data-ttu-id="b0e47-601">Etapa de reprodução</span><span class="sxs-lookup"><span data-stu-id="b0e47-601">Repro step</span></span>

1.  <span data-ttu-id="b0e47-602">Reabra a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="b0e47-602">Reopen the INSS-CPRB tax assessment, even if you don't assess INSS-CPRB tax.</span></span>

2.  <span data-ttu-id="b0e47-603">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b0e47-603">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

<span data-ttu-id="b0e47-604">**Consultar evento 5011**</span><span class="sxs-lookup"><span data-stu-id="b0e47-604">**Inquire event 5011**</span></span>

1.  <span data-ttu-id="b0e47-605">Após a entrega do R-2090 ao governo e a atualização de seu status para **Aguardando resposta** (**Resposta pendente)**, selecione **Executar processamento** e, em seguida, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-605">After R-2090 is delivered to the government and its status is updated to **Pending Response** (**Pendente resposta**), select **Run processing**, and then select **SPED Reinf**.</span></span>

2.  <span data-ttu-id="b0e47-606">Defina a opção **Escolher ação** como **Habilitar** e, em seguida, selecione a ação **Gerar** para gerar a mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="b0e47-606">Set the **Choose action** option to be **Enable** and select the action **Gerar** to generate the XML message.</span></span>

3.  <span data-ttu-id="b0e47-607">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-607">Select **OK** to confirm the action.</span></span>

4.  <span data-ttu-id="b0e47-608">Depois que o item de mensagem é criado, o tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Gerada**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-608">After the message item is created, the **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Consulta Gerada**.</span></span>

5.  <span data-ttu-id="b0e47-609">Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-609">Select **Run processing**, and then select **SPED Reinf** again.</span></span>

6.  <span data-ttu-id="b0e47-610">Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Enviar consulta** para entregar a consulta relacionada às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="b0e47-610">Set the **Choose action** option to be **Enable** and select the action **Enviar consulta** to deliver the related inquiry to the tax authorities.</span></span>

7.  <span data-ttu-id="b0e47-611">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-611">Select **OK** to confirm the action.</span></span>

8.  <span data-ttu-id="b0e47-612">O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Enviada**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-612">The **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Consulta Enviada**.</span></span>

9.  <span data-ttu-id="b0e47-613">Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.</span><span class="sxs-lookup"><span data-stu-id="b0e47-613">Select **Run processing**, and then select **SPED Reinf** again.</span></span>

10. <span data-ttu-id="b0e47-614">Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Obter consulta resposta** para obter a aprovação da autoridade fiscal e o número do protocolo final, para poder fechar o período do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="b0e47-614">Set the **Choose action** option to be **Enable** and select the action **Obter consulta resposta** to get the approval from the tax authority and the final protocol number, so that you can close the SPED-Reinf period.</span></span>

11. <span data-ttu-id="b0e47-615">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="b0e47-615">Select **OK** to confirm the action.</span></span>

12. <span data-ttu-id="b0e47-616">O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Aceito**.</span><span class="sxs-lookup"><span data-stu-id="b0e47-616">The **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Aceito**.</span></span>
