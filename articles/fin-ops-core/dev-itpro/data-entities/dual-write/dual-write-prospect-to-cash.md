---
title: Cliente potencial com pagamento à vista em gravação dupla
description: Este tópico fornece informações sobre o cliente potencial com pagamento à vista em gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 57aabeef0ee94b4b13bbe6e3925bcafe1e809ab2
ms.sourcegitcommit: 984604fd651d74aa49a2d7513f096faaf49f9f27
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2020
ms.locfileid: "3270279"
---
# <a name="prospect-to-cash-in-dual-write"></a>Cliente potencial com pagamento à vista em gravação dupla

[!include [banner](../../includes/banner.md)]



Um objetivo importante da maioria das empresas é converter clientes potenciais em clientes e, depois, manter um relacionamento contínuo de negócios com esses clientes. Nos aplicativos do Microsoft Dynamics 365, o processo de cliente potencial com pagamento à vista ocorre por meio de cotações ou fluxos de trabalho de processamento de pedidos e as finanças são reconciliadas e reconhecidas. A integração do cliente potencial com pagamento à vista em gravação dupla cria um fluxo de trabalho que recebe uma cotação e uma ordem que se origina no Dynamics 365 Sales ou Dynamics 365 Supply Chain Management e torna a cotação e a ordem disponíveis nos dois aplicativos.

Nas interfaces de aplicativo, você pode acessar os status de processamento e as informações de nota fiscal em tempo real. Portanto, você pode gerenciar mais facilmente as funções como estoque de produtos, manuseio de estoque e preenchimento no Supply Chain Management, sem ter que criar novamente cotações e ordens.

![Fluxo de dados de gravação dupla em cliente potencial com pagamento à vista](../dual-write/media/dual-write-prospect-to-cash[1].png)

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

Para sincronizar votações de venda, você deve atualizar as seguintes configurações.

### <a name="setup-in-sales"></a>Configuração no Sales

Em Vendas, vá para **Configurações \> Administração \> Configurações do sistema \> Vendas** e certifique-se de que as seguintes configurações sejam usadas:

- A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
- O campo **Método de cálculo de desconto** está definido como **Item de linha**.

### <a name="sites-and-warehouses"></a>Sites e depósitos

Em Supply Chain Management, os campos **Site** e **depósito** são necessários para linhas de cotação e linhas de pedido. Se você definir o local e o depósito nas configurações de ordem padrão, esses campos serão automaticamente definidos quando você adicionar um produto a uma linha de cotação ou a uma linha de ordem. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sequências numéricas para cotações e ordens

As sequências numéricas para Supply Chain Management e Vendas não são conectadas quando cotações e ordens são criadas e sincronizadas em Vendas e Supply Chain Management. Se uma ordem de venda criada em Vendas for sincronizada com o Supply Chain Management, ela terá o mesmo número da ordem de venda em Supply Chain Management. Para ajudar a garantir que o número da ordem de venda não seja duplicado, você deve usar sistemas de sequência numérica diferentes nos dois aplicativos.

Por exemplo, a sequência numérica em Supply Chain Management é **1, 2, 3, 4, 5, ...** e a sequência numérica em Vendas é **100, 99, 98, ...** Se você criar 100 ordens de venda em Vendas, um número de ordem será gerado eventualmente já existente no em Supply Chain Management. Em outras palavras, as duas sequências numéricas acabarão se sobrepondo, pois as ordens de venda são criadas em Supply Chain Management e Vendas. Em vez disso, você pode usar uma sequência numérica como **F1, F2, F3, ...** no Supply Chain Management e em uma sequência numérica como **C1, C2, C3,...** em Vendas. Essas sequências numéricas nunca produzirão números de ordem de venda duplicados.

## <a name="sales-quotations"></a>Cotações de venda

As cotações de venda podem ser criadas em Vendas ou em Supply Chain Management. Se você criar uma cotação em Vendas, ela será sincronizada com Supply Chain Management em tempo real. Da mesma forma, se você criar uma cotação em Supply Chain Management, ele é sincronizada em Vendas em tempo real. Observe os seguintes pontos:

+ Você pode adicionar um desconto ao produto na cotação. Nesse caso, o desconto será sincronizado com Supply Chain Management. Os campos **Desconto**, **Encargos** e **Imposto** no cabeçalho são controlados por uma configuração no Supply Chain Management. Essa configuração não dá suporte ao mapeamento de integração. Em vez disso, os campos **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidos e tratados pelo Supply Chain Management.
+ Os campos **% de Desconto**, **Desconto** e **Valor do Frete** no cabeçalho de cotação de vendas são campos apenas leitura.
+ Os campos **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

Se você também estiver usando a solução do Field Service, certifique-se de reabilitar o parâmetro **Criação Rápida de Linha de Cotação**. Habilitar novamente o parâmetro permite que você continue criando linhas de cotação usando a função de criação rápida.
1. Navegue até o aplicativo Dynamics 365 Sales.
2. Selecione o ícone configurações na barra de navegação superior.
3. Selecione **Configurações Avançadas**.
4. Escolha a opção **Personalizar o Sistema**.
5. Selecione o item de menu **Linha de Cotação**.
6. Acesse a seção **Serviços de Dados** e marque a caixa de seleção **Permitir criação rápida**.

## <a name="sales-orders"></a>Ordens de Venda

As ordens de venda podem ser criadas em Vendas ou em Supply Chain Management. Se você criar uma ordem de venda em Vendas, ela será sincronizada com Supply Chain Management em tempo real. Da mesma forma, se você criar uma ordem de venda em Supply Chain Management, ela é sincronizada em Vendas em tempo real. Observe os seguintes pontos:

+ Você pode ativar e sincronizar ordens somente de vendas se todos os produtos da ordem vierem de aplicativos Finance and Operations. Portanto, não pode haver nenhum produto inserido.
+ Cálculo de desconto e arredondamento:

    - O modelo de cálculo de desconto no Sales difere do modelo de cálculo de desconto no Supply Chain Management. No Supply Chain Management, o valor final de descontos em uma linha de venda pode ser o resultado de uma combinação de valores de desconto e porcentagens de desconto. Se este valor final de descontos for dividido pela quantidade na linha, poderá haver um arredondamento. No entanto, esse arredondamento não é considerado se um valor de desconto por unidade arredondado é sincronizado para o Sales. Para ajudar a garantir que o valor total do desconto da linha de venda no Supply Chain Management seja sincronizado corretamente para o Sales, o valor total deve ser sincronizado sem ser dividido pela quantidade da linha. Portanto, você deve definir o método de cálculo de desconto como **Item de linha** em Sales.
    - Quando uma linha da ordem de venda for sincronizada do Sales para o Supply Chain Management, o valor de desconto de linha total será usado. Como o Supply Chain Management não tem campos que possam armazenar o valor total de desconto para uma linha, o valor é dividido pela quantidade e armazenado no campo **Desconto de linha**. Qualquer arredondamento que ocorrer durante esta divisão será armazenado no campo **Encargos de venda** na linha de venda.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Exemplo: Sincronização do Sales para o Supply Chain Management

Você tem a seguinte ordem de venda:

+ **Vendas:** Quantidade = 3, desconto por linha = $ 10,00
+ **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01

Se você sincronizar de Supply Chain Management às Vendas, obterá o seguinte resultado:

+ **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01
+ **Vendas:** Quantidade = 3, desconto por linha = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="dual-write-solution-for-sales"></a>Solução de gravação dupla para Vendas

Novos campos foram adicionados à entidade **Ordem** e são exibidos na página. A maioria desses campos aparece na guia **Integração** em Vendas. Há alguns campos especiais:

+ O campo **Status de processamento** mostra o status de processamento da ordem no Supply Chain Management. Este campo está bloqueado e mostra somente o status da ordem do Supply Chain Management. Os valores a seguir estão disponíveis:

    + **Ativo** – O status depois que a ordem é ativada no Sales usando o botão **Ativar**.
    + **Confirmada**
    + **Entregues**
    + **Faturadas**
    + **Parcialmente entregue**
    + **Parcialmente faturada**
    + **Separado**
    + **Cancelada**

    A tabela a seguir mostra como o status de processamento é mapeado para o valor do **Código de status do CRM**.

    | Status do processamento           | Código de status do CRM    |
    |-----------------------------|--------------------|
    | Ativos                      | Novo/Pendente/Em espera |
    | Confirmado/Separado            | Em andamento        |
    | Parcialmente entregue         | Parcial            |
    | Entregues                   | Completo           |
    | Faturado/Parcialmente faturado | Faturadas           |
    | Cancelada                    | Sem dinheiro           |

+ Os botões **Criar fatura** e **Cancelar pedido** na página **Ordem de venda** estão ocultos em Vendas.
+ O valor de **Status da ordem de venda** permanecerá **Ativo** para ajudar a garantir que as alterações no Supply Chain Management possam fluir para a ordem de venda em Vendas. Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo**.

## <a name="invoices"></a>Faturas

As faturas de vendas são criadas no Supply Chain Management e sincronizadas no Sales. Observe os seguintes pontos:

+ Um campo **Número de fatura** foi adicionado à entidade **Fatura** e aparece na página.
+ O botão **Criar fatura** na página **Ordem de venda** é ocultado, pois as faturas serão criadas no Supply Chain Management e sincronizadas com o Sales. A página **Fatura** não pode ser editada, pois as faturas serão sincronizadas do Supply Chain Management.
+ O valor do **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Supply Chain Management é sincronizada com o Sales. Além disso, o proprietário da ordem de venda da qual a fatura foi criada é atribuído como o proprietário da fatura. Portanto, o proprietário da ordem de venda pode exibir a fatura.
+ Os campos **Condições de frete**, **Condições de entrega** e **Método de remessa** não estão incluídos no mapeamento padrão. Para mapear esses campos, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a entidade está sincronizada.

## <a name="templates"></a>Modelos

Cliente potencial com pagamento à vista inclui um conjunto de mapas de entidades centrais que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos Finance and Operations | Aplicativos controlados por modelos no Dynamics 365 | descrição |
|-----------------------------|-----------------------------------|-------------|
| Cabeçalhos de fatura de venda V2    | faturas                          |             |
| Linhas da fatura de venda V2      | invoicedetails                    |             |
| Cabeçalhos de ordens de venda CDS     | salesorders                       |             |
| Linhas de ordem de venda do CDS       | salesorderdetails                 |             |
| Códigos de origem de ordem de venda    | msdyn\_salesorderorigins          |             |
| Cabeçalho de cotação de venda CDS  | cotações                            |             |
| Linhas de cotação de venda do CDS   | quotedetails                      |             |

Estes são os mapas de entidade principal relacionados para cliente potencial com pagamento à vista:

+ [Clientes V3 para contas](customer-mapping.md#customers-v3-to-accounts)
+ [Contatos V2 do CDS para contatos](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [Clientes V3 para contatos](customer-mapping.md#customers-v3-to-contacts)
+ [Produtos liberados V2 para msdyn_sharedproductdetails](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [Todos os produtos para msdyn_globalproducts](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Lista de preços](product-mapping.md)

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]
