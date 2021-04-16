---
title: Serviço de cálculo de imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do serviço de cálculo de imposto.
author: wangchen
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818215"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="2f907-103">Serviço de cálculo de imposto (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="2f907-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="2f907-104">O serviço de cálculo de imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="2f907-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="2f907-105">O mecanismo de cálculo de imposto é totalmente configurável.</span><span class="sxs-lookup"><span data-stu-id="2f907-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="2f907-106">Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="2f907-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="2f907-107">O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="2f907-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="2f907-108">O serviço de cálculo de imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2f907-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="2f907-109">Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="2f907-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="2f907-110">O serviço de cálculo de imposto é um mecanismo de cálculo de imposto baseado na Microsoft que oferece escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="2f907-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="2f907-111">Ele pode ajudar você a executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="2f907-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="2f907-112">Configure o serviço de cálculo de imposto com o Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="2f907-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="2f907-113">O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="2f907-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="2f907-114">Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f907-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="2f907-115">Configure a matriz de impostos para determinar o número de registro do imposto.</span><span class="sxs-lookup"><span data-stu-id="2f907-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="2f907-116">Configure o designer de cálculo de imposto para definir fórmulas e condições.</span><span class="sxs-lookup"><span data-stu-id="2f907-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="2f907-117">Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="2f907-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="2f907-118">Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="2f907-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="2f907-119">Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2f907-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="2f907-120">Para obter mais informações, consulte [Introdução ao serviço de imposto](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="2f907-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="2f907-121">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="2f907-121">Availability</span></span>

<span data-ttu-id="2f907-122">O serviço de cálculo de imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="2f907-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="2f907-123">Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="2f907-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="2f907-124">Novos recursos continuarão sendo entregues no serviço de cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="2f907-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="2f907-125">Portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="2f907-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="2f907-126">O serviço de cálculo de imposto é implantado nas seguintes regiões do Azure.</span><span class="sxs-lookup"><span data-stu-id="2f907-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="2f907-127">Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:</span><span class="sxs-lookup"><span data-stu-id="2f907-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="2f907-128">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="2f907-128">United States</span></span>
- <span data-ttu-id="2f907-129">Europa</span><span class="sxs-lookup"><span data-stu-id="2f907-129">Europe</span></span>
- <span data-ttu-id="2f907-130">França</span><span class="sxs-lookup"><span data-stu-id="2f907-130">France</span></span>
- <span data-ttu-id="2f907-131">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="2f907-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="2f907-132">O serviço de cálculo de imposto não é compatível com implantações locais do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2f907-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="2f907-133">Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="2f907-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="2f907-134">Destaques do recurso</span><span class="sxs-lookup"><span data-stu-id="2f907-134">Feature highlights</span></span>

- <span data-ttu-id="2f907-135">Uma matriz de impostos configurável para determinar e calcular impostos automaticamente</span><span class="sxs-lookup"><span data-stu-id="2f907-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="2f907-136">Suporte para vários números de registro de imposto sobre valor agregado (IVA)</span><span class="sxs-lookup"><span data-stu-id="2f907-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="2f907-137">Suporte para ordem de transferência de determinação e cálculo de imposto</span><span class="sxs-lookup"><span data-stu-id="2f907-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="2f907-138">Suporte para ordem de transferência para a determinação de vários números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="2f907-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="2f907-139">Transações com suporte</span><span class="sxs-lookup"><span data-stu-id="2f907-139">Supported transactions</span></span>

<span data-ttu-id="2f907-140">O serviço de cálculo de imposto pode ser habilitado por entidade legal e transação.</span><span class="sxs-lookup"><span data-stu-id="2f907-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="2f907-141">As seguintes transações são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="2f907-141">The following transactions are supported:</span></span>

- <span data-ttu-id="2f907-142">Processo de Vendas</span><span class="sxs-lookup"><span data-stu-id="2f907-142">Sales process</span></span>

    - <span data-ttu-id="2f907-143">Cotação de Venda</span><span class="sxs-lookup"><span data-stu-id="2f907-143">Sales quotation</span></span>
    - <span data-ttu-id="2f907-144">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="2f907-144">Sales order</span></span>
    - <span data-ttu-id="2f907-145">Confirmação</span><span class="sxs-lookup"><span data-stu-id="2f907-145">Confirmation</span></span>
    - <span data-ttu-id="2f907-146">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="2f907-146">Picking list</span></span>
    - <span data-ttu-id="2f907-147">Guia de Remessa</span><span class="sxs-lookup"><span data-stu-id="2f907-147">Packing slip</span></span>
    - <span data-ttu-id="2f907-148">Fatura de venda</span><span class="sxs-lookup"><span data-stu-id="2f907-148">Sales invoice</span></span>
    - <span data-ttu-id="2f907-149">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="2f907-149">Credit note</span></span>
    - <span data-ttu-id="2f907-150">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="2f907-150">Return order</span></span>
    - <span data-ttu-id="2f907-151">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2f907-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2f907-152">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="2f907-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="2f907-153">Processo de compra</span><span class="sxs-lookup"><span data-stu-id="2f907-153">Purchase process</span></span>

    - <span data-ttu-id="2f907-154">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="2f907-154">Purchase order</span></span>
    - <span data-ttu-id="2f907-155">Confirmação</span><span class="sxs-lookup"><span data-stu-id="2f907-155">Confirmation</span></span>
    - <span data-ttu-id="2f907-156">Lista de Recebimentos</span><span class="sxs-lookup"><span data-stu-id="2f907-156">Receipts list</span></span>
    - <span data-ttu-id="2f907-157">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="2f907-157">Product receipt</span></span>
    - <span data-ttu-id="2f907-158">Fatura de compra</span><span class="sxs-lookup"><span data-stu-id="2f907-158">Purchase invoice</span></span>
    - <span data-ttu-id="2f907-159">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2f907-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="2f907-160">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="2f907-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="2f907-161">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="2f907-161">Credit note</span></span>
    - <span data-ttu-id="2f907-162">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="2f907-162">Return order</span></span>
    - <span data-ttu-id="2f907-163">Requisição de Compra</span><span class="sxs-lookup"><span data-stu-id="2f907-163">Purchase requisition</span></span>
    - <span data-ttu-id="2f907-164">Encargos diversos da linha de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="2f907-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="2f907-165">Solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="2f907-165">Request for quotation</span></span>
    - <span data-ttu-id="2f907-166">Encargos diversos do cabeçalho da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="2f907-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="2f907-167">Encargos diversos da linha da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="2f907-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="2f907-168">Processo de estoque</span><span class="sxs-lookup"><span data-stu-id="2f907-168">Inventory process</span></span>

    - <span data-ttu-id="2f907-169">Ordem de transferência – enviar</span><span class="sxs-lookup"><span data-stu-id="2f907-169">Transfer order – ship</span></span>
    - <span data-ttu-id="2f907-170">Ordem de transferência – receber</span><span class="sxs-lookup"><span data-stu-id="2f907-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="2f907-171">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f907-171">Related resources</span></span>

[<span data-ttu-id="2f907-172">Introdução ao serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="2f907-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="2f907-173">Vários números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="2f907-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="2f907-174">Suporte ao recurso de imposto para a ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="2f907-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="2f907-175">Como criar uma extensão no serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="2f907-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
