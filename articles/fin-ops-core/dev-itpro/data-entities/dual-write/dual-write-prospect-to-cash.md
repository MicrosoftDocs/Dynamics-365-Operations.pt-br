---
title: Cliente potencial com pagamento à vista em gravação dupla
description: Este tópico fornece informações sobre o cliente potencial com pagamento à vista em gravação dupla.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 7c53bcd1084d89b59d0f6b2674a85d7c3481a9bf
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781782"
---
# <a name="prospect-to-cash-in-dual-write"></a>Cliente potencial com pagamento à vista em gravação dupla

[!include [banner](../../includes/banner.md)]

Um objetivo importante da maioria das empresas é converter clientes potenciais em clientes e, depois, manter um relacionamento contínuo de negócios com esses clientes. Nos aplicativos do Microsoft Dynamics 365, o processo de cliente potencial com pagamento à vista ocorre por meio de cotações ou fluxos de trabalho de processamento de pedidos e as finanças são reconciliadas e reconhecidas. A integração do cliente potencial com pagamento à vista em gravação dupla cria um fluxo de trabalho que recebe uma cotação e uma ordem que se origina no Dynamics 365 Sales ou Dynamics 365 Supply Chain Management e torna a cotação e a ordem disponíveis nos dois aplicativos.

Nas interfaces de aplicativo, você pode acessar os status de processamento e as informações de nota fiscal em tempo real. Portanto, você pode gerenciar mais facilmente as funções como estoque de produtos, manuseio de estoque e preenchimento no Supply Chain Management, sem ter que criar novamente cotações e ordens.

![Fluxo de dados de gravação dupla em cliente potencial com pagamento à vista.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Para obter informações sobre a integração entre cliente e contato, consulte [Cliente mestre integrado](customer-mapping.md). Para obter mais informações sobre a integração de produtos, consulte [Experiência unificada de produtos](product-mapping.md).

> [!NOTE]
> No Dynamics 365 Sales, um cliente potencial e um cliente real referem-se a um registro na tabela **Contas** em que a coluna **RelationshipType** é **Cliente potencial** ou **Cliente**. Se a lógica comercial incluir um processo de qualificação de **Conta**, no qual o registro **Conta** é criado e qualificado como um cliente potencial primeiro, o registro só é sincronizado com o aplicativo do Finance and Operations quando ele for um cliente (`RelationshipType=Customer`). Se quiser que a linha **Conta** seja sincronizada como um cliente potencial, você precisará de um mapa personalizado para integrar os dados do cliente potencial.

## <a name="prerequisites-and-mapping-setup"></a>Pré-requisitos e configuração de mapeamento

Para sincronizar votações de venda, você deve atualizar as seguintes configurações.

### <a name="setup-in-sales"></a>Configuração no Sales

Em Vendas, Acesse **Configurações \> Administração \> Configurações do sistema \> Vendas** e certifique-se de que as seguintes configurações sejam usadas:

- A opção **Usar sistema de cálculo de precificação do sistema** está definida como **Sim**.
- A coluna **Método de cálculo de desconto** está definida como **Item de linha**.

### <a name="sites-and-warehouses"></a>Sites e depósitos

Em Supply Chain Management, as colunas **Site** e **Depósito** são necessárias para linhas de cotação e linhas de pedido. Se você definir o local e o depósito nas configurações de ordem padrão, esses campos serão automaticamente definidos quando você adicionar um produto a uma linha de cotação ou a uma linha de ordem. 

### <a name="number-sequences-for-quotations-and-orders"></a>Sequências numéricas para cotações e ordens

As sequências numéricas para Supply Chain Management e Vendas não são conectadas quando cotações e ordens são criadas e sincronizadas em Vendas e Supply Chain Management. Se uma ordem de venda criada em Vendas for sincronizada com o Supply Chain Management, ela terá o mesmo número da ordem de venda em Supply Chain Management. Para ajudar a garantir que o número da ordem de venda não seja duplicado, você deve usar sistemas de sequência numérica diferentes nos dois aplicativos.

Por exemplo, a sequência numérica em Supply Chain Management é **1, 2, 3, 4, 5, ...** e a sequência numérica em Vendas é **100, 99, 98, ...** Se você criar 100 ordens de venda em Vendas, um número de ordem será gerado eventualmente já existente no em Supply Chain Management. Em outras palavras, as duas sequências numéricas acabarão se sobrepondo, pois as ordens de venda são criadas em Supply Chain Management e Vendas. Em vez disso, você pode usar uma sequência numérica como **F1, F2, F3, ...** no Supply Chain Management e em uma sequência numérica como **C1, C2, C3,...** em Vendas. Essas sequências numéricas nunca produzirão números de ordem de venda duplicados.

## <a name="sales-quotations"></a>Cotações de venda

As cotações de venda podem ser criadas em Vendas ou em Supply Chain Management. Se você criar uma cotação em Vendas, ela será sincronizada com Supply Chain Management em tempo real. Da mesma forma, se você criar uma cotação em Supply Chain Management, ele é sincronizada em Vendas em tempo real. Observe os seguintes pontos:

+ Você pode adicionar um desconto ao produto na cotação. Nesse caso, o desconto será sincronizado com Supply Chain Management. As colunas **Desconto**, **Encargos** e **Imposto** no cabeçalho são controladas por uma configuração no Supply Chain Management. Essa configuração não dá suporte ao mapeamento de integração. Em vez disso, as colunas **Preço**, **Desconto**, **Encargo** e **Imposto** são mantidas e tratadas pelo Supply Chain Management.
+ As colunas **% de Desconto**, **Desconto** e **Valor do Frete** no cabeçalho de cotação de vendas são colunas apenas leitura.
+ As colunas **Condições de frete**, **Condições de entrega**, **Método de entrega** e **Modo de entrega** não estão incluídas no mapeamento padrão. Para mapear essas colunas, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a tabela está sincronizada.

Se você também estiver usando a solução do Field Service, certifique-se de reabilitar o parâmetro **Criação Rápida de Linha de Cotação**. Habilitar novamente o parâmetro permite que você continue criando linhas de cotação usando a função de criação rápida.

1. Navegue até o aplicativo Dynamics 365 Sales.
2. Selecione o ícone configurações na barra de navegação superior.
3. Selecione **Configurações Avançadas**.
4. Escolha a opção **Personalizar o Sistema**.
5. Selecione o item de menu **Linha de Cotação**.
6. Acesse a seção **Serviços de Dados** e marque a caixa de seleção **Permitir criação rápida**.

## <a name="sales-orders"></a>Ordens de Venda

As ordens de venda podem ser criadas em Vendas ou em Supply Chain Management. Se você criar uma ordem de venda em Vendas, ela será sincronizada com Supply Chain Management em tempo real. Da mesma forma, se você criar uma ordem de venda em Supply Chain Management, ela é sincronizada em Vendas em tempo real. Observe os seguintes pontos:

+ Os produtos inseridos no Dynamics 365 Sales serão exibidos como categorias de produtos no Dynamics 365 Supply Chain Management.
+ Cálculo de desconto e arredondamento:

    - O modelo de cálculo de desconto no Sales difere do modelo de cálculo de desconto no Supply Chain Management. No Supply Chain Management, o valor final de descontos em uma linha de venda pode ser o resultado de uma combinação de valores de desconto e porcentagens de desconto. Se este valor final de descontos for dividido pela quantidade na linha, poderá haver um arredondamento. No entanto, esse arredondamento não é considerado se um valor de desconto por unidade arredondado é sincronizado para o Sales. Para ajudar a garantir que o valor total do desconto da linha de venda no Supply Chain Management seja sincronizado corretamente para o Sales, o valor total deve ser sincronizado sem ser dividido pela quantidade da linha. Portanto, você deve definir o método de cálculo de desconto como **Item de linha** em Sales.
    - Quando uma linha da ordem de venda for sincronizada do Sales para o Supply Chain Management, o valor de desconto de linha total será usado. Como o Supply Chain Management não tem colunas que possam armazenar o valor total de desconto para uma linha, o valor é dividido pela quantidade e armazenado na coluna **Desconto de linha**. Qualquer arredondamento que ocorrer durante esta divisão será armazenado na coluna **Encargos de venda** na linha de venda.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Exemplo: Sincronização do Sales para o Supply Chain Management

Você tem a seguinte ordem de venda:

+ **Vendas:** Quantidade = 3, desconto por linha = $ 10,00
+ **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01

Se você sincronizar de Supply Chain Management às Vendas, obterá o seguinte resultado:

+ **Supply Chain Management:** Quantidade = 3, valor do desconto de linha = US$ 3,33, encargo de venda = -US$ 0,01
+ **Vendas:** Quantidade = 3, desconto por linha = (3 × $ 3,33) + $ 0,01 = $ 10,00

## <a name="dual-write-solution-for-sales"></a>Solução de gravação dupla para Vendas

Novas colunas foram adicionadas à tabela **Ordem** e são exibidas na página. A maioria dessas colunas aparece na guia **Integração** em Vendas. Para saber mais sobre como as colunas de status são mapeados, consulte [Configurar o mapeamento para colunas de status da ordem de venda](sales-status-map.md).

+ Os botões **Criar fatura** e **Cancelar pedido** na página **Ordem de venda** estão ocultos em Vendas.
+ O valor de **Status da ordem de venda** permanecerá **Ativo** para ajudar a garantir que as alterações no Supply Chain Management possam fluir para a ordem de venda em Vendas. Para controlar este comportamento, defina o padrão do valor **Statecode \[Status\]** para **Ativo**.

## <a name="invoices"></a>Faturas

As faturas de vendas são criadas no Supply Chain Management e sincronizadas no Sales. Observe os seguintes pontos:

+ Uma coluna **Número de fatura** foi adicionado à tabela **Fatura** e aparece na página.
+ O botão **Criar fatura** na página **Ordem de venda** é ocultado, pois as faturas serão criadas no Supply Chain Management e sincronizadas com o Sales. A página **Fatura** não pode ser editada, pois as faturas serão sincronizadas do Supply Chain Management.
+ O valor do **Status da ordem de venda** é alterado automaticamente para **Faturado** quando a fatura relacionada do Supply Chain Management é sincronizada com o Sales. Além disso, o proprietário da ordem de venda da qual a fatura foi criada é atribuído como o proprietário da fatura. Portanto, o proprietário da ordem de venda pode exibir a fatura.
+ As colunas **Condições de frete**, **Condições de entrega** e **Método de entrega** não estão incluídas no mapeamento padrão. Para mapear essas colunas, é necessário configurar um mapeamento de valor que é específico para os dados nas organizações às quais a tabela está sincronizada.

## <a name="templates"></a>Modelos

O item Do cliente potencial ao pagamento à vista inclui um conjunto de mapas de entidades centrais que trabalham juntos durante a interação de dados, conforme mostrado na tabela a seguir.

| Aplicativos Finance and Operations | Aplicativos do Customer Engagement | descrição |
|-----------------------------|-----------------------------------|-------------|
[Todos os produtos](mapping-reference.md#138) | msdyn_globalproducts | |
[Clientes V3](mapping-reference.md#101) | contas | |
[Clientes V3](mapping-reference.md#116) | contatos | |
[Contatos V2](mapping-reference.md#221) | msdyn_contactforparties | |
[Cabeçalhos de ordens de venda CDS](mapping-reference.md#217) | salesorders | |
[Linhas de ordem de venda do CDS](mapping-reference.md#216) | salesorderdetails | |
[Cabeçalho de cotação de venda CDS](mapping-reference.md#215) | cotações | |
[Linhas de cotação de venda do CDS](mapping-reference.md#214) | quotedetails | |
[Produtos liberados V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Cabeçalhos de fatura de venda V2](mapping-reference.md#118) | faturas | A tabela de cabeçalhos da fatura de venda V2 no aplicativo do Finance and Operations contém faturas para ordens de venda e faturas de texto livre. Um filtro é aplicado no Dataverse para a gravação dupla, que filtrará qualquer documento de fatura de texto livre. |
[Linhas da fatura de venda V2](mapping-reference.md#117) | invoicedetails | |
[Códigos de origem de ordem de venda](mapping-reference.md#186) | msdyn_salesorderorigins | |

Para obter mais informações sobre listas de preços, consulte [Experiência unificada de produtos](product-mapping.md).

## <a name="limitations"></a>Limitações

- Não há suporte para ordens de devolução.
- Não há suporte para notas de crédito.
- As dimensões financeiras devem ser definidas para os dados mestre, por exemplo, cliente e fornecedor. Quando um cliente é adicionado a uma cotação ou a uma ordem de venda, as dimensões financeiras associadas ao fluxo do registro do cliente para a ordem automaticamente. No momento, a gravação dupla não inclui dados de dimensões financeiras para dados mestre.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
