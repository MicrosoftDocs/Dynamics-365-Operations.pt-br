---
title: Aprovações de fatura móvel
description: Este tópico tem como objetivo fornecer uma abordagem prática para criar cenários móveis tirando aprovações da fatura de fornecedor do celular como um caso de uso.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5d3b85e076292b9d41de6a4cf3198ed9b38d27c8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828025"
---
# <a name="mobile-invoice-approvals"></a><span data-ttu-id="aed4d-103">Aprovações de fatura móvel</span><span class="sxs-lookup"><span data-stu-id="aed4d-103">Mobile invoice approvals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="aed4d-104">Os recursos móveis permitem que um usuário corporativo crie experiências móveis.</span><span class="sxs-lookup"><span data-stu-id="aed4d-104">Mobile capabilities let a business user design mobile experiences.</span></span> <span data-ttu-id="aed4d-105">Para cenários avançados, a plataforma também permite que os desenvolvedores estendam as funcionalidades que desejam.</span><span class="sxs-lookup"><span data-stu-id="aed4d-105">For advanced scenarios, the platform also lets developers extend the capabilities as they desire.</span></span> <span data-ttu-id="aed4d-106">A maneira mais eficaz de aprender alguns dos novos conceitos em dispositivo móvel é passar pelo processo de desenvolvimento de alguns cenários.</span><span class="sxs-lookup"><span data-stu-id="aed4d-106">The most effective way to learn some of the new concepts on mobile is to go through the process of designing a few scenarios.</span></span> <span data-ttu-id="aed4d-107">Este tópico tem como objetivo fornecer uma abordagem prática para criar cenários móveis tirando aprovações da fatura de fornecedor do celular como um caso de uso.</span><span class="sxs-lookup"><span data-stu-id="aed4d-107">This topic is intended to provide a practical approach to designing mobile scenarios by taking vendor invoice approvals for mobile as a use case.</span></span> <span data-ttu-id="aed4d-108">Esse tópico deve ajudá-lo a criar outras variações de cenários e também pode ser aplicado a outros cenários que não são relacionados a faturas de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="aed4d-108">This topic should help you design other variations of the scenarios and can also be applied to other scenarios that aren’t related to vendor invoices.</span></span>

<a name="prerequisites"></a><span data-ttu-id="aed4d-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="aed4d-109">Prerequisites</span></span>
-------------

| <span data-ttu-id="aed4d-110">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="aed4d-110">Prerequisite</span></span>                                                                                            | <span data-ttu-id="aed4d-111">descrição</span><span class="sxs-lookup"><span data-stu-id="aed4d-111">Description</span></span>                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="aed4d-112">Pré-leitura do manual móvel</span><span class="sxs-lookup"><span data-stu-id="aed4d-112">Mobile handbook pre-read</span></span>                                                                                |[<span data-ttu-id="aed4d-113">Plataforma móvel</span><span class="sxs-lookup"><span data-stu-id="aed4d-113">Mobile platform</span></span>](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| <span data-ttu-id="aed4d-114">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="aed4d-114">Dynamics 365 Finance</span></span>                                                                              | <span data-ttu-id="aed4d-115">Um ambiente com a versão 1611 e a Platform update 3 (novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="aed4d-115">An environment that has version 1611 and Platform update 3 (November 2016)</span></span>                   |
| <span data-ttu-id="aed4d-116">Instalar hotfix KB 3204341.</span><span class="sxs-lookup"><span data-stu-id="aed4d-116">Install hotfix KB 3204341.</span></span>                                                                              | <span data-ttu-id="aed4d-117">O gravador de tarefas pode registrar erroneamente dois comandos Fechar para caixas de diálogo suspensas; isso está incluído na Platform update 3 (atualização de novembro de 2016).</span><span class="sxs-lookup"><span data-stu-id="aed4d-117">Task recorder can erroneously record two Close commands for dropdown dialogs; this is included in Platform update 3 (November 2016 update).</span></span> |
| <span data-ttu-id="aed4d-118">Instalar hotfix KB 3207800.</span><span class="sxs-lookup"><span data-stu-id="aed4d-118">Install hotfix KB 3207800.</span></span>                                                                              | <span data-ttu-id="aed4d-119">Este hotfix habilita a exibição de anexos no cliente móvel; isso está incluído na Platform update 3 (atualização de novembro de 2016).</span><span class="sxs-lookup"><span data-stu-id="aed4d-119">This hotfix enables attachments to be viewed on the mobile client; this is included in Platform update 3 (November 2016 update).</span></span>           |
| <span data-ttu-id="aed4d-120">Instalar hotfix KB 3208224.</span><span class="sxs-lookup"><span data-stu-id="aed4d-120">Install hotfix KB 3208224.</span></span>                                                                              | <span data-ttu-id="aed4d-121">Código do aplicativo para o aplicativo móvel de aprovação de fatura de fornecedor; isso está incluído na versão 7.0.1 (maio de 2016).</span><span class="sxs-lookup"><span data-stu-id="aed4d-121">Application code for the mobile vendor invoice approval application; this is included in version 7.0.1 (May 2016).</span></span>                          |
| <span data-ttu-id="aed4d-122">Um dispositivo Android, iOS ou Windows que tenha o aplicativo móvel instalado.</span><span class="sxs-lookup"><span data-stu-id="aed4d-122">An Android or iOS or a Windows device that has the mobile app installed.</span></span> | <span data-ttu-id="aed4d-123">Procurar pelo aplicativo na loja de aplicativo apropriada.</span><span class="sxs-lookup"><span data-stu-id="aed4d-123">Search for the app in the appropriate app store.</span></span>                                                                                                                     |

## <a name="introduction"></a><span data-ttu-id="aed4d-124">Apresentação</span><span class="sxs-lookup"><span data-stu-id="aed4d-124">Introduction</span></span>
<span data-ttu-id="aed4d-125">Aprovações móveis para faturas de fornecedor exigem os três hotfixes mencionados na seção "Pré-requisitos".</span><span class="sxs-lookup"><span data-stu-id="aed4d-125">Mobile approvals for vendor invoices require the three hotfixes that are mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="aed4d-126">Esses hotfixes não fornecem um espaço de trabalho para as aprovações de fatura.</span><span class="sxs-lookup"><span data-stu-id="aed4d-126">These hotfixes don’t provide a workspace for the invoice approvals.</span></span> <span data-ttu-id="aed4d-127">Para saber o que é um espaço de trabalho no contexto de dispositivo móvel, leia o manual do dispositivo mencionado na seção “Pré-requisitos”.</span><span class="sxs-lookup"><span data-stu-id="aed4d-127">To learn what a workspace is in the context of mobile, read the mobile handbook that is mentioned in the “Prerequisites” section.</span></span> <span data-ttu-id="aed4d-128">O espaço de trabalho das aprovações de fatura deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="aed4d-128">The invoice approvals workspace must be designed.</span></span> 

<span data-ttu-id="aed4d-129">Cada organização orquestra e define seu processo comercial para faturas de fornecedor de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-129">Every organization orchestrates and defines its business process for vendor invoices differently.</span></span> <span data-ttu-id="aed4d-130">Antes de criar uma experiência móvel para aprovações da fatura de fornecedor, considere os seguintes aspectos do processo comercial.</span><span class="sxs-lookup"><span data-stu-id="aed4d-130">Before you design a mobile experience for vendor invoice approvals, you should consider the following aspects of the business process.</span></span> <span data-ttu-id="aed4d-131">A ideia é usar esses pontos de dados o máximo possível para otimizar a experiência de usuário no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aed4d-131">The idea is to use these data points as much as possible to optimize the user experience on the device.</span></span>

-   <span data-ttu-id="aed4d-132">Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-132">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="aed4d-133">Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-133">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span>
-   <span data-ttu-id="aed4d-134">Quantas linhas de fatura estão presentes em uma fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-134">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="aed4d-135">Aplicar a regra 80-20 aqui e otimizá-la para 80%.</span><span class="sxs-lookup"><span data-stu-id="aed4d-135">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span>
-   <span data-ttu-id="aed4d-136">Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões?</span><span class="sxs-lookup"><span data-stu-id="aed4d-136">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span> <span data-ttu-id="aed4d-137">Se a resposta a essa pergunta for sim, considere as seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="aed4d-137">If the answer to this question is yes, consider the following questions:</span></span>
    -   <span data-ttu-id="aed4d-138">Quantas distribuições contábeis (preço bruto, impostos, encargos, separações, e assim por diante) existem para uma linha de fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-138">How many accounting distributions (extended price, sales tax, charges, splits, and so on) are there for an invoice line?</span></span> <span data-ttu-id="aed4d-139">Novamente, aplique a regra 80-20.</span><span class="sxs-lookup"><span data-stu-id="aed4d-139">Again, apply the 80-20 rule.</span></span>
    -   <span data-ttu-id="aed4d-140">As faturas também têm distribuições contábeis no cabeçalho da fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-140">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="aed4d-141">Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-141">If so, should these accounting distributions be available on the device?</span></span>

    > [!NOTE]
    > <span data-ttu-id="aed4d-142">Este tópico explica como não editar distribuições contábeis, porque essa funcionalidade não é suportada atualmente para cenários móveis.</span><span class="sxs-lookup"><span data-stu-id="aed4d-142">This topic doesn’t explain how to edit accounting distributions, because this functionality isn’t currently supported for mobile scenarios.</span></span>

-   <span data-ttu-id="aed4d-143">Os usuários desejarão consultar anexos da fatura no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-143">Will users want to see attachments for the invoice on the device?</span></span>

<span data-ttu-id="aed4d-144">O design da experiência móvel para aprovações de fatura será diferente, dependendo das respostas a essas perguntas.</span><span class="sxs-lookup"><span data-stu-id="aed4d-144">The design of the mobile experience for invoice approvals will differ, depending on the answers to these questions.</span></span> <span data-ttu-id="aed4d-145">O objetivo é otimizar a experiência de usuário do processo comercial no celular em uma organização.</span><span class="sxs-lookup"><span data-stu-id="aed4d-145">The objective is to optimize the user experience for the business process on mobile in an organization.</span></span> <span data-ttu-id="aed4d-146">No restante deste tópico, olharemos duas variações de cenário baseadas em diferentes respostas às perguntas acima.</span><span class="sxs-lookup"><span data-stu-id="aed4d-146">In the rest of this topic, we will look at two scenario variations that are based on different answers to the preceding questions.</span></span> 

<span data-ttu-id="aed4d-147">Como regra geral, ao trabalhar com o designer móvel, certifique-se de “publicar” as alterações para evitar perda de atualizações.</span><span class="sxs-lookup"><span data-stu-id="aed4d-147">As a general guidance, when working with the mobile designer, make sure to 'publish' the changes to prevent losing the updates.</span></span>

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a><span data-ttu-id="aed4d-148">Como criar um cenário simples de aprovação de fatura para Contoso</span><span class="sxs-lookup"><span data-stu-id="aed4d-148">Designing a simple invoice approval scenario for Contoso</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aed4d-149">Atributo de cenário</span><span class="sxs-lookup"><span data-stu-id="aed4d-149">Scenario attribute</span></span></th>
<th><span data-ttu-id="aed4d-150">Resposta</span><span class="sxs-lookup"><span data-stu-id="aed4d-150">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aed4d-151">Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-151">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="aed4d-152">Nome do Fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-152">Vendor name</span></span></li>
<li><span data-ttu-id="aed4d-153">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-153">Invoice total</span></span></li>
<li><span data-ttu-id="aed4d-154">Conta de fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-154">Invoice account</span></span></li>
<li><span data-ttu-id="aed4d-155">Número da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-155">Invoice number</span></span></li>
<li><span data-ttu-id="aed4d-156">Data da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-156">Invoice date</span></span></li>
<li><span data-ttu-id="aed4d-157">Descrição da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-157">Invoice description</span></span></li>
<li><span data-ttu-id="aed4d-158">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="aed4d-158">Due date</span></span></li>
<li><span data-ttu-id="aed4d-159">Moeda da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-159">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-160">Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-160">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="aed4d-161">Categoria de compras</span><span class="sxs-lookup"><span data-stu-id="aed4d-161">Procurement category</span></span></li>
<li><span data-ttu-id="aed4d-162">Quantidade</span><span class="sxs-lookup"><span data-stu-id="aed4d-162">Quantity</span></span></li>
<li><span data-ttu-id="aed4d-163">Preço unitário</span><span class="sxs-lookup"><span data-stu-id="aed4d-163">Unit price</span></span></li>
<li><span data-ttu-id="aed4d-164">Valor líquido da linha</span><span class="sxs-lookup"><span data-stu-id="aed4d-164">Line net amount</span></span></li>
<li><span data-ttu-id="aed4d-165">Valor do 1099</span><span class="sxs-lookup"><span data-stu-id="aed4d-165">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-166">Quantas linhas de fatura estão presentes em uma fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-166">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="aed4d-167">Aplicar a regra 80-20 aqui e otimizá-la para 80%.</span><span class="sxs-lookup"><span data-stu-id="aed4d-167">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="aed4d-168">1</span><span class="sxs-lookup"><span data-stu-id="aed4d-168">1</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-169">Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões?</span><span class="sxs-lookup"><span data-stu-id="aed4d-169">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="aed4d-170">Sim</span><span class="sxs-lookup"><span data-stu-id="aed4d-170">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-171">Quantas distribuições contábeis (preço bruto, impostos, encargos, e assim por diante) existem para uma linha de fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-171">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="aed4d-172">Novamente, aplique a regra 80-20.</span><span class="sxs-lookup"><span data-stu-id="aed4d-172">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="aed4d-173">Preço bruto: 2 Imposto: 0 Despesas: 0</span><span class="sxs-lookup"><span data-stu-id="aed4d-173">Extended price: 2 Sales tax: 0 Charges: 0</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-174">As faturas também têm distribuições contábeis no cabeçalho da fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-174">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="aed4d-175">Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-175">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="aed4d-176">Não usado</span><span class="sxs-lookup"><span data-stu-id="aed4d-176">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-177">Os usuários desejarão consultar anexos da fatura no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-177">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="aed4d-178">Sim</span><span class="sxs-lookup"><span data-stu-id="aed4d-178">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a><span data-ttu-id="aed4d-179">Criar o espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-179">Create the workspace</span></span>

1.  <span data-ttu-id="aed4d-180">Em um navegador, entre no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aed4d-180">In a browser, and sign in to the application.</span></span>
2.  <span data-ttu-id="aed4d-181">Após entrar, anexe, append **&mode=mobile** à URL, conforme mostrado no seguinte exemplo e atualize a página: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span><span class="sxs-lookup"><span data-stu-id="aed4d-181">After you’ve signed in, append **&mode=mobile** to the URL as shown in the following example, and refresh the page: https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**</span></span>
3.  <span data-ttu-id="aed4d-182">Clique no botão **Configurações** (imagem) na parte superior direita da página e clique em **Aplicativo móvel**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-182">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**.</span></span> <span data-ttu-id="aed4d-183">O designer de aplicativo móvel deve aparecer apenas enquanto o gravador de tarefas é exibido.</span><span class="sxs-lookup"><span data-stu-id="aed4d-183">The mobile app designer must show up just as Task recorder shows up.</span></span>
4.  <span data-ttu-id="aed4d-184">Clique em **Adicionar** para criar um novo espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-184">Click **Add** to create a new workspace.</span></span> <span data-ttu-id="aed4d-185">Por exemplo, nomeie o espaço de trabalho **Minhas aprovações**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-185">For this example, name the workspace **My approvals**.</span></span>
5.  <span data-ttu-id="aed4d-186">Insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-186">Enter a description.</span></span>
6.  <span data-ttu-id="aed4d-187">Selecionar uma cor do espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-187">Select a workspace color.</span></span> <span data-ttu-id="aed4d-188">A cor do espaço de trabalho será usada para o estilo geral da experiência móvel deste espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-188">The workspace color will be used for the overall style of the mobile experience for this workspace.</span></span>
7.  <span data-ttu-id="aed4d-189">Selecionar um ícone para o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-189">Select an icon for the workspace.</span></span>
8.  <span data-ttu-id="aed4d-190">Clique em **Concluído**</span><span class="sxs-lookup"><span data-stu-id="aed4d-190">Click **Done**</span></span>
9.  <span data-ttu-id="aed4d-191">Clique em **Publicar espaço de trabalho** para salvar as alterações</span><span class="sxs-lookup"><span data-stu-id="aed4d-191">Click **Publish workspace** to save the changes</span></span>

### <a name="vendor-invoices-assigned-to-me"></a><span data-ttu-id="aed4d-192">Faturas de fornecedor atribuídas a mim</span><span class="sxs-lookup"><span data-stu-id="aed4d-192">Vendor invoices assigned to me</span></span>

<span data-ttu-id="aed4d-193">A primeira página móvel que você deve criar pela lista de faturas atribuídas ao usuário para revisão.</span><span class="sxs-lookup"><span data-stu-id="aed4d-193">The first mobile page that you should design is the list of invoices that are assigned to the user for review.</span></span> <span data-ttu-id="aed4d-194">Para criar essa página móvel, use a página **VendMobileInvoiceAssignedToMeListPage**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-194">To design this mobile page, use the **VendMobileInvoiceAssignedToMeListPage** page.</span></span> <span data-ttu-id="aed4d-195">Para concluir esse procedimento, certifique-se de que pelo menos uma fatura de fornecedor está atribuída a você para revisão e que a linha de fatura tem duas distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-195">Before you complete this procedure, make sure that at least one vendor invoice is assigned to you for review, and that the invoice line has two distributions.</span></span> <span data-ttu-id="aed4d-196">Essa configuração atende aos requisitos desse cenário.</span><span class="sxs-lookup"><span data-stu-id="aed4d-196">This setup meets the requirements for this scenario.</span></span>

1.  <span data-ttu-id="aed4d-197">Na URL, substitua o nome do item de menu por **VendMobileInvoiceAssignedToMeListPage** para abrir a versão móvel da página da lista **Faturas de fornecedor pendentes atribuídas a mim** no módulo **Contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-197">In the URL, replace the name of the menu item with **VendMobileInvoiceAssignedToMeListPage** to open the mobile version of the **Pending vendor invoices assigned to me** list page in the **Accounts payable** module.</span></span> <span data-ttu-id="aed4d-198">Dependendo do número de faturas atribuídas a você no sistema, esta página mostrará essas faturas.</span><span class="sxs-lookup"><span data-stu-id="aed4d-198">Depending on the number of invoices that you have in your system assigned to you, this page will show those invoices.</span></span> <span data-ttu-id="aed4d-199">Para encontrar uma fatura específica, você pode usar o filtro à esquerda.</span><span class="sxs-lookup"><span data-stu-id="aed4d-199">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="aed4d-200">Entretanto, não exigimos uma fatura específica para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="aed4d-200">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="aed4d-201">Nós exigimos apenas algumas faturas atribuídas a você que permitirão que você crie a página móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-201">We just require some invoice assigned to you which is going to allow you to design the mobile page.</span></span> <span data-ttu-id="aed4d-202">Novas páginas disponíveis foram criadas especificamente para desenvolvimento de cenários móveis para fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="aed4d-202">The new pages that are available have been designed specifically for developing mobile scenarios for vendor invoice.</span></span> <span data-ttu-id="aed4d-203">Portanto, você deve usar essas páginas.</span><span class="sxs-lookup"><span data-stu-id="aed4d-203">Therefore, you must use these pages.</span></span> <span data-ttu-id="aed4d-204">A URL deve ser parecida com a URL a seguir e, depois de inserida, a página mostrada na ilustração deverá ser exibida: https://&lt;suaURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span><span class="sxs-lookup"><span data-stu-id="aed4d-204">The URL should resemble the following URL, and after you enter it, the page that is shown in the illustration must appear: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile</span></span> 

    <span data-ttu-id="aed4d-205">[![Página Faturas de fornecedor atribuídas a mim](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-205">[![Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)</span></span>
    
2.  <span data-ttu-id="aed4d-206">Clique no botão **Configurações** (imagem) na parte superior à direita da página e clique em **Aplicativo móvel**</span><span class="sxs-lookup"><span data-stu-id="aed4d-206">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>
3.  <span data-ttu-id="aed4d-207">Selecione seu espaço de trabalho e clique em **Editar**</span><span class="sxs-lookup"><span data-stu-id="aed4d-207">Select your workspace and click **Edit**</span></span>
4.  <span data-ttu-id="aed4d-208">Clique em **Adicionar página** para criar a primeira página móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-208">Click **Add page** to create the first mobile page.</span></span>
5.  <span data-ttu-id="aed4d-209">Insira um nome, como **Minhas faturas de fornecedor**, e uma descrição, como **Faturas de fornecedor atribuídas a mim para revisão**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-209">Enter a name, such as **My vendor invoices**, and a description, such as **Vendor invoices assigned to me for review**.</span></span>
6.  <span data-ttu-id="aed4d-210">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-210">Click **Done**.</span></span>
7.  <span data-ttu-id="aed4d-211">No desenvolvedor móvel, na guia **Campos**, clique em **Selecionar campos**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-211">In the mobile designer, on the **Fields** tab, click **Select fields**.</span></span> <span data-ttu-id="aed4d-212">As colunas da página de lista devem relembrar a ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-212">The columns on the list page must resemble the following illustration.</span></span> 

    <span data-ttu-id="aed4d-213">[![Colunas na página Faturas de fornecedor pendentes atribuídas a mim](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-213">[![Columns on the Pending vendor invoices assigned to me page](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)</span></span>
    
8.  <span data-ttu-id="aed4d-214">Adicionar as colunas necessárias da página de listagem que deve ser exibida aos usuários na página móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-214">Add the required columns from the list page that must be shown to the users in the mobile page.</span></span> <span data-ttu-id="aed4d-215">A ordem em que você adicionar é a ordem em que os campos serão exibidos ao usuário final.</span><span class="sxs-lookup"><span data-stu-id="aed4d-215">The order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="aed4d-216">A única maneira de alterar a ordem dos campos será selecionar novamente todos os campos.</span><span class="sxs-lookup"><span data-stu-id="aed4d-216">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> <span data-ttu-id="aed4d-217">Com base nos requisitos deste cenário, estes oito campos são necessários.</span><span class="sxs-lookup"><span data-stu-id="aed4d-217">Based on the requirements for this scenario, the following eight fields are required.</span></span> <span data-ttu-id="aed4d-218">No entanto, alguns usuários podem considerar oito campos muita informação para se ter em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-218">However, some users might consider eight fields too much information to have on a mobile device.</span></span> <span data-ttu-id="aed4d-219">Portanto, mostraremos apenas os campos mais importantes na exibição de lista móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-219">Therefore, we will show only the most important fields in the mobile list view.</span></span> <span data-ttu-id="aed4d-220">Os demais campos aparecerão nos detalhes que criaremos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-220">The remaining fields will appear in the details view that we will design later.</span></span> <span data-ttu-id="aed4d-221">Por hora, adicionaremos os campos a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-221">For now, we will add the following fields.</span></span> <span data-ttu-id="aed4d-222">Clique no sinal de mais (**+**) nessas colunas para adicionar a página móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-222">Click the plus sign (**+**) in these columns to add to the mobile page.</span></span>
    - <span data-ttu-id="aed4d-223">Nome do Fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-223">Vendor name</span></span>
    - <span data-ttu-id="aed4d-224">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-224">Invoice total</span></span>
    - <span data-ttu-id="aed4d-225">Conta de fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-225">Invoice account</span></span>
    - <span data-ttu-id="aed4d-226">Número da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-226">Invoice number</span></span>
    - <span data-ttu-id="aed4d-227">Data da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-227">Invoice date</span></span>

    <span data-ttu-id="aed4d-228">Depois dos campos serem adicionados, a página móvel deve ser semelhante à ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-228">After the fields are added, the mobile page must resemble the following illustration.</span></span> 
    
    <span data-ttu-id="aed4d-229">[![Página após os campos serem adicionados](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-229">[![Page after fields are added](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)</span></span>

9.  <span data-ttu-id="aed4d-230">Você também deve adicionar as seguintes colunas agora, para que possamos habilitar ações de fluxo de trabalho posteriormente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-230">You must also add the following columns now, so that we can enable workflow actions later.</span></span>
    - <span data-ttu-id="aed4d-231">Exibir tarefa concluída</span><span class="sxs-lookup"><span data-stu-id="aed4d-231">Show complete task</span></span>
    - <span data-ttu-id="aed4d-232">Exibir tarefa delegada</span><span class="sxs-lookup"><span data-stu-id="aed4d-232">Show delegate task</span></span>
    - <span data-ttu-id="aed4d-233">Exibir tarefa de recuperação</span><span class="sxs-lookup"><span data-stu-id="aed4d-233">Show recall task</span></span>
    - <span data-ttu-id="aed4d-234">Exibir tarefa de rejeição</span><span class="sxs-lookup"><span data-stu-id="aed4d-234">Show reject task</span></span>
    - <span data-ttu-id="aed4d-235">Exibe tarefa de conclusão de solicitação</span><span class="sxs-lookup"><span data-stu-id="aed4d-235">Show request completion task</span></span>
    - <span data-ttu-id="aed4d-236">Exibir tarefa de reenvio</span><span class="sxs-lookup"><span data-stu-id="aed4d-236">Show resubmit task</span></span>

10. <span data-ttu-id="aed4d-237">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-237">Click **Done** to exit edit mode.</span></span>
11. <span data-ttu-id="aed4d-238">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-238">Click **Back** and then **Done** to exit the workspace</span></span>
12. <span data-ttu-id="aed4d-239">Clique em **Publicar espaço de trabalho** para salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-239">Click **Publish workspace** to save your work.</span></span>
13. <span data-ttu-id="aed4d-240">Habilite **Exibir total de fatura na lista de faturas de fornecedor pendentes** no formulário de parâmetros de contas a pagar em **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-240">Enable **Display invoice total on pending vendor invoices list** in accounts payable parameters form under **Invoice**.</span></span> <span data-ttu-id="aed4d-241">Observe que, apenas ao habilitar esse parâmetro, os totais de fatura serão calculados para serem exibidos na página de listagem de faturas de fornecedor pendentes.</span><span class="sxs-lookup"><span data-stu-id="aed4d-241">Note that, only by enabling this parameter, invoice totals will be calculated to be displayed on the pending vendor invoices list page.</span></span> <span data-ttu-id="aed4d-242">Este é um novo recurso como parte do pré-requisito do hot fix 3208224.</span><span class="sxs-lookup"><span data-stu-id="aed4d-242">This is a new capability as part of the pre-requisite hot fix 3208224.</span></span>

### <a name="vendor-invoice-details"></a><span data-ttu-id="aed4d-243">Detalhes da fatura do fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-243">Vendor invoice details</span></span>

<span data-ttu-id="aed4d-244">Para criar a página de detalhes da fatura para dispositivos móveis, use a página **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-244">To design the invoice details page for mobile, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="aed4d-245">Observe que, dependendo do número de faturas que você possui no sistema, esta página exibe fatura mais antiga (a fatura criada primeiro.)</span><span class="sxs-lookup"><span data-stu-id="aed4d-245">Note that, depending on the number of invoices that you have in your system, this page shows the oldest invoice (the invoice that was created first).</span></span> <span data-ttu-id="aed4d-246">Para encontrar uma fatura específica, você pode usar o filtro à esquerda.</span><span class="sxs-lookup"><span data-stu-id="aed4d-246">To find a specific invoice, you can use the filter on the left.</span></span> <span data-ttu-id="aed4d-247">Entretanto, não exigimos uma fatura específica para este exemplo.</span><span class="sxs-lookup"><span data-stu-id="aed4d-247">However, we don’t require a specific invoice for this example.</span></span> <span data-ttu-id="aed4d-248">Nós exigimos apenas alguns dados de fatura para que possamos criar a página móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-248">We just require some invoice data so that we can design the mobile page.</span></span> 

<span data-ttu-id="aed4d-249">[![Página do fluxo de trabalho](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-249">[![Workflow page](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)</span></span>

1. <span data-ttu-id="aed4d-250">Na URL, substitua o nome do item de menu por **VendMobileInvoiceHeaderDetails** para abrir o formulário</span><span class="sxs-lookup"><span data-stu-id="aed4d-250">In the URL, replace the name of the menu item with **VendMobileInvoiceHeaderDetails** to open the form</span></span>

2. <span data-ttu-id="aed4d-251">Abra o criador móvel a partir do botão **Configurações** (imagem).</span><span class="sxs-lookup"><span data-stu-id="aed4d-251">Open the mobile designer from the **Settings** (gear) button.</span></span>

3. <span data-ttu-id="aed4d-252">Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-252">Click the **Edit** button to start edit mode in the workspace.</span></span>

4. <span data-ttu-id="aed4d-253">Selecione a página **Minhas fatura de fornecedor** que você criou anteriormente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-253">Select the **My vendor invoices** page that you created earlier, and then click **Edit**.</span></span>

5. <span data-ttu-id="aed4d-254">Na guia **Campos**, clique no cabeçalho da coluna **Grade**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-254">On the **Fields** tab, click the **Grid** column heading.</span></span>

6. <span data-ttu-id="aed4d-255">Clique em **Propriedades &gt; Adicionar página**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-255">Click **Properties &gt; Add page**.</span></span> <span data-ttu-id="aed4d-256">**Observação:** Quando clicar no cabeçalho **Grade** e adicionar uma página, a relação com a página de detalhes é estabelecida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-256">**Note:** When you click the **Grid** heading and add a page, the relationship with the details page is established automatically.</span></span>

7. <span data-ttu-id="aed4d-257">Insira um título de página, como **Detalhes de fatura**, e uma descrição, como **Exibir cabeçalho de fatura e detalhes de linha**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-257">Enter a page title, such as **Invoice details**, and a description, such as **View invoice header and line details**.</span></span>

8. <span data-ttu-id="aed4d-258">Clique em **Selecionar campos**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-258">Click **Select fields**.</span></span> <span data-ttu-id="aed4d-259">Observe que, a ordem em que você adicionar é a ordem em que os campos serão exibidos para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="aed4d-259">Note that, the order in which you add is the order in which the fields will be displayed to the end user.</span></span> <span data-ttu-id="aed4d-260">A única maneira de alterar a ordem dos campos será selecionar novamente todos os campos.</span><span class="sxs-lookup"><span data-stu-id="aed4d-260">The only way to change the ordering of the fields will be by re-selecting all the fields.</span></span> 

9. <span data-ttu-id="aed4d-261">Adicione os campos a seguir a partir do cabeçalho baseado nos requisitos deste cenário:</span><span class="sxs-lookup"><span data-stu-id="aed4d-261">Add the following fields from the header, based on the requirements for this scenario:</span></span>
   - <span data-ttu-id="aed4d-262">Nome do Fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-262">Vendor name</span></span>
   - <span data-ttu-id="aed4d-263">Total da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-263">Invoice total</span></span>
   - <span data-ttu-id="aed4d-264">Conta de fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-264">Invoice account</span></span>
   - <span data-ttu-id="aed4d-265">Número da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-265">Invoice number</span></span>
   - <span data-ttu-id="aed4d-266">Data da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-266">Invoice date</span></span>
   - <span data-ttu-id="aed4d-267">Descrição da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-267">Invoice description</span></span>
   - <span data-ttu-id="aed4d-268">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="aed4d-268">Due date</span></span>
   - <span data-ttu-id="aed4d-269">Moeda da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-269">Invoice currency</span></span>

10. <span data-ttu-id="aed4d-270">Adicione os seguintes campos das linhas da grade na página:</span><span class="sxs-lookup"><span data-stu-id="aed4d-270">Add the following fields from the lines grid on the page:</span></span>
    - <span data-ttu-id="aed4d-271">Categoria de compras</span><span class="sxs-lookup"><span data-stu-id="aed4d-271">Procurement category</span></span>
    - <span data-ttu-id="aed4d-272">Quantidade</span><span class="sxs-lookup"><span data-stu-id="aed4d-272">Quantity</span></span>
    - <span data-ttu-id="aed4d-273">Preço unitário</span><span class="sxs-lookup"><span data-stu-id="aed4d-273">Unit price</span></span>
    - <span data-ttu-id="aed4d-274">Valor líquido da linha</span><span class="sxs-lookup"><span data-stu-id="aed4d-274">Line net amount</span></span>
    - <span data-ttu-id="aed4d-275">Valor do 1099</span><span class="sxs-lookup"><span data-stu-id="aed4d-275">1099 amount</span></span>

11. <span data-ttu-id="aed4d-276">Depois que todos os campos das duas etapas anteriores terem sido adicionados, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-276">After all the fields from the previous two steps have been added, click **Done**.</span></span> <span data-ttu-id="aed4d-277">A página deve ser semelhante à ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-277">The page must resemble the following illustration.</span></span>
    
    <span data-ttu-id="aed4d-278">[![Página após os campos serem adicionados](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-278">[![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)</span></span>

12. <span data-ttu-id="aed4d-279">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-279">Click **Done** to exit edit mode.</span></span>

13. <span data-ttu-id="aed4d-280">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-280">Click **Back** and then **Done** to exit the workspace</span></span>

14. <span data-ttu-id="aed4d-281">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-281">Click **Publish workspace** to save your work</span></span>

### <a name="workflow-actions"></a><span data-ttu-id="aed4d-282">Ações de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-282">Workflow actions</span></span>

<span data-ttu-id="aed4d-283">Para adicionar ações de fluxo de trabalho, use a página **VendMobileInvoiceHeaderDetails**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-283">To add workflow actions, use the **VendMobileInvoiceHeaderDetails** page.</span></span> <span data-ttu-id="aed4d-284">Para abrir essa página, substitua o nome do item de menu na URL, como você fez anteriormente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-284">To open this page, replace the name of the menu item in the URL, as you did earlier.</span></span> <span data-ttu-id="aed4d-285">Para abrir o criador móvel a partir do botão **Configurações** (imagem).</span><span class="sxs-lookup"><span data-stu-id="aed4d-285">Then open the mobile designer from the **Settings** (gear) button.</span></span> <span data-ttu-id="aed4d-286">Rastreie essas etapas para adicionar ações de fluxo de trabalho na página de detalhes.</span><span class="sxs-lookup"><span data-stu-id="aed4d-286">Follow these steps to add workflow actions on the details page.</span></span> <span data-ttu-id="aed4d-287">É necessário ter faturas atribuídas a você que estão no estado apropriado para realizar ações de fluxo de trabalho disponíveis a você e que você criará.</span><span class="sxs-lookup"><span data-stu-id="aed4d-287">You must have invoices assigned to you that are in the appropriate state to make the workflow actions available to you that you are going to design for.</span></span>

#### <a name="record-workflow-actions"></a><span data-ttu-id="aed4d-288">Registro de ações de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-288">Record workflow actions</span></span>
1.  <span data-ttu-id="aed4d-289">Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-289">Click the **Edit** button to start edit mode in the workspace.</span></span>
2.  <span data-ttu-id="aed4d-290">Selecione a página **Detalhes de fatura** que você criou anteriormente e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-290">Select the **Invoice details** page that you created earlier, and then click **Edit**.</span></span>
3.  <span data-ttu-id="aed4d-291">Na guia **Ações**, clique em **Adicionar ação**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-291">On the **Actions** tab, click **Add action**.</span></span>
4.  <span data-ttu-id="aed4d-292">Insira um título de ação, como **Aprovar** e uma descrição como **Aprovação de fatura**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-292">Enter an action title, such as **Approve**, and a description, such as **Approve invoice**.</span></span> <span data-ttu-id="aed4d-293">Observe que o título da ação inserido aqui se transforma no nome da ação exibido para o usuário no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-293">Note that the action title that you enter here becomes the name of the action that is shown to the user in the mobile app.</span></span>
5.  <span data-ttu-id="aed4d-294">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-294">Click **Done**.</span></span>
6.  <span data-ttu-id="aed4d-295">Clique em **Selecionar campos**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-295">Click **Select fields**.</span></span>
7.  <span data-ttu-id="aed4d-296">Passe pelo processo de fluxo de trabalho na página **VendMobileInvoiceHeaderDetails** e complete a ação que deseja registrar.</span><span class="sxs-lookup"><span data-stu-id="aed4d-296">Go through the workflow process on the **VendMobileInvoiceHeaderDetails** page, and complete the action that you wanted to record.</span></span> <span data-ttu-id="aed4d-297">Verifique se você inseriu os comentários de fluxo de trabalho durante esse processo, para que um campo de comentários também seja incluído na experiência móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-297">Make sure that you enter workflow comments during this process, so that a comments field is also included in the mobile experience.</span></span>
8.  <span data-ttu-id="aed4d-298">Depois da ação de fluxo de trabalho ser executada, clique em **Concluído** para concluir a tarefa Selecionar campos.</span><span class="sxs-lookup"><span data-stu-id="aed4d-298">After the workflow action is run, click **Done** to complete the Select fields task.</span></span>
9.  <span data-ttu-id="aed4d-299">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-299">Click **Done** to exit edit mode.</span></span>
10. <span data-ttu-id="aed4d-300">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-300">Click **Back** and then **Done** to exit the workspace</span></span>
11. <span data-ttu-id="aed4d-301">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-301">Click **Publish workspace** to save your work</span></span>
12. <span data-ttu-id="aed4d-302">Repita as etapas anteriores para registrar todas as ações necessárias do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-302">Repeat the previous steps to record all the required workflow actions.</span></span> 

#### <a name="create-a-js-file"></a><span data-ttu-id="aed4d-303">Crie um arquivo .js</span><span class="sxs-lookup"><span data-stu-id="aed4d-303">Create a .js file</span></span>
1. <span data-ttu-id="aed4d-304">Abra o Bloco de Notas ou Visual Studio e cole o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-304">Open Notepad or Microsoft Visual Studio, and paste the following code.</span></span> <span data-ttu-id="aed4d-305">Salve o arquivo como .js.</span><span class="sxs-lookup"><span data-stu-id="aed4d-305">Save the file as a .js file.</span></span> <span data-ttu-id="aed4d-306">Este código faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aed4d-306">This code does the following:</span></span>
    - <span data-ttu-id="aed4d-307">Oculta colunas relacionadas a fluxo de trabalho extra que foram adicionadas anteriormente na página de listagem móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-307">It hides the extra workflow-related columns that we added earlier on the mobile list page.</span></span> <span data-ttu-id="aed4d-308">Nós adicionamos essas colunas de forma que o aplicativo tenha essas informações no contexto e possa executar a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="aed4d-308">We added these columns so that the app has that information in context and can do the next step.</span></span>
    - <span data-ttu-id="aed4d-309">Com a etapa do fluxo de trabalho ativa, aplique a lógica para mostrar somente aquelas ações.</span><span class="sxs-lookup"><span data-stu-id="aed4d-309">Based on the workflow step that is active, it applies logic to show only those actions.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aed4d-310">O nome das páginas e outros controles no código devem ser iguais aos nomes no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-310">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  <span data-ttu-id="aed4d-311">Carregue o arquivo do código ao espaço de trabalho selecionando a guia **Lógica**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-311">Upload the code file to the workspace by selecting the **Logic** tab</span></span>
3.  <span data-ttu-id="aed4d-312">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-312">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="aed4d-313">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-313">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="aed4d-314">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-314">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-attachments"></a><span data-ttu-id="aed4d-315">Anexos da fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-315">Vendor invoice attachments</span></span>

1. <span data-ttu-id="aed4d-316">Clique no botão **Configurações** (imagem) na parte superior à direita da página e clique em **Aplicativo móvel**</span><span class="sxs-lookup"><span data-stu-id="aed4d-316">Click the **Settings** (gear) button in the upper right of the page, and then click **Mobile app**</span></span>

2. <span data-ttu-id="aed4d-317">Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-317">Click the **Edit** button to start edit mode in the workspace.</span></span>

3. <span data-ttu-id="aed4d-318">Selecione a página <strong>Detalhes da fatura \*\*criada anteriormente e clique em \*\*Editar</strong>.</span><span class="sxs-lookup"><span data-stu-id="aed4d-318">Select the <strong>Invoice details \*\*page that you created earlier, and then click \*\*Edit</strong>.</span></span>

4. <span data-ttu-id="aed4d-319">Defina a opção **Gerenciamento de documento** para **Sim** como exibido abaixo.</span><span class="sxs-lookup"><span data-stu-id="aed4d-319">Set the **Document management** option to **Yes** as shown below.</span></span> <span data-ttu-id="aed4d-320">**Observação:** Se não houver requisitos para exibir os anexos no dispositivo móvel, você pode deixar essa opção definida como **Não**, que é a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="aed4d-320">**Note:** If there are no requirements to show attachments on the mobile device, you can leave this option set to **No**, which is the default setting.</span></span>
   
   ![Gerenciamento de documentos](./media/docmanagement-216x300.png)

5. <span data-ttu-id="aed4d-322">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-322">Click **Done** to exit edit mode.</span></span>

6. <span data-ttu-id="aed4d-323">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-323">Click **Back** and then **Done** to exit the workspace</span></span>

7. <span data-ttu-id="aed4d-324">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-324">Click **Publish workspace** to save your work</span></span>

### <a name="vendor-invoice-line-distributions"></a><span data-ttu-id="aed4d-325">Distribuições de linha de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-325">Vendor invoice line distributions</span></span>

<span data-ttu-id="aed4d-326">Os requisitos para este cenário confirmam que haverá apenas distribuições ao nível de linha e que uma fatura terá sempre apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="aed4d-326">The requirements for this scenario confirm that there will be only line-level distributions, and that an invoice will always have only one line.</span></span> <span data-ttu-id="aed4d-327">Como esse cenário é simples, a experiência de usuário no dispositivo móvel deve ser suficientemente simples para o usuário não ter de fazer busca detalhada de vários níveis para exibir as distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-327">Because this scenario is simple, the user experience on the mobile device must also be simple enough that the user doesn’t have to drill down several levels to view the distributions.</span></span> <span data-ttu-id="aed4d-328">As faturas de fornecedor incluem a opção de mostrar todas as distribuições do cabeçalho de fatura.</span><span class="sxs-lookup"><span data-stu-id="aed4d-328">Vendor invoices include the option of showing all distributions from the invoice header.</span></span> <span data-ttu-id="aed4d-329">Essa experiência é o que precisamos para o cenário móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-329">This experience is what we need for the mobile scenario.</span></span> <span data-ttu-id="aed4d-330">Portanto, usaremos a página **VendMobileInvoiceAllDistributionTree** para criar essa parte do cenário móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-330">Therefore, we will use the **VendMobileInvoiceAllDistributionTree** page to design this part of the mobile scenario.</span></span> 

> [!NOTE] 
> <span data-ttu-id="aed4d-331">Saber os requisitos nos ajuda a decidir qual página específica usar e quão exatamente otimizar a experiência móvel para o usuário quando criarmos o cenário.</span><span class="sxs-lookup"><span data-stu-id="aed4d-331">Knowing the requirements helps us decide which specific page to use and how exactly to optimize the mobile experience for the user when we design the scenario.</span></span> <span data-ttu-id="aed4d-332">No segundo cenário, usaremos uma página diferente para mostrar as distribuições, pois as necessidades para esse cenário são diferentes.</span><span class="sxs-lookup"><span data-stu-id="aed4d-332">In the second scenario, we will use a different page to show the distributions, because the requirements for that scenario differ.</span></span>

1.  <span data-ttu-id="aed4d-333">Na URL, substitua o nome do item de menu, como fez anteriormente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-333">In the URL, replace the name of the menu item, as you did before.</span></span> <span data-ttu-id="aed4d-334">A página que aparece deve ser semelhante à ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-334">The page that appears should resemble the following illustration.</span></span>

    <span data-ttu-id="aed4d-335">[![Página de todas as distribuições](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span><span class="sxs-lookup"><span data-stu-id="aed4d-335">[![All distributions page](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)</span></span>

2.  <span data-ttu-id="aed4d-336">Abra o criador móvel a partir do botão **Configurações** (imagem).</span><span class="sxs-lookup"><span data-stu-id="aed4d-336">Open the mobile designer from the **Settings** (gear) button.</span></span>

3.  <span data-ttu-id="aed4d-337">Clique no botão **Editar** para iniciar o modo de edição no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-337">Click the **Edit** button to start edit mode in the workspace.</span></span> <span data-ttu-id="aed4d-338">**Observação:** Você verá que duas novas páginas foram criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aed4d-338">**Note:** You will see that two new pages were created automatically.</span></span> <span data-ttu-id="aed4d-339">O sistema cria essas páginas porque você ativou o gerenciamento de documentos na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="aed4d-339">The system creates these pages, because you turned on document management in the previous section.</span></span> <span data-ttu-id="aed4d-340">Você pode ignorar essas novas páginas.</span><span class="sxs-lookup"><span data-stu-id="aed4d-340">You can ignore these new pages.</span></span>

4.  <span data-ttu-id="aed4d-341">Clique em **Adicionar página**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-341">Click **Add page**.</span></span>

5.  <span data-ttu-id="aed4d-342">Insira um título de página, como **Exibir contabilidade**, e uma descrição como **Exibir contabilidade da fatura**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-342">Enter a page title, such as **View accounting**, and a description, such as **View accounting for the invoice**.</span></span>

6.  <span data-ttu-id="aed4d-343">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-343">Click **Done**.</span></span>

7.  <span data-ttu-id="aed4d-344">Na guia **Campos**, clique em **Selecionar campos**, selecione os campos a seguir das páginas de distribuição e depois clique em **Concluído**:</span><span class="sxs-lookup"><span data-stu-id="aed4d-344">On the **Fields** tab, click **Select fields**, select the following fields from the distributions page, and then click **Done**:</span></span>
    1.  <span data-ttu-id="aed4d-345">Valor</span><span class="sxs-lookup"><span data-stu-id="aed4d-345">Amount</span></span>
    2.  <span data-ttu-id="aed4d-346">Moeda</span><span class="sxs-lookup"><span data-stu-id="aed4d-346">Currency</span></span>
    3.  <span data-ttu-id="aed4d-347">Conta contábil</span><span class="sxs-lookup"><span data-stu-id="aed4d-347">Ledger account</span></span>

    > [!NOTE] 
    > <span data-ttu-id="aed4d-348">Não selecionamos a coluna **Descrição** da grade de distribuições porque os requisitos desse cenário confirmaram que o preço bruto é o único valor que existirá para as distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-348">We didn’t select the **Description** column from the distributions grid, because the requirements for this scenario confirmed that the extended price is the only amount that there will be distributions for.</span></span> <span data-ttu-id="aed4d-349">Portanto, o usuário não exigirá outro campo para determinar o tipo de valor para o qual a distribuição foi criada.</span><span class="sxs-lookup"><span data-stu-id="aed4d-349">Therefore, the user won’t require another field to determine the amount type that the distribution is for.</span></span> <span data-ttu-id="aed4d-350">No entanto, nesse cenário, nós **usaremos** essa informação porque os requisitos desse cenário especificam que outros tipos de valores têm distribuições (por exemplo, imposto).</span><span class="sxs-lookup"><span data-stu-id="aed4d-350">However, in the next scenario, we **will** use this information, because the requirements for that scenario specify that other amount types have distributions (for example, sales tax).</span></span>

8.  <span data-ttu-id="aed4d-351">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-351">Click **Done** to exit edit mode.</span></span>

9.  <span data-ttu-id="aed4d-352">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-352">Click **Back** and then **Done** to exit the workspace</span></span>

10. <span data-ttu-id="aed4d-353">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-353">Click **Publish workspace** to save your work</span></span>

#### <a name="adding-navigation-to-view-accounting-page"></a><span data-ttu-id="aed4d-354">Adicionando navegação à página "Exibir contabilidade"</span><span class="sxs-lookup"><span data-stu-id="aed4d-354">Adding navigation to "View accounting" page</span></span>

<span data-ttu-id="aed4d-355">A página móvel **Exibir contabilidade** não está vinculada atualmente a quaisquer páginas móveis que criamos até agora.</span><span class="sxs-lookup"><span data-stu-id="aed4d-355">The **View accounting** mobile page isn’t currently linked to any of the mobile pages that we have designed so far.</span></span> <span data-ttu-id="aed4d-356">Como o usuário deve poder navegar até a página **Exibir contabilidade** da página **Detalhes de fatura** no dispositivo móvel, devemos fornecer navegação da página **Detalhes da fatura** para a página **Exibir contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-356">Because the user should be able to navigate to the **View accounting** page from the **Invoice details** page on the mobile device, we must provide navigation from the **Invoice details** page to the **View accounting** page.</span></span> <span data-ttu-id="aed4d-357">Nós estabelecemos essa navegação usando a lógica adicional por JavaScript.</span><span class="sxs-lookup"><span data-stu-id="aed4d-357">We establish this navigation by using additional logic via JavaScript.</span></span>

1.  <span data-ttu-id="aed4d-358">Abra o arquivo .js criado anteriormente e adicione linhas realçadas no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-358">Open the .js file that you created earlier, and add the lines that are highlighted in the following code.</span></span> <span data-ttu-id="aed4d-359">Este código faz duas coisas:</span><span class="sxs-lookup"><span data-stu-id="aed4d-359">This code does two things:</span></span>
    1.  <span data-ttu-id="aed4d-360">Ajuda a garantir que os usuários não consigam navegar diretamente do espaço de trabalho até a página **Exibir contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-360">It helps guarantee that users can’t navigate directly from the workspace to the **View accounting** page.</span></span>
    2.  <span data-ttu-id="aed4d-361">Estabelece o controle de navegação da página **Detalhes de fatura** até a página **Exibir contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-361">It establishes a navigation control from the **Invoice details** page to the **View accounting** page.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="aed4d-362">O nome das páginas e outros controles no código devem ser iguais aos nomes no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-362">The name of the pages and other controls in the code must be the same as the names in the workspace.</span></span>

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  <span data-ttu-id="aed4d-363">Carregue o arquivo do código ao espaço de trabalho selecionando a guia **Lógica** para sobrescrever o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="aed4d-363">Upload the code file to the workspace by selecting the **Logic** tab to overwrite the previous code</span></span>
3.  <span data-ttu-id="aed4d-364">Clique em **Concluído** para sair do modo de edição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-364">Click **Done** to exit edit mode.</span></span>
4.  <span data-ttu-id="aed4d-365">Clique em **Voltar** e depois em **Concluído** para sair da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-365">Click **Back** and then **Done** to exit the workspace</span></span>
5.  <span data-ttu-id="aed4d-366">Clique em **Publicar espaço de trabalho** para salvar seu trabalho</span><span class="sxs-lookup"><span data-stu-id="aed4d-366">Click **Publish workspace** to save your work</span></span>

### <a name="validation"></a><span data-ttu-id="aed4d-367">Validação</span><span class="sxs-lookup"><span data-stu-id="aed4d-367">Validation</span></span>

<span data-ttu-id="aed4d-368">No dispositivo móvel, abra o aplicativo e conecte-se à sua instância.</span><span class="sxs-lookup"><span data-stu-id="aed4d-368">From your mobile device, open the app, and connect to your instance.</span></span> <span data-ttu-id="aed4d-369">Certifique-se de que você está conectado à empresa onde as faturas de fornecedor são atribuídas a você para revisão.</span><span class="sxs-lookup"><span data-stu-id="aed4d-369">Make sure that you sign in to the company where vendor invoices are assigned to you for review.</span></span> <span data-ttu-id="aed4d-370">Você deve ser capaz de executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="aed4d-370">You should be able to perform the following actions:</span></span>

-   <span data-ttu-id="aed4d-371">Consulte o espaço de trabalho **Minhas aprovações**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-371">See the **My approvals** workspace.</span></span>
-   <span data-ttu-id="aed4d-372">Entre na área de trabalho **Minhas aprovações** e consulte a página **Minhas faturas de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="aed4d-372">Drill into the **My approvals** workspace and see the **My vendor invoices** page.</span></span>
-   <span data-ttu-id="aed4d-373">Entre na página **Minhas faturas de fornecedor** e consulte a lista de faturas atribuídas a você.</span><span class="sxs-lookup"><span data-stu-id="aed4d-373">Drill into the **My vendor invoices** page and see the list of invoices that are assigned to you.</span></span>
-   <span data-ttu-id="aed4d-374">Entre em uma das faturas, e consulte os detalhes do cabeçalho de fatura e os detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="aed4d-374">Drill into one of the invoices, and see the invoice header details and line details.</span></span>
-   <span data-ttu-id="aed4d-375">Na página de detalhes, consulte um link para anexos e use esse link para navegar à lista de anexos e ver os anexos.</span><span class="sxs-lookup"><span data-stu-id="aed4d-375">On the details page, see a link to attachments, and use this link to navigate to the attachments list and view the attachments.</span></span>
-   <span data-ttu-id="aed4d-376">Na página de detalhes, consulte um link para a página **Exibir contabilidade** e use esse link para navegar à página de distribuições e ver as distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-376">On the details page, see a link to the **View accounting** page, and use this link to navigate to the distributions page and view the distributions.</span></span>
-   <span data-ttu-id="aed4d-377">Na página de detalhes, clique no menu **Ações** na parte inferior e realize ações de fluxo de trabalho que são aplicáveis à etapa de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="aed4d-377">On the details page, click the **Actions** menu at the bottom, and perform workflow actions that are applicable to the workflow step.</span></span>

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a><span data-ttu-id="aed4d-378">Como criar um cenário complexo de aprovação de fatura para Fabrikam</span><span class="sxs-lookup"><span data-stu-id="aed4d-378">Designing a complex invoice approval scenario for Fabrikam</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aed4d-379">Atributo de cenário</span><span class="sxs-lookup"><span data-stu-id="aed4d-379">Scenario attribute</span></span></th>
<th><span data-ttu-id="aed4d-380">Resposta</span><span class="sxs-lookup"><span data-stu-id="aed4d-380">Answer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aed4d-381">Quais campos do cabeçalho de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-381">What fields from the invoice header will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="aed4d-382">Nome do Fornecedor</span><span class="sxs-lookup"><span data-stu-id="aed4d-382">Vendor name</span></span></li>
<li><span data-ttu-id="aed4d-383">Valor da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-383">Invoice amount</span></span></li>
<li><span data-ttu-id="aed4d-384">Conta de fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-384">Invoice account</span></span></li>
<li><span data-ttu-id="aed4d-385">Número da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-385">Invoice number</span></span></li>
<li><span data-ttu-id="aed4d-386">Data da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-386">Invoice date</span></span></li>
<li><span data-ttu-id="aed4d-387">Descrição da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-387">Invoice description</span></span></li>
<li><span data-ttu-id="aed4d-388">Data de Vencimento</span><span class="sxs-lookup"><span data-stu-id="aed4d-388">Due date</span></span></li>
<li><span data-ttu-id="aed4d-389">Moeda da fatura</span><span class="sxs-lookup"><span data-stu-id="aed4d-389">Invoice currency</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-390">Quais campos das linhas de fatura o usuário desejará ver na experiência móvel, e em que ordem?</span><span class="sxs-lookup"><span data-stu-id="aed4d-390">What fields from the invoice lines will the user want to see in the mobile experience, and in what order?</span></span></td>
<td><ol>
<li><span data-ttu-id="aed4d-391">Categoria de compras</span><span class="sxs-lookup"><span data-stu-id="aed4d-391">Procurement category</span></span></li>
<li><span data-ttu-id="aed4d-392">Quantidade</span><span class="sxs-lookup"><span data-stu-id="aed4d-392">Quantity</span></span></li>
<li><span data-ttu-id="aed4d-393">Preço unitário</span><span class="sxs-lookup"><span data-stu-id="aed4d-393">Unit price</span></span></li>
<li><span data-ttu-id="aed4d-394">Valor líquido da linha</span><span class="sxs-lookup"><span data-stu-id="aed4d-394">Line net amount</span></span></li>
<li><span data-ttu-id="aed4d-395">Valor do 1099</span><span class="sxs-lookup"><span data-stu-id="aed4d-395">1099 amount</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-396">Quantas linhas de fatura estão presentes em uma fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-396">How many invoice lines are there in an invoice?</span></span> <span data-ttu-id="aed4d-397">Aplicar a regra 80-20 aqui e otimizá-la para 80%.</span><span class="sxs-lookup"><span data-stu-id="aed4d-397">Apply the 80-20 rule here, and optimize for the 80 percent.</span></span></td>
<td><span data-ttu-id="aed4d-398">5</span><span class="sxs-lookup"><span data-stu-id="aed4d-398">5</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-399">Os usuários desejarão consultar as distribuições contábeis (codificação de fatura) no dispositivo móvel durante as revisões?</span><span class="sxs-lookup"><span data-stu-id="aed4d-399">Will users want to see accounting distributions (invoice coding) on the mobile device during reviews?</span></span></td>
<td><span data-ttu-id="aed4d-400">Sim</span><span class="sxs-lookup"><span data-stu-id="aed4d-400">Yes</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-401">Quantas distribuições contábeis (preço bruto, impostos, encargos, e assim por diante) existem para uma linha de fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-401">How many accounting distributions (extended price, sales tax, charges, and so on) are there for an invoice line?</span></span> <span data-ttu-id="aed4d-402">Novamente, aplique a regra 80-20.</span><span class="sxs-lookup"><span data-stu-id="aed4d-402">Again, apply the 80-20 rule.</span></span></td>
<td><span data-ttu-id="aed4d-403">Preço bruto: 2 Imposto: 2 Despesas: 2</span><span class="sxs-lookup"><span data-stu-id="aed4d-403">Extended price: 2 Sales tax: 2 Charges: 2</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aed4d-404">As faturas também têm distribuições contábeis no cabeçalho da fatura?</span><span class="sxs-lookup"><span data-stu-id="aed4d-404">Do the invoices also have accounting distributions on the invoice header?</span></span> <span data-ttu-id="aed4d-405">Em caso afirmativo, essas distribuições contábeis devem estar disponíveis no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-405">If so, should these accounting distributions be available on the device?</span></span></td>
<td><span data-ttu-id="aed4d-406">Não usado</span><span class="sxs-lookup"><span data-stu-id="aed4d-406">Not used</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aed4d-407">Os usuários desejarão consultar anexos da fatura no dispositivo?</span><span class="sxs-lookup"><span data-stu-id="aed4d-407">Will users want to see attachments for the invoice on the device?</span></span></td>
<td><span data-ttu-id="aed4d-408">Sim</span><span class="sxs-lookup"><span data-stu-id="aed4d-408">Yes</span></span></td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a><span data-ttu-id="aed4d-409">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="aed4d-409">Next steps</span></span>

<span data-ttu-id="aed4d-410">As variações a seguir podem ser realizadas para o cenário 1, com base nos requisitos do cenário 2.</span><span class="sxs-lookup"><span data-stu-id="aed4d-410">The following variations can be done for scenario 1, based on the requirements for scenario 2.</span></span> <span data-ttu-id="aed4d-411">Você pode usar esta seção para melhorar a sua experiência com o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="aed4d-411">You can use this section to improve your mobile app experience.</span></span>

1.  <span data-ttu-id="aed4d-412">Como mais linhas de fatura são esperadas no cenário 2, as alterações a seguir para a criação ajudarão a otimizar a experiência do usuário no dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="aed4d-412">Because more invoice lines are expected in scenario 2, the following changes to the design will help optimize the user experience on the mobile device:</span></span>
    1.  <span data-ttu-id="aed4d-413">Em vez de exibir linhas na página de detalhes (como no cenário 1), os usuários podem escolher exibir linhas em uma página móvel separada.</span><span class="sxs-lookup"><span data-stu-id="aed4d-413">Instead of viewing invoice lines on the details page (as in scenario 1), users can choose to view lines on a separate mobile page.</span></span>
    2.  <span data-ttu-id="aed4d-414">Como mais de uma linha de fatura é esperada neste cenário, se a página **VendMobileInvoiceAllDistributionTree** for usada para criar a página de distribuições para dispositivo móvel (como no cenário 1), pode ser confuso para o usuário correlacionar as linhas de distribuição.</span><span class="sxs-lookup"><span data-stu-id="aed4d-414">Because more than one invoice line is expected in this scenario, if the **VendMobileInvoiceAllDistributionTree** page is used to design the distributions page for mobile (as in scenario 1), it might be confusing for the user to correlate lines to distributions.</span></span> <span data-ttu-id="aed4d-415">Portanto, use a página **VendMobileInvoiceLineDistributionTree** para criar a página de distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-415">Therefore, use the **VendMobileInvoiceLineDistributionTree** page to design the distributions page.</span></span>
    3.  <span data-ttu-id="aed4d-416">Idealmente, as distribuições devem ser mostradas no contexto de uma linha de fatura neste cenário.</span><span class="sxs-lookup"><span data-stu-id="aed4d-416">Ideally, the distributions should be shown in the context of an invoice line in this scenario.</span></span> <span data-ttu-id="aed4d-417">Portanto, certifique-se de que o usuário pode entrar em uma linha para exibir a página de distribuições.</span><span class="sxs-lookup"><span data-stu-id="aed4d-417">Therefore, make sure that the user can drill into a line to see the distributions page.</span></span> <span data-ttu-id="aed4d-418">Use o recurso de link de página para estabelecer a entrada, assim como fez no cabeçalho e nas páginas de detalhes no cenário 1.</span><span class="sxs-lookup"><span data-stu-id="aed4d-418">Use the page link capability to establish the drill-through, just as you did for the header and details pages in scenario 1.</span></span>

2.  <span data-ttu-id="aed4d-419">Como mais de um tipo de valor é esperado nas distribuições no cenário 2 (impostos, cobranças e assim por diante), será útil exibir a descrição do tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="aed4d-419">Because more than one amount type is expected on the distributions in scenario 2 (sales tax, charges, and so on), it will be useful to show the description of the amount type.</span></span> <span data-ttu-id="aed4d-420">(Omitimos estas informações no cenário 1.)</span><span class="sxs-lookup"><span data-stu-id="aed4d-420">(We omitted this information in scenario 1.)</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]