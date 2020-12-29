---
title: Solucionar problemas de ordens de compra
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de compra.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 234458f865e37a2d962aee8ab218b9521847081d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422606"
---
# <a name="troubleshoot-purchase-orders"></a>Solucionar problemas de ordens de compra

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de compra.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>Uma ação pode ser concluída somente após o número da linha ser totalmente distribuído.

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>Quando as ordens de compra são importadas por meio do gerenciamento de dados, os números de linha da ordem de compra não seguem o incremento definido nos parâmetros do sistema.

### <a name="issue-description"></a>Descrição do problema

Por padrão, os números de linha gerados automaticamente para linhas de ordem de compra que são importadas por meio da entidade de dados *Linhas da ordem de compra V2* não usam o incremento de número de linha do sistema especificado nos parâmetros do sistema. Se você criar manualmente uma ordem de compra e adicionar linhas por meio da interface do usuário (IU), os números de linha serão incrementados corretamente. No entanto, se você usar a DMF (Estrutura de gerenciamento de dados), elas não serão incrementadas corretamente.

Esse problema ocorre porque, quando você importa linhas via DMF, se os números de linha ainda não estiverem atribuídos na entidade importada, o sistema usará o método de DMF para atribuí-los. Esse método sempre incrementa os números de linha em um.

### <a name="issue-workaround"></a>Solução alternativa do problema

Certifique-se de que os números de linha desejados já tenham sido fornecidos nos campos de número de linha da entidade de dados quando você importar as linhas da ordem de compra. Nesse caso, a DMF não substituirá os números de linha.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>Um grupo de impostos padrão e um desconto à vista padrão não são preenchidos a partir da conta da fatura.

Se você estiver usando uma conta da fatura diferente da conta do cliente, um grupo de impostos padrão e um desconto à vista padrão não serão preenchidos a partir da conta da fatura quando uma ordem de compra for criada.

Esse comportamento é por design. Os valores padrão para o grupo de impostos, descontos à vista e outras informações de preço são baseados na conta do cliente, não na conta da fatura.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Recebo uma mensagem de erro "Referência de objeto não definida" durante a confirmação da ordem de compra ou uma "Exceção lançada pelo destino de uma chamada" ocorre durante o lançamento da fatura do fornecedor.

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas.

### <a name="issue-description"></a>Descrição do problema

Você recebe o seguinte erro: "Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas".

### <a name="issue-resolution"></a>Resolução do problema

Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.

Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**. Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>É possível mostrar somente as ordens de compra que criei?

Essa funcionalidade não está disponível no momento.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>Posso reservar estoque e criar transações em relação ao estoque registrado em uma ordem de compra?

### <a name="issue-description"></a>Descrição do problema

Mesmo quando os itens estão em um estado *Registrado* em uma ordem de compra, você ainda pode reservar o estoque. Em outras palavras, você pode criar transações no estoque registrado.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Criar uma ordem de compra.
2. Registre a linha da ordem de compra.
3. Observe que você pode gerar reservas ou transações no estoque registrado.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. A expectativa é de que os itens registrados tenham sido entregues fisicamente no depósito ou estoque e que, portanto, estejam disponíveis para reserva.

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>As ordens de compra não refletem as configurações de idioma da entidade legal.

### <a name="issue-description"></a>Descrição do problema

O nome do produto em uma ordem de compra é mostrado no idioma do sistema, e não no idioma definido para a entidade legal na qual a ordem de compra foi criada.

### <a name="reproduce-the-issue"></a>Reproduzir o problema

O seguinte procedimento mostra uma forma de reproduzir o problema.

1. Defina o idioma do sistema como *EN-US* (Inglês dos EUA).
1. Verifique se há um produto no qual os idiomas *EN-US* e *DE* (Alemão) são mantidos para traduções do nome do produto.
1. Altere o idioma de uma entidade legal para *DE*.
1. Na entidade legal onde *DE* é definido como o idioma, crie uma ordem de compra que inclua o produto.
1. Observe que o nome do produto ainda é mostrado em inglês dos EUA (o idioma do sistema).

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. Nas ordens de compra, o produto sempre é mostrado no idioma do sistema. A linguagem da ordem de compra é usada quando um diário de confirmação é criado.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>A lista de Fornecedores aprovados por entidade de produto não permite que a data de efetivação seja alterada.

### <a name="issue-description"></a>Descrição do problema

Um produto tem um fornecedor aprovado que tem, por exemplo, uma data de efetivação de 11 de janeiro de 2018 (*11/01/2018*) e uma data de vencimento *Nunca*. Se você tentar alterar a data de efetivação para 10 de janeiro de 2018 (*10/01/2018*) ou 12 de janeiro, 2018 (*12/01/2018*), receberá o seguinte erro:

> Não é possível criar um registro na lista de fornecedores Aprovados (PdsApproveVendorList). O valor de 'Vencimento' precisa ser maior ou igual ao valor de 'Efetivo'.

### <a name="issue-resolution"></a>Resolução do problema

Você só pode estender o período para o qual o fornecedor foi aprovado. As seguintes regras são aplicadas:

- Para alterar a data de efetivação de forma que ela seja anterior a qualquer um dos registros existentes (períodos) para o fornecedor do item, a data de vencimento do novo período deve ser anterior a todas as datas de vencimento nos registros existentes.
- Para alterar a data de vencimento para que seja posterior a qualquer um dos períodos existentes, a data de efetivação deve ser posterior à data de vencimento mais recente em qualquer registro existente.
- Para reduzir o período geral para o qual o fornecedor foi aprovado, você deve excluir ou modificar os registros existentes. Como alternativa, você pode usar o alternador **truncar** durante a importação. Esta opção exclui todos os registros existentes na tabela para fornecedores aprovados por item.

Para o cenário de exemplo descrito na descrição do problema, em que um registro tem uma data de efetivação de *11/01/2018* e uma data de expiração *Nunca*, você pode importar um novo registro que tenha uma data de efetivação de *10/01/2018* e uma data de expiração *Nunca*. No entanto, não é possível reduzir o período para que a data de efetivação seja atualizada para *12/01/2018* por meio do gerenciamento de dados. Você deve fazer essa alteração por meio da interface do usuário.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>Depois de alterar o endereço de entrega em um cabeçalho de ordem de compra, o nome da entrega não é sincronizado.

### <a name="issue-description"></a>Descrição do problema

O endereço no cabeçalho de uma ordem de compra é atualizado para um endereço que não é um endereço de entrega. Embora o endereço seja atualizado na ordem de compra, o nome da entrega não é atualizado com base no endereço atualizado.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. O endereço selecionado deve ser classificado como um endereço de entrega. Caso contrário, o nome da entrega não será atualizado com base no endereço selecionado.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>É possível encontrar o usuário que cancelou uma ordem de compra?

Essas informações serão rastreadas somente se a ordem de compra estiver sujeita a gerenciamento de alterações. Se você usar o gerenciamento de alterações, poderá ver quem enviou a alteração (o cancelamento) e quem a aprovou.
