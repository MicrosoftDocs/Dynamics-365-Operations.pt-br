---
title: Adquirir ativos por meio de compra
description: Este tópico descreve como configurar a integração entre Ativos fixos e Contas a pagar para criar automaticamente ativos fixos de ordens ou faturas de fornecedor ou lançar automaticamente transações de aquisições e de ajuste de aquisições para ativos fixos.
author: moaamer
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 3481
ms.assetid: d4e73a3f-633b-48b2-b8db-7a4a59a4d7ec
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b654dbf97f8d91e0a3233803ee182b1383ad317d
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712080"
---
# <a name="acquire-assets-through-procurement"></a>Adquirir ativos por meio de compra

[!include [banner](../includes/banner.md)]

Este tópico descreve como configurar a integração entre Ativos fixos e Contas a pagar para criar automaticamente ativos fixos de ordens ou faturas de fornecedor ou lançar automaticamente transações de aquisições e de ajuste de aquisições para ativos fixos. Uma linha de compras criará um ativo, independentemente da quantidade na linha de compras. Se precisar criar vários ativos fixos, você deverá criar várias linhas de compras.

 Os seguintes métodos estão disponíveis para integrar Ativos fixos e Contas a pagar, e você deve usar o mesmo método para todos os ativos fixos:
-   Crie manualmente um ativo fixo antes de adicionar o número do ativo fixo à linha na ordem de compra ou na fatura de fornecedor. Uma transação de aquisição é lançada automaticamente para o ativo quando você lança a fatura de fornecedor. Esse é o método padrão.
-   Crie manualmente um ativo fixo antes de adicionar o número do ativo fixo à linha na ordem de compra ou na fatura de fornecedor. Nenhuma transação de aquisição é lançada para o ativo quando você lança a fatura de fornecedor.
-   Um ativo fixo é criado automaticamente quando você lança um recebimento de produtos ou uma fatura de fornecedor na qual a caixa de seleção Criar um novo ativo fixo está marcada. Uma transação de aquisição é lançada automaticamente para o ativo quando você lança a fatura de fornecedor.
-   Um ativo fixo é criado automaticamente quando você lança um recebimento de produtos ou uma fatura de fornecedor na qual a caixa de seleção Criar um novo ativo fixo está marcada. Nenhuma transação de aquisição é lançada para o ativo quando você lança a fatura de fornecedor.

Selecione um dos primeiros dois métodos se você preferir criar ativos fixos manualmente e atribua o número de ativo fixo à ordem de compra ou à fatura de fornecedor. Selecione um dos dois últimos métodos se você preferir uma abordagem mais flexível: às vezes você pode criar ativos fixos manualmente e, às vezes, você pode criar automaticamente um ativo fixo com base nas informações de ativo fixo nos detalhes do item de linha. 

Se você cria ativos fixos manualmente ou usa uma abordagem mais flexível, também deve decidir se uma transação de aquisição só pode ser lançada em Ativos fixos ou se pode ser lançada ao lançar uma fatura de fornecedor. Algumas organizações preferem que os usuários criem aquisições e transações de aquisição manualmente nos Ativos fixos usando entradas de diário ou propostas manuais. 

Este tópico discute os detalhes de cada método.

## <a name="methods-for-manually-creating-fixed-assets"></a>Métodos para criar ativos fixos manualmente
Quando você lança uma fatura de fornecedor com um número de ativo fixo inserido nas linhas, se a opção Permitir aquisição de ativo de Compras estiver selecionada na página Parâmetros de ativos fixos, a aquisição será lançada automaticamente e o status do ativo será alterado para Aberto. 

Se uma aquisição não puder ser lançada, você poderá inserir uma transação de aquisição manualmente em Ativos fixos ou usar uma proposta de aquisição no diário Ativos fixos para criar várias transações de aquisição de uma vez.

> [!NOTE]                                                                                                                              
> Se a guia rápida Ativos fixos estiver configurada para limitar o lançamento de transações de aquisição para um grupo de usuários específico, você deverá ser um membro desse grupo de usuários para lançar transações de aquisição de faturas.

## <a name="methods-for-automatically-creating-fixed-assets"></a>Métodos para criar ativos fixos automaticamente
Quando você lança um recebimento de produtos que tem a opção Criar um novo ativo fixo selecionada para uma linha, um novo ativo fixo é criado com um status Ainda não adquirido. Então, quando você lançar uma fatura de fornecedor com um novo ativo fixo, será lançada uma transação de aquisição para o novo ativo e o status do ativo será alterado para Aberto, se a Guia Rápida Ativos fixos estiver configurada para permitir aquisições de ativo de Contas a pagar e você for um membro de um grupo de usuários que podem lançar transações de aquisição. 

Se a opção Novo ativo fixo? não tiver sido selecionada na linha de compra quando você lançou o recebimento de produtos, mas foi selecionada quando a fatura de fornecedor foi lançada, o novo ativo fixo será criado e adquirido com um status Aberto, se a Guia Rápida Ativos fixos estiver configurada para permitir a criação e a aquisição. Um ativo adicional não é criado quando você lança uma fatura de fornecedor se um ativo já foi criado ao lançar o recebimento de produtos.

### <a name="capitalization-threshold"></a>Limite de capitalização

Quando você usar um método no qual o ativo é criado e adquirido automaticamente, é possível configurar o sistema para verificar se o valor da compra do ativo fixo atende ao limite de capitalização especificado para a depreciação de ativo. Em caso afirmativo, a opção Depreciação será marcada nos registros de depreciações para o ativo quando é criado a partir das Contas a pagar. 

Um limite de capitalização é um valor monetário que determina se os ativos serão depreciados se atenderem ao valor especificado. Por exemplo, se você comprar um ativo e o valor de compra for menor que o limite de capitalização, o ativo não é designado para depreciação; se o valor de compra atende ou excede o limite, o ativo é designado para depreciação. 

Você pode configurar o limite de capitalização na página Grupos de ativos fixos.

## <a name="scenario"></a>Cenário
O cenário a seguir discute um ciclo completo de uma integração de Ativos fixos e Contas a pagar. Uma configuração de exemplo é mostrada e o uso de propostas de aquisição também é descrito. 

Nesse cenário, o sistema é configurado da seguinte forma:

-   Os ativos são criados automaticamente durante o lançamento de recebimento de produtos ou de fatura de fornecedor, mas a guia rápida Ativos fixos está configurada para impedir o lançamento de transações de aquisição de Contas a pagar.
-   As contas são especificadas no campo Tipo de conta para os tipos de conta Recebimento de ativo fixo e Emissão de ativo fixo na página Grupos de itens.
-   O limite de capitalização para o grupo de computadores (COMP) é de 1.500.
-   A sua tarefa é inserir uma ordem de compra para um novo laptop que um funcionário usará, lançar a ordem de compra, verificar se o vendedor de remessa lança um recebimento de produtos, lançar a fatura de fornecedor e verificar se o contador atualiza o ativo do laptop para um status Aberto.

Para começar, use a página Ordem de compra para inserir os detalhes do laptop, que custa 1.600. Você seleciona a opção Novo ativo fixo? na Guia Rápida Ativos fixos das linhas de ordem de compra, seleciona COMP como o grupo de ativos fixos e salva a ordem de compra. 

Quando o laptop for recebido, um vendedor de remessa inserirá e lançará um recebimento de produtos para registrar o recebimento do laptop. O ativo do laptop é criado e tem um status Ainda não adquirido. O valor excede o limite de capitalização. Portanto, a opção Depreciação é selecionada nos registros de depreciações para o ativo do laptop. As transações a seguir ocorreram.

| Descrição                               | Conta             | Débito    | Crédito   |
|-------------------------------------------|---------------------|----------|----------|
| Compra, compra de recebimento de produtos        | Recebimentos não faturados | 1.600,00 |          |
| Compra, contrapartida de compra do recebimento de produtos | Compras acumuladas   |          | 1.600,00 |

Em seguida, você lança a fatura de fornecedor para o laptop. O status do laptop não é alterado porque a guia rápida Ativos fixos está configurada para impedir que uma transação de aquisição de ativo seja lançada quando uma fatura de fornecedor é lançada. A opção Criar um novo ativo fixo foi selecionada quando a fatura do fornecedor foi lançada. Consequentemente, a conta Recebimento de ativo fixo foi usada. A conta Emissão de ativo fixo não foi usada porque não foi lançada nenhuma aquisição; ela será usada posteriormente quando o contador de sua organização lançar uma transação de aquisição em Ativos fixos usando propostas de aquisição. 

As transações a seguir ocorreram.

| Descrição                               | Conta             | Débito    | Crédito   |
|-------------------------------------------|---------------------|----------|----------|
| Compra, contrapartida de compra do recebimento de produtos | Compras acumuladas   | 1.600,00 |          |
| Saldo do fornecedor                            | Contas a pagar    |          | 1.600,00 |
| Comprar, recebimento de ativo fixo             | Despesa de computador    | 1.600,00 |          |
| Compra, compra de recebimento de produtos        | Recebimentos não faturados |          | 1.600,00 |

Finalmente, o contador verifica todos os ativos fixos com um status Ainda não adquirido. Portanto, o novo ativo do laptop é verificado. O contador então abre a página Proposta de aquisição nas linhas do diário Ativos fixos e cria transações de aquisição para todos os ativos com uma fatura mas que ainda tenham um status Ainda não adquirido. Quando o diário é lançado, o status do ativo do laptop é alterado para Aberto. A conta Emissão de ativo fixo é creditada e a conta de aquisição de ativo é debitada. 

A seguir, encontram-se as variações para esse cenário:

-   Se a guia rápida Ativos fixos está configurada para permitir que transações de aquisição de ativo sejam lançadas quando faturas de fornecedor são lançadas, o contador não precisa usar propostas de aquisição em Ativos fixos porque a transação de aquisição foi criada. Além disso, contas diferentes também são atualizadas ao lançar a fatura de fornecedor. Em vez de Despesa de computador, a conta de estoque Recebimento de ativo fixo é debitada e ocorrem duas transações adicionais: a conta de aquisição de ativo é debitada e a conta de estoque Emissão de ativo fixo é creditada.
-   Se a opção Criar um novo ativo fixo não estiver selecionada quando o recebimento de produtos for lançado, nenhum ativo será criado nesse momento. Se você selecionar a opção Criar um novo ativo fixo antes de lançar a fatura de fornecedor, o ativo será criado e terá um status Ainda não adquirido ou um status Aberto se você também lançar transações de aquisição quando as faturas de fornecedor forem lançadas.
-   Se o custo do laptop é 1.400, em vez de 1.600, o limite de capitalização não é atingido. Portanto, o ativo é criado e a opção Depreciação é desmarcada.
-   Se um registro de fatura for usado, use a página Diário de aprovação de fatura após o lançamento do registro da fatura para recuperar o comprovante, vincule a ordem de compra à fatura de fornecedor, selecione a opção Criar um novo ativo fixo e lance a fatura de fornecedor. Se você for membro de um grupo de usuários que pode criar transações de aquisição, a aquisição será criada e o ativo terá um status Aberto.
-   Se for recebida somente uma quantidade parcial, não será criada nenhuma aquisição de ativo para a primeira fatura de fornecedor por causa das restrições do grupo de usuários. A única forma que uma aquisição pode ser lançada para a segunda fatura de fornecedor que completa a quantidade encomendada é se uma transação de aquisição já foi inserida para a primeira fatura de fornecedor e você for membro do grupo de usuários que tem permissão para lançar aquisições.


Para obter mais informações, consulte [Integração de ativos fixos](fixed-asset-integration.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
