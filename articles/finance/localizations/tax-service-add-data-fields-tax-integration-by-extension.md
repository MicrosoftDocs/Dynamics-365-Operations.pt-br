---
title: Adicionar campos de dados na integração de imposto usando extensões
description: Este tópico explica como usar as extensões X++ para adicionar campos de dados na integração de imposto.
author: qire
ms.date: 03/26/2021
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
ms.openlocfilehash: fdf112bbdd5245d19ab1d07cfcf94c58bf8208c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830331"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="7ed56-103">Adicionar campos de dados na integração de imposto usando uma extensão</span><span class="sxs-lookup"><span data-stu-id="7ed56-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="7ed56-104">Este tópico explica como usar as extensões X++ para adicionar campos de dados na integração de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="7ed56-105">Esses campos podem ser estendidos para o modelo de dados de imposto do serviço de imposto e usados para determinar códigos de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="7ed56-106">Para obter mais informações, consulte [Adicionar campos de dados em configurações de imposto](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="7ed56-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="7ed56-107">Modelo de dados</span><span class="sxs-lookup"><span data-stu-id="7ed56-107">Data model</span></span>

<span data-ttu-id="7ed56-108">Os dados no modelo de dados contém objetos e são implementados por classes.</span><span class="sxs-lookup"><span data-stu-id="7ed56-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="7ed56-109">Veja esta lista dos objetos principais:</span><span class="sxs-lookup"><span data-stu-id="7ed56-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="7ed56-110">AxClass/TaxIntegration **Documento** Objeto</span><span class="sxs-lookup"><span data-stu-id="7ed56-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="7ed56-111">AxClass/TaxIntegration **Linha** Objeto</span><span class="sxs-lookup"><span data-stu-id="7ed56-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="7ed56-112">AxClass/TaxIntegration **TaxLine** Objeto</span><span class="sxs-lookup"><span data-stu-id="7ed56-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="7ed56-113">A ilustração abaixo mostra como esses objetos estão relacionados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="7ed56-114">[![Relação de objeto do modelo de dados](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="7ed56-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="7ed56-115">Um objeto de **Documento** pode conter muitos objetos de **Linha**.</span><span class="sxs-lookup"><span data-stu-id="7ed56-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="7ed56-116">Cada objeto contém metadados para o serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="7ed56-117">O `TaxIntegrationDocumentObject` tem metadados de `originAddress`, que contêm informações sobre o endereço de origem e os metadados `includingTax`, que indicam se o valor da linha inclui o imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="7ed56-118">O `TaxIntegrationLineObject` tem metadados `itemId`, `quantity`e `categoryId`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed56-119">O `TaxIntegrationLineObject` também implementa objetos de **Cobrança**.</span><span class="sxs-lookup"><span data-stu-id="7ed56-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="7ed56-120">Fluxo de integração</span><span class="sxs-lookup"><span data-stu-id="7ed56-120">Integration flow</span></span>

<span data-ttu-id="7ed56-121">Os dados no fluxo são manipulados pelas atividades.</span><span class="sxs-lookup"><span data-stu-id="7ed56-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="7ed56-122">Atividades principais</span><span class="sxs-lookup"><span data-stu-id="7ed56-122">Key activities</span></span>

* <span data-ttu-id="7ed56-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="7ed56-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="7ed56-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="7ed56-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="7ed56-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="7ed56-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="7ed56-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="7ed56-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="7ed56-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="7ed56-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="7ed56-128">As atividades são realizadas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="7ed56-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="7ed56-129">Recuperação da configuração</span><span class="sxs-lookup"><span data-stu-id="7ed56-129">Setting Retrieval</span></span>
2. <span data-ttu-id="7ed56-130">Recuperação de dados</span><span class="sxs-lookup"><span data-stu-id="7ed56-130">Data Retrieval</span></span>
3. <span data-ttu-id="7ed56-131">Serviço de cálculo</span><span class="sxs-lookup"><span data-stu-id="7ed56-131">Calculation Service</span></span>
4. <span data-ttu-id="7ed56-132">Câmbio da moeda</span><span class="sxs-lookup"><span data-stu-id="7ed56-132">Currency Exchange</span></span>
5. <span data-ttu-id="7ed56-133">Persistência de dados</span><span class="sxs-lookup"><span data-stu-id="7ed56-133">Data Persistence</span></span>

<span data-ttu-id="7ed56-134">Por exemplo, estender a **Recuperação de dados** antes do **Serviço de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="7ed56-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="7ed56-135">Atividades de recuperação de dados</span><span class="sxs-lookup"><span data-stu-id="7ed56-135">Data Retrieval activities</span></span>

<span data-ttu-id="7ed56-136">Essas atividades de **Recuperação de dados** recuperam dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="7ed56-137">Os adaptadores para transações diferentes estão disponíveis para recuperar dados de tabelas de transações diferentes:</span><span class="sxs-lookup"><span data-stu-id="7ed56-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="7ed56-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="7ed56-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="7ed56-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="7ed56-145">Nessas atividades de **Recuperação de dados**, os dados são copiados do banco de dados para `TaxIntegrationDocumentObject` e `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="7ed56-146">Como todas essas atividades incluem a mesma classe de modelo abstrata, elas têm métodos comuns.</span><span class="sxs-lookup"><span data-stu-id="7ed56-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="7ed56-147">Atividades de Serviço de cálculo</span><span class="sxs-lookup"><span data-stu-id="7ed56-147">Calculation Service activities</span></span>

<span data-ttu-id="7ed56-148">A atividade de **Serviço de cálculo** é o vínculo entre o serviço de imposto e a integração de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="7ed56-149">Essa atividade é responsável pelas seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="7ed56-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="7ed56-150">Criar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="7ed56-150">Construct the request.</span></span>
2. <span data-ttu-id="7ed56-151">Enviar a solicitação para o serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="7ed56-152">Obter a resposta do serviço de imposto.</span><span class="sxs-lookup"><span data-stu-id="7ed56-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="7ed56-153">Analisar a resposta.</span><span class="sxs-lookup"><span data-stu-id="7ed56-153">Parse the response.</span></span>

<span data-ttu-id="7ed56-154">Um campo de dados adicionado à solicitação será enviado junto com outros metadados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="7ed56-155">Implementação de extensão</span><span class="sxs-lookup"><span data-stu-id="7ed56-155">Extension implementation</span></span>

<span data-ttu-id="7ed56-156">Esta seção fornece etapas detalhadas que explicam como implementar a extensão.</span><span class="sxs-lookup"><span data-stu-id="7ed56-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="7ed56-157">Ele usa o **Centro de custo** e as dimensões financeiras do **Projeto** como exemplos.</span><span class="sxs-lookup"><span data-stu-id="7ed56-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="7ed56-158">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="7ed56-158">Step 1.</span></span> <span data-ttu-id="7ed56-159">Adicione a variável de dados na classe de objeto</span><span class="sxs-lookup"><span data-stu-id="7ed56-159">Add the data variable in the object class</span></span>

<span data-ttu-id="7ed56-160">A classe de objeto contém a variável de dados e os métodos getter/setter para os dados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="7ed56-161">Adicione o campo de dados a `TaxIntegrationDocumentObject` ou `TaxIntegrationLineObject`, dependendo do nível do campo.</span><span class="sxs-lookup"><span data-stu-id="7ed56-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="7ed56-162">O exemplo abaixo usa o nível da linha e o nome do arquivo é `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed56-163">Se o campo de dados que você está adicionando estiver no nível do documento, altere o nome do arquivo para `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

<span data-ttu-id="7ed56-164">O **Centro de custos** e o **Projeto** são adicionados como variáveis particulares.</span><span class="sxs-lookup"><span data-stu-id="7ed56-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="7ed56-165">Crie métodos getter e setter para esses campos de dados para gerenciar os dados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="7ed56-166">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="7ed56-166">Step 2.</span></span> <span data-ttu-id="7ed56-167">Recuperar dados do banco de dados</span><span class="sxs-lookup"><span data-stu-id="7ed56-167">Retrieve data from the database</span></span>

<span data-ttu-id="7ed56-168">Especifique a transação e estenda as classes de adaptador apropriadas para recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="7ed56-169">Por exemplo, se você usar uma transação de **Ordem de compra**, deverá estender `TaxIntegrationPurchTableDataRetrieval` e `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="7ed56-170">`TaxIntegrationPurchParmTableDataRetrieval` é herdado do `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="7ed56-171">Ele não deve ser alterado, a menos que a lógica das tabelas `purchTable` e `purchParmTable` seja diferente.</span><span class="sxs-lookup"><span data-stu-id="7ed56-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="7ed56-172">Se o campo de dados precisar ser adicionado para todas as transações, estenda todas as classes `DataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="7ed56-173">Como todas as atividades de **Recuperação de dados** incluem a mesma classe de modelo, as estruturas de classe, variáveis e métodos são semelhantes.</span><span class="sxs-lookup"><span data-stu-id="7ed56-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

<span data-ttu-id="7ed56-174">O exemplo a seguir mostra a estrutura básica quando a tabela `PurchTable` é usada.</span><span class="sxs-lookup"><span data-stu-id="7ed56-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

<span data-ttu-id="7ed56-175">Quando o método `CopyToDocument` é chamado, o buffer `this.purchTable` já existe.</span><span class="sxs-lookup"><span data-stu-id="7ed56-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="7ed56-176">A finalidade desse método é copiar todos os dados necessários da tabela `this.purchTable` para o objeto `document` usando o método setter criado na classe `DocumentObject`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="7ed56-177">Da mesma forma, um buffer `this.purchLine` já existe no método `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="7ed56-178">A finalidade desse método é copiar todos os dados necessários da tabela `this.purchLine` para o objeto `_line` usando o método setter criado na classe `LineObject`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="7ed56-179">A abordagem mais direta é estender os métodos `CopyToDocument` e `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="7ed56-180">No entanto, recomendamos que você experimente os métodos `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable` primeiro.</span><span class="sxs-lookup"><span data-stu-id="7ed56-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="7ed56-181">Se eles não funcionarem como esperado, implemente seu próprio método e o ative-o em `CopyToDocument` e `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="7ed56-182">Há três situações comuns em que você talvez use essa abordagem:</span><span class="sxs-lookup"><span data-stu-id="7ed56-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="7ed56-183">O campo obrigatório está em `PurchTable` ou `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="7ed56-184">Nessa situação, você pode estender `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="7ed56-185">Este é o código de exemplo.</span><span class="sxs-lookup"><span data-stu-id="7ed56-185">Here is the sample code.</span></span>

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- <span data-ttu-id="7ed56-186">Os dados necessários não estão na tabela padrão da transação.</span><span class="sxs-lookup"><span data-stu-id="7ed56-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="7ed56-187">No entanto, há algumas relações de associação com a tabela padrão e o campo é necessário na maioria das linhas.</span><span class="sxs-lookup"><span data-stu-id="7ed56-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="7ed56-188">Nessa situação, substitua `getDocumentQueryObject` ou `getLineObject` para consultar a tabela segundo as relações de associação.</span><span class="sxs-lookup"><span data-stu-id="7ed56-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="7ed56-189">No exemplo abaixo, o campo **Entregar agora** está integrado com a ordem de venda no nível de linha.</span><span class="sxs-lookup"><span data-stu-id="7ed56-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    <span data-ttu-id="7ed56-190">Neste exemplo, um buffer `mcrSalesLineDropShipment` é declarado, e a consulta é definida em `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="7ed56-191">A consulta usa a relação `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="7ed56-192">Enquanto estiver estendendo nessa situação, você poderá substituir `getLineQueryObject` pelo seu próprio objeto de consulta criado.</span><span class="sxs-lookup"><span data-stu-id="7ed56-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="7ed56-193">No entanto, observe os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="7ed56-193">However, note the following points:</span></span>

    * <span data-ttu-id="7ed56-194">Como o valor de retorno do método `getLineQueryObject` é `SysDaQueryObject`, você deve criar esse objeto usando a abordagem SysDa.</span><span class="sxs-lookup"><span data-stu-id="7ed56-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="7ed56-195">Não é possível remover a tabela existente.</span><span class="sxs-lookup"><span data-stu-id="7ed56-195">Can't remove existed table.</span></span>

- <span data-ttu-id="7ed56-196">Os dados necessários estarão relacionados à tabela de transações por uma relação de associação complicada, exceto se a relação não for um para um (1:1), mas de um para muitos (1:N).</span><span class="sxs-lookup"><span data-stu-id="7ed56-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="7ed56-197">Nessa situação, as coisas se tornam um pouco complicadas.</span><span class="sxs-lookup"><span data-stu-id="7ed56-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="7ed56-198">Essa situação se aplica ao exemplo de dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="7ed56-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="7ed56-199">Nessa situação, você pode implementar seu próprio método para recuperar os dados.</span><span class="sxs-lookup"><span data-stu-id="7ed56-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="7ed56-200">Este é o código de exemplo no arquivo `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="7ed56-201">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="7ed56-201">Step 3.</span></span> <span data-ttu-id="7ed56-202">Adicionar dados à solicitação</span><span class="sxs-lookup"><span data-stu-id="7ed56-202">Add data to the request</span></span>

<span data-ttu-id="7ed56-203">Estenda o método `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` ou `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` para adicionar dados à solicitação.</span><span class="sxs-lookup"><span data-stu-id="7ed56-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="7ed56-204">Este é o código de exemplo no arquivo `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

<span data-ttu-id="7ed56-205">Nesse código, `_destination` é o objeto wrapper usado para gerar a solicitação de lançamento, e `_source` é o objeto `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="7ed56-206">Defina a chave usada no formulário de solicitação como `private const str`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="7ed56-207">Defina o campo no método `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` usando o método `SetField`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="7ed56-208">O tipo de dados do segundo parâmetro deve ser `string`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="7ed56-209">Se o tipo de dados não for `string`, converta-o para `string`.</span><span class="sxs-lookup"><span data-stu-id="7ed56-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="7ed56-210">Anexo</span><span class="sxs-lookup"><span data-stu-id="7ed56-210">Appendix</span></span>

<span data-ttu-id="7ed56-211">Este apêndice mostra o código de exemplo completo para a integração de dimensões financeiras (**Centro de custo** e **Projeto**) no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="7ed56-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="7ed56-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="7ed56-212">TaxIntegrationLineObject_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="7ed56-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="7ed56-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="7ed56-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="7ed56-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
