---
title: Lançamento de ordem de compra
description: Este artigo descreve a guia Ordem de compra da página Perfis de lançamento de estoque.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 0793c58b07d2c0a133e1a5bc0607483f22206b95
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849921"
---
# <a name="purchase-order-posting"></a>Lançamento de ordem de compra

A guia **Ordem de compra** na página **Perfis de lançamento de estoque** é usada para controlar como as ordens de compra serão lançadas na contabilidade. Duas atividades principais são lançadas na contabilidade para um pedido de compra: 

- Recebimento de produtos
- Fatura

Para que uma transação física (recebimento de produto) seja lançada na contabilidade em um pedido de compra, as seguintes caixas de seleção devem ser marcadas:

- A caixa de seleção **Lançar o recebimento de produtos no razão** na página **Parâmetros de gerenciamento de estoque e depósito**.
- As caixas de seleção **Lançar estoque físico** e **Acumular passivo no recebimento de produtos** na página **Grupos de modelos de item**.

As contas principais devem ser especificas na página **Perfil de lançamento de estoque** para os seguintes tipos de lançamento:

- Custo de materiais comprados recebidos
- Despesa de compra, não faturada
- Compra, acúmulo

Para uma transação financeira (fatura) ser lançada na contabilidade para um pedido de compra, as seguintes condições deverão ser atendidas:

- A caixa de seleção **Lançar estoque financeiro** deve ser marcada na página **Grupos de modelos de item** para o item selecionado na linha do pedido de compra.
- As contas principais devem ser especificas na página **Perfil de lançamento de estoque** para os seguintes tipos de lançamento:
  - Custo de materiais comprados faturados
  - Despesa de compra para produto
  - Despesa de compra para despesa
  - Desconto (opcional)

## <a name="fixed-receipt-price-posting"></a>Lançamento de preço de recebimento fixo

Você pode usar o preço de recebimento fixo como o custo padrão de um produto como alternativa para selecionar a opção **Custo padrão** no campo **Modelo de estoque** na página **Grupos de modelos de item** para um item. A principal diferença é que, quando **Preço de recebimento fixo** é usado, o preço de custo atual será usado para o item quando o recebimento de estoque for lançado. Não há processo de reavaliação de custos para **Preço de recebimento fixo**; quando uma atualização financeira é lançada, o preço de custo atual é usado no momento do lançamento. Se houver uma diferença entre o preço de custo usado no recebimento e na fatura, a variação será lançada nas contas de lucros e perdas do preço de recebimento fixo.

Para usar um preço de recebimento fixo para um produto, você deve configurar o seguinte:

- Na página **Grupos de modelos de item**, marque as caixas de seleção **Lançar estoque físico** e **Preço de recebimento fixo**. 
- Na página **Parâmetros de gerenciamento de estoque e depósito**, marque a caixa de seleção **Lançar guia de remessa no razão**.
- Na página **Perfil de lançamento de estoque**, especifique as contas principais para os seguintes tipos de lançamento:
  - Lucro sobre preço de recebimento fixo
  - Perda sobre preço de recebimento fixo
  - Compensação do preço de recebimento fixo

Para obter mais informações, acesse [Preço de recebimento fixo](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Encargos de compra e lançamento de variação de estoque

Se você planeja considerar os encargos de compra e variações de estoque, faça o seguinte:

- Na página **Parâmetros de contas a pagar** na guia **Invoice**, marque a caixa de seleção **Lançar na conta de encargos no razão**.
- Na página **Grupos de modelos de item** para o item selecionado na linha do pedido de compra, marque as caixas de seleção **Lançar estoque físico**, **Lançar estoque financeiro** e **Acumular passivo no recebimento de produtos**.
- Na página **Parâmetros de aquisição e fornecimento**, marque a caixa de seleção **Gerar encargos no recibo do produto**.
- Na página **Parâmetros de gerenciamento de estoque e depósito**, marque a caixa de seleção **Lançar guia de remessa no razão**.

Na página **Perfil de lançamento de estoque**, você deve especificar as contas principais para os seguintes tipos de lançamento:

- Despesa de compra, não faturada
- Despesa de compra para produto
- Variação de estoque

> [!NOTE]
> O tipo de lançamento **Encargo** não é usado quando o parâmetro **Lançar na conta de encargos no razão** é selecionado.

Para obter mais informações, acesse [Princípio contábil de lançar na conta de encargos](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Exemplo de configuração de perfil de lançamento

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições do exemplo:

- A coluna **Conta de compensação** indica que o tipo de lançamento é uma conta de compensação. O valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada. 
- A coluna **P/F** indica **P** para lançamento físico e **F** para lançamento financeiro. 
- A coluna **Seguir** indica se a conta principal para um tipo de lançamento específico é geralmente igual a outro tipo de lançamento. O valor na coluna indica o tipo de lançamento que normalmente é usado.

> [!NOTE]
> As contas principais e os nomes de conta principal são apenas sugestões. Nós recomendamos<!--note from editor: Via Writing Style Guide.--> que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.


| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Custo de materiais comprados recebidos | 140100</br>140101 | Estoque de materiais</br>Materiais enviados não faturados | Ativo | Débito | Sim | S | Custo de materiais comprados faturados | Usado quando um recebimento de produto do pedido de compra é lançado. A contrapartida para a conta é a despesa de compra, não faturada. O valor nessa conta é revertido quando uma fatura de pedido de compra é lançada. |
| Despesa de compra, não faturada | 600180 | Recebimentos de material | Despesa | Débito | Sim | S | |Usado quando um recebimento de produto do pedido de compra é lançado. Dois comprovantes são criados para o recebimento para rastrear variações de preço de compra quando o custo padrão é usado. A contrapartida para a conta no primeiro comprovante é o acúmulo de compra. A compensação no segundo comprovante é a soma do custo dos materiais adquiridos recebidos e das contas de variação do preço de compra. Os valores lançados nesta conta são revertidos quando uma fatura de pedido de compra é lançada. |
| Custo de materiais comprados faturados | 140100 | Estoque de materiais | Ativo | Débito | Número | S  |Custo de materiais comprados recebidos | Usado quando uma fatura de pedido de compra é lançada. A contrapartida para essa conta é a despesa de compra do produto. Essa conta representa o estoque em seu balanço. A conta usada costuma ser a mesma usada para custo de unidades entregues e custo de unidades faturadas para o pedido de venda. |
| Despesa de compra para produto | 600180 | Recebimento de material | Despesa | Crédito | Número | S  | |Usado quando uma fatura de pedido de compra é lançada. A contrapartida para esta conta é o custo dos materiais adquiridos. Essa conta representa o estoque em seu balanço. |
| Lucro do preço de recebimento fixo (compra, lucro do preço de recebimento fixo*) | 510310 | Variação de preços de compra | Despesa | Crédito | Número | S | Perda sobre preço de recebimento fixo | Usado quando uma fatura de pedido de compra é lançada e há uma diferença entre o preço faturado e o custo padrão do item. Esta conta é utilizada quando a diferença é maior. A contrapartida para esta conta é a contrapartida do preço de recebimento fixo. |
| Perda do preço de recebimento fixo (compra, perda do preço de recebimento fixo*) | 510310 | Variação de preços de compra | Despesa | Débito | Número | S | Lucro sobre preço de recebimento fixo | Usado quando uma fatura de pedido de compra é lançada e há uma diferença entre o preço faturado e o custo padrão do item. Esta conta é utilizada quando a diferença é menor. A contrapartida para esta conta é a contrapartida do preço de recebimento fixo. |
| Contrapartida de preço de recebimento fixo (compra, contrapartida de preço de recebimento fixo*) | 140900 | Variação de estoque | Ativo | Ambos | Número | S  | |Usado quando uma fatura de pedido de compra é lançada e há uma diferença entre o preço faturado e o custo padrão do item. Esta conta é a contrapartida para as contas de lucros e perdas de preço de recebimento fixo. |
| Encargo | ND | ND | ND | ND | ND | ND | ND | Esta conta não é mais usada. Use a variação de estoque. |
| Variação de estoque | 600170 | Variação de estoque | Despesa | Crédito | Número | Ambos | | Esta conta é usada quando: <ul><li>Há uma diferença no preço unitário entre o recebimento do produto e a fatura.</li><li>Os encargos são lançados no item.</li><li>Os custos indiretos foram<!--note from editor: Edit okay?--> adicionados aos itens comprados. </li><li>A contrapartida para esta conta é a despesa de compra, conta não faturada.</li></ul> |
| Compra, acúmulo | 200140 | Compras Acumuladas | Passivo | Crédito | Y | S | |Usado quando um recebimento de produto de pedido de compra é lançado e a opção de acumular valores de compra está habilitada. |
| Imposto acumulado no recebimento | 250500 | Imposto sobre vendas acumulado | Passivo | Crédito | Y | Ambos  | |Esta conta é usada quando você seleciona a opção **Lançar imposto físico** em **Parâmetros de gerenciamento de estoque e depósito** e tem um pedido de compra com impostos. O valor é lançado quando você atualiza o pedido de compra fisicamente (recebimento de produto) e estornado quando você lança o pedido de compra financeiramente (fatura). |
| Recebimento de ativo fixo (débito de ativo fixo*) | 180100 | Ativos fixos tangíveis | Ativo | Débito | N | Ambos | Ambos | Esta conta é usada quando você seleciona a opção na linha do pedido de compra para ativos fixos. A integração do pedido de compra foi configurada para adquirir o ativo fixo no recebimento ou fatura do produto. Para obter mais informações sobre a integração de pedido de compra de ativo fixo, acesse [Adquirir ativos por meio de compra](/fixed-assets/acquire-assets-procurement). |
| Despesa de compra para despesa | 618900 | Despesas diversas | Despesa | Débito | N | Ambos | |Usado ao lançar um recibo ou fatura de produto para um pedido de compra em que os itens não estão estocados ou uma categoria de compras é usada. |
| Pagamento antecipado | 132190 | Despesa pré-paga | Ativo | Débito | N | Ambos | | Usado ao processar uma fatura de pré-pagamento em um pedido de compra. |


\*Os valores mostrados entre parênteses representam o valor usado no campo **Tipo de lançamento** na página **Transações de comprovante**. Você pode exibir o **Tipo de lançamento** na página **Transações de comprovante** na guia **Geral**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Lançamento de ativo fixo com pedidos de compra

Se você usa o módulo **Ativos fixos** e planeja comprar ativos fixos por meio de pedidos de compra, deve configurar o tipo de lançamento **Recebimento de ativo fixo** na guia **Ordem de compra** da página **Perfil de lançamento de estoque**. Para obter mais informações, acesse [Integração de ativos fixos](/fixed-assets/fixed-asset-integration.md) e [Criar e adquirir ativos de contas a pagar](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Lançamento de fatura de pedido de compra de pagamento antecipado

Se você planeja usar o recurso **Fatura de pagamento antecipado** para pedidos de compra, o tipo de lançamento **Pagamento antecipado** deve ser selecionado na guia **Ordem de compra** na página **Perfil de lançamento de estoque**. Para obter mais informações, vá para [Faturas de pagamento antecipado versus pagamentos antecipados](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Requisição de compra e lançamento de confirmação de pedido de compra

As requisições de compra e as confirmações de pedidos de compra também podem ser configuradas para lançar pré-ônus e ônus na contabilidade. Esses lançamentos são controlados por uma definição de lançamento. Para obter mais informações, acesse [Sobre ônus de pedido de compra](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Lançamento de categoria de compras

Como uma alternativa à configuração do lançamento de estoque para todos os itens, um grupo de itens ou um único item, você pode configurar categorias e controlar o lançamento contábil por categorias de compras. Para obter mais informações sobre como configurar categorias e atribuí-las a produtos, acesse [Exemplo de configuração de perfil de lançamento](#sample-posting-profile-configuration) anteriormente neste artigo.

Ao usar categorias com pedidos de compra ou faturas de fornecedores, a hierarquia de categorias precisa ser atribuída ao tipo **Hierarquia de categorias de compras** na página **Atribuições de função de hierarquia de categoria**.

### <a name="vendor-invoices-with-procurement-categories"></a>Faturas de fornecedor com categorias de compras

Se sua organização usa pedidos de compras para algumas compras e não para outras, você pode processar faturas não relacionadas a pedidos de compras de várias maneiras. Isso inclui o uso de diários em **Contas a pagar** ou pela página **Faturas de fornecedor pendentes** que é usada para gerar faturas para pedidos de compra. Ao criar faturas para faturas não relacionadas a pedidos de compra, você precisará criar categorias de compras para cada tipo de despesa. Você precisará mapear a categoria para a conta de despesas correta na página **Perfis de lançamento de estoque**.

O número exato de categorias varia de acordo com o número de contas de despesas que você usa para lançar suas faturas. Você precisará de pelo menos uma categoria de compras para cada conta principal para a qual você debita faturas de pedidos não relacionados a compras. Muitas categorias podem ser usadas para uma única conta principal. Isso pode ser útil para usabilidade, capacidade de pesquisa e relatórios dos tipos de despesas que você usa.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Benefícios de usar categorias de compras para faturas de fornecedores

Alguns benefícios do uso de categorias de compras para faturas de fornecedores incluem:

- Experiência de usuário consistente: quando você configura categorias de compras para todas as despesas não relacionadas a pedidos de compra, os usuários podem ser treinados em um processo de faturamento usando a página **Faturas de fornecedor pendentes**.
- Experiência de relatório aprimorada: ao configurar categorias de compras para todos os itens e todas as despesas não relacionadas a pedidos de compra, o relatório de gastos de compras analisará os gastos por fornecedor, categoria e muito mais.
- Fluxo de trabalho consistente: ao usar **Faturas de fornecedor pendentes** para processar todas as faturas, você pode criar um fluxo de trabalho consistente e um processo de aprovação usando um único fluxo de trabalho.

## <a name="consignment-inventory-posting"></a>Lançamento de estoque de consignação

O estoque em consignação usa o mesmo lançamento contábil que outros itens comprados. A principal diferença é que, quando o estoque é recebido, nenhuma transação contábil é registrada. Para transferir a propriedade para a organização quando um diário de **Alteração de propriedade de estoque** é lançado, um comprovante é gerado para registrar o custo do item. Para obter mais informações, acesse [Configurar consignação](/supply-chain/inventory/consignment.md).
