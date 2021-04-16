---
title: Sincronizar faturas de contrato no Field Service com faturas de texto livre no Supply Chain Management
description: Este tópico aborda os modelos e as tarefas subjacentes usados para sincronizar faturas de contrato no Dynamics 365 Field Service às faturas de texto livre no Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 04/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: f3066741781bd9058e09d7f577a35df4c9b453d4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819199"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a><span data-ttu-id="d2d35-103">Sincronizar faturas de contrato no Field Service com faturas de texto livre no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d2d35-103">Synchronize agreement invoices in Field Service to free text invoices in Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d2d35-104">Este tópico discute os modelos e as tarefas subjacentes usados para sincronizar faturas de contrato no Dynamics 365 Field Service às notas fiscais de texto livre no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d35-104">This topic discusses the templates and underlying tasks that are used to synchronize agreement invoices in Dynamics 365 Field Service to free text invoices in Dynamics 365 Supply Chain Management.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="d2d35-105">Modelos e tarefas</span><span class="sxs-lookup"><span data-stu-id="d2d35-105">Templates and tasks</span></span>

<span data-ttu-id="d2d35-106">O modelo e as tarefas subjacentes a seguir são usadas para executar a sincronização de faturas de contrato do Field Service para faturas de texto livre no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d35-106">The following template and underlying tasks are used to run synchronization of agreement invoices from Field Service to free text invoices in Supply Chain Management.</span></span>

<span data-ttu-id="d2d35-107">**Nome do modelo na Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="d2d35-107">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="d2d35-108">Faturas de contrato (Field Service para Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="d2d35-108">Agreement invoices (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="d2d35-109">**Nomes das tarefas no projeto de Integração de dados**</span><span class="sxs-lookup"><span data-stu-id="d2d35-109">**Names of the tasks in the Data integration project**</span></span>

- <span data-ttu-id="d2d35-110">Cabeçalhos de fatura</span><span class="sxs-lookup"><span data-stu-id="d2d35-110">Invoice headers</span></span>
- <span data-ttu-id="d2d35-111">Linhas da fatura</span><span class="sxs-lookup"><span data-stu-id="d2d35-111">Invoice lines</span></span>

<span data-ttu-id="d2d35-112">As sincronização a seguir é necessária antes que a sincronização de faturas de contrato possa ocorrer:</span><span class="sxs-lookup"><span data-stu-id="d2d35-112">The following synchronization is required before synchronization of agreement invoices can occur:</span></span>

- <span data-ttu-id="d2d35-113">Contas (Sales para Supply Chain Management) – Direto</span><span class="sxs-lookup"><span data-stu-id="d2d35-113">Accounts (Sales to Supply Chain Management) – Direct</span></span>

## <a name="entity-set"></a><span data-ttu-id="d2d35-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="d2d35-114">Entity set</span></span>

| <span data-ttu-id="d2d35-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="d2d35-115">Field Service</span></span>  | <span data-ttu-id="d2d35-116">Gerenciamento da Cadeia de Fornecedores</span><span class="sxs-lookup"><span data-stu-id="d2d35-116">Supply Chain Management</span></span>                 |
|----------------|----------------------------------------|
| <span data-ttu-id="d2d35-117">faturas</span><span class="sxs-lookup"><span data-stu-id="d2d35-117">invoices</span></span>       | <span data-ttu-id="d2d35-118">Cabeçalhos de fatura de texto livre de cliente do Dataverse</span><span class="sxs-lookup"><span data-stu-id="d2d35-118">Dataverse customer free text invoice headers</span></span> |
| <span data-ttu-id="d2d35-119">invoicedetails</span><span class="sxs-lookup"><span data-stu-id="d2d35-119">invoicedetails</span></span> | <span data-ttu-id="d2d35-120">Linhas de fatura de texto livre de cliente do Dataverse</span><span class="sxs-lookup"><span data-stu-id="d2d35-120">Dataverse customer free text invoice lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="d2d35-121">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="d2d35-121">Entity flow</span></span>

<span data-ttu-id="d2d35-122">As faturas criadas com base em um contrato no Field Service podem ser sincronizadas com o Supply Chain Management por um projeto de Integração de dados do Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d2d35-122">Invoices that are created from an agreement in Field Service can be synchronized to Supply Chain Management via a Microsoft Dataverse Data integration project.</span></span> <span data-ttu-id="d2d35-123">As atualizações dessas faturas serão sincronizadas com as faturas de texto livre no Supply Chain Management se o status de contabilidade das faturas de texto livre for **Em processamento**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-123">Updates to these invoices will be synchronized to the free text invoices in Supply Chain Management if the accounting status of the free text invoices is **In process**.</span></span> <span data-ttu-id="d2d35-124">Depois que as faturas de texto livre forem lançadas no Supply Chain Management e o status da contabilidade for atualizado para **Concluído**, você não poderá mais sincronizar atualizações do Field Service.</span><span class="sxs-lookup"><span data-stu-id="d2d35-124">After the free text invoices are posted in Supply Chain Management, and the accounting status is updated to **Completed**, you can no longer synchronize updates from Field Service.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="d2d35-125">Solução Field Service CRM</span><span class="sxs-lookup"><span data-stu-id="d2d35-125">Field Service CRM solution</span></span>

<span data-ttu-id="d2d35-126">A coluna **Tem Linhas com Origem de Contrato** foi adicionada à tabela **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-126">The **Has Lines With Agreement Origin** column has been added to the **Invoice** table.</span></span> <span data-ttu-id="d2d35-127">Essa coluna ajuda a garantir que somente as faturas criadas a partir de um contrato sejam sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="d2d35-127">This column helps guarantee that only invoices that are created from an agreement are synchronized.</span></span> <span data-ttu-id="d2d35-128">O valor será **verdadeiro** se a fatura contiver pelo menos uma linha de fatura que seja originária de um contrato.</span><span class="sxs-lookup"><span data-stu-id="d2d35-128">The value is **true** if the invoice contains at least one invoice line that originates from an agreement.</span></span>

<span data-ttu-id="d2d35-129">A coluna **Tem Origem de Contrato** foi adicionada à tabela **Linha de fatura**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-129">The **Has Agreement Origin** column has been added to the **Invoice Line** table.</span></span> <span data-ttu-id="d2d35-130">Essa coluna ajuda a garantir que somente as linhas de fatura criadas a partir de um contrato sejam sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="d2d35-130">This column helps guarantee that only invoice lines that are created from an agreement are synchronized.</span></span> <span data-ttu-id="d2d35-131">O valor será **verdadeiro** se a linha da fatura for originária de um contrato.</span><span class="sxs-lookup"><span data-stu-id="d2d35-131">The value is **true** if the invoice line originates from an agreement.</span></span>

<span data-ttu-id="d2d35-132">**Data da fatura** é um campo obrigatório no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d2d35-132">**Invoice date** is a mandatory field in Supply Chain Management.</span></span> <span data-ttu-id="d2d35-133">Portanto, a coluna deverá ter um valor no Field Service antes que a sincronização ocorra.</span><span class="sxs-lookup"><span data-stu-id="d2d35-133">Therefore, the column must have a value in Field Service before synchronization occurs.</span></span> <span data-ttu-id="d2d35-134">Para atender a esse requisito, lógica a seguir foi adicionada:</span><span class="sxs-lookup"><span data-stu-id="d2d35-134">To meet this requirement, the following logic is added:</span></span>

- <span data-ttu-id="d2d35-135">Se a coluna **Data da fatura** estiver em branco na tabela **Fatura** (ou seja, se não tiver nenhum valor), ela será definida como a data atual quando uma linha de fatura originária de um contrato for adicionada.</span><span class="sxs-lookup"><span data-stu-id="d2d35-135">If the **Invoice Date** column is blank on the **Invoice** table (that is, if it has no value), it's set to the current date when an invoice line that originates from an agreement is added.</span></span>
- <span data-ttu-id="d2d35-136">O usuário poderá alterar a coluna **Data da fatura**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-136">The user can change the **Invoice Date** column.</span></span> <span data-ttu-id="d2d35-137">No entanto, quando o usuário tentar salvar uma fatura originária de um contrato, ele receberá uma mensagem de erro de processo comercial se a coluna **Data da fatura** estiver em branco na fatura.</span><span class="sxs-lookup"><span data-stu-id="d2d35-137">However, when the user tries to save an invoice that originates from an agreement, he or she receives a business process error if the **Invoice Date** column is blank on the invoice.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="d2d35-138">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="d2d35-138">Prerequisites and mapping setup</span></span>

### <a name="in-supply-chain-management"></a><span data-ttu-id="d2d35-139">No Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d2d35-139">In Supply Chain Management</span></span>

<span data-ttu-id="d2d35-140">Uma origem de fatura deve ser configurada para a integração, para distinguir as faturas de texto livre no Supply Chain Management que são criadas com base em faturas de contrato no Field Service.</span><span class="sxs-lookup"><span data-stu-id="d2d35-140">An invoice origin must be set up for the integration, to distinguish the free text invoices in Supply Chain Management that are created from agreement invoices in Field Service.</span></span> <span data-ttu-id="d2d35-141">Quando uma fatura tiver uma origem do tipo **Integração de fatura de contrato** , o campo **Número da fatura externa** será exibido no cabeçalho **Fatura de venda** .</span><span class="sxs-lookup"><span data-stu-id="d2d35-141">When an invoice has an invoice origin of the **Agreement invoice integration** type, the **External invoice number** field is shown on the **Sales invoice** header.</span></span>

<span data-ttu-id="d2d35-142">Além de ser exibida no cabeçalho da fatura, as informação de **Número da fatura externa** pode ser usada para ajudar a garantir que as faturas criadas com base em faturas de contrato do Field Service sejam filtradas durante a sincronização de faturas do Supply Chain Management para o Field Service.</span><span class="sxs-lookup"><span data-stu-id="d2d35-142">Besides appearing on the invoice header, the **External invoice number** information can be used to help guarantee that invoices that are created from Field Service agreement invoices are filtered out during invoice synchronization from Supply Chain Management to Field Service.</span></span>

1. <span data-ttu-id="d2d35-143">Acesse **Contas a receber** \> **Configurar** \> **Códigos de origem da fatura**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-143">Go to **Accounts receivable** \> **Setup** \> **Invoice origin codes**.</span></span>
2. <span data-ttu-id="d2d35-144">Selecione **Nova** para criar uma nova origem de fatura.</span><span class="sxs-lookup"><span data-stu-id="d2d35-144">Select **New** to create a new invoice origin.</span></span>
3. <span data-ttu-id="d2d35-145">No campo **Origem da fatura** , insira um nome para a origem da fatura, como **FS**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-145">In the **Invoice origin** field, enter a name for the invoice origin, such as **FS**.</span></span>
4. <span data-ttu-id="d2d35-146">No campo **Descrição** insira uma descrição, como **Fatura de Contrato do Field Service**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-146">In the **Description** field, enter a description, such as **Field Service Agreement Invoice**.</span></span>
5. <span data-ttu-id="d2d35-147">Marque a caixa de seleção **Atribuição do tipo de origem** .</span><span class="sxs-lookup"><span data-stu-id="d2d35-147">Select the **Origin type assignment** check box.</span></span>
6. <span data-ttu-id="d2d35-148">Defina o campo **Tipo de origem da fatura** como **Integração de fatura de contrato**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-148">Set the **Invoice origin type** field to **Agreement invoice integration**.</span></span>
7. <span data-ttu-id="d2d35-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-149">Select **Save**.</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="d2d35-150">No Projeto de integração de dados</span><span class="sxs-lookup"><span data-stu-id="d2d35-150">In the Data Integration project</span></span>

<span data-ttu-id="d2d35-151">Tarefa: **linhas da fatura**</span><span class="sxs-lookup"><span data-stu-id="d2d35-151">Task: **Invoice lines**</span></span>  

<span data-ttu-id="d2d35-152">Verifique se o valor padrão do campo **Valor de Exibição da Conta Principal** do Supply Chain Management foi atualizado para corresponder ao valor desejado.</span><span class="sxs-lookup"><span data-stu-id="d2d35-152">Make sure that the default value for the Supply Chain Management field **Main Account Display Value** is updated to match the desired value.</span></span>

<span data-ttu-id="d2d35-153">O valor do modelo padrão é **401100**.</span><span class="sxs-lookup"><span data-stu-id="d2d35-153">The default template value is **401100**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="d2d35-154">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="d2d35-154">Template mapping in Data integration</span></span>

<span data-ttu-id="d2d35-155">As ilustrações a seguir mostram um mapeamento de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="d2d35-155">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a><span data-ttu-id="d2d35-156">Faturas de contrato (Field Service para Supply Chain Management): Cabeçalhos de fatura</span><span class="sxs-lookup"><span data-stu-id="d2d35-156">Agreement invoices (Field Service to Supply Chain Management): Invoice headers</span></span>

<span data-ttu-id="d2d35-157">[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span><span class="sxs-lookup"><span data-stu-id="d2d35-157">[![Template mapping in Data integration](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)</span></span>

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a><span data-ttu-id="d2d35-158">Faturas de contrato (Field Service para Supply Chain Management): Linhas da fatura</span><span class="sxs-lookup"><span data-stu-id="d2d35-158">Agreement invoices (Field Service to Supply Chain Management): Invoice lines</span></span>

<span data-ttu-id="d2d35-159">[![Mapeamento de modelo na Integração de dados](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span><span class="sxs-lookup"><span data-stu-id="d2d35-159">[![Template mapping in Data integration](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]