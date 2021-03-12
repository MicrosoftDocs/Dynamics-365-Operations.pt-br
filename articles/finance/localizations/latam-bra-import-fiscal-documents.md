---
title: Importar notas fiscais do Brasil
description: Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira.
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BrazilParameters, FiscalDocument_BR, PurchImportDeclaration_BR, PurchImportDeclarationList_BR, VendEditInvoice
audience: Application User
ms.reviewer: kfend
ms.custom: 270204
ms.assetid: b2389297-1359-498f-b755-c20574248ae1
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 25f3285b0aecadeef9f0a93d18a150533f9abf01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005766"
---
# <a name="import-fiscal-documents-for-brazil"></a><span data-ttu-id="f5a43-103">Importar notas fiscais do Brasil</span><span class="sxs-lookup"><span data-stu-id="f5a43-103">Import fiscal documents for Brazil</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5a43-104">Este tópico descreve a funcionalidade para notas fiscais de importação direta disponível da localização brasileira.</span><span class="sxs-lookup"><span data-stu-id="f5a43-104">This topic describes the functionality for direct import fiscal documents that is available for the Brazilian localization.</span></span>

<span data-ttu-id="f5a43-105">Você pode emitir uma nota fiscal de importação direta quando cria uma ordem de compra para importar itens de um fornecedor estrangeiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-105">You can issue a direct import fiscal document when you create a purchase order to import items from a foreign vendor.</span></span> <span data-ttu-id="f5a43-106">Uma nota fiscal de importação registra informações de trânsito sobre os itens que você importa.</span><span class="sxs-lookup"><span data-stu-id="f5a43-106">An import fiscal document records transit information about the items that you import.</span></span> <span data-ttu-id="f5a43-107">A nota fiscal de importação é usada para liberar os itens das tarifas alfandegárias e validar a entrada dos itens no depósito da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="f5a43-107">The import fiscal document is used to release items from customs and to validate the entry of the items in the warehouse of the legal entity.</span></span> <span data-ttu-id="f5a43-108">É necessário especificar as informações da declaração de importação (o número de adição e o número da declaração de importação) para uma ordem de compra que é emitida para importar itens de um fornecedor estrangeiro antes de lançar a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="f5a43-108">You must specify the import declaration information (the addition number and import declaration number) for a purchase order that is issued to import items from a foreign vendor before you post the purchase order.</span></span> <span data-ttu-id="f5a43-109">Um documento fiscal de importação direta inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="f5a43-109">A direct import fiscal document includes the following information:</span></span>

-   <span data-ttu-id="f5a43-110">Cálculo de impostos brasileiros para a nota fiscal de importação direta</span><span class="sxs-lookup"><span data-stu-id="f5a43-110">Calculation of Brazilian taxes for the direct import fiscal document</span></span>
-   <span data-ttu-id="f5a43-111">Informações introdutórias sobre a declaração de importação</span><span class="sxs-lookup"><span data-stu-id="f5a43-111">Introductory information about the import declaration</span></span>
-   <span data-ttu-id="f5a43-112">Geração de NF-e (modelo 55 de documento fiscal eletrônico brasileiro)</span><span class="sxs-lookup"><span data-stu-id="f5a43-112">Generation of the NF-e (Brazilian electronic fiscal document model 55)</span></span>
-   <span data-ttu-id="f5a43-113">Um documento DANFE impresso</span><span class="sxs-lookup"><span data-stu-id="f5a43-113">A printed DANFE document</span></span>
-   <span data-ttu-id="f5a43-114">Integração com o módulo **Livros fiscais**</span><span class="sxs-lookup"><span data-stu-id="f5a43-114">Integration with the **Fiscal books** module</span></span>

<span data-ttu-id="f5a43-115">**Observação:** Você também pode emitir uma nota fiscal de importação ao criar uma ordem de compra para importar serviços de um fornecedor estrangeiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-115">**Note:** You can also issue an import fiscal document when you create a purchase order to import services from a foreign vendor.</span></span> <span data-ttu-id="f5a43-116">Ao importar um serviço, não é obrigatório especificar o número da declaração de importação e o número de adição da nota fiscal do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5a43-116">When you import a service, it's not required that you specify the import declaration number and addition number for the vendor invoice.</span></span> <span data-ttu-id="f5a43-117">Antes de gerar uma nota fiscal de importação, selecione a opção **Gerar nota fiscal recebida** para o fornecedor estrangeiro na página **Fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="f5a43-117">Before you can generate an import fiscal document, you must select the **Generate incoming fiscal document** option for the foreign vendor on the **Vendors** page.</span></span> <span data-ttu-id="f5a43-118">Você pode usar a opção **Cancelar** para cancelar uma nota fiscal de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-118">You can use **Cancel** to cancel an incorrect import fiscal document.</span></span> <span data-ttu-id="f5a43-119">É possível usar **Consultar** para carregar todas as notas fiscais, junto com as informações relacionadas para a página **Visualizador de nota fiscal**.</span><span class="sxs-lookup"><span data-stu-id="f5a43-119">You can use **Inquire** to load all fiscal documents, together with the related information, onto the **Fiscal document viewer** page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5a43-120">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f5a43-120">Prerequisites</span></span>
<span data-ttu-id="f5a43-121">Antes de criar e lançar uma nota fiscal de importação direta, você deve definir os seguintes parâmetros no grupo de campos **Declaração de importação** na guia **Nota fiscal** da página **Parâmetros brasileiros**:</span><span class="sxs-lookup"><span data-stu-id="f5a43-121">Before you can create and post a direct import fiscal document, you must set the following parameters in the **Import declaration** field group on the **Fiscal document** tab of the **Brazilian parameters** page:</span></span>

-   <span data-ttu-id="f5a43-122">**O valor da linha baseia-se em** – Selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f5a43-122">**Line amount is based on** – Select one of the following values:</span></span>
    -   <span data-ttu-id="f5a43-123">**FOB** – O valor de linha na nota fiscal é igual ao valor de linha bruta.</span><span class="sxs-lookup"><span data-stu-id="f5a43-123">**FOB** – The line amount in the fiscal document is equal to the gross line amount.</span></span>
    -   <span data-ttu-id="f5a43-124">**CIF + II** – O **Valor de linha** na nota fiscal é igual ao valor bruto de linha além dos encargos diversos (exceto encargos diversos do SISCOMEX ou cliente) relacionados à instalação do processo de importação para a linha da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5a43-124">**CIF + II** – The **Line amount** in the fiscal document is equal to the gross line amount plus all miscellaneous charges (except SISCOMEX and customer miscellaneous charges) that are related to the setup of the import process for the vendor invoice line.</span></span>
-   <span data-ttu-id="f5a43-125">**ID do Texto** – selecione o texto usado para imprimir informações de declaração de importação como informações adicionais na nota fiscal impresso ou no DANFE.</span><span class="sxs-lookup"><span data-stu-id="f5a43-125">**Text ID** – Select the text that is used to print import declaration information as additional information in the printed fiscal document or DANFE.</span></span>

## <a name="import-declaration"></a><span data-ttu-id="f5a43-126">Declaração da importação</span><span class="sxs-lookup"><span data-stu-id="f5a43-126">Import declaration</span></span>
<span data-ttu-id="f5a43-127">Após criar e confirmar a ordem de compra de um fornecedor estrangeiro e antes da fatura do fornecedor ser lançada, é possível inserir as informações sobre a declaração de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-127">After you've created and confirmed the purchase order for a foreign vendor, and before the vendor invoice is posted, you can enter information about the import declaration.</span></span> <span data-ttu-id="f5a43-128">Na página **Comércio exterior**, selecione o número da declaração de importação criado anteriormente, ou crie um novo número de declaração de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-128">On the **Foreign trade** page, select the import declaration number that you previously created, or create a new import declaration number.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5a43-129">Campo</span><span class="sxs-lookup"><span data-stu-id="f5a43-129">Field</span></span></th>
<th><span data-ttu-id="f5a43-130">descrição</span><span class="sxs-lookup"><span data-stu-id="f5a43-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f5a43-131">Número de declaração da importação</span><span class="sxs-lookup"><span data-stu-id="f5a43-131">Import declaration number</span></span></td>
<td><span data-ttu-id="f5a43-132">O número de identificação da declaração de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-132">The identification number of the import declaration.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-133">Data</span><span class="sxs-lookup"><span data-stu-id="f5a43-133">Date</span></span></td>
<td><span data-ttu-id="f5a43-134">A data em que a declaração de importação foi emitida.</span><span class="sxs-lookup"><span data-stu-id="f5a43-134">The date when the import declaration is issued.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5a43-135">Porto</span><span class="sxs-lookup"><span data-stu-id="f5a43-135">Port</span></span></td>
<td><span data-ttu-id="f5a43-136">O código de identificação do porto onde o item importado é carregado.</span><span class="sxs-lookup"><span data-stu-id="f5a43-136">The identification code of the port where the imported item is loaded.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-137">Descrição (descrição do porto)</span><span class="sxs-lookup"><span data-stu-id="f5a43-137">Description (port description)</span></span></td>
<td><span data-ttu-id="f5a43-138">O nome e a descrição do porto.</span><span class="sxs-lookup"><span data-stu-id="f5a43-138">The name and description of the port.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5a43-139">Estado do porto</span><span class="sxs-lookup"><span data-stu-id="f5a43-139">Port state</span></span></td>
<td><span data-ttu-id="f5a43-140">O estado no qual o porto está localizado.</span><span class="sxs-lookup"><span data-stu-id="f5a43-140">The state where the port is located.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-141">Tipo de DI</span><span class="sxs-lookup"><span data-stu-id="f5a43-141">DI type</span></span></td>
<td><span data-ttu-id="f5a43-142">O tipo da declaração de importação:</span><span class="sxs-lookup"><span data-stu-id="f5a43-142">The type of import declaration:</span></span>
<ul>
<li><span data-ttu-id="f5a43-143"><strong>Declaração de importação</strong> – Uma declaração de importação detalhada é gerada.</span><span class="sxs-lookup"><span data-stu-id="f5a43-143"><strong>Import declaration</strong> – A detailed import declaration is generated.</span></span></li>
<li><span data-ttu-id="f5a43-144"><strong>Declaração de importação simplificada</strong> – Uma declaração de importação resumida é gerada.</span><span class="sxs-lookup"><span data-stu-id="f5a43-144"><strong>Simplified import declaration</strong> – A summarized import declaration is generated.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5a43-145">Data de nacionalização</span><span class="sxs-lookup"><span data-stu-id="f5a43-145">Nationalization date</span></span></td>
<td><span data-ttu-id="f5a43-146">A data na qual o item é nacionalizado no Brasil.</span><span class="sxs-lookup"><span data-stu-id="f5a43-146">The date when the item is nationalized in Brazil.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-147">Número do drawback</span><span class="sxs-lookup"><span data-stu-id="f5a43-147">Draw back number</span></span></td>
<td><span data-ttu-id="f5a43-148">O código de identificação da operação de drawback.</span><span class="sxs-lookup"><span data-stu-id="f5a43-148">The identification code of the draw-back operation.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5a43-149">Via de transporte</span><span class="sxs-lookup"><span data-stu-id="f5a43-149">Transport mode</span></span></td>
<td><span data-ttu-id="f5a43-150">O tipo de transporte.</span><span class="sxs-lookup"><span data-stu-id="f5a43-150">The type of transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-151">ARFMM</span><span class="sxs-lookup"><span data-stu-id="f5a43-151">ARFMM</span></span></td>
<td><span data-ttu-id="f5a43-152">O valor adicional de frete para o tipo de transporte <strong>Marinho</strong>.</span><span class="sxs-lookup"><span data-stu-id="f5a43-152">The amount of additional freight for transportation of the <strong>Marine</strong> type.</span></span></td>
</tr>
</tbody>
</table>

## <a name="scenario-overview"></a><span data-ttu-id="f5a43-153">Visão geral do cenário</span><span class="sxs-lookup"><span data-stu-id="f5a43-153">Scenario overview</span></span>
<span data-ttu-id="f5a43-154">Para esse cenário, você deve criar e lançar uma nota fiscal de importação direta.</span><span class="sxs-lookup"><span data-stu-id="f5a43-154">For this scenario, you must create and post a direct import fiscal document.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f5a43-155">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="f5a43-155">Background</span></span></td>
<td><span data-ttu-id="f5a43-156">A empresa importa os itens e deve emitir uma nota fiscal de entrada para os itens importados com corretos os impostos corretos calculados para os itens serem liberados nas Alfândegas.</span><span class="sxs-lookup"><span data-stu-id="f5a43-156">The company imports items and must issue an entrance nota fiscal for the imported items with the correct taxes calculated for the items to be released in Customs.</span></span> <span data-ttu-id="f5a43-157">As seguintes pessoas/funções estão envolvidas:</span><span class="sxs-lookup"><span data-stu-id="f5a43-157">The following people/roles are involved:</span></span>
<ul>
<li><span data-ttu-id="f5a43-158">Alicia (Agente de compras)</span><span class="sxs-lookup"><span data-stu-id="f5a43-158">Alicia (Purchasing agent)</span></span></li>
<li><span data-ttu-id="f5a43-159">April (coordenador de Contas a Pagar)</span><span class="sxs-lookup"><span data-stu-id="f5a43-159">April (Accounts payable coordinator)</span></span></li>
<li><span data-ttu-id="f5a43-160">Sammy (Remessa e recebimento)</span><span class="sxs-lookup"><span data-stu-id="f5a43-160">Sammy (Shipping and receiving)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f5a43-161">Metas do usuário</span><span class="sxs-lookup"><span data-stu-id="f5a43-161">User goals</span></span></td>
<td><ul>
<li><span data-ttu-id="f5a43-162">Ter os impostos (IPI, II, PIS, COFINS, ICMS) calculados corretamente para a nota fiscal de importação, de acordo com as regras especificadas pelo governo.</span><span class="sxs-lookup"><span data-stu-id="f5a43-162">Have the sales tax (II, IPI, PIS, COFINS, ICMS) correctly calculated for the import nota fiscal, according to the rules that are specified by the government.</span></span></li>
<li><span data-ttu-id="f5a43-163">Imprima a nota fiscal de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5a43-163">Print the entrance nota fiscal.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f5a43-164">Etapas de cenário</span><span class="sxs-lookup"><span data-stu-id="f5a43-164">Scenario steps</span></span></td>
<td><ol>
<li><span data-ttu-id="f5a43-165">Alicia cria uma ordem de compra para um fornecedor estrangeiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-165">Alicia creates a purchase order for a foreign vendor.</span></span> <span data-ttu-id="f5a43-166">A ordem de compra usa a moeda estrangeira pela qual o preço do item foi negociado.</span><span class="sxs-lookup"><span data-stu-id="f5a43-166">The purchase order uses the foreign currency that the item price was negotiated in.</span></span></li>
<li><span data-ttu-id="f5a43-167">O despachante aduaneiro notifica Alicia de que os itens chegaram no porto ou no aeroporto e fornece o valor previsto de imposto a ser pago, antes de o porto ou aeroporto liberar os itens.</span><span class="sxs-lookup"><span data-stu-id="f5a43-167">The Customs agent (despachante aduaneiro) notifies Alicia that the items arrived in the port or at the airport, and provides the estimated amount of sales taxes that must be paid before the port or airport can release the items.</span></span></li>
<li><span data-ttu-id="f5a43-168">April gera um pagamento antecipado na moeda da empresa do despachante aduaneiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-168">April generates a prepayment in the company&#39;s currency to the Customs agent.</span></span> <span data-ttu-id="f5a43-169">Ela usa o valor estimado do imposto como referência.</span><span class="sxs-lookup"><span data-stu-id="f5a43-169">She uses the estimated amount of sales tax as a reference.</span></span></li>
<li><span data-ttu-id="f5a43-170">O despachante aduaneiro gera um documento de declaração de importação por fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f5a43-170">Customs (Aduana) generates one import declaration document per vendor.</span></span> <span data-ttu-id="f5a43-171">Este documento de declaração de importação é entregue ao despachante aduaneiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-171">This import declaration document is delivered to the Customs agent.</span></span> <span data-ttu-id="f5a43-172">É baseado nos impostos que são apresentados na declaração de importação e gera e paga os documentos de pagamento de impostos (GARE).</span><span class="sxs-lookup"><span data-stu-id="f5a43-172">It&#39;s based on the taxes that are presented in the import declaration, and generates and pays the tax payment documents (GARE).</span></span></li>
<li><span data-ttu-id="f5a43-173">O despachante aduaneiro envia uma cópia do documento de declaração de importação para April.</span><span class="sxs-lookup"><span data-stu-id="f5a43-173">The Customs agent sends a copy of the import declaration document to April.</span></span> <span data-ttu-id="f5a43-174">April ajusta os valores de encargos diversos relacionados a frete, seguro e SISCOMEX em ordens de compra relacionadas ao processo de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-174">April then adjusts the miscellaneous charge amounts that are related to freight, insurance, and SISCOMEX in the purchase orders that are related to the import process.</span></span> <span data-ttu-id="f5a43-175">(A distribuição de encargos diversos é criada manualmente por April).</span><span class="sxs-lookup"><span data-stu-id="f5a43-175">(The distribution of miscellaneous charges is done manually by April.)</span></span></li>
<li><span data-ttu-id="f5a43-176">April prepara a nota fiscal de importação, selecionando as ordens de compra e os itens da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="f5a43-176">April prepares the import nota fiscal by selecting the purchase orders and purchase order items.</span></span> <span data-ttu-id="f5a43-177">Em seguida, ela insere o número de declaração de importação na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="f5a43-177">She then enters the import declaration number in the purchase order.</span></span> <span data-ttu-id="f5a43-178">Ela também insere o número de adição nas linhas de nota fiscal de lançamento por item de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="f5a43-178">She also enters the addition number in the posting invoice lines per purchase order item.</span></span></li>
<li><span data-ttu-id="f5a43-179">April verifica o valor de impostos sobre vendas antes de lançar a nota fiscal de importação com a declaração de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-179">April checks the sales tax amount before she posts the import nota fiscal against the import declaration.</span></span> <span data-ttu-id="f5a43-180">Quando os valores de impostos da nota fiscal de importação e da declaração de importação forem correspondentes, ela lança a fatura.</span><span class="sxs-lookup"><span data-stu-id="f5a43-180">When the sales tax amounts of the import nota fiscal and import declaration match, she posts the invoice.</span></span> <span data-ttu-id="f5a43-181">Se os valores não forem correspondentes, ela ajusta os valores da nota fiscal da fatura que deve ser lançada.</span><span class="sxs-lookup"><span data-stu-id="f5a43-181">If the amounts don&#39;t match, she adjusts the sales tax amounts of the invoice that must be posted.</span></span> <span data-ttu-id="f5a43-182"><strong>Observação:</strong> Como as mercadorias ainda não estão incluídas na posse de uma empresa, um depósito diferente pode ser usado em cada linha de ordem de compra relacionada à nota fiscal de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-182"><strong>Note:</strong> Because the goods aren&#39;t yet in the company&#39;s possession, a different warehouse can be used on each purchase order line that is related to the import nota fiscal.</span></span></li>
<li><span data-ttu-id="f5a43-183">April envia a nota fiscal de fornecedor impressa ao despachante aduaneiro.</span><span class="sxs-lookup"><span data-stu-id="f5a43-183">April sends the printed vendor invoice to the Customs agent.</span></span></li>
<li><span data-ttu-id="f5a43-184">O despachante aduaneiro adiciona os documentos que são necessários para liberar as mercadorias: a declaração de importação, o GARE (impostos pagos) e a nota fiscal impressa de importação (própria nota fiscal).</span><span class="sxs-lookup"><span data-stu-id="f5a43-184">The Customs agent joins the documents that are required in order to release the goods: the import declaration, GARE (taxes paid), and printed import nota fiscal (self-nota fiscal).</span></span> <span data-ttu-id="f5a43-185">O despachante aduaneiro solicita que o porto ou o aeroporto libere as mercadorias.</span><span class="sxs-lookup"><span data-stu-id="f5a43-185">The Customs agent then requests that the port or airport release the goods.</span></span></li>
<li><span data-ttu-id="f5a43-186">As mercadorias são transportadas para o depósito da empresa.</span><span class="sxs-lookup"><span data-stu-id="f5a43-186">The goods are transported to the company’s warehouse.</span></span></li>
<li><span data-ttu-id="f5a43-187">Sammy recebe as mercadorias quando chegam na empresa e transfere os itens de depósito temporário para o depósito efetivo.</span><span class="sxs-lookup"><span data-stu-id="f5a43-187">Sammy receives the goods when they arrive at the company and transfers the items from the temporary warehouse to the effective warehouse.</span></span></li>
<li><span data-ttu-id="f5a43-188">Alicia usa a fatura complementar para adicionar as despesas do despachante aduaneiro, mais frete nacional ou outros custos relacionados ao processo de importação, após a nacionalização de mercadorias (entrada no território brasil), aos custos do item da nota fiscal original de importação.</span><span class="sxs-lookup"><span data-stu-id="f5a43-188">Alicia uses the complementary invoice to add the Customs agent expenses, plus national freight or other costs that are related to the import process after nationalization of goods (entrance into the Brazilian territory) occurs, to the item costs of the original import nota fiscal.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>





