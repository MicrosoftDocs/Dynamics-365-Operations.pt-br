---
title: Cálculo de Imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b26472e195d9bdbba340a118c106de1a4dc79b34
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021923"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="db3a4-103">Cálculo de Imposto (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="db3a4-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="db3a4-104">O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="db3a4-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="db3a4-105">O mecanismo de cálculo de imposto é totalmente configurável.</span><span class="sxs-lookup"><span data-stu-id="db3a4-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="db3a4-106">Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="db3a4-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="db3a4-107">O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="db3a4-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="db3a4-108">O Cálculo de Imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="db3a4-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="db3a4-109">Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="db3a4-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="db3a4-110">O Cálculo de Imposto é um mecanismo de cálculo de imposto baseado em microsserviço que oferece escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="db3a4-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="db3a4-111">Ele pode ajudar você a executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="db3a4-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="db3a4-112">Configure o Cálculo de Imposto com o Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="db3a4-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="db3a4-113">O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="db3a4-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="db3a4-114">Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="db3a4-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="db3a4-115">Configure a matriz de impostos para determinar o número de registro do imposto.</span><span class="sxs-lookup"><span data-stu-id="db3a4-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="db3a4-116">Configure o designer de cálculo de imposto para definir fórmulas e condições.</span><span class="sxs-lookup"><span data-stu-id="db3a4-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="db3a4-117">Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="db3a4-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="db3a4-118">Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="db3a4-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="db3a4-119">Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="db3a4-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="db3a4-120">Para obter mais informações, consulte [Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="db3a4-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="db3a4-121">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="db3a4-121">Availability</span></span>

<span data-ttu-id="db3a4-122">O Cálculo de Imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="db3a4-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="db3a4-123">Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="db3a4-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="db3a4-124">Novos recursos continuarão a ser entregues; portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="db3a4-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="db3a4-125">O Cálculo de Imposto é implantado nas regiões do Azure a seguir.</span><span class="sxs-lookup"><span data-stu-id="db3a4-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="db3a4-126">Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:</span><span class="sxs-lookup"><span data-stu-id="db3a4-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="db3a4-127">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="db3a4-127">United States</span></span>
- <span data-ttu-id="db3a4-128">Europa</span><span class="sxs-lookup"><span data-stu-id="db3a4-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="db3a4-129">O Cálculo de Imposto não é compatível com implantações locais do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="db3a4-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="db3a4-130">Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="db3a4-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="db3a4-131">Destaques do recurso</span><span class="sxs-lookup"><span data-stu-id="db3a4-131">Feature highlights</span></span>

- <span data-ttu-id="db3a4-132">Uma matriz de impostos configurável para determinar e calcular impostos automaticamente</span><span class="sxs-lookup"><span data-stu-id="db3a4-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="db3a4-133">Suporte para vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="db3a4-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="db3a4-134">Suporte para ordem de transferência de determinação e cálculo de imposto</span><span class="sxs-lookup"><span data-stu-id="db3a4-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="db3a4-135">Suporte para ordem de transferência para a determinação de vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="db3a4-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="db3a4-136">Transações com suporte</span><span class="sxs-lookup"><span data-stu-id="db3a4-136">Supported transactions</span></span>

<span data-ttu-id="db3a4-137">O Cálculo de Imposto pode ser habilitado por entidade legal e transação.</span><span class="sxs-lookup"><span data-stu-id="db3a4-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="db3a4-138">As seguintes transações são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="db3a4-138">The following transactions are supported:</span></span>

- <span data-ttu-id="db3a4-139">Processo de Vendas</span><span class="sxs-lookup"><span data-stu-id="db3a4-139">Sales process</span></span>

    - <span data-ttu-id="db3a4-140">Cotação de Venda</span><span class="sxs-lookup"><span data-stu-id="db3a4-140">Sales quotation</span></span>
    - <span data-ttu-id="db3a4-141">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="db3a4-141">Sales order</span></span>
    - <span data-ttu-id="db3a4-142">Confirmação</span><span class="sxs-lookup"><span data-stu-id="db3a4-142">Confirmation</span></span>
    - <span data-ttu-id="db3a4-143">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="db3a4-143">Picking list</span></span>
    - <span data-ttu-id="db3a4-144">Guia de Remessa</span><span class="sxs-lookup"><span data-stu-id="db3a4-144">Packing slip</span></span>
    - <span data-ttu-id="db3a4-145">Fatura de venda</span><span class="sxs-lookup"><span data-stu-id="db3a4-145">Sales invoice</span></span>
    - <span data-ttu-id="db3a4-146">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="db3a4-146">Credit note</span></span>
    - <span data-ttu-id="db3a4-147">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="db3a4-147">Return order</span></span>
    - <span data-ttu-id="db3a4-148">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="db3a4-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="db3a4-149">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="db3a4-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="db3a4-150">Processo de compra</span><span class="sxs-lookup"><span data-stu-id="db3a4-150">Purchase process</span></span>

    - <span data-ttu-id="db3a4-151">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="db3a4-151">Purchase order</span></span>
    - <span data-ttu-id="db3a4-152">Confirmação</span><span class="sxs-lookup"><span data-stu-id="db3a4-152">Confirmation</span></span>
    - <span data-ttu-id="db3a4-153">Lista de Recebimentos</span><span class="sxs-lookup"><span data-stu-id="db3a4-153">Receipts list</span></span>
    - <span data-ttu-id="db3a4-154">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="db3a4-154">Product receipt</span></span>
    - <span data-ttu-id="db3a4-155">Fatura de compra</span><span class="sxs-lookup"><span data-stu-id="db3a4-155">Purchase invoice</span></span>
    - <span data-ttu-id="db3a4-156">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="db3a4-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="db3a4-157">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="db3a4-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="db3a4-158">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="db3a4-158">Credit note</span></span>
    - <span data-ttu-id="db3a4-159">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="db3a4-159">Return order</span></span>
    - <span data-ttu-id="db3a4-160">Requisição de Compra</span><span class="sxs-lookup"><span data-stu-id="db3a4-160">Purchase requisition</span></span>
    - <span data-ttu-id="db3a4-161">Encargos diversos da linha de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="db3a4-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="db3a4-162">Solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="db3a4-162">Request for quotation</span></span>
    - <span data-ttu-id="db3a4-163">Encargos diversos do cabeçalho da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="db3a4-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="db3a4-164">Encargos diversos da linha da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="db3a4-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="db3a4-165">Processo de estoque</span><span class="sxs-lookup"><span data-stu-id="db3a4-165">Inventory process</span></span>

    - <span data-ttu-id="db3a4-166">Ordem de transferência – enviar</span><span class="sxs-lookup"><span data-stu-id="db3a4-166">Transfer order – ship</span></span>
    - <span data-ttu-id="db3a4-167">Ordem de transferência – receber</span><span class="sxs-lookup"><span data-stu-id="db3a4-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="db3a4-168">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="db3a4-168">Related resources</span></span>

[<span data-ttu-id="db3a4-169">Introdução ao serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="db3a4-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="db3a4-170">Vários números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="db3a4-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="db3a4-171">Suporte ao recurso de imposto para a ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="db3a4-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="db3a4-172">Como criar uma extensão no serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="db3a4-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)