---
title: Automação das faturas dos fornecedores
description: Este tópico explica os recursos disponíveis para a automação ponta a ponta de notas fiscais de fornecedor, até mesmo notas fiscais que incluem anexos.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ba986afb5c17c7a317b47d1e9cf4ae57ac29da97
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176473"
---
# <a name="vendor-invoice-automation"></a><span data-ttu-id="a990a-103">Automação das faturas dos fornecedores</span><span class="sxs-lookup"><span data-stu-id="a990a-103">Vendor invoice automation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a990a-104">Este tópico explica os recursos disponíveis para a automação ponta a ponta de notas fiscais de fornecedor, até mesmo notas fiscais que incluem anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-104">This topic explains the features that are available for end-to-end automation of vendor invoices, even invoices that include attachments.</span></span>

<span data-ttu-id="a990a-105">As organizações que desejam agilizar seus processos de Contas a Pagar (AP) geralmente identificam o processamento da fatura como uma das principais áreas de processo que devem ser mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="a990a-105">Organizations that want to streamline their Accounts payable (AP) processes often identify invoice processing as one of the top process areas that should be more efficient.</span></span> <span data-ttu-id="a990a-106">Em muitos casos, essas organizações descarregam o processamento de faturas em papel para um provedor de serviços de reconhecimento óptico de caracteres (OCR) de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a990a-106">In many cases, these organizations offload the processing of paper invoices to a third-party optical character recognition (OCR) service provider.</span></span> <span data-ttu-id="a990a-107">Eles então recebem metadados de fatura legíveis por máquina, juntamente com uma imagem digitalizada de cada fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-107">They then receive machine-readable invoice metadata together with a scanned image of each invoice.</span></span> <span data-ttu-id="a990a-108">Para ajudar com a automação, uma solução de "última milha" foi construída para permitir o consumo desses artefatos no sistema de faturamento.</span><span class="sxs-lookup"><span data-stu-id="a990a-108">To help with automation, a “last mile” solution is then built to enable consumption of these artifacts in the invoicing system.</span></span> <span data-ttu-id="a990a-109">Agora, esta automação de "última milha" é habilitada e pronta para uso, por meio de uma solução de automação de fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-109">Now this “last mile” automation is enabled out of the box, through an invoice automation solution.</span></span>

## <a name="solution-context"></a><span data-ttu-id="a990a-110">Contexto da solução</span><span class="sxs-lookup"><span data-stu-id="a990a-110">Solution context</span></span>

<span data-ttu-id="a990a-111">A solução de automação de fatura permite uma interface padrão que pode aceitar metadados de fatura para o cabeçalho da fatura e linhas de fatura, e também os anexos aplicáveis ​​à fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-111">The invoice automation solution enables a standard interface that can accept invoice metadata for the invoice header and invoice lines, and also attachments that are applicable to the invoice.</span></span> <span data-ttu-id="a990a-112">Qualquer sistema externo que possa gerar artefatos compatíveis esta interface poderá enviar o feed para o processamento automático de faturas e anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-112">Any external system that can generate artifacts that comply with this interface will be able to send the feed for automatic processing of invoices and attachments.</span></span>

<span data-ttu-id="a990a-113">A ilustração a seguir mostra um exemplo de cenário de integração onde a Contoso se associou com um provedor de serviços de OCR para processamento de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a990a-113">The following illustration shows a sample integration scenario where Contoso has partnered with an OCR service provider for vendor invoice processing.</span></span> <span data-ttu-id="a990a-114">Os fornecedores da Contoso enviam faturas ao provedor de serviços por e-mail.</span><span class="sxs-lookup"><span data-stu-id="a990a-114">Contoso’s vendors send invoices to the service provider by email.</span></span> <span data-ttu-id="a990a-115">Através do processamento de OCR, o provedor de serviços gera metadados de fatura (cabeçalho e/ou linhas) e uma imagem digitalizada da fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-115">Through OCR processing, the service provider generates invoice metadata (header and/or lines) and a scanned image of the invoice.</span></span> <span data-ttu-id="a990a-116">Uma camada de integração transforma esses artefatos para que possam ser consumidos.</span><span class="sxs-lookup"><span data-stu-id="a990a-116">An integration layer then transforms these artifacts so that they can be consumed.</span></span>

![Cenário de integração de amostra](media/vendor_invoice_automation_01.png)

<span data-ttu-id="a990a-118">Várias variações do cenário anterior são possíveis se a integração da fatura for necessária.</span><span class="sxs-lookup"><span data-stu-id="a990a-118">Several variations of the preceding scenario are possible if invoice integration is required.</span></span> <span data-ttu-id="a990a-119">A migração de dados é outro caso de uso em que esta interface pode ser usada para criar faturas e anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-119">Data migration is another use case where this interface can be used to create invoices and attachments.</span></span>

### <a name="solution-components"></a><span data-ttu-id="a990a-120">Componentes da solução</span><span class="sxs-lookup"><span data-stu-id="a990a-120">Solution components</span></span>

<span data-ttu-id="a990a-121">A pegada de solução consiste nos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="a990a-121">The solution footprint consists of the following components:</span></span>

+ <span data-ttu-id="a990a-122">Entidades de dados para o cabeçalho da fatura, linhas de fatura e anexos de fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-122">Data entities for the invoice header, invoice lines, and invoice attachments</span></span>
+ <span data-ttu-id="a990a-123">Processamento de exceção para faturas</span><span class="sxs-lookup"><span data-stu-id="a990a-123">Exception processing for invoices</span></span>
+ <span data-ttu-id="a990a-124">Um visualizador de anexo lado a lado nas faturas</span><span class="sxs-lookup"><span data-stu-id="a990a-124">A side-by-side attachment viewer in invoices</span></span>

<span data-ttu-id="a990a-125">O restante deste tópico fornece descrições detalhadas desses componentes da solução.</span><span class="sxs-lookup"><span data-stu-id="a990a-125">The rest of this topic provides detailed descriptions of these solution components.</span></span>

## <a name="data-entities"></a><span data-ttu-id="a990a-126">Entidades de dados</span><span class="sxs-lookup"><span data-stu-id="a990a-126">Data entities</span></span>

<span data-ttu-id="a990a-127">Um pacote de dados é a unidade de trabalho que deve ser enviada para que cabeçalhos de fatura, linhas de fatura e anexos de fatura possam ser criados.</span><span class="sxs-lookup"><span data-stu-id="a990a-127">A data package is the unit of work that must be sent so that invoice headers, invoice lines, and invoice attachments can be created.</span></span> <span data-ttu-id="a990a-128">As seguintes entidades de dados são usadas para os artefatos que compõem o pacote de dados:</span><span class="sxs-lookup"><span data-stu-id="a990a-128">The following data entities are used for the artifacts that make up the data package:</span></span>

+ <span data-ttu-id="a990a-129">Cabeçalho da fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a990a-129">Vendor invoice header</span></span>
+ <span data-ttu-id="a990a-130">Linha de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a990a-130">Vendor invoice line</span></span>
+ <span data-ttu-id="a990a-131">Anexo de documento de fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a990a-131">Vendor invoice document attachment</span></span>

<span data-ttu-id="a990a-132">O anexo do documento de fatura do fornecedor é uma nova entidade de dados que é introduzida como parte desse recurso.</span><span class="sxs-lookup"><span data-stu-id="a990a-132">Vendor invoice document attachment is a new data entity that is introduced as part of this feature.</span></span> <span data-ttu-id="a990a-133">A entidade do cabeçalho da fatura de fornecedor foi modificada para que ele suporte anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-133">The Vendor invoice header entity has been modified so that it supports attachments.</span></span> <span data-ttu-id="a990a-134">A entidade da linha de fatura do fornecedor não foi modificada para esse recurso.</span><span class="sxs-lookup"><span data-stu-id="a990a-134">The Vendor invoice line entity hasn’t been modified for this feature.</span></span>

<span data-ttu-id="a990a-135">Este tópico não fornece uma definição detalhada de um pacote de dados.</span><span class="sxs-lookup"><span data-stu-id="a990a-135">This topic doesn’t give a detailed definition of a data package.</span></span> <span data-ttu-id="a990a-136">Também não explica como criar pacotes de dados.</span><span class="sxs-lookup"><span data-stu-id="a990a-136">It also doesn’t explain how to create data packages.</span></span> <span data-ttu-id="a990a-137">Para essa informações, consulte [Estrutura entidades de dados e pacotes](../../dev-itpro/data-entities/data-entities-data-packages.md).</span><span class="sxs-lookup"><span data-stu-id="a990a-137">For this information, see [Data entities and packages framework](../../dev-itpro/data-entities/data-entities-data-packages.md).</span></span>

<span data-ttu-id="a990a-138">Para gerar rapidamente dados de teste que incluem faturas e anexos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a990a-138">To quickly generate test data that includes invoices and attachments, follow these steps.</span></span>

1. <span data-ttu-id="a990a-139">Entre na sua instância.</span><span class="sxs-lookup"><span data-stu-id="a990a-139">Sign in to your instance.</span></span>
1. <span data-ttu-id="a990a-140">Vá para **Contas a pagar** > **Faturas** > **Faturas de fornecedor em aberto**.</span><span class="sxs-lookup"><span data-stu-id="a990a-140">Go to **Accounts payables** > **Invoices** > **Pending vendor invoices**.</span></span>
1. <span data-ttu-id="a990a-141">Crie faturas com linhas e anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-141">Create invoices that have lines and attachments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a990a-142">Os anexos devem ser anexos de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a990a-142">The attachments must be header attachments.</span></span> <span data-ttu-id="a990a-143">Atualmente, a entidade de anexo de documento de fatura de fornecedor não suporta anexos de linha.</span><span class="sxs-lookup"><span data-stu-id="a990a-143">Currently, the Vendor invoice document attachment entity doesn’t support line attachments.</span></span>

1. <span data-ttu-id="a990a-144">Abra o espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="a990a-144">Open the **Data management** workspace.</span></span>
1. <span data-ttu-id="a990a-145">Crie um trabalho de exportação que inclua o cabeçalho da fatura de fornecedor, a linha da fatura de fornecedor e as entidades de anexo do documento de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a990a-145">Create an export job that includes the Vendor invoice header, Vendor invoice line, and Vendor invoice document attachment entities.</span></span>
1. <span data-ttu-id="a990a-146">Exporte os dados.</span><span class="sxs-lookup"><span data-stu-id="a990a-146">Export the data.</span></span>
1. <span data-ttu-id="a990a-147">Baixe os dados exportados na forma de pacote.</span><span class="sxs-lookup"><span data-stu-id="a990a-147">Download the exported data as a package.</span></span> <span data-ttu-id="a990a-148">Agora você pode usar o pacote para importar dados em instâncias de destino para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="a990a-148">You can now use the package to import data into target instances for testing purposes.</span></span>

### <a name="determining-the-legal-entity-for-an-invoice"></a><span data-ttu-id="a990a-149">Determinar a entidade legal para uma fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-149">Determining the legal entity for an invoice</span></span>

<span data-ttu-id="a990a-150">As faturas que são importadas através de pacotes de dados podem ser associadas à entidade legal à qual pertencem de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="a990a-150">Invoices that are imported via data packages can be associated with the legal entity that they belong to in two ways:</span></span>

+ <span data-ttu-id="a990a-151">O trabalho de importação que processa a fatura importa-a para a mesma empresa em que o trabalho estava agendado no espaço de trabalho **Gerenciamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="a990a-151">The import job that processes the invoice imports it into the same company in which the job was scheduled in the **Data management** workspace.</span></span> <span data-ttu-id="a990a-152">Em outras palavras, a empresa do trabalho determina a empresa à qual a fatura pertence.</span><span class="sxs-lookup"><span data-stu-id="a990a-152">In other words, the company of the job determines the company that the invoice belongs to.</span></span>
+ <span data-ttu-id="a990a-153">Quando o pacote de dados que contém as faturas é enviado para o Finance, o solicitante (ou seja, o aplicativo de integração que funciona fora do Finance) pode mencionar explicitamente a ID da empresa na solicitação HTTP.</span><span class="sxs-lookup"><span data-stu-id="a990a-153">When the data package that contains invoices is sent to Finance, the caller (that is, the integration application that runs outside of Finance) can explicitly mention the company ID in the HTTP request.</span></span> <span data-ttu-id="a990a-154">Nesse caso, o contexto da empresa em que o trabalho de processamento é executado no Finance é substituído, e as faturas são importadas para a empresa que foi passada por meio da solicitação HTTP.</span><span class="sxs-lookup"><span data-stu-id="a990a-154">In this case, the company context in which the processing job runs in Finance is overridden, and the invoices are imported into the company that was passed via the HTTP request.</span></span>

> [!NOTE]
> <span data-ttu-id="a990a-155">Esse comportamento é um comportamento padrão de gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="a990a-155">This behavior is standard data management behavior.</span></span> <span data-ttu-id="a990a-156">É explicado aqui, no contexto das faturas, apenas por uma questão de exaustividade.</span><span class="sxs-lookup"><span data-stu-id="a990a-156">It’s explained here, in the context of invoices, just for the sake of completeness.</span></span>

## <a name="exception-processing"></a><span data-ttu-id="a990a-157">Processamento de exceções</span><span class="sxs-lookup"><span data-stu-id="a990a-157">Exception processing</span></span>

<span data-ttu-id="a990a-158">Nos cenários em que as faturas dos fornecedores entram no Finance and Operations por meio da integração, deve haver uma maneira fácil para um membro da equipe de contas a pagar processar exceções ou faturas que falharam e criar faturas pendentes fora das faturas que falharam.</span><span class="sxs-lookup"><span data-stu-id="a990a-158">In scenarios where vendor invoices come into Finance and Operations via integration, there must be an easy way for an Accounts payable team member to process exceptions or failed invoices, and to create pending invoices out of failed invoices.</span></span> <span data-ttu-id="a990a-159">Esse processamento de exceção para faturas de fornecedores agora é parte do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a990a-159">This exception processing for vendor invoices is now part of Finance and Operations.</span></span>

### <a name="exceptions-list-page"></a><span data-ttu-id="a990a-160">Página da lista de exceções</span><span class="sxs-lookup"><span data-stu-id="a990a-160">Exceptions list page</span></span>

<span data-ttu-id="a990a-161">A página da lista nova para exceções de fatura está disponível em **Contas a pagar** > **Faturas** > **Importar falhas** > **Faturas de fornecedor que falharam na importação**.</span><span class="sxs-lookup"><span data-stu-id="a990a-161">The new list page for invoice exceptions is available at **Accounts payable** > **Invoices** > **Import failures** > **Vendor invoices that failed to import**.</span></span> <span data-ttu-id="a990a-162">Esta página mostra todos os registros de cabeçalho da fatura de fornecedor na tabela de teste da entidade de dados do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a990a-162">This page shows all the vendor invoice header records from the staging table of the Vendor invoice header data entity.</span></span> <span data-ttu-id="a990a-163">Observe que você pode visualizar os mesmos registros no espaço de trabalho **Gerenciamento de dados** onde você também pode executar as mesmas ações que são fornecidas no recurso de tratamento de exceção.</span><span class="sxs-lookup"><span data-stu-id="a990a-163">Note that you can view the same records from the **Data management** workspace, where you can also perform the same actions that are provided in the exception handling feature.</span></span> <span data-ttu-id="a990a-164">No entanto, a UI que o recurso de tratamento de exceção fornece é otimizada para um usuário funcional.</span><span class="sxs-lookup"><span data-stu-id="a990a-164">However, the UI that the exception handling feature provides is optimized for a functional user.</span></span>

![Página da lista de exceções](media/vendor_invoice_automation_02.png)

<span data-ttu-id="a990a-166">Esta página da lista inclui os seguintes campos que entram através do feed:</span><span class="sxs-lookup"><span data-stu-id="a990a-166">This list page includes the following fields that come in via the feed:</span></span>

+ <span data-ttu-id="a990a-167">**Empresa** – A empresa à qual a fatura pertence</span><span class="sxs-lookup"><span data-stu-id="a990a-167">**Company** – The company that the invoice belongs to</span></span>
+ <span data-ttu-id="a990a-168">**Mensagem de erro** – A mensagem de erro que a estrutura de gerenciamento de dados envolve para explicar por que a fatura não pôde ser criada</span><span class="sxs-lookup"><span data-stu-id="a990a-168">**Error message** – The error message that the data management framework issues to explain why the invoice could not be created</span></span>
+ <span data-ttu-id="a990a-169">**Número** – O número da fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-169">**Number** – The invoice number</span></span>
+ <span data-ttu-id="a990a-170">**Conta de fatura**</span><span class="sxs-lookup"><span data-stu-id="a990a-170">**Invoice account**</span></span>
+ <span data-ttu-id="a990a-171">**Nome** – O nome do fornecedor</span><span class="sxs-lookup"><span data-stu-id="a990a-171">**Name** – The vendor’s name</span></span>
+ <span data-ttu-id="a990a-172">**Conta de fornecedor**</span><span class="sxs-lookup"><span data-stu-id="a990a-172">**Vendor account**</span></span>
+ <span data-ttu-id="a990a-173">**Ordem de compra** – O número da ordem de compra (OC) da fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-173">**Purchase order** – The purchase order (PO) number for the invoice</span></span>
+ <span data-ttu-id="a990a-174">**Data do lançamento**</span><span class="sxs-lookup"><span data-stu-id="a990a-174">**Posting date**</span></span>
+ <span data-ttu-id="a990a-175">**Data da fatura**</span><span class="sxs-lookup"><span data-stu-id="a990a-175">**Invoice date**</span></span>
+ <span data-ttu-id="a990a-176">**Descrição da fatura**</span><span class="sxs-lookup"><span data-stu-id="a990a-176">**Invoice description**</span></span>
+ <span data-ttu-id="a990a-177">**Moeda**</span><span class="sxs-lookup"><span data-stu-id="a990a-177">**Currency**</span></span>
+ <span data-ttu-id="a990a-178">**Registro**</span><span class="sxs-lookup"><span data-stu-id="a990a-178">**Log**</span></span>
+ <span data-ttu-id="a990a-179">**Referência de linha** – O identificador proveniente do sistema externo</span><span class="sxs-lookup"><span data-stu-id="a990a-179">**Line reference** – The identifier that comes from the external system</span></span>

    > [!NOTE]
    > <span data-ttu-id="a990a-180">A linha de referência não é o ID de fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-180">The line reference isn’t the invoice ID.</span></span>

<span data-ttu-id="a990a-181">Esta página da lista também possui um painel de visualização que você pode usar das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a990a-181">This list page also has a preview pane that you can used in the following ways:</span></span>

+ <span data-ttu-id="a990a-182">Veja toda a mensagem de erro, para que não seja necessário expandir a coluna **Mensagem de erro** na grade.</span><span class="sxs-lookup"><span data-stu-id="a990a-182">View the whole error message, so that you don’t have to expand the **Error message** column in the grid.</span></span>
+ <span data-ttu-id="a990a-183">Exiba toda a lista de anexos para a fatura, se algum anexo tiver sido fornecido com a fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-183">View the whole list of attachments for the invoice, if any attachments came with the invoice.</span></span>

<span data-ttu-id="a990a-184">A página da lista suporta as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a990a-184">The list page supports the following actions:</span></span>

+ <span data-ttu-id="a990a-185">**Editar** – Abra a gravação de exceção no modo de edição, para que você possa resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="a990a-185">**Edit** – Open the exception record in edit mode, so that you can fix the issues.</span></span>
+ <span data-ttu-id="a990a-186">**Opções** – Acessar opções padrão disponíveis em páginas de listagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-186">**Options** – Access the standard options that are available on list pages.</span></span> <span data-ttu-id="a990a-187">Você pode usar a opção **Adicionar ao espaço de trabalho** para inserir a página da lista de exceções em seu espaço de trabalho como uma lista ou bloco.</span><span class="sxs-lookup"><span data-stu-id="a990a-187">You can use the **Add to workspace** option to pin the exceptions list page to your workspace as a list or tile.</span></span>

### <a name="exception-details-page"></a><span data-ttu-id="a990a-188">Página de detalhes de exceção</span><span class="sxs-lookup"><span data-stu-id="a990a-188">Exception details page</span></span>

<span data-ttu-id="a990a-189">Quando você inicia o modo de edição, aparece a página de detalhes da exceção da fatura com problemas.</span><span class="sxs-lookup"><span data-stu-id="a990a-189">When you start edit mode, the exception details page for the invoice that has issues appears.</span></span> <span data-ttu-id="a990a-190">Se houver anexos, a fatura e o anexo padrão aparecem lado a lado na página de detalhes da exceção.</span><span class="sxs-lookup"><span data-stu-id="a990a-190">If there are any attachments, the invoice and the default attachment appear side by side on the exception details page.</span></span>

![Página de detalhes de exceção](media/vendor_invoice_automation_03.png)

<span data-ttu-id="a990a-192">Na ilustração anterior, não havia nenhuma linha para o cabeçalho da fatura de fornecedor que entrou.</span><span class="sxs-lookup"><span data-stu-id="a990a-192">In the preceding illustration, there weren’t any lines for the vendor invoice header that came in.</span></span> <span data-ttu-id="a990a-193">Portanto, a seção de linhas está vazia.</span><span class="sxs-lookup"><span data-stu-id="a990a-193">Therefore, the lines section is empty.</span></span>

<span data-ttu-id="a990a-194">A página de detalhes da exceção suporta a seguinte operação:</span><span class="sxs-lookup"><span data-stu-id="a990a-194">The exception details page supports the following operation:</span></span>

+ <span data-ttu-id="a990a-195">**Criar fatura em aberto** – Depois de corrigir os problemas na fatura como parte do processamento de exceções, você pode clicar neste botão para criar a fatura pendente.</span><span class="sxs-lookup"><span data-stu-id="a990a-195">**Create pending invoice** – After you’ve fixed the issues on the invoice as part of exception processing, you can click this button to create the pending invoice.</span></span> <span data-ttu-id="a990a-196">A criação de faturas em aberto ocorre em segundo plano (como uma operação assíncrona).</span><span class="sxs-lookup"><span data-stu-id="a990a-196">The creation of pending invoices occurs in the background (as an asynchronous operation).</span></span>

### <a name="shared-service-vs-organization-based-exception-processing"></a><span data-ttu-id="a990a-197">Serviço compartilhado versus processamento de exceções baseado em organização</span><span class="sxs-lookup"><span data-stu-id="a990a-197">Shared service vs. organization-based exception processing</span></span>

<span data-ttu-id="a990a-198">A página da lista de exceções suporta as construções de segurança padrão que a área de trabalho **Gerenciamento de dados** suporta para processamento dos registros de preparo.</span><span class="sxs-lookup"><span data-stu-id="a990a-198">The exceptions list page supports the standard security constructs that the **Data management** workspace supports for the processing of staging records.</span></span> <span data-ttu-id="a990a-199">O trabalho de importação de fatura pode ser protegido das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a990a-199">The invoice import job can be secured in the following ways:</span></span>

+ <span data-ttu-id="a990a-200">Por função de usuário</span><span class="sxs-lookup"><span data-stu-id="a990a-200">By user role</span></span>
+ <span data-ttu-id="a990a-201">Por usuário</span><span class="sxs-lookup"><span data-stu-id="a990a-201">By user</span></span>
+ <span data-ttu-id="a990a-202">Por entidade legal</span><span class="sxs-lookup"><span data-stu-id="a990a-202">By legal entity</span></span>

![Trabalho de importação garantido por função de usuário e entidade legal](media/vendor_invoice_automation_04.png)

<span data-ttu-id="a990a-204">Se a segurança estiver configurada para o trabalho de importação de fatura, a página da lista de exceções estará de acordo com essas configurações.</span><span class="sxs-lookup"><span data-stu-id="a990a-204">If security is configured for the invoice import job, the exceptions list page honors those settings.</span></span> <span data-ttu-id="a990a-205">Os usuários poderão ver apenas os registros de exceções de fatura que esta configuração permite ver.</span><span class="sxs-lookup"><span data-stu-id="a990a-205">Users will be able to see only the invoice exception records that this setup allows them to see.</span></span>

<span data-ttu-id="a990a-206">Por exemplo, a Contoso decidiu processar exceções de fatura por entidade legal.</span><span class="sxs-lookup"><span data-stu-id="a990a-206">For example, Contoso has decided to process invoice exceptions by legal entity.</span></span> <span data-ttu-id="a990a-207">Portanto, a segurança é configurada no trabalho de importação de fatura de tal forma que um usuário na entidade legal A pode ver apenas exceções de fatura na entidade legal A, enquanto um usuário na entidade legal B pode ver apenas exceções de fatura na entidade legal B. Esta configuração permite a segregação de funções para a gestão de exceções de fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-207">Therefore, security is configured on the invoice import job in such a way that a user in legal entity A can see only invoice exceptions in legal entity A, whereas a user in legal entity B can see only invoice exceptions in legal entity B. This setup enables segregation of duties for the management of invoice exceptions.</span></span>

<span data-ttu-id="a990a-208">A Contoso também pode decidir não aplicar qualquer segurança, de modo que os mesmos usuários possam processar exceções de faturamento para todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="a990a-208">Contoso could also decide not to enforce any security, so that the same users can process invoice exceptions for all legal entities.</span></span> <span data-ttu-id="a990a-209">Essa configuração permite um cenário de serviços compartilhados para o gerenciamento de exceções de fatura.</span><span class="sxs-lookup"><span data-stu-id="a990a-209">This setup enables a shared services scenario for the management of invoice exceptions.</span></span>

## <a name="side-by-side-attachment-viewer"></a><span data-ttu-id="a990a-210">Visualizador de anexo lado a lado</span><span class="sxs-lookup"><span data-stu-id="a990a-210">Side-by-side attachment viewer</span></span>

<span data-ttu-id="a990a-211">Para ajudá-lo a visualizar facilmente os anexos para as faturas de fornecedor, as seguintes páginas que são usadas no processo de faturamento agora fornecem um visualizador de anexos:</span><span class="sxs-lookup"><span data-stu-id="a990a-211">To help you easily view the attachments for vendor invoices, the following pages that are used in the invoicing process now provide an attachment viewer:</span></span>

+ <span data-ttu-id="a990a-212">**Manuseio de exceção**</span><span class="sxs-lookup"><span data-stu-id="a990a-212">**Exception handling**</span></span>
+ <span data-ttu-id="a990a-213">Página **Faturas de fornecedor em aberto** (também disponível no processo de revisão de fatura)</span><span class="sxs-lookup"><span data-stu-id="a990a-213">**Pending vendor invoices** page (also available in the invoice review process)</span></span>
+ <span data-ttu-id="a990a-214">Página de consulta **Diário de fatura** (para as faturas lançadas)</span><span class="sxs-lookup"><span data-stu-id="a990a-214">**Invoice journal** inquiry page (for posted invoices)</span></span>

<span data-ttu-id="a990a-215">Veja aqui a funcionalidade principal que o visualizador de anexos fornece:</span><span class="sxs-lookup"><span data-stu-id="a990a-215">Here is the main functionality that the attachment viewer provides:</span></span>

+ <span data-ttu-id="a990a-216">Veja todos os tipos de anexos suportados pelo Gerenciamento de documentos (arquivos, imagens, URLs e notas).</span><span class="sxs-lookup"><span data-stu-id="a990a-216">View all attachment types that Document management supports (files, images, URLs, and notes).</span></span>
+ <span data-ttu-id="a990a-217">Exiba arquivos TIFF de várias páginas.</span><span class="sxs-lookup"><span data-stu-id="a990a-217">View multi-page TIFF files.</span></span>
+ <span data-ttu-id="a990a-218">Execute as seguintes ações em arquivos de imagem:</span><span class="sxs-lookup"><span data-stu-id="a990a-218">Perform the following actions on image files:</span></span>
  + <span data-ttu-id="a990a-219">Realce as partes da imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-219">Highlight parts of the image.</span></span>
  + <span data-ttu-id="a990a-220">Bloqueie as partes da imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-220">Block parts of the image.</span></span>
  + <span data-ttu-id="a990a-221">Adicione notas à imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-221">Add annotations to the image.</span></span>
  + <span data-ttu-id="a990a-222">Aumente ou diminua o zoom na imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-222">Zoom in and out on the image.</span></span>
  + <span data-ttu-id="a990a-223">Filtre a imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-223">Pan the image.</span></span>
  + <span data-ttu-id="a990a-224">Desfaça e refaça ações.</span><span class="sxs-lookup"><span data-stu-id="a990a-224">Undo and redo actions.</span></span>
  + <span data-ttu-id="a990a-225">Ajuste o tamanho da imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-225">Fit the image to size.</span></span>

> [!NOTE]
> <span data-ttu-id="a990a-226">Essas ações estão disponíveis apenas para arquivos de imagem (JPEG, TIFF, PNG, etc.).</span><span class="sxs-lookup"><span data-stu-id="a990a-226">These actions are available only for image files (JPEG, TIFF, PNG, and so on).</span></span> <span data-ttu-id="a990a-227">Todas as alterações que você faz em uma imagem usando essas ações são salvas no arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="a990a-227">Any changes that you make to an image by using these actions are saved to the image file.</span></span> <span data-ttu-id="a990a-228">Atualmente, o visualizador de anexos não inclui capacidades de controle de versão ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="a990a-228">Currently, the attachment viewer doesn’t include versioning or auditing capabilities.</span></span>

### <a name="default-attachment"></a><span data-ttu-id="a990a-229">Anexo padrão</span><span class="sxs-lookup"><span data-stu-id="a990a-229">Default attachment</span></span>

<span data-ttu-id="a990a-230">Se uma fatura de fornecedor tiver mais de um anexo, você pode definir um dos documentos como anexo padrão na página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="a990a-230">If a vendor invoice has more than one attachment, you can set one of the documents as the default attachment on the **Attachments** page.</span></span> <span data-ttu-id="a990a-231">A opção **Anexo é o padrão** é uma nova opção que é adicionada como parte desse recurso.</span><span class="sxs-lookup"><span data-stu-id="a990a-231">The **Is default attachment** option is a new option that was added as part of this feature.</span></span> <span data-ttu-id="a990a-232">Esta opção também está exposta na entidade de dados de anexo do documento de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a990a-232">This option is also exposed in the Vendor invoice document attachment data entity.</span></span> <span data-ttu-id="a990a-233">Portanto, o anexo padrão pode ser configurado através de integrações.</span><span class="sxs-lookup"><span data-stu-id="a990a-233">Therefore, the default attachment can be set through integrations.</span></span>

<span data-ttu-id="a990a-234">Apenas um documento pode ser configurado como anexo padrão.</span><span class="sxs-lookup"><span data-stu-id="a990a-234">Only one document can be set as the default attachment.</span></span> <span data-ttu-id="a990a-235">Depois de configurar um documento como anexo padrão, ele é exibido automaticamente no visualizador de anexos quando a fatura é aberta.</span><span class="sxs-lookup"><span data-stu-id="a990a-235">After you set a document as the default attachment, it’s automatically shown in the attachment viewer when the invoice is opened.</span></span> <span data-ttu-id="a990a-236">Se você não definir nenhum documento como anexo padrão, o visualizador não mostrará automaticamente nenhum anexo quando a fatura for aberta.</span><span class="sxs-lookup"><span data-stu-id="a990a-236">If you don’t set any document as the default attachment, the viewer doesn’t automatically show any attachment when the invoice is opened.</span></span>

### <a name="showhide-invoice-attachments"></a><span data-ttu-id="a990a-237">Mostrar/ocultar anexos de fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-237">Show/hide invoice attachments</span></span>

<span data-ttu-id="a990a-238">Um novo botão que está disponível nas páginas de consulta **Processamento de exceções**, **Fatura em aberto**, e **Diário de fatura** permite exibir ou ocultar o visualizador de anexo.</span><span class="sxs-lookup"><span data-stu-id="a990a-238">A new button that is available on the **Exception processing**, **Pending invoice**, and **Invoice journal** inquiry pages lets you show or hide the attachment viewer.</span></span>

### <a name="security"></a><span data-ttu-id="a990a-239">Segurança</span><span class="sxs-lookup"><span data-stu-id="a990a-239">Security</span></span>

<span data-ttu-id="a990a-240">As seguintes ações no visualizador de anexos são controladas por meio de segurança baseada em função:</span><span class="sxs-lookup"><span data-stu-id="a990a-240">The following actions in the attachment viewer are controlled via role-based security:</span></span>

+ <span data-ttu-id="a990a-241">Realce</span><span class="sxs-lookup"><span data-stu-id="a990a-241">Highlighting</span></span>
+ <span data-ttu-id="a990a-242">Bloquear</span><span class="sxs-lookup"><span data-stu-id="a990a-242">Block</span></span>
+ <span data-ttu-id="a990a-243">Nota</span><span class="sxs-lookup"><span data-stu-id="a990a-243">Annotation</span></span>

### <a name="pending-vendor-invoices-page"></a><span data-ttu-id="a990a-244">Página de faturas de fornecedor em aberto</span><span class="sxs-lookup"><span data-stu-id="a990a-244">Pending vendor invoices page</span></span>

<span data-ttu-id="a990a-245">Os seguintes privilégios fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para as ações de destaque, bloqueio e anotação:</span><span class="sxs-lookup"><span data-stu-id="a990a-245">The following privileges provide ready-only access or read/write access to the attachment viewer for the highlighting, block, and annotation actions:</span></span>

+ <span data-ttu-id="a990a-246">**Manter a imagem de fatura de fornecedor** – Esse privilégio fornece acesso de leitura/gravação.</span><span class="sxs-lookup"><span data-stu-id="a990a-246">**Maintain vendor invoice image** – This privilege provides read/write access.</span></span>
+ <span data-ttu-id="a990a-247">**Exibir a imagem de fatura de fornecedor** – Esse privilégio fornece acesso somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a990a-247">**View vendor invoice image** – This privilege provides read-only access.</span></span>

<span data-ttu-id="a990a-248">Os seguintes deveres fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para essas ações:</span><span class="sxs-lookup"><span data-stu-id="a990a-248">The following duties provide read-only access or read/write access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a990a-249">**Manter faturas de fornecedor** – O privilégio Manter imagem da fatura do fornecedor é atribuído a este dever.</span><span class="sxs-lookup"><span data-stu-id="a990a-249">**Maintain vendor invoices** – The Maintain vendor invoice image privilege is assigned to this duty.</span></span>
+ <span data-ttu-id="a990a-250">**Consultar status da fatura de fornecedor** – O privilégio de Exibir imagem da fatura de vendedor é atribuído a este dever.</span><span class="sxs-lookup"><span data-stu-id="a990a-250">**Inquire into vendor invoice status** – The View vendor invoice image privilege is assigned to this duty.</span></span>

<span data-ttu-id="a990a-251">As seguintes funções fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para essas ações:</span><span class="sxs-lookup"><span data-stu-id="a990a-251">The following roles provide read-only access or read/write access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a990a-252">**Funcionário de contas a pagar** e **Gerente de contas a pagar** – O dever Manter faturas de fornecedor é atribuído a essas funções.</span><span class="sxs-lookup"><span data-stu-id="a990a-252">**Accounts payable clerk** and **Accounts payable manager** – The Maintain vendor invoices duty is assigned to these roles.</span></span>
+ <span data-ttu-id="a990a-253">**Funcionário de contas a pagar**, **Gerente de contas a pagar**, **Funcionário de pagamento centralizado de contas a pagar** e **Funcionário de pagamentos de contas a pagar** – O dever Consultar status da fatura de fornecedor é atribuído a essas funções.</span><span class="sxs-lookup"><span data-stu-id="a990a-253">**Accounts payable clerk**, **Accounts payable manager**, **Accounts payable centralized payments clerk**, and **Accounts payable payments clerk** – The Inquire into vendor invoice status duty is assigned to these roles.</span></span>

### <a name="invoice-exception-details-page"></a><span data-ttu-id="a990a-254">Página de detalhes de exceção de fatura</span><span class="sxs-lookup"><span data-stu-id="a990a-254">Invoice exception details page</span></span>

<span data-ttu-id="a990a-255">Os seguintes privilégios fornecem acesso somente leitura ou acesso de leitura/gravação ao visualizador de anexos para as ações de destaque, bloqueio e anotação.</span><span class="sxs-lookup"><span data-stu-id="a990a-255">The following privileges provide ready-only access or read/write access to the attachment viewer for the highlighting, block, and annotation actions.</span></span>

> [!NOTE]
> <span data-ttu-id="a990a-256">Fora da caixa, as funções mencionadas nesta seção fornecem acesso somente leitura às imagens de fatura no visualizador de anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-256">Out of the box, the roles that are mentioned in this section provide read-only access to the invoice images in the attachment viewer.</span></span> <span data-ttu-id="a990a-257">Se uma função também precisar ter acesso de gravação às imagens, você pode conceder acesso de gravação a essa função usando o privilégio e o dever que são descritos aqui.</span><span class="sxs-lookup"><span data-stu-id="a990a-257">If a role must also have write access to the images, you can grant write access to that role by using the privilege and duty that are described here.</span></span>

+ <span data-ttu-id="a990a-258">**Manter imagem da entidade de cabeçalho da fatura de fornecedor** – Este privilégio fornece acesso de leitura/gravação às imagens da fatura no visualizador de anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-258">**Maintain vendor invoice header entity image** – This privilege provides read/write access to the invoice images in the attachment viewer.</span></span>
+ <span data-ttu-id="a990a-259">**Exibir imagem de entidade de cabeçalho da fatura de fornecedor** – Este privilégio fornece visualização somente leitura para a imagem da fatura no visualizador de anexos.</span><span class="sxs-lookup"><span data-stu-id="a990a-259">**View vendor invoice header entity image** – This privilege provides read-only view to the invoice image in the attachment viewer.</span></span>

<span data-ttu-id="a990a-260">Os seguintes deveres fornecem acesso somente leitura ao visualizador de anexos para essas ações:</span><span class="sxs-lookup"><span data-stu-id="a990a-260">The following duties provide read-only access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a990a-261">**Manter faturas de fornecedor** – O privilégio Manter imagem da entidade de cabeçalho da fatura de fornecedor é atribuído a este dever.</span><span class="sxs-lookup"><span data-stu-id="a990a-261">**Maintain vendor invoices** – The Maintain vendor invoice header entity image privilege is assigned to this duty.</span></span>

<span data-ttu-id="a990a-262">As seguintes funções fornecem acesso somente leitura ao visualizador de anexos para essas ações:</span><span class="sxs-lookup"><span data-stu-id="a990a-262">The following roles provide read-only access to the attachment viewer for those actions:</span></span>

+ <span data-ttu-id="a990a-263">**Funcionário de contas a pagar** e **Gerente de contas a pagar** – O dever Manter faturas de fornecedor é atribuído a essas funções.</span><span class="sxs-lookup"><span data-stu-id="a990a-263">**Accounts payable clerk** and **Accounts payable manager** – The Maintain vendor invoices duty is assigned to these roles.</span></span>

<span data-ttu-id="a990a-264">Por padrão, se a função do usuário fornecer direitos de edição em qualquer página, o usuário também terá direitos de edição no visualizador de anexos para as ações de destaque, bloqueio e anotação.</span><span class="sxs-lookup"><span data-stu-id="a990a-264">By default, if the user role provides edit rights on any page, the user will also have edit rights on the attachments viewer for the highlighting, block, and annotation actions.</span></span> <span data-ttu-id="a990a-265">No entanto, se houver cenários em que uma função específica deve ter direitos de edição na página, mas não no visualizador de anexos, os privilégios apropriados da lista anterior podem ser usados para satisfazer o caso de uso.</span><span class="sxs-lookup"><span data-stu-id="a990a-265">However, if there are scenarios where a specific role should have edit rights on the page but not on the attachment viewer, the appropriate privileges from the preceding list can be used to satisfy the use case.</span></span>
