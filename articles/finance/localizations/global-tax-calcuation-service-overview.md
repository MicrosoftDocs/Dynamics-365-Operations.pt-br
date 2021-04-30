---
title: Cálculo de Imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: wangchen
ms.date: 04/12/2021
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892340"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="b1793-103">Cálculo de Imposto (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b1793-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="b1793-104">O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="b1793-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="b1793-105">O mecanismo de cálculo de imposto é totalmente configurável.</span><span class="sxs-lookup"><span data-stu-id="b1793-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="b1793-106">Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="b1793-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="b1793-107">O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="b1793-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="b1793-108">O Cálculo de Imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b1793-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b1793-109">Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b1793-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="b1793-110">O Cálculo de Imposto é um mecanismo de cálculo de imposto baseado em microsserviço que oferece escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="b1793-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="b1793-111">Ele pode ajudar você a executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="b1793-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="b1793-112">Configure o Cálculo de Imposto com o Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="b1793-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="b1793-113">O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="b1793-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="b1793-114">Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b1793-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="b1793-115">Configure a matriz de impostos para determinar o número de registro do imposto.</span><span class="sxs-lookup"><span data-stu-id="b1793-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="b1793-116">Configure o designer de cálculo de imposto para definir fórmulas e condições.</span><span class="sxs-lookup"><span data-stu-id="b1793-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="b1793-117">Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="b1793-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="b1793-118">Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b1793-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b1793-119">Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b1793-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="b1793-120">Para obter mais informações, consulte [Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="b1793-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="b1793-121">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b1793-121">Availability</span></span>

<span data-ttu-id="b1793-122">O Cálculo de Imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="b1793-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="b1793-123">Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="b1793-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="b1793-124">Novos recursos continuarão a ser entregues; portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="b1793-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="b1793-125">O Cálculo de Imposto é implantado nas regiões do Azure a seguir.</span><span class="sxs-lookup"><span data-stu-id="b1793-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="b1793-126">Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:</span><span class="sxs-lookup"><span data-stu-id="b1793-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="b1793-127">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="b1793-127">United States</span></span>
- <span data-ttu-id="b1793-128">Europa</span><span class="sxs-lookup"><span data-stu-id="b1793-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="b1793-129">O Cálculo de Imposto não é compatível com implantações locais do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1793-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="b1793-130">Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="b1793-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="b1793-131">Destaques do recurso</span><span class="sxs-lookup"><span data-stu-id="b1793-131">Feature highlights</span></span>

- <span data-ttu-id="b1793-132">Uma matriz de impostos configurável para determinar e calcular impostos automaticamente</span><span class="sxs-lookup"><span data-stu-id="b1793-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="b1793-133">Suporte para vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="b1793-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="b1793-134">Suporte para ordem de transferência de determinação e cálculo de imposto</span><span class="sxs-lookup"><span data-stu-id="b1793-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="b1793-135">Suporte para ordem de transferência para a determinação de vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="b1793-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="b1793-136">Transações com suporte</span><span class="sxs-lookup"><span data-stu-id="b1793-136">Supported transactions</span></span>

<span data-ttu-id="b1793-137">O Cálculo de Imposto pode ser habilitado por entidade legal e transação.</span><span class="sxs-lookup"><span data-stu-id="b1793-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="b1793-138">As seguintes transações são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="b1793-138">The following transactions are supported:</span></span>

- <span data-ttu-id="b1793-139">Processo de Vendas</span><span class="sxs-lookup"><span data-stu-id="b1793-139">Sales process</span></span>

    - <span data-ttu-id="b1793-140">Cotação de Venda</span><span class="sxs-lookup"><span data-stu-id="b1793-140">Sales quotation</span></span>
    - <span data-ttu-id="b1793-141">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="b1793-141">Sales order</span></span>
    - <span data-ttu-id="b1793-142">Confirmação</span><span class="sxs-lookup"><span data-stu-id="b1793-142">Confirmation</span></span>
    - <span data-ttu-id="b1793-143">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="b1793-143">Picking list</span></span>
    - <span data-ttu-id="b1793-144">Guia de Remessa</span><span class="sxs-lookup"><span data-stu-id="b1793-144">Packing slip</span></span>
    - <span data-ttu-id="b1793-145">Fatura de venda</span><span class="sxs-lookup"><span data-stu-id="b1793-145">Sales invoice</span></span>
    - <span data-ttu-id="b1793-146">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="b1793-146">Credit note</span></span>
    - <span data-ttu-id="b1793-147">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="b1793-147">Return order</span></span>
    - <span data-ttu-id="b1793-148">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="b1793-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="b1793-149">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="b1793-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="b1793-150">Processo de compra</span><span class="sxs-lookup"><span data-stu-id="b1793-150">Purchase process</span></span>

    - <span data-ttu-id="b1793-151">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="b1793-151">Purchase order</span></span>
    - <span data-ttu-id="b1793-152">Confirmação</span><span class="sxs-lookup"><span data-stu-id="b1793-152">Confirmation</span></span>
    - <span data-ttu-id="b1793-153">Lista de Recebimentos</span><span class="sxs-lookup"><span data-stu-id="b1793-153">Receipts list</span></span>
    - <span data-ttu-id="b1793-154">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="b1793-154">Product receipt</span></span>
    - <span data-ttu-id="b1793-155">Fatura de compra</span><span class="sxs-lookup"><span data-stu-id="b1793-155">Purchase invoice</span></span>
    - <span data-ttu-id="b1793-156">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="b1793-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="b1793-157">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="b1793-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="b1793-158">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="b1793-158">Credit note</span></span>
    - <span data-ttu-id="b1793-159">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="b1793-159">Return order</span></span>
    - <span data-ttu-id="b1793-160">Requisição de Compra</span><span class="sxs-lookup"><span data-stu-id="b1793-160">Purchase requisition</span></span>
    - <span data-ttu-id="b1793-161">Encargos diversos da linha de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="b1793-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="b1793-162">Solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="b1793-162">Request for quotation</span></span>
    - <span data-ttu-id="b1793-163">Encargos diversos do cabeçalho da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="b1793-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="b1793-164">Encargos diversos da linha da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="b1793-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="b1793-165">Processo de estoque</span><span class="sxs-lookup"><span data-stu-id="b1793-165">Inventory process</span></span>

    - <span data-ttu-id="b1793-166">Ordem de transferência – enviar</span><span class="sxs-lookup"><span data-stu-id="b1793-166">Transfer order – ship</span></span>
    - <span data-ttu-id="b1793-167">Ordem de transferência – receber</span><span class="sxs-lookup"><span data-stu-id="b1793-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="b1793-168">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="b1793-168">Related resources</span></span>

[<span data-ttu-id="b1793-169">Introdução ao serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="b1793-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="b1793-170">Vários números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="b1793-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="b1793-171">Suporte ao recurso de imposto para a ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="b1793-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="b1793-172">Como criar uma extensão no serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="b1793-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)