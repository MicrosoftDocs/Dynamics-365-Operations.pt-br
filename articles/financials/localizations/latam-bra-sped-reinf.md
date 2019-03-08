---
title: Declaração de imposto de SPED-Reinf (Brasil)
description: Este tópico fornece informações sobre a configuração de eventos do SPED-Reinf usando Livros fiscais e a estrutura de registro de relatórios SII no Microsoft Dynamics 365 for Finance and Operations para o Brasil.
author: sndray
manager: AnnBe
ms.date: 01/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: e5e5fa94b639a6b36749d6792819fa52614dad44
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "371572"
---
# <a name="sped-reinf-tax-statement-brazil"></a><span data-ttu-id="d291c-103">Declaração de imposto de SPED-Reinf (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d291c-103">SPED-Reinf tax statement (Brazil)</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d291c-104">O SPED-Reinf é um novo relatório de declaração de imposto que coleta informações sobre imposto retido na fonte e outras informações fiscais de interesse da Receita Federal do Brasil (RFB) e da Previdência Social.</span><span class="sxs-lookup"><span data-stu-id="d291c-104">The SPED-Reinf is a new tax statement report that gathers information about withholding tax and other tax information that is of interest from the Brazilian Internal Revenue Service (RFB) and Social Security.</span></span> <span data-ttu-id="d291c-105">(Reinf significa "Retenções e Outras Informações Fiscais".) A declaração consiste em um conjunto de eventos que devem ser entregues, em layouts específicos, por meio do ambiente do Sistema Público de Escrituração Digital (SPED).</span><span class="sxs-lookup"><span data-stu-id="d291c-105">(In Brazilian Portuguese, Reinf stands for "Retenções e Outras Informações Fiscais.") The statement consists of a set of events that must be delivered, in specific layouts, through the environment of the public digital bookkeeping system (SPED).</span></span> <span data-ttu-id="d291c-106">Além disso, eles devem ser entregues usando um certificado digital válido, emitido por uma entidade credenciada pela Infraestrutura de Chaves Públicas Brasileira (ICP-Brasil).</span><span class="sxs-lookup"><span data-stu-id="d291c-106">Additionally, they must be delivered by using a valid digital certificate that is issued by an entity that is accredited by the Brazilian Public Key Infrastructure (ICP-Brasil).</span></span> <span data-ttu-id="d291c-107">A declaração será considerada válida após a confirmação do recebimento e a validação do conteúdo dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="d291c-107">The statement will be considered valid after receipt is confirmed and the contents of the files are validated.</span></span>

<span data-ttu-id="d291c-108">O SPED-Reinf foi criado para apurar impostos federais retidos, para fins de imposto de renda e Previdência Social, em atividades que não estão relacionadas ao trabalho.</span><span class="sxs-lookup"><span data-stu-id="d291c-108">The SPED-Reinf was created to assess federal taxes that are withheld, for Social Security and income taxes purposes, for activities that aren't related to labor.</span></span> <span data-ttu-id="d291c-109">Exemplos dessas atividades incluem notas fiscais, pagamentos e outros eventos.</span><span class="sxs-lookup"><span data-stu-id="d291c-109">Examples of these activities include fiscal documents, payments, and other events.</span></span>

<span data-ttu-id="d291c-110">O Microsoft Dynamics oferece suporte à geração de eventos do SPED-Reinf por meio do módulo **Livros fiscais** e da estrutura de registro de relatórios SII.</span><span class="sxs-lookup"><span data-stu-id="d291c-110">Microsoft Dynamics supports the generation of SPED-Reinf events through the **Fiscal books** module and the SII reporting register framework.</span></span> <span data-ttu-id="d291c-111">Os usuários podem trocar mensagens XML para cada evento exigido pela autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-111">Users can exchange XML messages for every event that is required by the tax authority.</span></span>

<span data-ttu-id="d291c-112">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="d291c-112">**Scope**</span></span>

-   <span data-ttu-id="d291c-113">Versão do SPED-Reinf com suporte: 1.3.</span><span class="sxs-lookup"><span data-stu-id="d291c-113">Supported SPED-Reinf version: 1.3.</span></span>

-   <span data-ttu-id="d291c-114">Versões com suporte: Microsoft Dynamics AX 2012 R3 e Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d291c-114">Supported versions: Microsoft Dynamics AX 2012 R3 and Microsoft Dynamics 365 for Finance and Operations.</span></span>

-   <span data-ttu-id="d291c-115">A integração de livros fiscais do Microsoft Dynamics AX 2009 não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="d291c-115">Microsoft Dynamics AX 2009 fiscal books integration isn't supported.</span></span>

-   <span data-ttu-id="d291c-116">A procuração eletrônica não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="d291c-116">Electronic power of attorney (procuração eletronica) isn't supported.</span></span>

<span data-ttu-id="d291c-117">**Tabela de eventos**</span><span class="sxs-lookup"><span data-stu-id="d291c-117">**Table of events**</span></span>

| <span data-ttu-id="d291c-118">**Evento**</span><span class="sxs-lookup"><span data-stu-id="d291c-118">**Event**</span></span> | <span data-ttu-id="d291c-119">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d291c-119">**Description**</span></span>                                                   | <span data-ttu-id="d291c-120">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="d291c-120">**Event type**</span></span>             | <span data-ttu-id="d291c-121">**Com suporte no Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="d291c-121">**Supported in Microsoft Dynamics**</span></span> | <span data-ttu-id="d291c-122">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="d291c-122">**Comments**</span></span>                                                                                                                                                                |
|-----------|-------------------------------------------------------------------|----------------------------|-------------------------------------|----------------------------------------|
| <span data-ttu-id="d291c-123">R-1000</span><span class="sxs-lookup"><span data-stu-id="d291c-123">R-1000</span></span>    | <span data-ttu-id="d291c-124">Informações do contribuinte</span><span class="sxs-lookup"><span data-stu-id="d291c-124">Taxpayer information</span></span>                                              | <span data-ttu-id="d291c-125">Inicial</span><span class="sxs-lookup"><span data-stu-id="d291c-125">Initial</span></span>                    | <span data-ttu-id="d291c-126">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-126">**Yes**</span></span>                             | <span data-ttu-id="d291c-127">Suporte para contribuintes como entidades legais.</span><span class="sxs-lookup"><span data-stu-id="d291c-127">Support for taxpayers as legal entities.</span></span>   |
| <span data-ttu-id="d291c-128">R-1070</span><span class="sxs-lookup"><span data-stu-id="d291c-128">R-1070</span></span>    | <span data-ttu-id="d291c-129">Processo administrativo e judicial</span><span class="sxs-lookup"><span data-stu-id="d291c-129">Administrative and Judicial process</span></span>                               | <span data-ttu-id="d291c-130">Quando um processo está em vigor</span><span class="sxs-lookup"><span data-stu-id="d291c-130">When a process is in place</span></span> | <span data-ttu-id="d291c-131">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-131">**Yes**</span></span>                             |                                              |
| <span data-ttu-id="d291c-132">R-2010</span><span class="sxs-lookup"><span data-stu-id="d291c-132">R-2010</span></span>    | <span data-ttu-id="d291c-133">Serviços adquiridos</span><span class="sxs-lookup"><span data-stu-id="d291c-133">Acquired services</span></span>                                                 | <span data-ttu-id="d291c-134">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-134">Periodic event</span></span>             | <span data-ttu-id="d291c-135">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-135">**Yes**</span></span>                             | <span data-ttu-id="d291c-136">Sem suporte para estabelecimentos fiscais compradores como construções civis.</span><span class="sxs-lookup"><span data-stu-id="d291c-136">No support for acquirer fiscal establishments as civil constructions.</span></span> <span data-ttu-id="d291c-137">(As construções civis exigem um CNO em vez de um CNPJ.)</span><span class="sxs-lookup"><span data-stu-id="d291c-137">(Civil constructions require a CNO instead of a CNPJ.)</span></span>                                                |
| <span data-ttu-id="d291c-138">R-2020</span><span class="sxs-lookup"><span data-stu-id="d291c-138">R-2020</span></span>    | <span data-ttu-id="d291c-139">Serviços fornecidos</span><span class="sxs-lookup"><span data-stu-id="d291c-139">Provided services</span></span>                                                 | <span data-ttu-id="d291c-140">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-140">Periodic event</span></span>             | <span data-ttu-id="d291c-141">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-141">**Yes**</span></span>                             | <span data-ttu-id="d291c-142">Sem suporte para tomadores de serviço (clientes) como construções civis.</span><span class="sxs-lookup"><span data-stu-id="d291c-142">No support for service takers (customers) as civil constructions.</span></span> <span data-ttu-id="d291c-143">(As construções civis exigem um CNO em vez de um CNPJ.)</span><span class="sxs-lookup"><span data-stu-id="d291c-143">(Civil constructions require a CNO instead of a CNPJ.)</span></span>                                                    |
| <span data-ttu-id="d291c-144">R-2030</span><span class="sxs-lookup"><span data-stu-id="d291c-144">R-2030</span></span>    | <span data-ttu-id="d291c-145">Valores recebidos por associações esportivas</span><span class="sxs-lookup"><span data-stu-id="d291c-145">Amounts received by sport associations</span></span>                            | <span data-ttu-id="d291c-146">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-146">Periodic event</span></span>             | <span data-ttu-id="d291c-147">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-147">**No**</span></span>                              |                                              |
| <span data-ttu-id="d291c-148">R-2040</span><span class="sxs-lookup"><span data-stu-id="d291c-148">R-2040</span></span>    | <span data-ttu-id="d291c-149">Valores pagos a associações esportivas</span><span class="sxs-lookup"><span data-stu-id="d291c-149">Amounts paid to sport associations</span></span>                                | <span data-ttu-id="d291c-150">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-150">Periodic event</span></span>             | <span data-ttu-id="d291c-151">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-151">**No**</span></span>                              |                                              |
| <span data-ttu-id="d291c-152">R-2050</span><span class="sxs-lookup"><span data-stu-id="d291c-152">R-2050</span></span>    | <span data-ttu-id="d291c-153">Comércio da produção rural por entidades legais rurais ou pelo agronegócio</span><span class="sxs-lookup"><span data-stu-id="d291c-153">Trade of rural production by rural legal entities or agribusiness</span></span> | <span data-ttu-id="d291c-154">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-154">Periodic event</span></span>             | <span data-ttu-id="d291c-155">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-155">**No**</span></span>                              |                                               |
| <span data-ttu-id="d291c-156">R-2060</span><span class="sxs-lookup"><span data-stu-id="d291c-156">R-2060</span></span>    | <span data-ttu-id="d291c-157">Apuração do INSS-CPRB</span><span class="sxs-lookup"><span data-stu-id="d291c-157">INSS-CPRB assessment</span></span>                                              | <span data-ttu-id="d291c-158">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-158">Periodic event</span></span>             | <span data-ttu-id="d291c-159">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-159">**Yes**</span></span>                             | <span data-ttu-id="d291c-160">Sem suporte para apuração do imposto CPRB das Operações de varejo.</span><span class="sxs-lookup"><span data-stu-id="d291c-160">No support for CPRB tax assessment from Retail operations.</span></span>  |
| <span data-ttu-id="d291c-161">R-2070</span><span class="sxs-lookup"><span data-stu-id="d291c-161">R-2070</span></span>    | <span data-ttu-id="d291c-162">Retenção em pagamentos (IR, CSLL, PIS, COFINS)</span><span class="sxs-lookup"><span data-stu-id="d291c-162">Withholding on payments (IR, CSLL, PIS, COFINS)</span></span>                   | <span data-ttu-id="d291c-163">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-163">Periodic event</span></span>             | <span data-ttu-id="d291c-164">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-164">**No**</span></span>                              | <span data-ttu-id="d291c-165">O suporte será incluído como um recurso separado na próxima versão.</span><span class="sxs-lookup"><span data-stu-id="d291c-165">Support will be included as a separate feature in the next release.</span></span> <span data-ttu-id="d291c-166">Para obter mais informações, consulte **Sped REINF - evento R-2070** no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="d291c-166">For more information, see **Sped REINF - event R-2070** in Microsoft Dynamics Lifecycle Services (LCS).</span></span> |
| <span data-ttu-id="d291c-167">R-2098</span><span class="sxs-lookup"><span data-stu-id="d291c-167">R-2098</span></span>    | <span data-ttu-id="d291c-168">Reabertura de atividades periódicas</span><span class="sxs-lookup"><span data-stu-id="d291c-168">Reopening of periodic</span></span>                                             | <span data-ttu-id="d291c-169">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-169">Periodic event</span></span>             | <span data-ttu-id="d291c-170">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-170">**Yes**</span></span>                             |                                                |
| <span data-ttu-id="d291c-171">R-2099</span><span class="sxs-lookup"><span data-stu-id="d291c-171">R-2099</span></span>    | <span data-ttu-id="d291c-172">Fechamento</span><span class="sxs-lookup"><span data-stu-id="d291c-172">Closing</span></span>                                                           | <span data-ttu-id="d291c-173">Evento periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-173">Periodic event</span></span>             | <span data-ttu-id="d291c-174">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-174">**Yes**</span></span>                             |                                              |
| <span data-ttu-id="d291c-175">R-3010</span><span class="sxs-lookup"><span data-stu-id="d291c-175">R-3010</span></span>    | <span data-ttu-id="d291c-176">Receita de espetáculo de esporte</span><span class="sxs-lookup"><span data-stu-id="d291c-176">Sport spectacle revenue</span></span>                                           | <span data-ttu-id="d291c-177">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-177">Non-periodic event</span></span>         | <span data-ttu-id="d291c-178">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-178">**No**</span></span>                              |                                                |
| <span data-ttu-id="d291c-179">R-5001</span><span class="sxs-lookup"><span data-stu-id="d291c-179">R-5001</span></span>    | <span data-ttu-id="d291c-180">Base de cálculo de impostos consolidada por contribuinte</span><span class="sxs-lookup"><span data-stu-id="d291c-180">Consolidated tax calculation basis by taxpayer</span></span>                    | <span data-ttu-id="d291c-181">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-181">Non-periodic event</span></span>         | <span data-ttu-id="d291c-182">**Não**</span><span class="sxs-lookup"><span data-stu-id="d291c-182">**No**</span></span>                              |                                               
| <span data-ttu-id="d291c-183">R-5011</span><span class="sxs-lookup"><span data-stu-id="d291c-183">R-5011</span></span>    | <span data-ttu-id="d291c-184">Base consolidada e valor do imposto</span><span class="sxs-lookup"><span data-stu-id="d291c-184">Consolidated base and tax amount</span></span>                                  | <span data-ttu-id="d291c-185">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-185">Non-periodic event</span></span>         | <span data-ttu-id="d291c-186">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-186">**Yes**</span></span>                             | <span data-ttu-id="d291c-187">Este evento é usado para consultar o status do evento de fechamento R-2099.</span><span class="sxs-lookup"><span data-stu-id="d291c-187">This event is used to inquire about the status of closing event R-2099.</span></span> |
| <span data-ttu-id="d291c-188">R-9000</span><span class="sxs-lookup"><span data-stu-id="d291c-188">R-9000</span></span>    | <span data-ttu-id="d291c-189">Exclusão </span><span class="sxs-lookup"><span data-stu-id="d291c-189">Deletion</span></span>                                                          | <span data-ttu-id="d291c-190">Evento não periódico</span><span class="sxs-lookup"><span data-stu-id="d291c-190">Non-periodic event</span></span>         | <span data-ttu-id="d291c-191">**Sim**</span><span class="sxs-lookup"><span data-stu-id="d291c-191">**Yes**</span></span>                             |                                                |

-   <span data-ttu-id="d291c-192">Somente os contribuintes em conformidade com o SPED-ECD têm suporte.</span><span class="sxs-lookup"><span data-stu-id="d291c-192">Only taxpayers that comply with SPED-ECD are supported.</span></span>

-   <span data-ttu-id="d291c-193">Sem suporte para contribuintes como departamentos públicos.</span><span class="sxs-lookup"><span data-stu-id="d291c-193">No support for taxpayers as public departments.</span></span>

-   <span data-ttu-id="d291c-194">Sem suporte para serviços fornecidos em projetos de construções civis.</span><span class="sxs-lookup"><span data-stu-id="d291c-194">No support for services that are provided on civil constructions projects.</span></span>

-   <span data-ttu-id="d291c-195">Sem suporte para tomadores de serviço em projetos de construções civis.</span><span class="sxs-lookup"><span data-stu-id="d291c-195">No support for service takers on civil constructions projects.</span></span>

-   <span data-ttu-id="d291c-196">Escrituração manual do pagamento para liquidação do valor de CPRB devido.</span><span class="sxs-lookup"><span data-stu-id="d291c-196">Manual bookkeeping of the payment for settlement of the CPRB amount that is due.</span></span>

-   <span data-ttu-id="d291c-197">O pagamento do valor de CPRB devido está fora do escopo.</span><span class="sxs-lookup"><span data-stu-id="d291c-197">Payment of the CPRB amount that is due are out of scope.</span></span>

<span data-ttu-id="d291c-198">**Configuração do SPED-Reinf**</span><span class="sxs-lookup"><span data-stu-id="d291c-198">**SPED-Reinf setup**</span></span>

<span data-ttu-id="d291c-199">Esta seção descreve a configuração necessária para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d291c-199">This section describes the configuration that is required for Finance and Operations.</span></span>

### <a name="set-up-electronic-messages-functionality"></a><span data-ttu-id="d291c-200">**Configurar a funcionalidade Mensagens eletrônicas**</span><span class="sxs-lookup"><span data-stu-id="d291c-200">**Set up Electronic messages functionality**</span></span>

<span data-ttu-id="d291c-201">A funcionalidade Mensagens eletrônicas é nova no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d291c-201">Electronic messages functionality is new in Finance and Operations.</span></span> <span data-ttu-id="d291c-202">Ela permite manter e acompanhar vários processos para mensagens eletrônicas quando há uma troca de informações entre o Finance and Operations e os serviços Web da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-202">It lets you maintain and track various processes for electronic messages when there is an exchange of information between Finance and Operations and tax authority web services.</span></span>

<span data-ttu-id="d291c-203">Antes de entregar eventos do SPED-Reinf ao site do governo, use a configuração predefinida que a Microsoft preparou para atender aos requisitos do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="d291c-203">Before you issue SPED-Reinf events to government website, use the predefined configuration that Microsoft has prepared to meet SPED-Reinf requirements.</span></span> <span data-ttu-id="d291c-204">Essa configuração é fornecida como uma entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="d291c-204">This configuration is delivered as a data entity.</span></span> <span data-ttu-id="d291c-205">Depois de importada para o Finance and Operations, os usuários poderão gerar, validar e entregar todos os eventos descritos no escopo do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="d291c-205">After it's imported into Finance and Operations, users will able to generate, validate, and deliver all events that are described in the SPED-Reinf scope.</span></span>

#### <a name="import-the-configuration-from-the-data-entity"></a><span data-ttu-id="d291c-206">**Importar a configuração da entidade de dados**</span><span class="sxs-lookup"><span data-stu-id="d291c-206">**Import the configuration from the data entity**</span></span>

<span data-ttu-id="d291c-207">Para configurar a funcionalidade Mensagens eletrônicas para comunicações de eventos do SPED-Reinf, use a configuração predefinida disponível no LCS.</span><span class="sxs-lookup"><span data-stu-id="d291c-207">To set up Electronic messages functionality for SPED-Reinf event communications, use the predefined configuration that is available in LCS.</span></span>

1.  <span data-ttu-id="d291c-208">Ir para http://lcs.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="d291c-208">Go to http://lcs.dynamics.com.</span></span>

2.  <span data-ttu-id="d291c-209">Entre.</span><span class="sxs-lookup"><span data-stu-id="d291c-209">Sign in.</span></span>

3.  <span data-ttu-id="d291c-210">Selecione **Biblioteca de ativos compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="d291c-210">Select **Shared asset library**.</span></span>

4.  <span data-ttu-id="d291c-211">Na guia **Pacote de dados**, selecione as entidades de dados de comunicações de eventos do SPED Reinf e salve o arquivo no local onde as entidades de dados devem ser armazenadas.</span><span class="sxs-lookup"><span data-stu-id="d291c-211">On the **Data package** tab, select the SPED Reinf events communications data entities, and save the file in the location where data entities should be stored.</span></span>

5.  <span data-ttu-id="d291c-212">Entre no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d291c-212">Sign in to Finance and Operations.</span></span>

6.  <span data-ttu-id="d291c-213">Vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Importar**.</span><span class="sxs-lookup"><span data-stu-id="d291c-213">Go to **Workspaces \> Data management**, and then select the **Import** tile.</span></span>

7.  <span data-ttu-id="d291c-214">Insira uma descrição e um nome para identificar o trabalho, como **SpedReinf**.</span><span class="sxs-lookup"><span data-stu-id="d291c-214">Enter a description and a name to identify the job, such as **SpedReinf**.</span></span>

8.  <span data-ttu-id="d291c-215">No campo **Formato de dados de origem**, selecione **Pacote**.</span><span class="sxs-lookup"><span data-stu-id="d291c-215">In the **Source data format** field, select **Package**.</span></span>

9.  <span data-ttu-id="d291c-216">Selecione **Carregar** e, em seguida, selecione o arquivo que você salvou do LCS (**SPEDReinf_EMSettings.zip**).</span><span class="sxs-lookup"><span data-stu-id="d291c-216">Select **Upload**, and then select the file that you saved from LCS (**SPEDReinf_EMSettings.zip**).</span></span>

10. <span data-ttu-id="d291c-217">Selecione **Salvar** e aguarde até que todas as entidades de dados sejam exibidas na página.</span><span class="sxs-lookup"><span data-stu-id="d291c-217">Select **Save** and wait until all data entities are shown on the page.</span></span>

11. <span data-ttu-id="d291c-218">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="d291c-218">Select **Import**.</span></span>

>   <span data-ttu-id="d291c-219">Você receberá uma notificação sobre o processo de importação.</span><span class="sxs-lookup"><span data-stu-id="d291c-219">You receive a notification about the import process.</span></span> <span data-ttu-id="d291c-220">Também é possível atualizar a página manualmente para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="d291c-220">You can also manually refresh the page to see the progress of the import process.</span></span> <span data-ttu-id="d291c-221">Quando o processo for concluído, você poderá visualizar a página **Resumo de execução**.</span><span class="sxs-lookup"><span data-stu-id="d291c-221">When the process is completed, you can view the **Execution summary** page.</span></span>

![Página Resumo de execução](media/bra-execution-summary-page.png)

#### <a name="structure-of-electronic-messages"></a><span data-ttu-id="d291c-223">**Estrutura de mensagens eletrônicas**</span><span class="sxs-lookup"><span data-stu-id="d291c-223">**Structure of electronic messages**</span></span>

<span data-ttu-id="d291c-224">Cada evento criado, entregue e recebido é representado por uma mensagem e um item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="d291c-224">Every event that is created, delivered, and received is represented by a message and a message item.</span></span>

![Electronic-messages-structure](media/bra-electronic-messages-structure.png)

<span data-ttu-id="d291c-226">O item de mensagem é representado pela mensagem de evento XML e também inclui as seguintes informações adicionais que são armazenadas na mensagem ou atualizadas no Microsoft Dynamics:</span><span class="sxs-lookup"><span data-stu-id="d291c-226">The message item is represented by the XML event message, and it also includes the following additional information that is stored in the message or updated in Microsoft Dynamics:</span></span>

-   <span data-ttu-id="d291c-227">O CNPJ do estabelecimento fiscal (número completo)</span><span class="sxs-lookup"><span data-stu-id="d291c-227">The CNPJ of the fiscal establishment (full number)</span></span>

-   <span data-ttu-id="d291c-228">O CNPJ raiz</span><span class="sxs-lookup"><span data-stu-id="d291c-228">The root CNPJ</span></span>

-   <span data-ttu-id="d291c-229">O período de escrituração</span><span class="sxs-lookup"><span data-stu-id="d291c-229">The booking period</span></span>

-   <span data-ttu-id="d291c-230">A data inicial do período para o qual a mensagem é válida</span><span class="sxs-lookup"><span data-stu-id="d291c-230">The start date of the period that the message is valid for</span></span>

-   <span data-ttu-id="d291c-231">O número do protocolo de recebimento</span><span class="sxs-lookup"><span data-stu-id="d291c-231">The receipt protocol number</span></span>

-   <span data-ttu-id="d291c-232">Um valor que indica se a mensagem está registrada no Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="d291c-232">A value that indicates whether the message is registered in Microsoft Dynamics</span></span>

<span data-ttu-id="d291c-233">Você pode encontrar essa configuração em **Imposto \> Configuração \> Mensagens eletrônicas \> Campos adicionais**.</span><span class="sxs-lookup"><span data-stu-id="d291c-233">You can find this configuration at **Tax \> Setup \> Electronic messages \> Additional fields**.</span></span>

![Electronic-messages-additional-fields](media/bra-electronic-messaging-additional-fields.png)

> [!NOTE]
> <span data-ttu-id="d291c-235">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="d291c-235">Don't remove this configuration.</span></span> <span data-ttu-id="d291c-236">Essa configuração está incluída no pacote.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-236">This configuration is included in the package.\*</span></span>

<span data-ttu-id="d291c-237">Os tipos de item de mensagem são classificados pelo tipo de evento em **Imposto \> Configuração \> Mensagens eletrônicas \> Tipos de item de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="d291c-237">The message item types are classified by the type of event at **Tax \> Setup \> Electronic messages \> Message item types**.</span></span>

![Message-types](media/bra-message-types.png)

> [!NOTE]
> <span data-ttu-id="d291c-239">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="d291c-239">Don't remove this configuration.</span></span> <span data-ttu-id="d291c-240">A configuração desses tipos está incluída no pacote.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-240">These types configuration are included in the package.\*</span></span>

<span data-ttu-id="d291c-241">Vá para **Imposto \> Configuração \> Parâmetros \> Parâmetros da contabilidade** e, em seguida, na guia **Sequências numéricas**, selecione **Mensagem** e **Item de mensagem** para configurar a sequência numérica para itens de mensagem.</span><span class="sxs-lookup"><span data-stu-id="d291c-241">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Number sequences** tab, select **Message** and **Message item** to set up the sequence number for message items.</span></span>

![Electronic-messages-number-sequences](media/bra-electronic-messages-number-sequences.png)

> [!NOTE]
> <span data-ttu-id="d291c-243">A sequência numérica deve ser definida como não contínua.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-243">The number sequence must be defined as non-continuous.\*</span></span>

#### <a name="certificates"></a><span data-ttu-id="d291c-244">**Certificados**</span><span class="sxs-lookup"><span data-stu-id="d291c-244">**Certificates**</span></span>

<span data-ttu-id="d291c-245">Certificados confiáveis devem ser configurados e usados pelo Microsoft Dynamics, pois o SPED-Reinf deve ser sempre assinado por um certificado e-CNPJ autorizado pela entidade ICP-Brasil, independentemente de quaisquer outras assinaturas.</span><span class="sxs-lookup"><span data-stu-id="d291c-245">Trusted certificates must be configured and used by Microsoft Dynamics, because the SPED-Reinf should always be signed by an e-CNPJ certificate that is authorized by the ICP-Brazil entity, regardless of any other signatures.</span></span> <span data-ttu-id="d291c-246">Esse certificado e-CNPJ deve corresponder aos oito primeiros dígitos do CNPJ do estabelecimento fiscal matriz, pois o relatório é enviado por esse estabelecimento e pelos estabelecimentos fiscais relacionados.</span><span class="sxs-lookup"><span data-stu-id="d291c-246">This e-CNPJ certificate should match the first eight digits of the root fiscal establishment's CNPJ, because the report is issued by the root fiscal establishment and the related fiscal establishments.</span></span>

<span data-ttu-id="d291c-247">No Finance and Operations, você deve registrar o certificado do Key Vault no Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="d291c-247">In Finance and Operations, you must register the Key Vault certificate in Microsoft Azure.</span></span>

<span data-ttu-id="d291c-248">Para obter informações sobre como configurar um cliente do Key Vault, consulte [Configuração do Cliente do Azure Key Vault](https://support.microsoft.com/en-us/help/4040305).</span><span class="sxs-lookup"><span data-stu-id="d291c-248">For information about how to set up a Key Vault client, see [Setting up Azure Key Vault Client](https://support.microsoft.com/en-us/help/4040305).</span></span>

1.  <span data-ttu-id="d291c-249">Vá para **Administração do sistema \> Configuração \> Parâmetros do Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="d291c-249">Go to **System administration \> Setup \> Key Vault parameters**.</span></span>

2.  <span data-ttu-id="d291c-250">Digite as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d291c-250">Enter the following information:</span></span>

-   <span data-ttu-id="d291c-251">URL do Key Vault</span><span class="sxs-lookup"><span data-stu-id="d291c-251">Key Vault URL</span></span>

-   <span data-ttu-id="d291c-252">Cliente do Key Vault</span><span class="sxs-lookup"><span data-stu-id="d291c-252">Key Vault client</span></span>

-   <span data-ttu-id="d291c-253">Chave secreta do Key Vault</span><span class="sxs-lookup"><span data-stu-id="d291c-253">Key Vault secret key</span></span>

-   <span data-ttu-id="d291c-254">ID secreta do Key Vault</span><span class="sxs-lookup"><span data-stu-id="d291c-254">Key vault secret ID</span></span>

<span data-ttu-id="d291c-255">Após o registro, associe o certificado nos parâmetros de configuração para a ação **Geração de relatório**, conforme descrito na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="d291c-255">After registration, associate the certificate in the setup parameters for the **Report generation** action, as described in the next section.</span></span>

#### <a name="setup-parameters"></a><span data-ttu-id="d291c-256">**Parâmetros de configuração**</span><span class="sxs-lookup"><span data-stu-id="d291c-256">**Setup parameters**</span></span> 

<span data-ttu-id="d291c-257">Sempre que uma mensagem é criada, preparada, validada, entregue ou recebida, a ação relacionada deve ser identificada por meio de uma classe X++ em **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de classe executável**.</span><span class="sxs-lookup"><span data-stu-id="d291c-257">Every time that a message is created, prepared, validated, delivered, or received, the related action must be identified through a X++ class at **Tax \> Setup \> Electronic messages \> Executable class settings**.</span></span>

-   <span data-ttu-id="d291c-258">**Preparação dos eventos –** Esta ação é usada para criar e preparar a mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="d291c-258">**Preparation items (Preparacao dos eventos) –** This action is used to create and prepare the XML message.</span></span> <span data-ttu-id="d291c-259">Ela solicita parâmetros adicionais, como **Data de escrituração**, **CNPJ** e **CNPJ raiz**, pois os eventos são gerados com base nessas informações.</span><span class="sxs-lookup"><span data-stu-id="d291c-259">It requests additional parameters, such as **Booking date**, **CNPJ**, and **CNPJ root**, because the events are generated based on this information.</span></span>

![Preparation-items](media/bra-preparation-items.png)

-   <span data-ttu-id="d291c-261">**Processo de resposta** – Esta ação é usada para atualizar a mensagem entregue quando ela for aprovada pelo governo usando um número de protocolo.</span><span class="sxs-lookup"><span data-stu-id="d291c-261">**Process response (Processo de reposta)** – This action is used to update the delivered message when it's approved by the government by using a protocol number.</span></span> <span data-ttu-id="d291c-262">Além disso, a mensagem é atualizada conforme registrado no site do governo.</span><span class="sxs-lookup"><span data-stu-id="d291c-262">Additionally, the message is updated as registered on the     government website.</span></span>

![Preparation-items-process-response](media/bra-preparation-items-process-response.png)

-   <span data-ttu-id="d291c-264">**Geração de relatório** – Esta ação é usada para enviar e receber o item de mensagem.</span><span class="sxs-lookup"><span data-stu-id="d291c-264">**Report generation (Geracao de relatório)** – This action is used to send and receive the message item.</span></span>

![Generate-reports-parameters](media/bra-generate-reports-parameters.png)

> [!NOTE]
> <span data-ttu-id="d291c-266">Não remova esta configuração.</span><span class="sxs-lookup"><span data-stu-id="d291c-266">Don't remove this configuration.</span></span> <span data-ttu-id="d291c-267">Essa configuração está incluída no pacote.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-267">This configuration is included in the package.\*</span></span>

#### <a name="specific-actions"></a><span data-ttu-id="d291c-268">**Ações específicas**</span><span class="sxs-lookup"><span data-stu-id="d291c-268">**Specific actions**</span></span>

<span data-ttu-id="d291c-269">Antes que uma mensagem seja entregue, você deve configurar a validação do esquema XML para evitar rejeições do site do governo.</span><span class="sxs-lookup"><span data-stu-id="d291c-269">Before a message is delivered, you must set up XML schema validation to prevent rejections from the government website.</span></span>

<span data-ttu-id="d291c-270">Vá para **Administração da organização \> Gerenciamento de documentos \> Parâmetros de gerenciamento de documentos** e habilite arquivos XSD adicionando **XSD** como um novo tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d291c-270">Go to **Organization administration \> Document management \> Document management parameters**, and enable XSD files by adding **XSD** as a new file type.</span></span>

![Document-management-parameters](media/bra-document-management-parameters.png)

<span data-ttu-id="d291c-272">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens** e selecione **Novo \> Arquivo** para anexar os esquemas (arquivos .xsd) para as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="d291c-272">Go to **Tax \> Setup \> Electronic messages \> Message processing actions**, and select **New \> File** to attach the schemas (.xsd files) for the following actions:</span></span>

-   <span data-ttu-id="d291c-273">Validar</span><span class="sxs-lookup"><span data-stu-id="d291c-273">Verify (Validar)</span></span>

-   <span data-ttu-id="d291c-274">Re-Validar</span><span class="sxs-lookup"><span data-stu-id="d291c-274">Re-Verify (Re-Validar)</span></span>

-   <span data-ttu-id="d291c-275">Exclusão-Validar</span><span class="sxs-lookup"><span data-stu-id="d291c-275">Cancel-Verify (Exclusão-Validar)</span></span>

<span data-ttu-id="d291c-276">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens**, selecione a ação **Preencher** (**Incluir**) e, em seguida, no campo **Ação de preencher registros**, selecione **Registrar transações**.</span><span class="sxs-lookup"><span data-stu-id="d291c-276">Go to **Tax \> Setup \> Electronic messages \> Message processing actions**, select the **Populate** (**Incluir**) action, and then, in the **Populate records action** field, select **Registrar transacões**.</span></span>

![Message-Processing-actions](media/bra-message-processing-actions.png)

<span data-ttu-id="d291c-278">Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Configurações de serviço Web** e configure uma conexão de serviços Web e certificados para enviar e consultar eventos.</span><span class="sxs-lookup"><span data-stu-id="d291c-278">Go to **Tax \> Setup \> Electronic messages \> Web service settings**, and set up a web services connection and certificates for issuing and inquiring about events.</span></span>

![Webservices-settings](media/bra-web-service-settings.png)

<span data-ttu-id="d291c-280">Observação: nas configurações do **SPED Reinf assíncrono**, inclua o endereço do serviço Web para consultar o evento R-5011.</span><span class="sxs-lookup"><span data-stu-id="d291c-280">Note: In the settings for **SPED Reinf asynchronous (SPED Reinf – assíncrono)**, include the web service address for inquire event R-5011.</span></span>

### <a name="set-up-service-types"></a><span data-ttu-id="d291c-281">**Configurar tipos de serviço**</span><span class="sxs-lookup"><span data-stu-id="d291c-281">**Set up service types**</span></span>

<span data-ttu-id="d291c-282">A tabela de tipos de serviço representa a tabela 06 que as autoridades fiscais estabeleceram para classificar os serviços fornecidos, com base na atribuição de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d291c-282">The service type table represents table 06 that the tax authorities have established to classify the services that are provided, based on assignment of labor.</span></span> <span data-ttu-id="d291c-283">Uma lista detalhada de valores disponíveis está à disposição no site do SPED.</span><span class="sxs-lookup"><span data-stu-id="d291c-283">A detailed list of available values is available on the SPED website.</span></span>

1.  <span data-ttu-id="d291c-284">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Tipos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="d291c-284">Go to **Fiscal books \> Setup \> SPED Reinf \> Service types**.</span></span>

2.  <span data-ttu-id="d291c-285">Selecione **Novo**, insira um código de classificação que tenha sido estabelecido pelas autoridades fiscais e insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d291c-285">Select **New**, enter a classification code that has been established by the tax authorities, and enter a description.</span></span>

![Service-types](media/bra-service-type-setup.png)

<span data-ttu-id="d291c-287">Depois que a lista de tipos de serviço for criada, eles devem ser atribuídos a códigos de serviço.</span><span class="sxs-lookup"><span data-stu-id="d291c-287">After the list of service types is created, the service types must be assigned to service codes.</span></span> <span data-ttu-id="d291c-288">Vá para **Gerenciamento de estoque \> Configuração \> Informações fiscais \> Código de serviço** e, em seguida, para cada serviço, atribua o tipo de serviço relacionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-288">Go to **Inventory management \> Setup \> Fiscal information \> Service code**, and then, for each service, assign the related service type.</span></span>

<span data-ttu-id="d291c-289">**Configurar códigos de classificação de imposto**</span><span class="sxs-lookup"><span data-stu-id="d291c-289">**Set up tax classification codes**</span></span>

<span data-ttu-id="d291c-290">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Códigos de classificação de imposto** e insira os tipos de classificação disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d291c-290">Go to **Fiscal books \> Setup \> SPED Reinf \> Tax classification codes** and enter the available classification types.</span></span>

![Tax-classification](media/bra-tax-classification-codes.png)

<span data-ttu-id="d291c-292">Essa informação é atribuída à organização fiscal na FastTab **Geral** em **Livros fiscais \> Configuração \> Organização fiscal**.</span><span class="sxs-lookup"><span data-stu-id="d291c-292">This information is assigned to the fiscal organization on the **General** FastTab at **Fiscal books \> Setup \> Fiscal organization**.</span></span>

![Fiscal-organization](media/bra-fiscal-organization-setup.png)

### <a name="set-up-codes-explanation-suspension"></a><span data-ttu-id="d291c-294">**Configurar suspensão da explicação de códigos**</span><span class="sxs-lookup"><span data-stu-id="d291c-294">**Set up codes explanation suspension**</span></span>

<span data-ttu-id="d291c-295">Vá para **Livros fiscais \> Configuração \> SPED Reinf \> Suspensão da explicação de códigos** e configure os códigos que são usados no evento R-1070 quando a suspensão da retenção se aplica.</span><span class="sxs-lookup"><span data-stu-id="d291c-295">Go to **Fiscal books \> Setup \> SPED Reinf \> Codes explanation suspension**, and set up the codes that are used in event R-1070 when suspension of withholding applies.</span></span> <span data-ttu-id="d291c-296">Esses códigos são atribuídos em **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.</span><span class="sxs-lookup"><span data-stu-id="d291c-296">These codes are assigned at **Fiscal books \> Periodic \> SPED Reinf \> Administrative and judicial process**.</span></span>

![Explanation-codes](media/bra-codes-explanation-suspension.png)

### <a name="set-up-fiscal-books-parameters"></a><span data-ttu-id="d291c-298">**Configurar parâmetros de livros fiscais**</span><span class="sxs-lookup"><span data-stu-id="d291c-298">**Set up fiscal books parameters**</span></span>

<span data-ttu-id="d291c-299">Vá para **Livros fiscais \> Configuração \> Parâmetros de livros fiscais** e configure a sequência numérica para os eventos R-2010 e R-2020.</span><span class="sxs-lookup"><span data-stu-id="d291c-299">Go to **Fiscal books \> Setup \> Fiscal books parameters**, and set up the number sequence for events R-2010 and R-2020.</span></span>

![Fiscal-books-parameters](media/bra-sped-fiscal-books-parameters.png)

<span data-ttu-id="d291c-301">**Observação**: se as sequências numéricas não tiverem sido inicializadas durante a lista de verificação da configuração para a instalação de KB, você poderá gerá-las usando um assistente.</span><span class="sxs-lookup"><span data-stu-id="d291c-301">**Note**: If the number sequences weren't initialized during the setup checklist for KB installation, you can generate them by using a wizard.</span></span> <span data-ttu-id="d291c-302">Para iniciar o assistente, vá para **Administração da organização \> Sequências numéricas \> Sequências numéricas** e selecione **Gerar**.</span><span class="sxs-lookup"><span data-stu-id="d291c-302">To start the wizard, go to **Organization administration \> Number sequences \> Number sequences**, and select **Generate**.</span></span> <span data-ttu-id="d291c-303">Assim você poderá configurar a sequência numérica relacionada.</span><span class="sxs-lookup"><span data-stu-id="d291c-303">You will then be able to configure the related number sequence.</span></span>

-   <span data-ttu-id="d291c-304">**Área:** Livros fiscais</span><span class="sxs-lookup"><span data-stu-id="d291c-304">**Area:** Fiscal books</span></span>

-   <span data-ttu-id="d291c-305">**Referência:** ID de evento do SPED-Reinf</span><span class="sxs-lookup"><span data-stu-id="d291c-305">**Reference:** SPED-Reinf event ID</span></span>

<span data-ttu-id="d291c-306">**Eventos do SPED-Reinf**</span><span class="sxs-lookup"><span data-stu-id="d291c-306">**SPED-Reinf events**</span></span>

<span data-ttu-id="d291c-307">Todas as informações que o SPED-Reinf fornece sobre impostos e contribuições em um determinado período de apuração são conhecidas como uma *movimentação*.</span><span class="sxs-lookup"><span data-stu-id="d291c-307">All the information that the SPED-Reinf provides about taxes and contributions in a given assessment period is known as a *movement*.</span></span> <span data-ttu-id="d291c-308">Portanto, cada movimentação pode conter um ou mais eventos.</span><span class="sxs-lookup"><span data-stu-id="d291c-308">Therefore, every movement can contain one or more events.</span></span>

<span data-ttu-id="d291c-309">Para encerrar a transmissão de eventos periódicos para uma determinada movimentação em um período de apuração específico, você deve enviar o evento R-2099 "Fechamento de evento periódico”.</span><span class="sxs-lookup"><span data-stu-id="d291c-309">To close the transmission of periodic events for a given movement in a specific assessment period, you must send event R-2099, "Closure of periodic event."</span></span> <span data-ttu-id="d291c-310">Depois que o evento de fechamento é processado e validado, ele é aceito.</span><span class="sxs-lookup"><span data-stu-id="d291c-310">After the closure event is processed and validated, it's accepted.</span></span> <span data-ttu-id="d291c-311">A aceitação do evento de fechamento finaliza a soma das bases de cálculo incluídas na movimentação.</span><span class="sxs-lookup"><span data-stu-id="d291c-311">Acceptance of the closure event finalizes the sum of the calculation bases that are included in the movement.</span></span> <span data-ttu-id="d291c-312">O crédito de imposto poderá então ser calculado e o DARF poderá ser gerado para coletar os impostos e as contribuições devidos.</span><span class="sxs-lookup"><span data-stu-id="d291c-312">The tax credit can then be calculated, and the DARF can be generated to collect taxes and contributions that are owed.</span></span>

<span data-ttu-id="d291c-313">Se for necessário enviar uma correção ou novos eventos para uma movimentação que já foi fechada, você deverá reabri-la enviando o evento R-2098, “Reabertura de evento periódico”.</span><span class="sxs-lookup"><span data-stu-id="d291c-313">If a correction or new events must be sent for a movement that has already been closed, you must reopen the movement by sending event R-2098, "Reopening of periodic event."</span></span> <span data-ttu-id="d291c-314">Após a reabertura de uma movimentação, você deve enviar um novo evento de fechamento.</span><span class="sxs-lookup"><span data-stu-id="d291c-314">After a movement is reopened, you must send a new closing event.</span></span>

<span data-ttu-id="d291c-315">**Quando não há movimentações no período de apuração**</span><span class="sxs-lookup"><span data-stu-id="d291c-315">**When there is no movement in the assessment period**</span></span>

<span data-ttu-id="d291c-316">A situação “sem movimentação” para um contribuinte ocorre somente quando não há informações a serem enviadas ao grupo de eventos periódicos do evento R-2010 ao evento R-2070.</span><span class="sxs-lookup"><span data-stu-id="d291c-316">The "no movement" situation for a taxpayer occurs only when there is no information to send to the periodic event group from event R-2010 to event R-2070.</span></span> <span data-ttu-id="d291c-317">Nesse caso, o evento R-2099, "Fechamento de evento periódico”, que fornece as informações para o fechamento, declara a não ocorrência de transações no primeiro período de apuração do ano em que essa situação ocorre.</span><span class="sxs-lookup"><span data-stu-id="d291c-317">In this case, event R-2099, "Closure of periodic event," which provides the information for closure, declares the non-occurrence of transactions in the first assessment period of the year that this situation occurs in.</span></span> <span data-ttu-id="d291c-318">Se a situação “sem movimentação” persistir nos anos seguintes, o contribuinte deverá repetir esse procedimento no mês de janeiro de cada ano.</span><span class="sxs-lookup"><span data-stu-id="d291c-318">If the "no movement" situation persists in the following years, the taxpayer must repeat this procedure in January of each year.</span></span>

<span data-ttu-id="d291c-319">**Protocolo de recebimento**</span><span class="sxs-lookup"><span data-stu-id="d291c-319">**Receiving protocol**</span></span>

<span data-ttu-id="d291c-320">O protocolo de recebimento confirma que as informações enviadas foram validadas e entregues com êxito ao ambiente do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="d291c-320">The receiving protocol confirms that the information that was sent was successfully delivered and validated to the SPED-Reinf environment.</span></span> <span data-ttu-id="d291c-321">O protocolo de recebimento é o ponto inicial para corrigir ou excluir um determinado evento, se a correção e a exclusão forem permitidas.</span><span class="sxs-lookup"><span data-stu-id="d291c-321">The receiving protocol is the starting point for correcting or deleting a given event, if correction and deletion are allowed.</span></span>

<span data-ttu-id="d291c-322">Cada evento transmitido tem um protocolo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="d291c-322">Every event that is transmitted has a receiving protocol.</span></span> <span data-ttu-id="d291c-323">Para corrigir um evento, é necessário inserir o número do protocolo de recebimento dele.</span><span class="sxs-lookup"><span data-stu-id="d291c-323">To correct an event, you must enter the number of the event's receiving protocol.</span></span>

<span data-ttu-id="d291c-324">A quantidade de tempo que os protocolos de recebimento são mantidos no banco de dados do governo não é definida.</span><span class="sxs-lookup"><span data-stu-id="d291c-324">The amount of time that receiving protocols are kept in the government database isn't defined.</span></span> <span data-ttu-id="d291c-325">Portanto, como precaução, é importante que o contribuinte os guarde, pois eles comprovam que a obrigação tributária acessória foi entregue e cumprida.</span><span class="sxs-lookup"><span data-stu-id="d291c-325">Therefore, as a precaution, it's important that the taxpayer retain them, because they provide proof that the ancillary tax obligation has been delivered and met.</span></span>

<span data-ttu-id="d291c-326">Observação: o protocolo de entrega consiste em informações transitórias que comprovam que o evento foi transmitido e que a validação apropriada será processada.</span><span class="sxs-lookup"><span data-stu-id="d291c-326">Note: The delivery protocol is transient information that provides proof that the event has been transmitted, and that the appropriate validation will be processed.</span></span> <span data-ttu-id="d291c-327">Ele não demonstra conformidade com a obrigação acessória.</span><span class="sxs-lookup"><span data-stu-id="d291c-327">It doesn't demonstrate compliance with the ancillary obligation.</span></span>

<span data-ttu-id="d291c-328">**Aditamento e correção**</span><span class="sxs-lookup"><span data-stu-id="d291c-328">**Amendment and correction**</span></span>

<span data-ttu-id="d291c-329">O procedimento para aditar as informações enviadas ao SPED-Reinf ocorre somente nos eventos R-1000, “Informações do contribuinte” e R-1070, "Tabela legal e administrativa".</span><span class="sxs-lookup"><span data-stu-id="d291c-329">The procedure for amending information that is sent to the SPED-Reinf occurs only in events R-1000, "Taxpayer information," and R-1070, "Administrative and lawsuits table."</span></span>

<span data-ttu-id="d291c-330">Em todos os outros casos em que as informações enviadas devem ser corrigidas, o procedimento para a correção ou exclusão deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="d291c-330">In all other cases where the information that was sent must be amended, the procedure for correction or deletion must be used.</span></span>

<span data-ttu-id="d291c-331">**Eventos de exclusão**</span><span class="sxs-lookup"><span data-stu-id="d291c-331">**Deletion events**</span></span>

<span data-ttu-id="d291c-332">Para excluir eventos que foram aprovados pela autoridade fiscal, mas entregues incorretamente, você deve enviar o evento R-9000, "Evento de exclusão".</span><span class="sxs-lookup"><span data-stu-id="d291c-332">To exclude events that were approved by the tax authority but incorrectly delivered, you must send event R-9000, "Deletion event."</span></span> <span data-ttu-id="d291c-333">Nesse evento, é necessário identificar o evento a ser excluído preenchendo a marca **Tipo de evento** (**TpEvento**).</span><span class="sxs-lookup"><span data-stu-id="d291c-333">In this event, you must identify the event to delete by filling in the **Event Type** tag (**TpEvento**).</span></span> <span data-ttu-id="d291c-334">Você também deve preencher o **Número de recebimento do evento** (**NRRECEVT**), que especifica o número do protocolo de recebimento do arquivo que foi enviado e deve ser excluído.</span><span class="sxs-lookup"><span data-stu-id="d291c-334">You must also fill in **Event Receipt Number** (**NRRECEVT**), which specifies the receipt protocol number of the file that was sent and must be deleted.</span></span>

<span data-ttu-id="d291c-335">**Assinatura digital**</span><span class="sxs-lookup"><span data-stu-id="d291c-335">**Digital signature**</span></span>

<span data-ttu-id="d291c-336">O certificado digital usado no SPED-Reinf deve ser emitido por uma autoridade de certificação credenciada pela ICP-Brasil.</span><span class="sxs-lookup"><span data-stu-id="d291c-336">The digital certificate that is used in the SPED-Reinf must be issued by a certification authority that is accredited by ICP-Brasil.</span></span>

<span data-ttu-id="d291c-337">O certificado digital deve pertencer à série ”A”.</span><span class="sxs-lookup"><span data-stu-id="d291c-337">The digital certificate must belong to the "A" series.</span></span> <span data-ttu-id="d291c-338">Os certificados podem pertencer a duas séries: série ”A” e série “S”.</span><span class="sxs-lookup"><span data-stu-id="d291c-338">Certificates can belong to two series: the "A" series and the "S" series.</span></span> <span data-ttu-id="d291c-339">A série ”A” inclui os certificados de assinatura digital usados para confirmação de identidade na Web em emails, redes virtuais privadas (VPNs) e documentos eletrônicos, com verificação da integridade de suas informações.</span><span class="sxs-lookup"><span data-stu-id="d291c-339">The "A" series includes the digital signature certificates that are used for web identity confirmation on emails, virtual private networks (VPNs), and electronic documents, with verification of the integrity of its information.</span></span> <span data-ttu-id="d291c-340">A série “S” inclui os certificados de confidencialidade usados na codificação de documentos, bancos de dados, mensagens e outras informações eletrônicas confidenciais.</span><span class="sxs-lookup"><span data-stu-id="d291c-340">The "S" series includes the confidentiality certificates that are used in the encoding of documents, databases, messages, and other sensitive electronic information.</span></span>

<span data-ttu-id="d291c-341">O certificado digital deve ser do tipo “A1” ou “A3”.</span><span class="sxs-lookup"><span data-stu-id="d291c-341">The digital certificate must be of the "A1" or "A3" type.</span></span> <span data-ttu-id="d291c-342">Certificados digitais do tipo “A1” são armazenados no computador em que são usados.</span><span class="sxs-lookup"><span data-stu-id="d291c-342">Digital certificates of the "A1" type are stored on the computer that they are used from.</span></span> <span data-ttu-id="d291c-343">Certificados digitais do tipo “A3” são armazenados em um dispositivo portátil à prova de adulterações com um chip capaz de realizar a assinatura digital.</span><span class="sxs-lookup"><span data-stu-id="d291c-343">Digital certificates of the "A3" type are stored in a tamper-resistant portable device that contains a chip that can do the digital signing.</span></span> <span data-ttu-id="d291c-344">Exemplos desses dispositivos incluem cartões inteligentes e tokens.</span><span class="sxs-lookup"><span data-stu-id="d291c-344">Examples of these devices include smart cards and tokens.</span></span> <span data-ttu-id="d291c-345">Esses dispositivos são razoavelmente seguros porque cada operação é feita pelo chip no dispositivo e não há nenhum acesso externo à chave privada do certificado digital.</span><span class="sxs-lookup"><span data-stu-id="d291c-345">These devices are reasonably secure, because every operation is done by the chip on the device, and there is no external access to the private key of the digital certificate.</span></span>

<span data-ttu-id="d291c-346">Os certificados digitais são necessários em dois momentos:</span><span class="sxs-lookup"><span data-stu-id="d291c-346">The digital certificates are required at two moments:</span></span>

-   <span data-ttu-id="d291c-347">**Para ações de entrega**: antes da solicitação de entrega ao SPED-Reinf ser iniciada, o certificado digital do solicitante é usado para ajudar a garantir a segurança do tráfego de informações na Internet.</span><span class="sxs-lookup"><span data-stu-id="d291c-347">**For delivery actions**: Before the request for delivery to the SPED-Reinf is started, the requestor's digital certificate is used to help guarantee the safety of the information traffic on the internet.</span></span> <span data-ttu-id="d291c-348">Para que o certificado digital seja aceito como uma função de transmissor, ele deve ser do tipo e-CNPJ.</span><span class="sxs-lookup"><span data-stu-id="d291c-348">For the digital certificate to be accepted as a transmitter function, it must be of the e-CNPJ type.</span></span>

-   <span data-ttu-id="d291c-349">**Para assinatura de documentos**: os eventos podem ser gerados por qualquer estabelecimento fiscal da entidade legal ou seu proxy.</span><span class="sxs-lookup"><span data-stu-id="d291c-349">**For document signing**: The events can be generated by any fiscal establishment of the legal entity or its proxy.</span></span> <span data-ttu-id="d291c-350">No entanto, o assinante digital desses eventos deve pertencer ao estabelecimento fiscal principal (matriz), seu representante legal ou um advogado concedido por meio de proxy eletrônico e não eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d291c-350">However, the digital subscriber of those events must belong to the main fiscal establishment (headquarters), its legal representative, or an attorney that is granted by means of electronic and non-electronic proxy.</span></span>

<span data-ttu-id="d291c-351">Os certificados digitais que são usados para assinar os eventos enviados ao SPED-Reinf devem ser habilitados para a função de assinatura digital de acordo com a política de certificação.</span><span class="sxs-lookup"><span data-stu-id="d291c-351">The digital certificates that are used to sign the events that are sent to the SPED-Reinf must be enabled for the digital signature function in accordance with the certificate policy.</span></span>

<span data-ttu-id="d291c-352">Os eventos no SPED-Reinf devem ser transmitidos usando um certificado digital válido.</span><span class="sxs-lookup"><span data-stu-id="d291c-352">The events in the SPED-Reinf must be transmitted by using a valid digital certificate.</span></span> <span data-ttu-id="d291c-353">No entanto, uma exceção será feita para micro e pequenas empresas (ME e EPP) que atendam aos critérios do Simples Nacional e possuam sete funcionários ou menos.</span><span class="sxs-lookup"><span data-stu-id="d291c-353">However, an exception is made for micro and small businesses (ME and EPP) that meet the Simple Nacional criteria and have seven or fewer employees.</span></span> <span data-ttu-id="d291c-354">Essas empresas podem transmitir seus eventos usando um código de acesso.</span><span class="sxs-lookup"><span data-stu-id="d291c-354">These businesses can transmit their events by using an access code.</span></span>

### <a name="general-process"></a><span data-ttu-id="d291c-355">**Processo geral**</span><span class="sxs-lookup"><span data-stu-id="d291c-355">**General process**</span></span> 

1.  <span data-ttu-id="d291c-356">Use uma mensagem eletrônica para criar, validar e entregar o evento ou lote de eventos por meio de itens de mensagem eletrônica.</span><span class="sxs-lookup"><span data-stu-id="d291c-356">Use an electronic message to create, validate, and deliver the event or batch of events through electronic message items.</span></span>

2.  <span data-ttu-id="d291c-357">O serviço Web da autoridade fiscal recebe o lote e valida seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d291c-357">The tax authority web service receives the batch and validates its contents.</span></span>

3.  <span data-ttu-id="d291c-358">O serviço Web retorna o resultado do processamento.</span><span class="sxs-lookup"><span data-stu-id="d291c-358">The web service returns the result of processing.</span></span> <span data-ttu-id="d291c-359">Se os eventos ou o lote de eventos forem recebidos com êxito, um protocolo de recebimento será retornado.</span><span class="sxs-lookup"><span data-stu-id="d291c-359">If the events or batch of events is successfully received, a receiving protocol is returned.</span></span> <span data-ttu-id="d291c-360">Caso contrário, uma mensagem de erro será retornada.</span><span class="sxs-lookup"><span data-stu-id="d291c-360">Otherwise, an error message is returned.</span></span> <span data-ttu-id="d291c-361">Nesse caso, o contribuinte pode resolver os erros e reenviar o evento por meio de um novo lote.</span><span class="sxs-lookup"><span data-stu-id="d291c-361">In that case, the taxpayer can resolve the errors and resubmit the event through a new batch.</span></span>

![<span data-ttu-id="d291c-362">Texto alternativo gerado por máquina: Contribuinte Eventos Gera Evento XML Assina Digitalmente & 80 T rata Rsultados Lote de Ev Clialte Notificaqäo de Retomo EFD-REINF Rec.cäo e Val idacäo (Lotede Eventosi BD Controle</span><span class="sxs-lookup"><span data-stu-id="d291c-362">Machine generated alternative text: Contribuinte Eventos Gera Evento XML Assina Digitalmente & 80 T rata Rsultados Lote de Ev Clialte Notificaqäo de Retomo EFD-REINF Rec.cäo e Val idacäo (Lotede Eventosi BD Controle</span></span> ](media/bra-general-process.png)

<span data-ttu-id="d291c-363">Os eventos são transmitidos às autoridades fiscais usando a funcionalidade Mensagens eletrônicas para estabelecer um relacionamento bidirecional, automatizado e instantâneo entre o contribuinte e os serviços Web do governo.</span><span class="sxs-lookup"><span data-stu-id="d291c-363">The events are transmitted to tax authorities by using Electronic messages functionality to establish a two-way, automated, and instantaneous relationship between the government web services and the taxpayer.</span></span>

<span data-ttu-id="d291c-364">As ilustrações a seguir mostram as ações que são realizadas e os status de itens de mensagem que causam a aprovação ou rejeição de cada evento ao ser entregue pela primeira vez (Inserção), atualizado (Aditamento/Atualização) ou cancelado ou excluído (Cancelamento/Exclusão).</span><span class="sxs-lookup"><span data-stu-id="d291c-364">The following illustrations show the actions that are performed and the status of message items that causes each event to be approved or rejected when it's delivered for the first time (Insertion), updated (Amendment/Update), or canceled or deleted (Cancel/Delete).</span></span>

![Flow-actions](media/bra-flow-actions.png)

#### <a name="insertion"></a><span data-ttu-id="d291c-366">**Inserção**</span><span class="sxs-lookup"><span data-stu-id="d291c-366">**Insertion**</span></span>

<span data-ttu-id="d291c-367">Este fluxo é usado para entregar qualquer evento pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d291c-367">This flow is used to deliver any event for the first time.</span></span>
<span data-ttu-id="d291c-368">![Inserção](media/bra-insertion-flow.png)</span><span class="sxs-lookup"><span data-stu-id="d291c-368">![Insertion](media/bra-insertion-flow.png)</span></span>

#### <a name="amendmentupdate"></a><span data-ttu-id="d291c-369">**Aditamento/Atualização**</span><span class="sxs-lookup"><span data-stu-id="d291c-369">**Amendment/Update**</span></span>

![Atualização](media/bra-amendment-update-flow.png)

#### <a name="canceldelete"></a><span data-ttu-id="d291c-371">**Cancelamento/Exclusão**</span><span class="sxs-lookup"><span data-stu-id="d291c-371">**Cancel/Delete**</span></span>

![Cancelar](media/bra-cancel-delete-flow.png)

#### <a name="inquire-event-5011-from-event-r-2099"></a><span data-ttu-id="d291c-373">**Consultar evento 5011 (do evento R-2099)**</span><span class="sxs-lookup"><span data-stu-id="d291c-373">**Inquire event 5011 (from event R-2099)**</span></span>

![Inquire-event-5011](media/bra-inquire-event-5011.png)

#### <a name="manage-electronic-messages"></a><span data-ttu-id="d291c-375">**Gerenciar mensagens eletrônicas**</span><span class="sxs-lookup"><span data-stu-id="d291c-375">**Manage electronic messages**</span></span> 

<span data-ttu-id="d291c-376">Todos os eventos são gerenciados e controlados em **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.</span><span class="sxs-lookup"><span data-stu-id="d291c-376">All events are managed and controlled at **Tax \> Inquiries and reports \> Electronic messages \> Electronic message items**.</span></span>

| <span data-ttu-id="d291c-377">**Nome do campo**</span><span class="sxs-lookup"><span data-stu-id="d291c-377">**Field name**</span></span>      | <span data-ttu-id="d291c-378">**Descrição do campo**</span><span class="sxs-lookup"><span data-stu-id="d291c-378">**Field description**</span></span>                                                                                                                                         |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d291c-379">Tipo de item de mensagem</span><span class="sxs-lookup"><span data-stu-id="d291c-379">Message item type</span></span>   | <span data-ttu-id="d291c-380">O tipo de evento:</span><span class="sxs-lookup"><span data-stu-id="d291c-380">The type of event:</span></span>                                                                                                                                            |
| <span data-ttu-id="d291c-381">Status de item de mensagem</span><span class="sxs-lookup"><span data-stu-id="d291c-381">Message item status</span></span> | <span data-ttu-id="d291c-382">O status atual do evento.</span><span class="sxs-lookup"><span data-stu-id="d291c-382">The current status of the event.</span></span> <span data-ttu-id="d291c-383">Este campo é automaticamente preenchido e atualizado, com base na troca de mensagens entre a autoridade fiscal e o contribuinte.</span><span class="sxs-lookup"><span data-stu-id="d291c-383">This field is automatically filled in and updated, based on the exchange of messages between the tax authority and taxpayer.</span></span> |

-   <span data-ttu-id="d291c-384">Processo administrativo e judicial (R-1070)</span><span class="sxs-lookup"><span data-stu-id="d291c-384">Administrative and judicial process (R-1070)</span></span>

-   <span data-ttu-id="d291c-385">Serviços adquiridos (R-2010)</span><span class="sxs-lookup"><span data-stu-id="d291c-385">Acquired services (R-2010)</span></span>

-   <span data-ttu-id="d291c-386">Apuração do INSS-CPRB (R-2060)</span><span class="sxs-lookup"><span data-stu-id="d291c-386">INSS-CPRB assessment (R-2060)</span></span>

-   <span data-ttu-id="d291c-387">Serviços fornecidos (R-2020)</span><span class="sxs-lookup"><span data-stu-id="d291c-387">Provided services (R-2020)</span></span>

-   <span data-ttu-id="d291c-388">Informações do contribuinte (R-1000)</span><span class="sxs-lookup"><span data-stu-id="d291c-388">Taxpayer information (R-1000</span></span>

-   <span data-ttu-id="d291c-389">Fechamento (R-2099)</span><span class="sxs-lookup"><span data-stu-id="d291c-389">Closing (R-2099)</span></span>

-   <span data-ttu-id="d291c-390">**Criado** – O evento foi adicionado ao registro, mas ainda não foi enviado aos serviços Web.</span><span class="sxs-lookup"><span data-stu-id="d291c-390">**Created** – The event was added to the register but hasn't yet been sent to the web services.</span></span>

-   <span data-ttu-id="d291c-391">**Rejeitado** – O evento foi enviado aos serviços Web, mas foi rejeitado pelo sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-391">**Rejected** – The event was sent to the web services, but it was rejected by the tax authority system.</span></span> <span data-ttu-id="d291c-392">Um grupo de marcas específico no arquivo XML que é retornado pelo governo especifica o código de erro e fornece uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d291c-392">A specific tag group in the XML file that is returned by the government specifies the error code and provides a description.</span></span>

-   <span data-ttu-id="d291c-393">**Aceito** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-393">**Accepted** – The event was sent to the web services and was accepted by the tax authority system.</span></span>

-   <span data-ttu-id="d291c-394">**Aceito com erros** – O evento foi enviado aos serviços Web e aceito pelo sistema da autoridade fiscal, apesar de haver erros.</span><span class="sxs-lookup"><span data-stu-id="d291c-394">**Accepted with errors** – The event was sent to the web services and was accepted by the tax authority system, even though there were errors.</span></span>


### <a name="event-r-1000-taxpayer-information"></a><span data-ttu-id="d291c-395">**Evento R-1000, "Informações do contribuinte"**</span><span class="sxs-lookup"><span data-stu-id="d291c-395">**Event R-1000, "Taxpayer information"**</span></span>

<span data-ttu-id="d291c-396">O evento R-1000 é usado para entregar informações sobre a empresa.</span><span class="sxs-lookup"><span data-stu-id="d291c-396">Event R-1000 is used to delivery information about the company.</span></span> <span data-ttu-id="d291c-397">Esse evento deve ser entregue apenas uma vez para registrar as informações no site do governo.</span><span class="sxs-lookup"><span data-stu-id="d291c-397">This event must be delivered only one time to register the information on the government site.</span></span> <span data-ttu-id="d291c-398">No entanto, após esse registro inicial de informações, pode ser entregue quantas vezes for necessário para ações de manutenção como atualizações e exclusões de dados.</span><span class="sxs-lookup"><span data-stu-id="d291c-398">However, after this initial registration of information, it can be delivered as many times as required for maintenance actions such as updates and deletions of data.</span></span>

<span data-ttu-id="d291c-399">Portanto, sempre que qualquer atributo do contribuinte ou a data válida de informações que foi fornecida anteriormente precisarem ser alterados, o evento R-1000 deve ser entregue novamente.</span><span class="sxs-lookup"><span data-stu-id="d291c-399">Therefore, whenever any taxpayer attribute or the valid date of information that was provided earlier must be changed, event R-1000 must be delivered again.</span></span> <span data-ttu-id="d291c-400">Quando for entregue novamente, o grupo de marcas correto para a ação desejada deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="d291c-400">When it's redelivered, the correct group of tags for the desired action must be specified.</span></span>

<span data-ttu-id="d291c-401">Como as comunicações podem falhar devido a problemas técnicos, como tempo limite ou falhas de Internet, o contador tributário deve ser capaz de reenviar o evento.</span><span class="sxs-lookup"><span data-stu-id="d291c-401">Because communications can fail for technical reasons, such as a time-out or an internet shortage, the tax accountant must be able to resubmit the event.</span></span> <span data-ttu-id="d291c-402">Além disso, como a validação do arquivo pelo serviço Web pode falhar, o contador tributário deve ser capaz de visualizar os detalhes e corrigir os erros relacionados.</span><span class="sxs-lookup"><span data-stu-id="d291c-402">Additionally, because validation of the file by the web service can fail, the tax accountant must be able to view the details and fix the related errors.</span></span> <span data-ttu-id="d291c-403">Após a validação do arquivo, o protocolo de recebimento que é retornado pelo serviço Web deve ser salvo e o contador tributário deve ser capaz de visualizar seus detalhes, como o número e o carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="d291c-403">After the file is validated, the receiving protocol that is returned by the web service must be saved, and the tax accountant must be able to view its details, such as the number and time stamp.</span></span>

#### <a name="repro-step--insertion"></a><span data-ttu-id="d291c-404">**Etapa de reprodução – Inserção**</span><span class="sxs-lookup"><span data-stu-id="d291c-404">**Repro step – Insertion**</span></span>

1.  <span data-ttu-id="d291c-405">Vá para **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Itens de mensagem eletrônica**.</span><span class="sxs-lookup"><span data-stu-id="d291c-405">Go to **Tax \> Inquiries and reports \> Electronic messages \> Electronic message items**.</span></span>

2.  <span data-ttu-id="d291c-406">No Painel de Ação, selecione **Executar processamento**.</span><span class="sxs-lookup"><span data-stu-id="d291c-406">On the Action Pane, select **Run processing**.</span></span> <span data-ttu-id="d291c-407">Em seguida, na caixa de diálogo **Executar processamento**, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="d291c-407">Then, in the **Run processing** dialog box, in the **Processing** field select **SPED Reinf**.</span></span>

3.  <span data-ttu-id="d291c-408">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Incluir**.</span><span class="sxs-lookup"><span data-stu-id="d291c-408">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Incluir**.</span></span>

    ![Run-processing](media/bra-run-processing.png)

4.  <span data-ttu-id="d291c-410">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="d291c-410">Select **OK** to confirm the settings.</span></span>

>   <span data-ttu-id="d291c-411">Um item de mensagem do tipo **Informações do contribuinte** é criado e seu status é definido como **Anexado**.</span><span class="sxs-lookup"><span data-stu-id="d291c-411">A message item of **Informações do contribuinte** type is created, and the status of the message item is set to **Anexado**.</span></span>

![Electronic-message-items-insertion](media/bra-electronic-message-items-insertion.png)

5.  <span data-ttu-id="d291c-413">Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="d291c-413">Select **Run processing** again, and then, in the dialog box, in the **Processing** field, select **SPED Reinf**.</span></span>

6.  <span data-ttu-id="d291c-414">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Parâmetros adicionais** para atualizar as informações relacionadas nos campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d291c-414">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Parâmetros adicionais** to update the related information in additional fields.</span></span>

![Run-processing-aditional-parameters](media/bra-run-processing-additional-parameters.png)

![Preparation-items](media/bra-preparation-items.png)

7.  <span data-ttu-id="d291c-417">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="d291c-417">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="d291c-418">O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Preparado**.</span><span class="sxs-lookup"><span data-stu-id="d291c-418">The message item of **Informações do contribuinte** type is updated, and the status of the message item is changed to **Preparado**.</span></span>

![Electronic-message-items-status](media/bra-electronic-message-items-status.png)

8.  <span data-ttu-id="d291c-420">Selecione **Executar processamento** novamente e, na caixa de diálogo, no campo **Processamento**, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="d291c-420">Select **Run processing** again, and then, in the dialog box, in the **Processing** field, select **SPED Reinf**.</span></span>

9.  <span data-ttu-id="d291c-421">Defina a opção **Escolher ação** como **Sim** e, em seguida, no campo **Ação**, selecione **Gerar** para gerar o XML.</span><span class="sxs-lookup"><span data-stu-id="d291c-421">Set the **Choose action** option to **Yes**, and then, in the **Action** field, select **Gerar** to generate the XML.</span></span>

10.  <span data-ttu-id="d291c-422">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="d291c-422">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="d291c-423">A caixa de diálogo **Gerar relatórios** aparece automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d291c-423">The **Generate reports** dialog box automatically appears.</span></span> <span data-ttu-id="d291c-424">Na FastTab **Registros a serem incluídos**, nas opções de filtro, a ID do tipo de item de mensagem que está solicitando a geração de um arquivo XML é selecionada no campo **Item de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="d291c-424">On the **Records to include** FastTab, in the filter options, the ID of the message item type that is requesting generation of an XML file is selected in the **Message item** field.</span></span>

![Generate-reports](media/bra-generate-reports.png)

11.  <span data-ttu-id="d291c-426">Selecione **OK** para confirmar as configurações.</span><span class="sxs-lookup"><span data-stu-id="d291c-426">Select **OK** to confirm the settings.</span></span> <span data-ttu-id="d291c-427">O item de mensagem do tipo **Informações do contribuinte** é atualizado e seu status é alterado para **Gerado**.</span><span class="sxs-lookup"><span data-stu-id="d291c-427">The message item of the **Informações do contribuinte** type is updated, and the status of the message item is changed to **Gerado**.</span></span>

12.  <span data-ttu-id="d291c-428">Repita essas etapas até concluir todas as ações no fluxo [Inserção](#insertion).</span><span class="sxs-lookup"><span data-stu-id="d291c-428">Repeat these steps until you've complete all the actions in the [Insertion](#insertion) flow.</span></span>

#### <a name="repro-step--amendment"></a><span data-ttu-id="d291c-429">**Etapa de reprodução – Aditamento**</span><span class="sxs-lookup"><span data-stu-id="d291c-429">**Repro step – Amendment**</span></span> 

<span data-ttu-id="d291c-430">Se algum dado da organização fiscal foi alterado ou se for necessário excluir o evento por algum motivo, o evento R-1010 deve ser transmitido novamente, mas o status deve ser diferente.</span><span class="sxs-lookup"><span data-stu-id="d291c-430">If any data of the fiscal organization has been changed, or if the event must be excluded for some reason, event R-1010 must be transmitted again, but the status must be different.</span></span>

<span data-ttu-id="d291c-431">Use o mesmo processo descrito na seção “Etapa de reprodução – Inserção” e conclua todas as ações no fluxo [Aditamento/Atualização](#amendmentupdate).</span><span class="sxs-lookup"><span data-stu-id="d291c-431">Use the same process that is described in the "Repro step – Insertion" section, and complete all the actions in the [Amendment/Update](#amendmentupdate) flow.</span></span>

<span data-ttu-id="d291c-432">O Microsoft Dynamics AX detectará quaisquer diferenças entre as informações no último evento e as informações atuais.</span><span class="sxs-lookup"><span data-stu-id="d291c-432">Microsoft Dynamics AX will detect any differences between the information in the last event and the current information.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-433">Se as alterações não afetarem o evento R-1010 relacionado, você receberá a seguinte mensagem: “0 registros foram adicionados”.</span><span class="sxs-lookup"><span data-stu-id="d291c-433">If changes don't affect the related R-1010 event, you will receive the following message: "0 records have been added."</span></span>

#### <a name="repro-step--cancel"></a><span data-ttu-id="d291c-434">**Etapa de reprodução – Cancelamento**</span><span class="sxs-lookup"><span data-stu-id="d291c-434">**Repro step – Cancel**</span></span>

<span data-ttu-id="d291c-435">Se, por algum motivo, o contribuinte quiser cancelar/excluir um evento aceito, selecione **Cancelar** e confirme a operação.</span><span class="sxs-lookup"><span data-stu-id="d291c-435">If for some many reason, the taxpayer wants to cancel/exclude an event that has accepted, select **Cancel**, and confirm the operation.</span></span> <span data-ttu-id="d291c-436">O status do evento será atualizado para **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="d291c-436">The status of the event will be updated to **Excluded**.</span></span> <span data-ttu-id="d291c-437">Conclua todas as ações no fluxo [Cancelamento/Exclusão](#canceldelete).</span><span class="sxs-lookup"><span data-stu-id="d291c-437">Complete all the actions in the [Cancel/Delete](#canceldelete) flow.</span></span>

### <a name="event-r-1070-administrative-and-judicial-process"></a><span data-ttu-id="d291c-438">**Evento R-1070, "Processo administrativo e judicial"**</span><span class="sxs-lookup"><span data-stu-id="d291c-438">**Event R-1070, "Administrative and judicial process"**</span></span>

<span data-ttu-id="d291c-439">O evento R-1070 é usado para relatar informações sobre os processos legais e administrativos ao sistema da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-439">Event R-1070 is used to report information about the administrative and lawsuits process to tax authority system.</span></span>

<span data-ttu-id="d291c-440">Os processos legais e administrativos podem ser iniciados pelo contribuinte ou pelo trabalhador quando valores da previdência social forem contestados.</span><span class="sxs-lookup"><span data-stu-id="d291c-440">The administrative and lawsuits process can be started by either the taxpayer or by the worker when the amounts in the social security are disputed.</span></span> <span data-ttu-id="d291c-441">Os procedimentos (judiciais ou administrativos) são realizados pelo tribunal.</span><span class="sxs-lookup"><span data-stu-id="d291c-441">The proceedings (either judicial or administrative) are carried out by the court.</span></span> <span data-ttu-id="d291c-442">Após o juiz chegar a um veredito, ele tem o poder de suspender (ou não) os valores que foram retidos.</span><span class="sxs-lookup"><span data-stu-id="d291c-442">After the judge reaches a final decision, he or she has the power to suspend (or not) the amounts that were retained.</span></span>

<span data-ttu-id="d291c-443">A finalidade desse evento é comunicar a existência de procedimentos desse tipo ao banco de dados do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="d291c-443">The purpose of this event is to communicate the existence of proceedings of this type to the SPED-Reinf database.</span></span> <span data-ttu-id="d291c-444">Depois que os procedimentos recebem a decisão final do tribunal que suspende a elegibilidade da retenção de valores, o evento se refere a essa decisão para explicar por que os valores foram relatados como suspensos nos eventos periódicos.</span><span class="sxs-lookup"><span data-stu-id="d291c-444">After the proceedings have a final court decision that suspends the eligibility of withholding amounts, the event refers to that decision to explain why the amounts have been reported as suspended in the periodic events.</span></span>

<span data-ttu-id="d291c-445">Além das informações típicas que identificam o contribuinte e o evento, o evento R-1070 contém os seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="d291c-445">Besides the typical information that identifies the taxpayer and the event, event R-1070 contains the following groups:</span></span>

-   <span data-ttu-id="d291c-446">Identificador do processo ou dos procedimentos</span><span class="sxs-lookup"><span data-stu-id="d291c-446">Identifier of the process or proceedings</span></span>

-   <span data-ttu-id="d291c-447">Informações da suspensão</span><span class="sxs-lookup"><span data-stu-id="d291c-447">Suspension information</span></span>

-   <span data-ttu-id="d291c-448">Informações complementares sobre os procedimentos</span><span class="sxs-lookup"><span data-stu-id="d291c-448">Complementary information about the proceedings</span></span>

<span data-ttu-id="d291c-449">Antes da entrega do evento R-1070, você deve criar o processo relacionado e incluir todas as informações relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d291c-449">Before event R-1070 can be delivered, you must create the related process and include all related information.</span></span>

#### <a name="repro-step--create-process"></a><span data-ttu-id="d291c-450">**Etapa de reprodução – Criar processo**</span><span class="sxs-lookup"><span data-stu-id="d291c-450">**Repro step – Create process**</span></span>

1.  <span data-ttu-id="d291c-451">Vá para **Livros fiscais \> Atividades periódicas \> SPED Reinf \> Processo administrativo e judicial**.</span><span class="sxs-lookup"><span data-stu-id="d291c-451">Go to **Fiscal books \> Periodic \> SPED Reinf \> Administrative and judicial process**.</span></span>

![Administrative-judicial-process](media/bra-administrative-judicial-process.png)

1.  <span data-ttu-id="d291c-453">Selecione **Novo** e defina os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="d291c-453">Select **New**, and set the following fields.</span></span>

| <span data-ttu-id="d291c-454">**Campo**</span><span class="sxs-lookup"><span data-stu-id="d291c-454">**Field**</span></span>                    | <span data-ttu-id="d291c-455">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d291c-455">**Description**</span></span>        |
|------------------------------|-----------------------|
| <span data-ttu-id="d291c-456">Número do processo</span><span class="sxs-lookup"><span data-stu-id="d291c-456">Number of the process</span></span>        | <span data-ttu-id="d291c-457">Insira o número do processo atribuído pelas autoridades competentes.</span><span class="sxs-lookup"><span data-stu-id="d291c-457">Enter the process number that was assigned by the competent authorities.</span></span> <span data-ttu-id="d291c-458">O sistema da autoridade fiscal valida o formato, pois há uma regra específica a ser considerada.</span><span class="sxs-lookup"><span data-stu-id="d291c-458">The tax authority system validates the format, because there is a specific rule to consider.</span></span> |
| <span data-ttu-id="d291c-459">Autor do processo</span><span class="sxs-lookup"><span data-stu-id="d291c-459">Author of process</span></span>            | <span data-ttu-id="d291c-460">Selecione a origem do processo:</span><span class="sxs-lookup"><span data-stu-id="d291c-460">Select the source that the process originated from:</span></span>                                                                                                                   |
| <span data-ttu-id="d291c-461">Tipo de processo</span><span class="sxs-lookup"><span data-stu-id="d291c-461">Type of process</span></span>              | <span data-ttu-id="d291c-462">Selecione o tipo de processo:</span><span class="sxs-lookup"><span data-stu-id="d291c-462">Select the type of process:</span></span>                                                                                                                                           |
| <span data-ttu-id="d291c-463">Cidade da vara judicial</span><span class="sxs-lookup"><span data-stu-id="d291c-463">City of the judicial section</span></span> | <span data-ttu-id="d291c-464">Selecione a cidade relacionada onde o processo foi originado.</span><span class="sxs-lookup"><span data-stu-id="d291c-464">Select the related city where the process originated.</span></span>                                                                                                                 |
| <span data-ttu-id="d291c-465">Código da vara judicial</span><span class="sxs-lookup"><span data-stu-id="d291c-465">Code of the judicial section</span></span> | <span data-ttu-id="d291c-466">Insira o código da vara judicial.</span><span class="sxs-lookup"><span data-stu-id="d291c-466">Enter the code for the judicial section.</span></span>                                                                                                                              |

-   <span data-ttu-id="d291c-467">Contribuinte</span><span class="sxs-lookup"><span data-stu-id="d291c-467">Taxpayer</span></span>

-   <span data-ttu-id="d291c-468">Outros terceiros</span><span class="sxs-lookup"><span data-stu-id="d291c-468">Other third party</span></span>

-   <span data-ttu-id="d291c-469">Administrativo</span><span class="sxs-lookup"><span data-stu-id="d291c-469">Administrative</span></span>

-   <span data-ttu-id="d291c-470">Judicial</span><span class="sxs-lookup"><span data-stu-id="d291c-470">Judicial</span></span>

1.  <span data-ttu-id="d291c-471">Na seção **Detalhes**, insira os detalhes das notas fiscais registradas no Microsoft Dynamics e que são afetadas pelo processo registrado, pois algumas delas podem ter exceções nos impostos retidos na fonte.</span><span class="sxs-lookup"><span data-stu-id="d291c-471">In the **Details** section, enter details of the fiscal documents that are registered in Microsoft Dynamics, and that are affected by the registered process, because some of them might have exceptions in withholding taxes.</span></span> <span data-ttu-id="d291c-472">Você pode adicionar notas fiscais ou remover as que foram adicionadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d291c-472">You can add fiscal documents or remove fiscal documents that were previously added.</span></span>

| <span data-ttu-id="d291c-473">**Campo**</span><span class="sxs-lookup"><span data-stu-id="d291c-473">**Field**</span></span>                        | <span data-ttu-id="d291c-474">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d291c-474">**Description**</span></span>                                                                                           |
|----------------------------------|-----------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="d291c-475">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="d291c-475">Reference</span></span>                        | <span data-ttu-id="d291c-476">O identificador exclusivo da relação entre o número do processo e a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-476">The unique identifier of the relation between the process number and the fiscal document.</span></span>                 |
| <span data-ttu-id="d291c-477">Código</span><span class="sxs-lookup"><span data-stu-id="d291c-477">Code</span></span>                             | <span data-ttu-id="d291c-478">Selecione o código de suspensão da explicação.</span><span class="sxs-lookup"><span data-stu-id="d291c-478">Select the explanation suspension code.</span></span>                                                                   |
| <span data-ttu-id="d291c-479">Tipo de serviço</span><span class="sxs-lookup"><span data-stu-id="d291c-479">Service type</span></span>                     | <span data-ttu-id="d291c-480">Selecione o tipo de serviço relacionado que é aplicável à nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-480">Select the related service type that is applicable for the fiscal document.</span></span>                               |
| <span data-ttu-id="d291c-481">Nota fiscal</span><span class="sxs-lookup"><span data-stu-id="d291c-481">Fiscal document</span></span>                  | <span data-ttu-id="d291c-482">Selecione a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-482">Select the fiscal document.</span></span>                                                                               |
| <span data-ttu-id="d291c-483">Data da decisão</span><span class="sxs-lookup"><span data-stu-id="d291c-483">Date of decision</span></span>                 | <span data-ttu-id="d291c-484">A data da decisão, da sentença ou do despacho administrativo.</span><span class="sxs-lookup"><span data-stu-id="d291c-484">The date of the decision, sentence, or administrative dispatch.</span></span>                                           |
| <span data-ttu-id="d291c-485">Valor da retenção</span><span class="sxs-lookup"><span data-stu-id="d291c-485">Amount of withholding</span></span>            | <span data-ttu-id="d291c-486">O valor da retenção que foi suspenso devido a um processo legal ou administrativo.</span><span class="sxs-lookup"><span data-stu-id="d291c-486">The amount of withholding that was suspended because of an administrative or lawsuits process.</span></span>            |
| <span data-ttu-id="d291c-487">Valor da retenção adicional</span><span class="sxs-lookup"><span data-stu-id="d291c-487">Amount of additional withholding</span></span> | <span data-ttu-id="d291c-488">O valor adicional da retenção que foi suspenso devido a um processo legal ou administrativo.</span><span class="sxs-lookup"><span data-stu-id="d291c-488">The additional amount of withholding that was suspended because of an administrative or lawsuits process.</span></span> |

> [!NOTE]
> <span data-ttu-id="d291c-489">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-489">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.\*</span></span>

### <a name="event-r-2010-acquired-services"></a><span data-ttu-id="d291c-490">**Evento R-2010, "Serviços adquiridos"**</span><span class="sxs-lookup"><span data-stu-id="d291c-490">**Event R-2010, "Acquired services"**</span></span>

<span data-ttu-id="d291c-491">O evento periódico R-2010 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço recebidas pelo estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-491">Periodic event R-2010 is used to report, to the tax authority system, information about the withholding amounts for social security that are present in service fiscal documents that were received by the fiscal establishment.</span></span> <span data-ttu-id="d291c-492">Esse evento não tem nenhuma outra finalidade além de relatar essas notas fiscais para o governo.</span><span class="sxs-lookup"><span data-stu-id="d291c-492">This event has no other purpose but to report those fiscal documents to the government.</span></span>

<span data-ttu-id="d291c-493">Esse evento deve ser enviado até o décimo quinto dia do mês seguinte.</span><span class="sxs-lookup"><span data-stu-id="d291c-493">This event must be sent until the fifteenth day of the next month.</span></span> <span data-ttu-id="d291c-494">Por ser um evento periódico, não é recomendável enviá-lo apenas uma vez, próximo à data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="d291c-494">Because it's a periodic event, we don't recommend that you send the event just one time, near the due date.</span></span> <span data-ttu-id="d291c-495">Em vez disso, você deve enviá-lo regularmente e com frequência durante o período.</span><span class="sxs-lookup"><span data-stu-id="d291c-495">Instead, you should send it regularly and frequently during the period.</span></span>

<span data-ttu-id="d291c-496">Além disso, a geração desse evento requer a adoção de novas semânticas para o tratamento de eventos em livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="d291c-496">Additionally, generation of this event requires the adoption of new semantics for handling events in fiscal books.</span></span> <span data-ttu-id="d291c-497">As novas semânticas são desacopladas de uma apuração de imposto, mas ainda estão no contexto do período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="d291c-497">The new semantics are decoupled from a tax assessment but are still in the context of the booking period.</span></span> <span data-ttu-id="d291c-498">Depois que todas as notas fiscais no módulo **Livros fiscais** estiverem no contexto de um período de escrituração, o evento R-2010 também deverá ser gerado por período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="d291c-498">After every fiscal document in the **Fiscal books** module is in the context of a booking period, event R-2010 must also be generated by booking period.</span></span>


<span data-ttu-id="d291c-499">Somente o imposto INSS Retido e o imposto sobre serviços devem ser selecionados para gerar esse evento no período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="d291c-499">Only service and retained INSS tax type must be selected to generate this event in the booking period.</span></span>

<span data-ttu-id="d291c-500">**Principais critérios**</span><span class="sxs-lookup"><span data-stu-id="d291c-500">**Main criteria**</span></span>

-   <span data-ttu-id="d291c-501">As notas fiscais são registradas e sincronizadas no estabelecimento fiscal e no período relacionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-501">The fiscal documents are booked and synced in the related period and fiscal establishment.</span></span>

-   <span data-ttu-id="d291c-502">As notas fiscais têm o status de **Aprovada** ou **Cancelada**.</span><span class="sxs-lookup"><span data-stu-id="d291c-502">The fiscal documents have a status of **Approved** or **Canceled**.</span></span>

-   <span data-ttu-id="d291c-503">O modelo da nota fiscal é **SE**.</span><span class="sxs-lookup"><span data-stu-id="d291c-503">The fiscal document model is **SE**.</span></span>

-   <span data-ttu-id="d291c-504">O tipo de imposto é **INSS** e ele é retido (a caixa de seleção **Imposto retido/recuperável** é marcada).</span><span class="sxs-lookup"><span data-stu-id="d291c-504">The tax type is **INSS**, and it's retained (the **Retained tax/to recuperate** check box is selected).</span></span>

![Brazilian-taxes](media/bra-brazilian-taxes.png)

> [!NOTE]
> <span data-ttu-id="d291c-506">Nunca use o tipo de imposto **INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="d291c-506">Never use the **INSS-CPRB** tax type.</span></span>

<span data-ttu-id="d291c-507">O relatório é agrupado por um valor **Tipo de código de serviço** (tabela 06 da documentação do SPED-Reinf).</span><span class="sxs-lookup"><span data-stu-id="d291c-507">The report is grouped by a **Type of service code** value (table 06 from the SPED-Reinf documentation).</span></span> <span data-ttu-id="d291c-508">Portanto, você deve modificar o lançamento de notas fiscais de serviço para habilitar a captura dessas informações.</span><span class="sxs-lookup"><span data-stu-id="d291c-508">Therefore, you must modify the posting of service fiscal documents to enable the capture of this information.</span></span> <span data-ttu-id="d291c-509">Caso contrário, não é possível gerar o evento.</span><span class="sxs-lookup"><span data-stu-id="d291c-509">Otherwise, the event can't be generated.</span></span>

<span data-ttu-id="d291c-510">O evento envia quatro tipos de valores para o banco de dados do governo:</span><span class="sxs-lookup"><span data-stu-id="d291c-510">The event sends four types of amounts to the government database:</span></span>

-   <span data-ttu-id="d291c-511">**Retenção** – O tipo de imposto INSS Retido calculado que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-511">**Withholding** – The calculated retained INSS tax type that is linked to the fiscal document line.</span></span>

-   <span data-ttu-id="d291c-512">**Retenção adicional** – Uma variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-512">**Additional withholding** – A variation of the INSS tax type that is linked to the fiscal document line.</span></span>

-   <span data-ttu-id="d291c-513">**Retenção suspensa** – O valor do tipo de imposto INSS Retido suspenso.</span><span class="sxs-lookup"><span data-stu-id="d291c-513">**Suspended withholding** – The amount of the suspended retained INSS tax type.</span></span>

-   <span data-ttu-id="d291c-514">**Retenção adicional suspensa** – O valor suspenso da variação do tipo de imposto INSS que está vinculado à linha da nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-514">**Suspended additional withholding** – The suspended amount on the variation of the INSS tax type that is linked to the fiscal document line.</span></span>

<span data-ttu-id="d291c-515">Sempre que uma suspensão de valores ocorrer, o processo legal ou administrativo associado deve ser especificado no evento para oferecer suporte aos motivos da suspensão ou explicá-los.</span><span class="sxs-lookup"><span data-stu-id="d291c-515">Whenever a suspension of amounts occurs, the associated administrative or lawsuits process must be specified in the event to support (or explain) the reasons for the suspension.</span></span> <span data-ttu-id="d291c-516">Essas informações devem ser inseridas manualmente nos campos **Valor da retenção** e **Valor da retenção adicional** na página **Processo administrativo e judicial** que é descrita na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="d291c-516">This information must be manually entered in the **Amount of withholding** and **Additional amount of withholding** fields on the **Administration and judicial process** page that is described in the previous section.</span></span>

<span data-ttu-id="d291c-517">O evento R-2010 usa o conceito de fechamento.</span><span class="sxs-lookup"><span data-stu-id="d291c-517">Event R-2010 uses the concept of closing.</span></span> <span data-ttu-id="d291c-518">Depois que esse evento for fechado, o serviço Web recusará quaisquer novas entradas ou modificações nele, a menos que seja reaberto manualmente.</span><span class="sxs-lookup"><span data-stu-id="d291c-518">After this event is closed, the web service will refuse any new entries or modifications for it, unless it's manually reopened.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-519">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-519">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.\*</span></span>

### <a name="event-r-2020-provided-services"></a><span data-ttu-id="d291c-520">**Evento R-2020, "Serviços fornecidos"**</span><span class="sxs-lookup"><span data-stu-id="d291c-520">**Event R-2020, "Provided services"**</span></span>

<span data-ttu-id="d291c-521">O evento periódico R-2020 é usado para relatar, ao sistema da autoridade fiscal, as informações sobre os valores de retenção para a previdência social que estão presentes em notas fiscais de serviço emitidas pelos estabelecimentos fiscais de uma organização fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-521">Periodic event R-2020 is used to report, to the tax authority system, information about the withholdings amounts for social security that are present in service fiscal documents that were issued by the fiscal establishments of a fiscal organization.</span></span>

<span data-ttu-id="d291c-522">Esse evento funciona como o evento R-2010, mas você deve considerar as contas de cliente e o modelo de nota fiscal SE (saída) que é emitido pelo estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-522">This event works like event R-2010, but you must consider customer accounts and fiscal document model SE (outgoing) that is issued by the fiscal establishment.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-523">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.\*</span><span class="sxs-lookup"><span data-stu-id="d291c-523">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.\*</span></span>

### <a name="event-r-2060-inss-cprb"></a><span data-ttu-id="d291c-524">**Evento R-2060, "INSS CPRB"**</span><span class="sxs-lookup"><span data-stu-id="d291c-524">**Event R-2060, "INSS CPRB"**</span></span>

<span data-ttu-id="d291c-525">O evento periódico R-2060 é usado para enviar informações sobre a apuração de imposto da retenção para a previdência social ao SPED-Reinf quando a organização fiscal escolher calcular a previdência social com base na receita bruta em vez da folha de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d291c-525">Periodic event R-2060 is used to send information about the tax assessment of the withholding for social security to the SPED-Reinf when the fiscal organization has chosen to calculate the social security based on the gross revenue instead of the payroll.</span></span>

<span data-ttu-id="d291c-526">Portanto, antes de gerar o evento, você deve realizar a apuração de imposto por organização fiscal no módulo **Livros fiscais**.</span><span class="sxs-lookup"><span data-stu-id="d291c-526">Therefore, before you generate the event, you must do the tax assessment by fiscal organization in the **Fiscal books** module.</span></span> <span data-ttu-id="d291c-527">Quando essa opção é estabelecida nos parâmetros do SPED-Reinf, os usuários podem criar a apuração de imposto para o INSS-CPRB e os impostos são calculados automaticamente com base nos critérios definidos nos Parâmetros de livros fiscais.</span><span class="sxs-lookup"><span data-stu-id="d291c-527">When this option is established in the SPED-Reinf parameters, users can create the tax assessment for INSS-CPRB, and taxes are automatically calculated based on the criteria that are defined in the Fiscal books parameters.</span></span>

<span data-ttu-id="d291c-528">O Microsoft Dynamics pegará todas as notas fiscais que estão registradas no período relacionado e que representam a receita e aplicará a alíquota de imposto ao valor base.</span><span class="sxs-lookup"><span data-stu-id="d291c-528">Microsoft Dynamics will pick up all fiscal documents that are booked in the related period and that represents revenue, and it will apply the tax rate to the base amount.</span></span> <span data-ttu-id="d291c-529">A alíquota de imposto aplicada pode variar, dependendo do produto ou serviço que gerou a receita.</span><span class="sxs-lookup"><span data-stu-id="d291c-529">The tax rate that is applied can vary, depending on the product or service that generated the revenue.</span></span> <span data-ttu-id="d291c-530">O resultado será o valor de CPRB.</span><span class="sxs-lookup"><span data-stu-id="d291c-530">The result will be the amount of CPRB.</span></span>

<span data-ttu-id="d291c-531">Para essa finalidade, um novo tipo de imposto brasileiro, o **INSS-CPRB**, foi criado.</span><span class="sxs-lookup"><span data-stu-id="d291c-531">For this purpose, a new Brazilian tax type, **INSS-CPRB**, was created.</span></span> <span data-ttu-id="d291c-532">Esse tipo de imposto só é usado na apuração do imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="d291c-532">This tax type is used only in the generation of the INSS-CPRB tax assessment.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-533">Não use o tipo de imposto **INSS-CPRB** para outras finalidades.</span><span class="sxs-lookup"><span data-stu-id="d291c-533">Don't use the **INSS-CPRB** tax type for other purposes.</span></span>

<span data-ttu-id="d291c-534">Como a apuração do imposto INSS-CPRB é um tipo de apuração de imposto, ajustes podem ser necessários.</span><span class="sxs-lookup"><span data-stu-id="d291c-534">Because the INSS-CPRB tax assessment is a type of tax assessment, adjustments might become necessary.</span></span> <span data-ttu-id="d291c-535">Esses ajustes devem ser inseridos manualmente como adições ou reduções.</span><span class="sxs-lookup"><span data-stu-id="d291c-535">These adjustments must be manually entered as either additions or reductions.</span></span>

<span data-ttu-id="d291c-536">Por fim, a apuração do imposto e os ajustes determinam o valor de CPRB que deve ser pago.</span><span class="sxs-lookup"><span data-stu-id="d291c-536">Finally, the tax assessment and the adjustments determine the amount of CPRB that must be paid.</span></span> <span data-ttu-id="d291c-537">No entanto, a geração do diário de pagamento e o registro nesse pagamento não são o escopo desse recurso.</span><span class="sxs-lookup"><span data-stu-id="d291c-537">However, generation of the payment journal and registration on this payment isn't in the scope of this feature.</span></span>

<span data-ttu-id="d291c-538">Os períodos nessa nova apuração de imposto devem ser gerenciados da mesma forma que em outras apurações.</span><span class="sxs-lookup"><span data-stu-id="d291c-538">Periods for this new tax assessment must be managed in the same way as other tax assessments.</span></span> <span data-ttu-id="d291c-539">Em outras palavras, a apuração de imposto pode ser criada ou atualizada somente enquanto estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="d291c-539">In other words, the tax assessment can be created or updated only while it's open.</span></span> <span data-ttu-id="d291c-540">Após ser finalizada, não poderá mais ser alterada a menos que seja reaberta.</span><span class="sxs-lookup"><span data-stu-id="d291c-540">After it's finalized, it can no longer be touched unless it's reopened.</span></span>

<span data-ttu-id="d291c-541">Após a criação da apuração de imposto e a realização dos ajustes necessários, o evento periódico R-2060 pode ser gerado.</span><span class="sxs-lookup"><span data-stu-id="d291c-541">After the tax assessment is created and any required adjustments are made, periodic event R-2060 can be generated.</span></span>

<span data-ttu-id="d291c-542">O evento R-2060 inclui os totais da apuração de impostos e detalhes dos cálculos de impostos por código de atividade econômica, ajustes (adições e reduções, quando aplicável) e referências a processos legais e administrativos.</span><span class="sxs-lookup"><span data-stu-id="d291c-542">Event R-2060 includes the totals of the tax assessment and details of the tax calculations by economic activity code, adjustments (additions and reductions, when applicable), and references to administrative and lawsuits processes.</span></span>

#### <a name="repro-step--setup"></a><span data-ttu-id="d291c-543">**Etapa de reprodução – Configuração**</span><span class="sxs-lookup"><span data-stu-id="d291c-543">**Repro step – Setup**</span></span>

1.  <span data-ttu-id="d291c-544">Vá para **Livros fiscais \> Configuração \> Organização fiscal**.</span><span class="sxs-lookup"><span data-stu-id="d291c-544">Go to **Fiscal books \> Setup \> Fiscal organization**.</span></span>

2.  <span data-ttu-id="d291c-545">Defina a opção **CPRB** como **Sim** para habilitar a criação da apuração do INSS-CPRB e a transmissão do evento R-2060.</span><span class="sxs-lookup"><span data-stu-id="d291c-545">Set the **CPRB** option to **Yes** to enable creation of the INSS-CPRB assessment and transmission of event R-2060.</span></span>

3.  <span data-ttu-id="d291c-546">Vá para **Livros fiscais \> Configuração \> Sped Reinf \> Códigos de atividades econômicas**.</span><span class="sxs-lookup"><span data-stu-id="d291c-546">Go to **Fiscal books \> Setup \> Sped Reinf \> Economic activity codes**.</span></span> <span data-ttu-id="d291c-547">Os códigos de atividades econômicas devem ser configurados para habilitar o cálculo automático dos valores do imposto INSS-CPRB, pois a nota fiscal não possui informações relacionadas sobre esse imposto.</span><span class="sxs-lookup"><span data-stu-id="d291c-547">Economic activity codes must be configured to enable automatic calculation of INSS-CPRB tax amounts, because the fiscal document has no related information about this tax.</span></span> <span data-ttu-id="d291c-548">Essa abordagem foi implementada para facilitar a configuração da matriz de impostos.</span><span class="sxs-lookup"><span data-stu-id="d291c-548">This approach was implemented to facilitate the configuration of the tax matrix.</span></span>

4.  <span data-ttu-id="d291c-549">Selecione **Novo** para criar um código de atividade econômica e insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="d291c-549">Select **New** to create an economic activity code, and enter a description.</span></span> <span data-ttu-id="d291c-550">Você deve verificar a Tabela 09 do Sped REINF no site da autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d291c-550">You must check the Sped REINF Table 09 on the tax authority website.</span></span>

5.  <span data-ttu-id="d291c-551">Selecione o código de imposto que contém a alíquota de imposto para aplicar ao produto ou serviço.</span><span class="sxs-lookup"><span data-stu-id="d291c-551">Select the tax code that contains the tax rate to apply for the product or service.</span></span> <span data-ttu-id="d291c-552">Você deve criar um tipo de imposto INSS Retido.</span><span class="sxs-lookup"><span data-stu-id="d291c-552">You must create a Retained INSS tax type.</span></span>

6.  <span data-ttu-id="d291c-553">Na guia **Linha**, insira os produtos ou serviços que estão relacionados pela atividade econômica.</span><span class="sxs-lookup"><span data-stu-id="d291c-553">On the **Line** tab, enter the products or services that are related by the economic activity.</span></span> <span data-ttu-id="d291c-554">Os produtos são identificados pelo código de classificação fiscal e os serviços pelo código de serviço (federal).</span><span class="sxs-lookup"><span data-stu-id="d291c-554">Products are identified by the fiscal classification code and services are identified by the service code (federal).</span></span>

#### <a name="repro-step--create-tax-assessment-option-1"></a><span data-ttu-id="d291c-555">**Etapa de reprodução – Criar apuração de imposto (opção 1)**</span><span class="sxs-lookup"><span data-stu-id="d291c-555">**Repro step – Create tax assessment (option 1)**</span></span>

1.  <span data-ttu-id="d291c-556">Vá para **Livros fiscais \> Comum \> Período de escrituração**.</span><span class="sxs-lookup"><span data-stu-id="d291c-556">Go to **Fiscal books \> Common \> Booking period**.</span></span>

2.  <span data-ttu-id="d291c-557">Selecione um período de escrituração.</span><span class="sxs-lookup"><span data-stu-id="d291c-557">Select a booking period.</span></span>

3.  <span data-ttu-id="d291c-558">No Painel de Ação, selecione **INSS-CPRN** e, em seguida, selecione **Novo** para criar uma apuração de imposto.</span><span class="sxs-lookup"><span data-stu-id="d291c-558">On the Action Pane, select **INSS-CPRN**, and then select **New** to create a tax assessment.</span></span> <span data-ttu-id="d291c-559">O Microsoft Dynamics automaticamente cria a apuração de imposto para o período de escrituração selecionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-559">Microsoft Dynamics automatically creates the tax assessment for the selected booking period.</span></span>

#### <a name="repro-step--create-tax-assessment-option-2"></a><span data-ttu-id="d291c-560">**Etapa de reprodução – Criar apuração de imposto (opção 2)**</span><span class="sxs-lookup"><span data-stu-id="d291c-560">**Repro step – Create tax assessment (option 2)**</span></span>

1.  <span data-ttu-id="d291c-561">Vá para **Livros fiscais \> Comum \> Apuração de imposto \> INSS-CPRB** e, em seguida, selecione **Apuração do imposto INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="d291c-561">Go to **Fiscal books \> Common \> Tax assessment \> INSS-CPRB**, and then select **INSS-CPRB tax assessment**.</span></span>

2.  <span data-ttu-id="d291c-562">Selecione o período de escrituração e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d291c-562">Select the booking period, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-563">Você poderá receber o seguinte aviso: “Linha XXXX: não foi possível identificar o código da atividade econômica”.</span><span class="sxs-lookup"><span data-stu-id="d291c-563">You might receive the following warning: "Line XXXX: unable to identify the economic activity code."</span></span> <span data-ttu-id="d291c-564">Esse aviso indica que o Microsoft Dynamics não encontrou o código da atividade econômica para a linha e a nota fiscal relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d291c-564">This warning indicates that Microsoft Dynamics didn't find the economic activity code for the related fiscal document and line.</span></span> <span data-ttu-id="d291c-565">Nesse caso, você deve concluir a configuração que é descrita na etapa de reprodução anterior.</span><span class="sxs-lookup"><span data-stu-id="d291c-565">In this case, you must complete the setup that is described in the previous repro step.</span></span>

>   <span data-ttu-id="d291c-566">**Excluir**</span><span class="sxs-lookup"><span data-stu-id="d291c-566">**Delete**</span></span>

>   <span data-ttu-id="d291c-567">Você pode excluir uma apuração do imposto INSS-CPRB existente se o status for   **Aberto**.</span><span class="sxs-lookup"><span data-stu-id="d291c-567">You can delete an existing INSS-CPRB tax assessment if the status is   **Opened**.</span></span>

>   <span data-ttu-id="d291c-568">**Notas fiscais e operações não fiscais**</span><span class="sxs-lookup"><span data-stu-id="d291c-568">**Fiscal documents and Non-fiscal operations**</span></span>

>   <span data-ttu-id="d291c-569">Quando os impostos INSS-CPRB são apurados, o valor tributável da nota fiscal é considerado e classificado durante o processo de apuração.</span><span class="sxs-lookup"><span data-stu-id="d291c-569">When INSS-CPRB taxes are assessed, the taxable amount of the fiscal document is considered and classified during the assessment process.</span></span> <span data-ttu-id="d291c-570">Você pode visualizar as operações não fiscais e as notas fiscais relacionadas que fazem parte do cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="d291c-570">You can view the related fiscal documents and non-fiscal operations that are part of the tax calculation.</span></span>

>   <span data-ttu-id="d291c-571">**Transações de imposto**</span><span class="sxs-lookup"><span data-stu-id="d291c-571">**Tax transactions**</span></span>

>   <span data-ttu-id="d291c-572">Quando os impostos INSS-CPRB são apurados, você pode visualizar os detalhes das transações de imposto que são gerados pelo processo.</span><span class="sxs-lookup"><span data-stu-id="d291c-572">When INSS-CPRB taxes are assessed, you can view the tax transactions details that are generated by the process.</span></span>

>   <span data-ttu-id="d291c-573">**Ajuste**</span><span class="sxs-lookup"><span data-stu-id="d291c-573">**Adjustment**</span></span>

>   <span data-ttu-id="d291c-574">Você pode inserir transações de ajuste adicionais para ajustar (aumentar ou diminuir) o valor do INSS-CPRB calculado.</span><span class="sxs-lookup"><span data-stu-id="d291c-574">You can enter additional adjustment transactions to adjust (increase or decrease) the amount of INSS-CPRB that is calculated.</span></span> <span data-ttu-id="d291c-575">Configure os códigos de ajuste em **Livros fiscais \> Configuração \> Códigos de ajuste de imposto \> Tabela de códigos de ajustes de INSS-CPRB**.</span><span class="sxs-lookup"><span data-stu-id="d291c-575">You configure the adjustment codes at **Fiscal books \> Setup \> Tax adjustment codes \> INSS-CPRB adjustments codes table**.</span></span>

1.  <span data-ttu-id="d291c-576">Selecione **Ajuste** para adicionar uma transação de ajuste que diminuirá ou aumentará o valor do imposto (débito) que é calculado.</span><span class="sxs-lookup"><span data-stu-id="d291c-576">Select **Adjustment** to add an adjustment transaction that will decrease or increase the tax amount (debit) that is calculated.</span></span>

2.  <span data-ttu-id="d291c-577">Selecione o código de ajuste.</span><span class="sxs-lookup"><span data-stu-id="d291c-577">Select the adjustment code.</span></span>

3.  <span data-ttu-id="d291c-578">Insira uma descrição da transação relacionada.</span><span class="sxs-lookup"><span data-stu-id="d291c-578">Enter a description of the related transaction.</span></span>

4.  <span data-ttu-id="d291c-579">Especifique o valor do ajuste e a atividade econômica.</span><span class="sxs-lookup"><span data-stu-id="d291c-579">Specify the adjustment amount and the economic activity.</span></span>

5.  <span data-ttu-id="d291c-580">Especifique a data do ajuste.</span><span class="sxs-lookup"><span data-stu-id="d291c-580">Specify the adjustment date.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-581">Os ajustes de INSS-CPRB estão disponíveis apenas por meio desse procedimento.</span><span class="sxs-lookup"><span data-stu-id="d291c-581">Adjustments for INSS-CPRB are available only through this procedure.</span></span> <span data-ttu-id="d291c-582">Esse tipo de ajuste não está disponível em **Livros fiscais \> Diários \> Ajuste geral de imposto/benefício/incentivo**.</span><span class="sxs-lookup"><span data-stu-id="d291c-582">This type of adjustment isn't available at **Fiscal books \> Journals \> General tax adjustment/benefit/incentive**.</span></span>

>   <span data-ttu-id="d291c-583">**Finalizar e reabrir**</span><span class="sxs-lookup"><span data-stu-id="d291c-583">**Finalize and Reopen**</span></span>

>   <span data-ttu-id="d291c-584">Você pode finalizar ou reabrir a apuração do imposto INSS-CPRB relacionada.</span><span class="sxs-lookup"><span data-stu-id="d291c-584">You can finalize or reopen the related INSS-CPRB tax assessment.</span></span>

>   <span data-ttu-id="d291c-585">Quando uma apuração do imposto INSS-CPRB é finalizada, nenhuma modificação é permitida nessa apuração para esse período, a menos que ela seja reaberta.</span><span class="sxs-lookup"><span data-stu-id="d291c-585">When an INSS-CPRB tax assessment is finalized, no modifications to the tax assessment are allowed for that period, unless the tax assessment is reopened.</span></span> <span data-ttu-id="d291c-586">Um comprovante é criado para lançar o imposto INSS-CPRB para coleta e as contas contábeis são definidas no lançamento contábil para o imposto INSS em **Imposto \> Configuração \> Imposto sobre vendas \> Grupos de lançamento contábil**.</span><span class="sxs-lookup"><span data-stu-id="d291c-586">A voucher is created to post the INSS-CPRB tax to collect, and the ledger accounts are defined in the ledger posting for INSS tax at **Tax \> Setup \> Sales tax \> Ledger posting groups**.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-587">Na atual arquitetura do SPED-Reinf definida pelo governo, o processo de pagamento e liquidação do passivo criado pela apuração de imposto será relatado a outro sistema chamado de DCTF Web.</span><span class="sxs-lookup"><span data-stu-id="d291c-587">In the current SPED-Reinf architecture that is defined by the government, the process for payment and settlement of the liability that is created by the tax assessment will be reported to another system that is named DCTF web.</span></span> <span data-ttu-id="d291c-588">Esse sistema consome a saída não apenas do SPED-Reinf, mas também de outros sistemas, como o eSocial e o PER/DCOMP.</span><span class="sxs-lookup"><span data-stu-id="d291c-588">This system consumes the output from not only the SPED-Reinf but also the other systems, such as eSocial and PER/DCOMP.</span></span> <span data-ttu-id="d291c-589">Portanto, o processo de pagamento atualmente está fora do escopo e é entregue por meio de outro recurso do Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="d291c-589">Therefore, the payment process is currently out of scope and is delivered through another Microsoft Dynamics feature.</span></span>

>   <span data-ttu-id="d291c-590">A ação de reabertura estará disponível se o evento R-2060 já tiver sido fechado para o estabelecimento fiscal matriz e se a apuração de imposto já estiver finalizada.</span><span class="sxs-lookup"><span data-stu-id="d291c-590">The reopen action is available if event R-2060 has already been closed for the root fiscal establishment, and if the tax assessment is already finalized.</span></span> <span data-ttu-id="d291c-591">A ação de reabertura reverte o comprovante anterior que foi gerado pela ação de fechamento.</span><span class="sxs-lookup"><span data-stu-id="d291c-591">The reopen action reverses the previous voucher that was generated by the closing action.</span></span>

> [!NOTE]
> <span data-ttu-id="d291c-592">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-592">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

### <a name="events-r-2090-closing-and-r-2098-reopen"></a><span data-ttu-id="d291c-593">**Eventos R-2090, "Fechamento" e R-2098, "Reabertura"**</span><span class="sxs-lookup"><span data-stu-id="d291c-593">**Events R-2090, "Closing," and R-2098, "Reopen"**</span></span>

<span data-ttu-id="d291c-594">**Fechamento**</span><span class="sxs-lookup"><span data-stu-id="d291c-594">**Closing**</span></span>

<span data-ttu-id="d291c-595">Os eventos periódicos R-2010, R-2010 e R-2060 devem ser fechados ao final de um período, quando não houver mais nenhuma transação a ser relatada nesse período.</span><span class="sxs-lookup"><span data-stu-id="d291c-595">Periodic events R-2010, R-2010, and R-2060 must be closed at the end of a period, when there are no more transactions to report in that period.</span></span>

#### <a name="repro-step"></a><span data-ttu-id="d291c-596">**Etapa de reprodução**</span><span class="sxs-lookup"><span data-stu-id="d291c-596">**Repro step**</span></span>

1.  <span data-ttu-id="d291c-597">Finalize a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="d291c-597">Finalize the INSS-CPRB tax assessment, even if you don't assess INSS-CPRB tax.</span></span>

2.  <span data-ttu-id="d291c-598">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-598">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

<span data-ttu-id="d291c-599">**Reabrir**</span><span class="sxs-lookup"><span data-stu-id="d291c-599">**Reopen**</span></span>

<span data-ttu-id="d291c-600">Depois que os eventos periódicos R-2010, R-2010 e R-2060 forem fechados por meio de um evento R-2099, eles poderão ser reabertos por meio de um evento R-2098.</span><span class="sxs-lookup"><span data-stu-id="d291c-600">After periodic events R-2010, R-2010, and R-2060 are closed through an event R-2099, they can be reopened through an event R-2098.</span></span> <span data-ttu-id="d291c-601">Você poderá então relatar novas transações ou modificar transações existentes para o período.</span><span class="sxs-lookup"><span data-stu-id="d291c-601">You can then report new transactions or modify existing transactions for the period.</span></span>

#### <a name="repro-step"></a><span data-ttu-id="d291c-602">**Etapa de reprodução**</span><span class="sxs-lookup"><span data-stu-id="d291c-602">**Repro step**</span></span>

1.  <span data-ttu-id="d291c-603">Reabra a apuração do imposto INSS-CPRB, mesmo que você não apure o imposto INSS-CPRB.</span><span class="sxs-lookup"><span data-stu-id="d291c-603">Reopen the INSS-CPRB tax assessment, even if you don't assess INSS-CPRB tax.</span></span>

2.  <span data-ttu-id="d291c-604">Siga as etapas descritas para o evento R-1000 a fim de inserir, atualizar ou cancelar o evento relacionado.</span><span class="sxs-lookup"><span data-stu-id="d291c-604">Follow the steps that are described for event R-1000 to insert, update, or cancel the related event.</span></span>

<span data-ttu-id="d291c-605">**Consultar evento 5011**</span><span class="sxs-lookup"><span data-stu-id="d291c-605">**Inquire event 5011**</span></span>

1.  <span data-ttu-id="d291c-606">Após a entrega do R-2090 ao governo e a atualização de seu status para **Aguardando resposta** (**Resposta pendente)**, selecione **Executar processamento** e, em seguida, selecione **SPED Reinf**.</span><span class="sxs-lookup"><span data-stu-id="d291c-606">After R-2090 is delivered to the government and its status is updated to **Pending Response** (**Pendente resposta**), select **Run processing**, and then select **SPED Reinf**.</span></span>

2.  <span data-ttu-id="d291c-607">Defina a opção **Escolher ação** como **Habilitar** e, em seguida, selecione a ação **Gerar** para gerar a mensagem XML.</span><span class="sxs-lookup"><span data-stu-id="d291c-607">Set the **Choose action** option to be **Enable** and select the action **Gerar** to generate the XML message.</span></span>

3.  <span data-ttu-id="d291c-608">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="d291c-608">Select **OK** to confirm the action.</span></span>

4.  <span data-ttu-id="d291c-609">Depois que o item de mensagem é criado, o tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Gerada**.</span><span class="sxs-lookup"><span data-stu-id="d291c-609">After the message item is created, the **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Consulta Gerada**.</span></span>

5.  <span data-ttu-id="d291c-610">Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.</span><span class="sxs-lookup"><span data-stu-id="d291c-610">Select **Run processing**, and then select **SPED Reinf** again.</span></span>

6.  <span data-ttu-id="d291c-611">Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Enviar consulta** para entregar a consulta relacionada às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="d291c-611">Set the **Choose action** option to be **Enable** and select the action **Enviar consulta** to deliver the related inquiry to the tax authorities.</span></span>

7.  <span data-ttu-id="d291c-612">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="d291c-612">Select **OK** to confirm the action.</span></span>

8.  <span data-ttu-id="d291c-613">O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Consulta Enviada**.</span><span class="sxs-lookup"><span data-stu-id="d291c-613">The **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Consulta Enviada**.</span></span>

9.  <span data-ttu-id="d291c-614">Selecione **Executar processamento** e, em seguida, selecione **SPED Reinf** novamente.</span><span class="sxs-lookup"><span data-stu-id="d291c-614">Select **Run processing**, and then select **SPED Reinf** again.</span></span>

10. <span data-ttu-id="d291c-615">Defina a opção **Escolher ação** como **Habilitar** e selecione a ação **Obter consulta resposta** para obter a aprovação da autoridade fiscal e o número do protocolo final, para poder fechar o período do SPED-Reinf.</span><span class="sxs-lookup"><span data-stu-id="d291c-615">Set the **Choose action** option to be **Enable** and select the action **Obter consulta resposta** to get the approval from the tax authority and the final protocol number, so that you can close the SPED-Reinf period.</span></span>

11. <span data-ttu-id="d291c-616">Selecione **OK** para confirmar a ação.</span><span class="sxs-lookup"><span data-stu-id="d291c-616">Select **OK** to confirm the action.</span></span>

12. <span data-ttu-id="d291c-617">O tipo de item de mensagem **Evento de fechamento** é atualizado e o status do item de mensagem é atualizado para **Aceito**.</span><span class="sxs-lookup"><span data-stu-id="d291c-617">The **Evento de fechamento** message item type is updated, and the status of the message item is updated to **Aceito**.</span></span>
