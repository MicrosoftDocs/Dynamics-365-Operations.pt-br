---
title: Visão geral da conversão em custo padrão
description: Este artigo fornece uma visão geral do processo para ajudar você a configurar e a executar uma conversão de custo padrão. As etapas listadas devem ser concluídas depois que você tiver concluído os pré-requisitos de uma conversão de custo padrão.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78212
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bcbd8464532722c83f170db6b19cca5dd77846a0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011788"
---
# <a name="standard-cost-conversion-overview"></a>Visão geral da conversão em custo padrão

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do processo para ajudar você a configurar e a executar uma conversão de custo padrão. As etapas listadas devem ser concluídas depois que você tiver concluído os pré-requisitos de uma conversão de custo padrão. 

Use a página **Conversões de custo padrão** para converter o modelo de estoque de um lote de itens selecionados de uma abordagem de custo real para uma abordagem de custo padrão. O processo de conversão envolve um fechamento obrigatório do estoque, várias etapas durante um período de transição, que é definido por uma data de início da transição e uma data de conversão planejada e, em seguida, a conversão e um fechamento de estoque associado.

-   Fechamento do estoque antes do período de transição – um fechamento do estoque representa uma etapa obrigatório porque liquida as transações abertas de um item usando o método de avaliação antigo. Durante o período de transição, você pode inserir e lançar transações de datas anteriores, tais como faturas, para que possa fechar o período anterior. A data de fechamento do estoque deve ser um dia antes da data de início da transição para garantir uma separação clara do método de avaliação antigo.
-   Etapas de conversão durante o período de transição – use a página **Conversões de custo padrão** para criar um registro de conversão que também tenha o identificador definido pelo usuário para uma nova versão dos custos. Identifique os itens que exigem conversão e, em seguida, insira os custos padrão pendentes do item na nova versão da avaliação de custo. Execute uma verificação dos itens selecionados para identificar problemas que podem impedir a conversão e, em seguida, execute outra verificação. Depois que os itens passarem com êxito pelas verificações, altere o status do registro de conversão para **Pronto**. Na data de conversão planejada, execute a conversão e, opcionalmente, inclua um fechamento do estoque. Os movimentos de estoque de um item durante o período de transição são lançados e avaliados de acordo com o modelo de estoque antigo. Em seguida, após a conversão ser concluída com êxito, os movimentos de estoque são reavaliados em custo padrão.
-   Fechamento do estoque antes da conversão − o fechamento do estoque pode ser incluído como parte da conversão na data de conversão planejada ou pode ser realizado como uma etapa preparatória antes da conversão.

Após o processo de conversão ser concluído com êxito, o modelo de estoque para cada item é baseado no custo padrão, e o custo padrão do item é habilitado. As transações de estoque subsequentes serão avaliadas pelo custo padrão do item. Além disso, o sistema converte as transações de estoque físico do item para recebimentos e saídas em custo padrão, baseado na data de conversão. O sistema também converte o estoque disponível financeiro do item em custo padrão e lança a diferença no valor como reavaliação de estoque. Todas as transações que ocorrerem após a conversão são avaliadas pelo custo padrão do item. Não é possível inserir transações de datas anteriores antes da data da conversão, pois um fechamento do estoque deve ser realizado um dia antes da data de conversão. Uma conversão pode ser realizada somente se um fechamento do estoque tiver sido realizado um dia antes. O fechamento do estoque não pode ser cancelado.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Definir um registro de conversão em custo padrão e a versão do custo associada
Use a página **Conversões de custo padrão** para criar um registro de conversão. Você só poderá criar um novo registro de conversão quando os registros de conversão existentes forem concluídos. A duração do período de transição planejado é definida pela data de início da transição e a data de conversão planejada. Um período de transição planejado pode ser de até um dia. Um período de transição planejado ajuda a garantir que o processo de conversão tenha tempo suficiente para executar todas as suas etapas. Deve-se executar um fechamento de estoque em uma data que seja dia antes da data inicial da transição para ajudar a garantir que as liquidações sejam concluídas antes que você inicie o processo de conversão. Para garantir que a data de início e a data de fechamento do estoque estejam corretamente alinhadas, você poderá alterar a data de início da transição para um dia após um fechamento estoque existente ou pode executar um fechamento de estoque. Ao inserir um registro de conversão, você também insere um identificador definido pelo usuário para uma nova versão do custo que conterá os custos padrão dos itens convertidos. A versão de avaliação de custo é gerada automaticamente quando você salva o registro de conversão.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Examinar e alterar a nova versão de avaliação de custo para o registro de conversão
A nova versão de avaliação de custo é dedicada ao registro de conversão, como indicado pelo tipo de avaliação de custo **Conversão**. A versão do custo dedicada é semelhante a uma versão do custo para custos padrão, e contém os registros de custo de item para os itens associados ao registro de conversão. A versão do custo dedicada a um registro de conversão tem as seguintes configurações, que você deve examinar e modificar nas diversas guias de acordo com a necessidade:

-   **Tipo de avaliação de custo:** esse campo deve ser definido como **Custo padrão**.
-   **Versão** − o identificador reflete as informações inseridas no registro de conversão para a ID da versão do custo.
-   **Nome:** por padrão, o nome está em branco. Opcionalmente, você pode inserir um nome.
-   **Bloquear:** esse campo deve ser definido como **Não**. Você pode inserir registros de custo na versão do custo até alterar o status do registro de conversão para **Pronto**. Um status **Pronto** significa que os itens selecionados foram verificados e que as alterações nos registros de custo não devem ser permitidas.
-   **Bloquear ativação:** esse campo deve ser definido como **Sim**. Você não pode ativar manualmente um registro de custo pendente em uma versão do custo dedicada. A ativação ocorre quando você executa a conversão.
-   **Data de início:** a data de início reflete a data de conversão planejada inserida no registro de conversão.
-   **Site:** deixe esse campo em branco para que os registros de custo possam ser inseridos para qualquer site.
-   **Permitir grupo de campos de tipo de preço:** defina esse campo como **Sim**, de forma que somente os registros de preço de custo possam ser inseridos.
-   **Princípio de fallback:** esse campo é definido como **Nenhum**. Altere o princípio do fallback para **Ativo** se você exigir informações de custo ativadas em outras versões do custo. Por exemplo, as informações de custo sobre componentes, categorias de custo e custos indiretos podem ser obrigatórias para calcular os custos de itens fabricados.
-   **Versão de avaliação de custo de fallback:** deixe esse campo em branco.

As informações de custo de item na versão do custo dedicada só podem ser mantidas na página **Conversões de custo padrão**. Você não pode usar a página **Configuração da versão de avaliação de custo** ou a página **Manutenção de versão de avaliação de custo** para calcular custos para a versão de avaliação de custo durante a conversão. No entanto, você pode usar essas páginas para manter a versão de avaliação de custo dedicada depois de concluir o processo de conversão.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Identificar os itens a serem convertidos em custo padrão
Use a página **Conversões de custo padrão** para identificar os itens individuais que devem ser convertidos em custo padrão. Você pode adicionar vários itens usando a página **Adicionar itens à conversão de custo padrão**. Em geral, você deve incluir todos os itens fabricados em um único registro de conversão para ajudar a garantir que os custos sejam calculados corretamente.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Inserir ou calcular o custo padrão pendente para cada item que está sendo convertido
Use a página **Preço de item** para inserir custos padrão pendentes na versão do custo dedicada para itens comprados e transferidos. Os registros de custos são específicos ao site e os custos pendentes de um item devem ser inseridos para cada site. Use a página **Preço de item** para calcular os custos padrão pendentes para itens fabricados. Os custos pendentes de um item fabricado devem ser calculados para cada site de fabricação, a menos que o site represente um site de transferência. Nesse caso, os custos pendentes devem ser inseridos manualmente. Alguns itens podem ter as dimensões do produto de cor, tamanho ou configuração. Na página **Conversões de custo padrão**, a caixa de seleção **Usar preço de custo por variante** mostra o custo padrão para cada combinação de dimensões do produto. Quando essa caixa de seleção é desmarcada, você deve inserir um custo pendente para o item.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Verificar e resolver os problemas dos itens que estão sendo convertidos
Use o relatório **Verificações da conversão de custo padrão** para identificar os problemas dos itens que estão sendo convertidos. Se um item não tiver problemas, o status dele no registro de conversão será alterado para **Verificado**. Se um item tiver problemas, você deverá resolver os problemas e então executar o relatório novamente até que o status do item seja alterado para **Verificado**. Se você não conseguir resolver os problemas de um item rapidamente, terá a opção de excluir o item do registro de conversão e convertê-lo posteriormente.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Altere o status do registro de conversão para Pronto.
Quando o status do registro de conversão for alterado para **Pronto**, o sistema realizará uma verificação final antes de executar uma conversão de custo padrão. O status só será alterado para **Pronto** quando as condições a seguir forem atendidas:

-   Todos os itens do registro de conversão têm o status **Verificado**.
-   Um fechamento de estoque foi realizado um dia antes da data inicial da transição. Para garantir que a data de início e a data de fechamento do estoque estejam corretamente alinhadas, você poderá alterar a data de início da transição para um dia após um fechamento estoque existente ou pode executar um fechamento de estoque.

## <a name="7-back-up-the-database-before-conversion"></a>7. Fazer backup do banco de dados antes da conversão
O backup permite que você restaure o banco de dados se forem encontrados erros durante a conversão.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Execute o processo de conversão quando o status do registro de conversão for Pronto.
O processo de conversão requer que um fechamento de estoque seja executado um dia antes da data de conversão planejada. Esse requisito ajuda a garantir que as transações com datas anteriores não possam ser inseridas durante o período de transição. Se um fechamento de estoque ainda não tiver sido realizado, será solicitado que você o execute como parte do processo de conversão. O processo de conversão trata um item por vez. Começa pelos itens mais baixos em uma estrutura de produto, com base no código de baixo nível do item. Quando um item é convertido com êxito, seu status no registro de conversão é alterado para **Convertido**. Se o processo de conversão for interrompido, todos os itens que não foram convertidos com êxito ainda terão o status **Verificado**. O êxito na conclusão do processo de conversão causa os efeitos a seguir:

-   O status do registro de conversão é alterado de **Pronto** para **Concluído** e o status de cada item selecionado é alterado de **Verificado** para **Convertido**.
-   O grupo de modelos de item dos itens convertidos é alterado para refletir um novo grupo com um modelo de estoque de custo padrão.
-   Os custos padrão dos itens convertidos foram habilitados com a versão do custo dedicada.
-   O tipo de custos da versão do custo é alterado de **Conversão** para **Custo padrão**, e a versão do custo passa a agir como qualquer outra versão de avaliação de custo para custos padrão.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Validar e reconciliar os valores de estoque dos itens convertidos
O relatório **Demonstrativo de análise de variação** permite analisar a variação da reavaliação e o relatório **Valor de estoque** permite que você exiba o valor de estoque em uma data específica.

-   Analise as variações de reavaliação. Use o relatório **Demonstrativo de análise de variação** para exibir as variações de reavaliação de estoque dos itens convertidos. Você também pode usar a página **Transações de custo padrão** para exibir as transações de reavaliação de estoque dos itens convertidos com o estoque.
-   Analise o valor de estoque antes da data inicial da transição. Use o relatório **Valor de estoque** para exibir os valores de estoque dos itens convertidos. Na Data de término do relatório, use uma data que seja um dia antes da data de início da transição.
-   Analise o valor de estoque antes da data de conversão. Use o relatório **Valor de estoque** para exibir os valores de estoque dos itens convertidos. Como a Data de término do relatório, use uma data que reflita um dia antes da data de conversão.
-   Analise o valor do estoque na data de conversão. Use o relatório **Valor do estoque** para exibir os valores do estoque na data de conversão. A Data de início e a Data de término do relatório devem corresponder à data de conversão. Os critérios de seleção do relatório devem refletir os itens convertidos.
-   Analise os movimentos de estoque de datas anteriores. Use o relatório **Data do estoque** para exibir os movimentos de estoque com datas anteriores inseridos após a conversão. A Data de início e a Data de término do relatório devem corresponder à data inicial da transição e à data de conversão, menos um dia. Os critérios de seleção do relatório devem refletir os itens convertidos. O relatório mostra os movimentos de estoque feitos ao custo padrão durante o período de transição.


<a name="additional-resources"></a>Recursos adicionais
--------

[Pré-requisitos para uma conversão em custo padrão](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]