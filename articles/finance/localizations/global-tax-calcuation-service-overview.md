---
title: Cálculo de Imposto (Versão preliminar)
description: Este tópico explica o escopo geral e os recursos do recurso Cálculo de Imposto.
author: wangchen
ms.date: 06/03/2021
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
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184092"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="fb186-103">Cálculo de Imposto (Versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="fb186-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="fb186-104">O Cálculo de Imposto é um serviço multilocatário hiperescalável que permite que o Global Tax Engine automatize e simplifique o processo de determinação e cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="fb186-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="fb186-105">O mecanismo de cálculo de imposto é totalmente configurável.</span><span class="sxs-lookup"><span data-stu-id="fb186-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="fb186-106">Os elementos que podem ser configurados incluem, entre outros, o modelo de dados tributável, o código de imposto, a matriz de aplicabilidade do imposto e a fórmula de cálculo do imposto.</span><span class="sxs-lookup"><span data-stu-id="fb186-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="fb186-107">O mecanismo de cálculo de imposto é executado na plataforma de serviços principais do Microsoft Azure e oferece tecnologia moderna e escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="fb186-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="fb186-108">O Cálculo de Imposto é integrado ao Dynamics 365 Finance e ao Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fb186-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="fb186-109">Futuramente, também será integrado ao Dynamics 365 Project Operations, Dynamics 365 Commerce e a outros aplicativos próprios e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fb186-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb186-110">Ao habilitar o serviço de cálculo de imposto, algumas operações em dados relacionados podem ser executadas em um data center diferente do data center que mantém os dados do serviço.</span><span class="sxs-lookup"><span data-stu-id="fb186-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="fb186-111">Revise os [Termos e Condições](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) antes de habilitar o serviço de cálculo de imposto.</span><span class="sxs-lookup"><span data-stu-id="fb186-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="fb186-112">Sua privacidade é importante para nós.</span><span class="sxs-lookup"><span data-stu-id="fb186-112">Your privacy is important to us.</span></span> <span data-ttu-id="fb186-113">Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="fb186-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="fb186-114">O Cálculo de Imposto é um mecanismo de cálculo de imposto baseado em microsserviço que oferece escalabilidade exponencial.</span><span class="sxs-lookup"><span data-stu-id="fb186-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="fb186-115">Ele pode ajudar você a executar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="fb186-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="fb186-116">Configure o Cálculo de Imposto com o Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="fb186-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="fb186-117">O RCS é uma versão aprimorada do designer do Relatório eletrônico (ER) e está disponível como serviço autônomo.</span><span class="sxs-lookup"><span data-stu-id="fb186-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="fb186-118">Configure a matriz de impostos para determinar os códigos e as taxas de impostos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fb186-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="fb186-119">Configure a matriz de impostos para determinar o número de registro do imposto.</span><span class="sxs-lookup"><span data-stu-id="fb186-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="fb186-120">Configure o designer de cálculo de imposto para definir fórmulas e condições.</span><span class="sxs-lookup"><span data-stu-id="fb186-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="fb186-121">Compartilhe a determinação e solução de cálculo de imposto nas entidades legais.</span><span class="sxs-lookup"><span data-stu-id="fb186-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="fb186-122">Para usar o serviço de cálculo de imposto, instale o suplemento do serviço de cálculo de imposto do projeto no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="fb186-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="fb186-123">Em seguida, conclua a configuração no RCS e habilite o serviço de cálculo de imposto no Finance e no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fb186-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="fb186-124">Para obter mais informações, consulte [Introdução ao serviço de imposto](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="fb186-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="fb186-125">Disponibilidade</span><span class="sxs-lookup"><span data-stu-id="fb186-125">Availability</span></span>

<span data-ttu-id="fb186-126">O Cálculo de Imposto está disponível somente em ambientes de área restrita e para alguns clientes, por meio de um programa de versão preliminar pública.</span><span class="sxs-lookup"><span data-stu-id="fb186-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="fb186-127">Futuramente, ele será disponibilizado de modo geral para todos os clientes e em ambientes de produção.</span><span class="sxs-lookup"><span data-stu-id="fb186-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="fb186-128">Novos recursos continuarão a ser entregues; portanto, verifique a documentação mais recente para saber mais sobre a cobertura e o escopo dos recursos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="fb186-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="fb186-129">O Cálculo de Imposto é implantado nas regiões do Azure a seguir.</span><span class="sxs-lookup"><span data-stu-id="fb186-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="fb186-130">Ele também será implantado em mais regiões do Azure, de acordo com as necessidades dos clientes:</span><span class="sxs-lookup"><span data-stu-id="fb186-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="fb186-131">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="fb186-131">United States</span></span>
- <span data-ttu-id="fb186-132">Europa</span><span class="sxs-lookup"><span data-stu-id="fb186-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="fb186-133">O Cálculo de Imposto não é compatível com implantações locais do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="fb186-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="fb186-134">Ele também não oferece suporte a versões anteriores, como o Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="fb186-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="fb186-135">Destaques do recurso</span><span class="sxs-lookup"><span data-stu-id="fb186-135">Feature highlights</span></span>

- <span data-ttu-id="fb186-136">Uma matriz de impostos configurável para determinar e calcular impostos automaticamente</span><span class="sxs-lookup"><span data-stu-id="fb186-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="fb186-137">Suporte para vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="fb186-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="fb186-138">Suporte para ordem de transferência de determinação e cálculo de imposto</span><span class="sxs-lookup"><span data-stu-id="fb186-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="fb186-139">Suporte para ordem de transferência para a determinação de vários números de registro de imposto</span><span class="sxs-lookup"><span data-stu-id="fb186-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="fb186-140">Transações com suporte</span><span class="sxs-lookup"><span data-stu-id="fb186-140">Supported transactions</span></span>

<span data-ttu-id="fb186-141">O Cálculo de Imposto pode ser habilitado por entidade legal e transação.</span><span class="sxs-lookup"><span data-stu-id="fb186-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="fb186-142">As seguintes transações são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="fb186-142">The following transactions are supported:</span></span>

- <span data-ttu-id="fb186-143">Processo de Vendas</span><span class="sxs-lookup"><span data-stu-id="fb186-143">Sales process</span></span>

    - <span data-ttu-id="fb186-144">Cotação de Venda</span><span class="sxs-lookup"><span data-stu-id="fb186-144">Sales quotation</span></span>
    - <span data-ttu-id="fb186-145">Ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="fb186-145">Sales order</span></span>
    - <span data-ttu-id="fb186-146">Confirmação</span><span class="sxs-lookup"><span data-stu-id="fb186-146">Confirmation</span></span>
    - <span data-ttu-id="fb186-147">Lista de Separação</span><span class="sxs-lookup"><span data-stu-id="fb186-147">Picking list</span></span>
    - <span data-ttu-id="fb186-148">Guia de Remessa</span><span class="sxs-lookup"><span data-stu-id="fb186-148">Packing slip</span></span>
    - <span data-ttu-id="fb186-149">Fatura de venda</span><span class="sxs-lookup"><span data-stu-id="fb186-149">Sales invoice</span></span>
    - <span data-ttu-id="fb186-150">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="fb186-150">Credit note</span></span>
    - <span data-ttu-id="fb186-151">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="fb186-151">Return order</span></span>
    - <span data-ttu-id="fb186-152">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fb186-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="fb186-153">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="fb186-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="fb186-154">Processo de compra</span><span class="sxs-lookup"><span data-stu-id="fb186-154">Purchase process</span></span>

    - <span data-ttu-id="fb186-155">Ordem de Compra</span><span class="sxs-lookup"><span data-stu-id="fb186-155">Purchase order</span></span>
    - <span data-ttu-id="fb186-156">Confirmação</span><span class="sxs-lookup"><span data-stu-id="fb186-156">Confirmation</span></span>
    - <span data-ttu-id="fb186-157">Lista de Recebimentos</span><span class="sxs-lookup"><span data-stu-id="fb186-157">Receipts list</span></span>
    - <span data-ttu-id="fb186-158">Recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="fb186-158">Product receipt</span></span>
    - <span data-ttu-id="fb186-159">Fatura de compra</span><span class="sxs-lookup"><span data-stu-id="fb186-159">Purchase invoice</span></span>
    - <span data-ttu-id="fb186-160">Encargos diversos do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="fb186-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="fb186-161">Encargos diversos da linha</span><span class="sxs-lookup"><span data-stu-id="fb186-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="fb186-162">Nota de Crédito</span><span class="sxs-lookup"><span data-stu-id="fb186-162">Credit note</span></span>
    - <span data-ttu-id="fb186-163">Ordem de retorno</span><span class="sxs-lookup"><span data-stu-id="fb186-163">Return order</span></span>
    - <span data-ttu-id="fb186-164">Requisição de Compra</span><span class="sxs-lookup"><span data-stu-id="fb186-164">Purchase requisition</span></span>
    - <span data-ttu-id="fb186-165">Encargos diversos da linha de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="fb186-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="fb186-166">Solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="fb186-166">Request for quotation</span></span>
    - <span data-ttu-id="fb186-167">Encargos diversos do cabeçalho da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="fb186-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="fb186-168">Encargos diversos da linha da solicitação de cotação</span><span class="sxs-lookup"><span data-stu-id="fb186-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="fb186-169">Processo de estoque</span><span class="sxs-lookup"><span data-stu-id="fb186-169">Inventory process</span></span>

    - <span data-ttu-id="fb186-170">Ordem de transferência – enviar</span><span class="sxs-lookup"><span data-stu-id="fb186-170">Transfer order – ship</span></span>
    - <span data-ttu-id="fb186-171">Ordem de transferência – receber</span><span class="sxs-lookup"><span data-stu-id="fb186-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="fb186-172">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="fb186-172">Related resources</span></span>

[<span data-ttu-id="fb186-173">Introdução ao serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="fb186-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="fb186-174">Vários números de registro de IVA</span><span class="sxs-lookup"><span data-stu-id="fb186-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="fb186-175">Suporte ao recurso de imposto para a ordem de transferência</span><span class="sxs-lookup"><span data-stu-id="fb186-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="fb186-176">Como criar uma extensão no serviço de imposto</span><span class="sxs-lookup"><span data-stu-id="fb186-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
