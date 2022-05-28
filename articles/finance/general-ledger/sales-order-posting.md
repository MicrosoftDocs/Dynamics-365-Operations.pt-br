---
title: Lançando de ordem de venda
description: Este tópico fornece informações sobre a guia Ordem de venda da página do perfil de lançamentos de estoque.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5d84723b51d6977867fa162c4a47befa61bd9ef6
ms.sourcegitcommit: dc3053625dfe24aef64399dd1d002214e7f7619f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755918"
---
# <a name="sales-order-posting"></a>Lançando de ordem de venda

A guia **Ordem de venda** na página **Perfis de lançamento de estoque** é usada para controlar como as ordens de venda serão lançadas na contabilidade. Duas atividades principais são lançadas na contabilidade para uma ordem de venda: 

- Guia de remessa
- Fatura

Para uma transação física (guia de remessa) ser lançada na contabilidade para uma ordem de venda, as seguintes condições deverão ser atendidas:

- Na página **Parâmetros de gerenciamento de estoque e depósito**, a caixa de seleção **Lançar guia de remessa no razão** deve ser marcada.
- Na página **Grupo de modelos de item** para o item selecionado na linha da ordem de venda, a caixa de seleção **Lançar estoque físico no razão** deve ser marcada.
- Na página **Perfil de lançamento de estoque**, as contas principais devem ser especificadas para os seguintes tipos de lançamento:
  - Custo unitário, entregue
  - Custo dos produtos vendidos, entregues

Para uma transação financeira (fatura) ser lançada na contabilidade para uma ordem de venda, as seguintes condições deverão ser atendidas:

- Na página **Grupo de modelos de item** para o item selecionado na linha da ordem de venda, a caixa de seleção **Lançar estoque financeiro no razão** deve ser marcada.
- As contas principais devem ser especificas na página **Perfil de lançamento de estoque** para os seguintes tipos de lançamento:
  - Custo unitário, faturado
  - Custo dos produtos vendidos, faturado
  - Renda
  - Desconto\*

> [!NOTE]
> A Conta de desconto é opcional. Muitas regulamentações contábeis, como GAAP e IFRS, exigem que os descontos reduzam a receita de vendas e, portanto, essas contas não são usadas em vários cenários. Se as leis locais permitirem, use uma conta principal separada para lançar a parte do preço de venda descontada.

Para lançar o valor de receita adiada (previsto) para a contabilidade ao gerar uma guia de remessa para uma ordem de venda, as seguintes condições deverão ser atendidas:

- Na página **Grupo de modelos de item** para o item selecionado na linha da ordem de venda, a caixa de seleção **Lançar estoque físico no razão** deve ser marcada.
- Na página **Grupo de modelos de item**, a caixa de seleção **Lançar na Conta de Receita Diferida na Entrega de Vendas** deve ser marcada.
- Na página **Parâmetros de gerenciamento de estoque e depósito**, a caixa de seleção **Lançar guia de remessa no razão** deve ser marcada.
- Na página **Parâmetros de gerenciamento de estoque e depósito**, a caixa de seleção **Lançar imposto físico** deve ser marcada.
- Na página **Parâmetros de contas a receber**, a caixa de seleção **Lançar guia de remessa no razão** deve ser marcada.
- Na página **Perfil de lançamento de estoque**, as contas principais devem ser especificadas para os seguintes tipos de lançamento:
  - Receita adiada na entrega
  - Deslocamento de receita adiada na entrega
  - Imposto adiado na entrega

> [!NOTE]
> Geralmente recomendamos que você habilite as opções **Lançar estoque físico** e **Lançar guia de remessa no razão**. Habilitar essas opções pode ajudar a acelerar os procedimentos de fechamento no mês final, porque não será necessário calcular e lançar os diferimentos manualmente. Além disso, demonstrativos financeiros refletirão os valores diferidos automaticamente sem intervenção manual.

> [!IMPORTANT]
> A opção **Lançar em Conta de Receita Diferida na Entrega de Venda** não é usada com reconhecimento de receita. Para obter mais informações sobre Reconhecimento de receita, vá para [Visão geral do reconhecimento de receita](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Exemplo de configuração de perfil de lançamento 

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições do exemplo:
 
- A coluna **Conta de compensação** indica que o tipo de lançamento é uma conta de compensação. O valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada. 
- A coluna **P/F** indica **P** para lançamento físico e **F** para lançamento financeiro. 
- A coluna **Seguir** indica se a conta principal para um tipo de lançamento específico é geralmente igual a outro tipo de lançamento. O valor na coluna indica o tipo de lançamento que normalmente é usado.

> [!NOTE]
> Essas contas principais e os nomes de conta principal são apenas sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.


| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Custo unitário, entregue | 140100</br>140101 | Estoque de materiais</br>Materiais enviados não faturados | Ativo | Crédito | Sim | S | Custo unitário, faturado | Usado quando uma guia de remessa de ordem de venda é lançada. A contrapartida da conta é o Custo dos produtos vendidos, entregues. O valor nessa conta é revertido quando uma fatura de ordem de venda é lançada. Talvez você queira usar uma Conta de materiais enviados não faturados para representar o estoque físico e reservar a Conta de estoque de materiais para a atualização financeira. |
| Custo dos produtos vendidos, entregues | 500150 | COGS adiadas | Despesa | Débito | Sim | S  | Usado quando uma guia de remessa de ordem de venda é lançada. A contrapartida da conta é o Custo de unidades, entregues. O valor nessa conta é revertido quando uma fatura de ordem de venda é lançada. |
| Custo unitário, faturado | 140100 | Estoque de materiais | Ativo | Crédito | Número | S | Custo unitário, entregue | Usado quando uma fatura de ordem de venda é lançada. A contrapartida dessa conta é o Custo dos produtos vendidos, faturados. Essa conta representa o estoque em seu balanço. |
| Custo dos produtos vendidos, faturado | 500100 | Materiais COGS | Despesa | Débito | Número | S  | Usado quando uma fatura de ordem de venda é lançada. A contrapartida dessa conta é o Custo de unidades, faturadas. Essa conta representa o COGS em seu demonstrativo de P&amp;L. |
| Receita (Receita de ordem de venda*) | 400100 | Materiais de receita | Renda | Crédito | Número | S   | Usado quando uma fatura de ordem de venda é lançada. A contrapartida para essa conta é a conta Resumo (Saldo do cliente*) no perfil de lançamento **Contas a receber**. |
| Comissão (Vendas, comissão*) | 602150 | Despesa de comissão | Despesa | Débito | Número | S  | Usado quando a comissão é habilitada e calculada para uma venda e lançada durante o processo de faturamento da ordem de venda. A contrapartida para essa conta é a Comissão a pagar. |
| Contrapartida de comissão (Vendas, contrapartida de comissão*) | 201110 | Comissões a pagar | Passivo | Crédito | Sim | S | Usado quando a comissão é habilitada e calculada para uma venda e lançada durante o processo de faturamento da ordem de venda. A contrapartida para essa conta é a Despesa de comissão. |
| Receita diferida na entrega (Vendas – receita da guia de remessa*) | 401400 | Vendas acumuladas | Renda | Crédito | Sim | S  | Usado quando a Receita diferida para entrega é habilitada e lançada quando você processa uma guia de remessa da ordem de venda. A contrapartida para essa conta é a Contrapartida de receita diferida. Os valores nessa conta são revertidos automaticamente quando você lança a fatura da ordem de venda. |
| Contrapartida de receita diferida na entrega (Vendas – contrapartida de receita da guia de remessa)* | 130400 | Contas a receber – não faturadas | Ativo | Débito | Sim | S  | Usado quando a Receita diferida para entrega é habilitada e lança quando você processa uma guia de remessa da ordem de venda. A contrapartida para essa conta é a Receita diferida na entrega. Os valores nessa conta são revertidos automaticamente quando você lança a fatura da ordem de venda. |
| Imposto diferido na entrega (Vendas, imposto da guia de remessa*) | 250500 | Imposto diferido | Passivo | Crédito | Sim | S  | Usado quando a Receita diferida para entrega estiver habilitada e Lançar imposto físico estiver habilitado. O valor do imposto é lançado quando você processa uma guia de remessa da ordem de venda. |

\*Os valores mostrados entre parênteses nesta tabela representam o valor usado no campo **Tipo de lançamento** na página **Transações de comprovante**. Você pode exibir o **Tipo de lançamento** na página **Transações de comprovante** na guia **Geral**.

## <a name="sales-category-posting"></a>Lançamento de categoria de vendas

Como uma alternativa à configuração do lançamento de estoque para todos os itens, um grupo de itens ou um único item, você pode configurar categorias e controlar o lançamento contábil por categorias de vendas. Para obter mais informações sobre como configurar uma hierarquia de categoria e atribuir categorias a produtos, vá para [Criar uma hierarquia de classificação de produtos](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) e [Classificar um produto usando hierarquias de categoria](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

Depois de criar uma hierarquia de categoria, você deverá atribuir a hierarquia a um ou mais tipos. Para usar uma hierarquia de categoria em ordens de venda, você deverá atribuir a categoria ao tipo de hierarquia de categoria de venda. Para obter mais informações, acesse [Sobre hierarquias de categoria](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Criar lançamento de receita por categoria de vendas

Para atribuir lançamentos contábeis para uma ordem de venda com base em uma categoria de venda, siga estas etapas:

1. Acesse **Gerenciamento de estoque** > **Configuração** > **Lançamento** > **Lançamento**.
2. Selecione a guia **Vendas**.
3. Selecione o botão de opção para o tipo de lançamento que você deseja configurar (por exemplo, **Receita**).
4. Selecione **Novo**.
5. No campo **Código de item**, selecione **Categoria**.
6. Use o campo **Relação de categoria** para selecionar a categoria para o perfil de lançamento.
7. No campo **Código de conta**, selecione uma opção para **Tabela**, **Grupo** ou **Todos**. Por exemplo, para aplicar o perfil de lançamento a todos os clientes, selecione **Todos**.
   - Se você tiver selecionado **Tabela** na etapa 6, selecione o **Número de fornecedor** específico para o perfil de lançamento no campo **Relação de conta**.
   - Se você tiver selecionado **Grupo** na etapa 6, selecione o **Grupo de fornecedores** específico para o perfil de lançamento no campo **Relação de conta**.
   - Se você tiver selecionado **Todos** na etapa 6, o campo **Relação de conta** será deixado em branco.

8. Para associar um determinado grupo de impostos que tenha o tipo de lançamento selecionado, escolha um **Grupo de impostos**. Se deixar este campo em branco, o tipo de lançamento se aplicará a todos os grupos de impostos existentes. O lançamento especificado para grupos de impostos aplica-se apenas a transações feitas para vendas e compras.

9. No campo **Conta principal**, especifique o número da conta para lançar o tipo de conta. Selecione um dos números de conta existentes no plano de contas.
