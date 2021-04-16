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
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Adicionar campos de dados na integração de imposto usando uma extensão

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este tópico explica como usar as extensões X++ para adicionar campos de dados na integração de imposto. Esses campos podem ser estendidos para o modelo de dados de imposto do serviço de imposto e usados para determinar códigos de imposto. Para obter mais informações, consulte [Adicionar campos de dados em configurações de imposto](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Modelo de dados

Os dados no modelo de dados contém objetos e são implementados por classes.

Veja esta lista dos objetos principais:

* AxClass/TaxIntegration **Documento** Objeto
* AxClass/TaxIntegration **Linha** Objeto
* AxClass/TaxIntegration **TaxLine** Objeto

A ilustração abaixo mostra como esses objetos estão relacionados.

[![Relação de objeto do modelo de dados](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Um objeto de **Documento** pode conter muitos objetos de **Linha**. Cada objeto contém metadados para o serviço de imposto.

- O `TaxIntegrationDocumentObject` tem metadados de `originAddress`, que contêm informações sobre o endereço de origem e os metadados `includingTax`, que indicam se o valor da linha inclui o imposto.
- O `TaxIntegrationLineObject` tem metadados `itemId`, `quantity`e `categoryId`.

> [!NOTE]
> O `TaxIntegrationLineObject` também implementa objetos de **Cobrança**.

## <a name="integration-flow"></a>Fluxo de integração

Os dados no fluxo são manipulados pelas atividades.

### <a name="key-activities"></a>Atividades principais

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

As atividades são realizadas na seguinte ordem:

1. Recuperação da configuração
2. Recuperação de dados
3. Serviço de cálculo
4. Câmbio da moeda
5. Persistência de dados

Por exemplo, estender a **Recuperação de dados** antes do **Serviço de cálculo**.

#### <a name="data-retrieval-activities"></a>Atividades de recuperação de dados

Essas atividades de **Recuperação de dados** recuperam dados do banco de dados. Os adaptadores para transações diferentes estão disponíveis para recuperar dados de tabelas de transações diferentes:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

Nessas atividades de **Recuperação de dados**, os dados são copiados do banco de dados para `TaxIntegrationDocumentObject` e `TaxIntegrationLineObject`. Como todas essas atividades incluem a mesma classe de modelo abstrata, elas têm métodos comuns.

#### <a name="calculation-service-activities"></a>Atividades de Serviço de cálculo

A atividade de **Serviço de cálculo** é o vínculo entre o serviço de imposto e a integração de imposto. Essa atividade é responsável pelas seguintes funções:

1. Criar a solicitação.
2. Enviar a solicitação para o serviço de imposto.
3. Obter a resposta do serviço de imposto.
4. Analisar a resposta.

Um campo de dados adicionado à solicitação será enviado junto com outros metadados. 

## <a name="extension-implementation"></a>Implementação de extensão

Esta seção fornece etapas detalhadas que explicam como implementar a extensão. Ele usa o **Centro de custo** e as dimensões financeiras do **Projeto** como exemplos.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Etapa 1. Adicione a variável de dados na classe de objeto

A classe de objeto contém a variável de dados e os métodos getter/setter para os dados. Adicione o campo de dados a `TaxIntegrationDocumentObject` ou `TaxIntegrationLineObject`, dependendo do nível do campo. O exemplo abaixo usa o nível da linha e o nome do arquivo é `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Se o campo de dados que você está adicionando estiver no nível do documento, altere o nome do arquivo para `TaxIntegrationDocumentObject_Extension.xpp`.

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

O **Centro de custos** e o **Projeto** são adicionados como variáveis particulares. Crie métodos getter e setter para esses campos de dados para gerenciar os dados.

### <a name="step-2-retrieve-data-from-the-database"></a>Etapa 2. Recuperar dados do banco de dados

Especifique a transação e estenda as classes de adaptador apropriadas para recuperar os dados. Por exemplo, se você usar uma transação de **Ordem de compra**, deverá estender `TaxIntegrationPurchTableDataRetrieval` e `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` é herdado do `TaxIntegrationPurchTableDataRetrieval`. Ele não deve ser alterado, a menos que a lógica das tabelas `purchTable` e `purchParmTable` seja diferente.

Se o campo de dados precisar ser adicionado para todas as transações, estenda todas as classes `DataRetrieval`.

Como todas as atividades de **Recuperação de dados** incluem a mesma classe de modelo, as estruturas de classe, variáveis e métodos são semelhantes.

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

O exemplo a seguir mostra a estrutura básica quando a tabela `PurchTable` é usada.

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

Quando o método `CopyToDocument` é chamado, o buffer `this.purchTable` já existe. A finalidade desse método é copiar todos os dados necessários da tabela `this.purchTable` para o objeto `document` usando o método setter criado na classe `DocumentObject`.

Da mesma forma, um buffer `this.purchLine` já existe no método `CopyToLine`. A finalidade desse método é copiar todos os dados necessários da tabela `this.purchLine` para o objeto `_line` usando o método setter criado na classe `LineObject`.

A abordagem mais direta é estender os métodos `CopyToDocument` e `CopyToLine`. No entanto, recomendamos que você experimente os métodos `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable` primeiro. Se eles não funcionarem como esperado, implemente seu próprio método e o ative-o em `CopyToDocument` e `CopyToLine`. Há três situações comuns em que você talvez use essa abordagem:

- O campo obrigatório está em `PurchTable` ou `PurchLine`. Nessa situação, você pode estender `copyToDocumentFromHeaderTable` e `copyToLineFromLineTable`. Este é o código de exemplo.

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

- Os dados necessários não estão na tabela padrão da transação. No entanto, há algumas relações de associação com a tabela padrão e o campo é necessário na maioria das linhas. Nessa situação, substitua `getDocumentQueryObject` ou `getLineObject` para consultar a tabela segundo as relações de associação. No exemplo abaixo, o campo **Entregar agora** está integrado com a ordem de venda no nível de linha.

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

    Neste exemplo, um buffer `mcrSalesLineDropShipment` é declarado, e a consulta é definida em `getLineQueryObject`. A consulta usa a relação `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. Enquanto estiver estendendo nessa situação, você poderá substituir `getLineQueryObject` pelo seu próprio objeto de consulta criado. No entanto, observe os seguintes pontos:

    * Como o valor de retorno do método `getLineQueryObject` é `SysDaQueryObject`, você deve criar esse objeto usando a abordagem SysDa.
    * Não é possível remover a tabela existente.

- Os dados necessários estarão relacionados à tabela de transações por uma relação de associação complicada, exceto se a relação não for um para um (1:1), mas de um para muitos (1:N). Nessa situação, as coisas se tornam um pouco complicadas. Essa situação se aplica ao exemplo de dimensões financeiras. 

    Nessa situação, você pode implementar seu próprio método para recuperar os dados. Este é o código de exemplo no arquivo `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.

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

### <a name="step-3-add-data-to-the-request"></a>Etapa 3. Adicionar dados à solicitação

Estenda o método `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` ou `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` para adicionar dados à solicitação. Este é o código de exemplo no arquivo `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.

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

Nesse código, `_destination` é o objeto wrapper usado para gerar a solicitação de lançamento, e `_source` é o objeto `TaxIntegrationLineObject`. 

> [!NOTE]
> * Defina a chave usada no formulário de solicitação como `private const str`.
> * Defina o campo no método `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` usando o método `SetField`. O tipo de dados do segundo parâmetro deve ser `string`. Se o tipo de dados não for `string`, converta-o para `string`.

## <a name="appendix"></a>Anexo

Este apêndice mostra o código de exemplo completo para a integração de dimensões financeiras (**Centro de custo** e **Projeto**) no nível da linha.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

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
