---
title: Usar o diário de estoque de segurança para atualizar a cobertura mínima para os itens
description: Este tópico descreve como usar o diário de estoque de segurança para atualizar a quantidade de estoque de segurança para itens calculando propostas de cobertura mínimas com base nas transações históricas.
author: ChristianRytt
ms.date: 10/28/2021
ms.topic: article
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, ReqItemTableSetup, ReqItemTable, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-28
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 59e4959898cd961582e1ac1d2285c0c0867ee7af
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790957"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage-for-items"></a>Usar o diário de estoque de segurança para atualizar a cobertura mínima para os itens

[!include [banner](../../includes/banner.md)]

O estoque de segurança indica uma quantidade adicional de um item que é mantido em estoque para ajudar a reduzir o risco de que o item fique esgotado. O estoque de segurança é usado como um estoque de reserva se as ordens de venda chegarem, mas o fornecedor não conseguir atender à data de remessa solicitada do cliente.

Este tópico descreve como usar o diário de estoque de segurança para calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas.

## <a name="overview-of-minimum-coverage-usage"></a>Visão geral do uso da cobertura mínima

O estoque de segurança é definido na página **Cobertura de item** para cada item. Os diferentes tipos de reabastecimento são representados por códigos de cobertura diferentes. (Para obter mais informações, consulte [Atendimento de estoque de segurança para itens](safety-stock-replenishment.md).) No entanto, todos os códigos de cobertura usam o valor definido no campo **Mínimo** na página **Cobertura de item** para cada item. Há duas abordagens principais para o uso do campo **Mínimo**:

- **Quantidade mínima para fins mínimos/máximos** – essa abordagem usa a quantidade mínima juntamente com a lógica de mín./máx. Ela se aplica quando o campo **Código de cobertura** é definido como *Mín./Máx.* para o item ou grupo de cobertura relevante. A quantidade **Mínima** representa o uso médio diário multiplicado pelo prazo de entrega do item.
- **Quantidade mínima para fins de plano de estoque** – essa abordagem usa a quantidade mínima para representar um plano de estoque em combinação com previsões de demanda. Ela se aplica quando o campo **Código de cobertura** é definido como *Período* ou *Requisito* para o item ou grupo de cobertura relevante. A quantidade **Mínima** representa um plano de estoque que reflete o nível de serviço de atendimento ao cliente desejado para ajudar a reduzir a quantidade de produtos fora de estoques, as remessas parciais e os tempos de entrega. A quantidade mínima reflete uma porcentagem da precisão da previsão para um determinado item. Ela não representa uma posição de estoque desejada.

O valor **Mínimo** pode ser definido de três maneiras:

- Manualmente, na página **Cobertura de item**
- Pela estrutura de Gerenciamento de Dados (entidades de dados *Cobertura de item*)
- Pelo cálculo do estoque de segurança que é feito pelos diários de estoque de segurança

## <a name="calculate-minimum-coverage-based-on-historical-usage"></a>Calcular cobertura mínima com base no uso histórico

Os diários de estoque de segurança são usados para calcular uma quantidade mínima proposta com base no uso histórico de um item, seja para fins mínimos/máximos ou para fins do plano de estoque. O uso histórico representa todas as transações de saída durante um período especificado. Essas transações de saída incluem transações de ordem de venda e ajustes de estoque. Os cálculos também identificam o impacto da quantidade mínima proposta de valor de estoque e a alteração no valor de estoque em comparação com as quantidades mínimas atuais.

Cada linha do diário de estoque de segurança representa um item e suas dimensões de cobertura. Essas linhas do diário são criadas e exibidas na página **Linhas de diário de estoque de segurança** (**Planejamento mestre \> Planejamento mestre \> Executar \> Cálculo de estoque de segurança**). O processo empresarial para usar os diários de estoque de segurança para calcular as quantidades mínimas propostas é descrito posteriormente neste tópico.

O planejador usa um diário de estoque de segurança para calcular as quantidades mínimas propostas para itens selecionados, com base no uso histórico durante períodos selecionados. Os mínimos propostos podem ser substituídos manualmente, conforme necessário, e você pode revisar o possível impacto dos mínimos propostos sobre o valor de estoque. Quando o diário é lançado, as quantidades mínimas associadas na cobertura de item são atualizadas automaticamente.

### <a name="create-a-new-safety-stock-journal-name"></a>Crie um novo nome de diário de estoque seguro

Você deve criar, pelo menos, um nome de diário de estoque antes que possa gerar esse tipo de diário. Normalmente, você pode usar vários nomes de diário para ajudar a separar os cálculos de estoque de segurança.

1. Acesse **Planejamento mestre \> Configuração \> Nomes do diário de estoque de segurança**.
1. No Painel de Ações, selecione **Novo**.
1. Na nova linha, defina os seguintes campos:

    - **Nome** – insira um nome curto para o diário.
    - **Descrição** – insira uma descrição do diário.
    - **Particular do grupo de usuários** – para limitar o público-alvo para o nome de diário atual, selecione um grupo de usuários.
    - **Excluir linhas após lançamento** – marque esta caixa de seleção para limpar as linhas do diário por padrão ao lançá-las. Desmarque-a para manter todas as linhas lançadas.

    O campo **Tipo de diário** é somente leitura e está predefinido como *Estoque de segurança*.

1. Feche a página.

### <a name="create-a-safety-stock-journal-and-lines"></a>Criar um diário de estoque de segurança e linhas

Esta etapa cria um diário e adiciona linhas a ele automaticamente. Cada linha identifica um item, suas dimensões de cobertura e várias quantidades calculadas do histórico de uso. As quantidades calculadas incluem as saídas médias por prazo de entrega do item, as saídas médias por mês e o desvio padrão mensal.

#### <a name="automatically-generate-journal-lines"></a>Gerar linhas do diário automaticamente

As linhas do diário só poderão ser geradas automaticamente se não houver linhas para o diário exibido no momento.

Siga estas etapas para gerar linhas de diário automaticamente.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Cálculo de estoque de segurança**.
1. No Painel de Ações, selecione **Novo**. Um novo diário de estoque de segurança será criado.
1. Na Guia Rápida **Detalhes do cabeçalho do diário**, defina os seguintes campos:

    - **Nome** – selecione o nome do diário de estoque de segurança ao qual adicionar a linha.
    - **Descrição** – o valor padrão é a descrição do nome do diário selecionado. No entanto, você pode editar o valor conforme desejado.
    - **Excluir linhas após lançamento** – marque esta caixa de seleção para limpar as linhas do diário ao lançá-las. Desmarque-a para manter todas as linhas lançadas. A configuração é herdada do nome do diário selecionado.

    O campo **Diário** é somente leitura e exibe o número da ID do diário que você está criando e adicionando linhas.

1. Na Guia Rápida **Linhas do diário**, selecione **Criar linhas** na barra de ferramentas.
1. Na caixa de diálogo **Criar linhas de diário para os níveis de estoque mínimos propostos**, defina os seguintes campos:

    - **Data inicial** – selecione a data inicial do período no qual as saídas devem ser incluídas no cálculo.
    - **Data final** – selecione a data de término do período no qual as saídas devem ser incluídas esse cálculo. Deve haver pelo menos dois meses entre as datas inicial e final.
    - **Calcular desvio padrão** – defina esta opção como *Sim* para calcular o desvio padrão. Você deve definir esta opção como *Sim* para usar a opção **Usar nível de serviço** ao calcular a proposta (conforme descrito posteriormente neste tópico).

1. Na Guia Rápida **Registros a serem incluídos**, você pode configurar filtros e restrições para definir quais itens são incluídos. (Por exemplo, é possível filtrar pelo valor do **Grupo de cobertura**.) Selecione **Filtrar** para abrir uma caixa de diálogo padrão do editor de consultas na qual você pode definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Microsoft Dynamics 365 Supply Chain Management.
1. Na Guia Rápida **Executar em segundo plano**, selecione se o trabalho deve ser executado no modo de lote e/ou configure uma agenda recorrente. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK**. Linhas serão criadas para as dimensões que tenham transações de estoque.

#### <a name="manually-add-or-remove-journal-lines"></a>Adicionar ou remover manualmente linhas do diário

Você pode adicionar e/ou remover manualmente as linhas do diário a qualquer momento (depois ou em vez de gerar linhas automaticamente). Use os botões a seguir na barra de ferramentas da Guia Rápida **Linhas do diário**:

- **Nova** – adicione uma nova linha. Em seguida, insira um valor em cada coluna para definir o produto a ser calculado e aplicar os novos mínimos. Como os cálculos mínimos propostos não estão disponíveis para linhas adicionadas manualmente, nenhum valor de **Quantidade mínima calculada** é mostrado para elas. Portanto, você deve inserir manualmente os valores de **Nova quantidade mínima**. No entanto, você ainda pode ver o possível impacto do valor de **Nova quantidade mínima** no valor do estoque e a possível alteração no estoque em comparação com o mínimo especificado no momento.
- **Excluir** – exclua uma linha selecionada.
- **Excluir linhas do diário** – exclua todas as linhas no diário.

### <a name="calculate-a-proposal"></a>Calcular uma proposta

Esta etapa calcula o mínimo proposto para cada linha de diário e o possível impacto da linha no valor do estoque. (O mínimo proposto é mostrado como o valor da **Quantidade mínima calculada**.) Você pode fazer o cálculo várias vezes, conforme necessário. O cálculo atualiza o valor da **Quantidade mínima calculada** que é mostrado para todas as linhas do diário.

Os cálculos exibidos não afetarão os valores de quantidade mínima real para cada produto até que você selecione **Lançar** no Painel de Ações. Nesse momento, os valores de **Nova quantidade mínima** serão aplicados a cada produto.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Cálculo de estoque de segurança**.
1. Abra o diário para o qual calcular uma proposta. Como alternativa, crie um diário conforme descrito anteriormente neste tópico.
1. Na Guia Rápida **Linhas do diário**, selecione **Calcular proposta** na barra de ferramentas. (Não é necessário selecionar linhas.)
1. Na caixa de diálogo **Calcular proposta de nível de estoque mínimo**, defina os seguintes campos:

    - **Usar média de saídas durante o prazo de entrega** – selecione esta opção para gerar valores de **Quantidade mínima calculada** com base na média de saídas durante o período especificado. Em seguida, no campo **Fator de multiplicação**, insira um valor para ajustar o resultado conforme necessário. Por exemplo, insira *1,0* para usar a média calculada exata ou *1,1* para adicionar um buffer extra de 10%.
    - **Usar nível de serviço** – selecione esta opção para calcular um mínimo proposto com base no nível de serviço desejado. Em seguida, no campo **Nível de serviço**, selecione o nível de serviço preferencial.
    - **Margem de prazo de entrega** – insira um valor para estender o prazo de entrega normal (por exemplo, para permitir a administração).
    - **Usar a quantidade mínima calculada como a nova quantidade mínima** – defina esta opção como *Sim* para copiar automaticamente os valores da coluna de **Quantidade mínima calculada** para a coluna **Nova quantidade mínima** em todas as linhas após a conclusão do cálculo. Se você definir esta opção como *Não*, o valor de **Quantidade mínima atual** será copiado para a coluna **Nova quantidade mínima** em todas as linhas. Será necessário editar manualmente os valores de **Nova quantidade mínima**, conforme necessário.

1. Na Guia Rápida **Executar em segundo plano**, selecione se o trabalho deve ser executado no modo de lote e/ou configure uma agenda recorrente. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK**. Os resultados do cálculo são mostrados na coluna **Quantidade mínima calculada** na Guia Rápida **Linhas do diário**. Por enquanto, os valores são somente valores propostos que ainda não foram aplicados a seus produtos.

### <a name="update-minimum-quantity"></a>Atualizar quantidade mínima

Você pode selecionar qualquer linha em um diário de estoque de segurança e substituir manualmente o valor do campo **Nova quantidade mínima**.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Cálculo de estoque de segurança**.
1. Abrir o diário para editá-lo. Como alternativa, crie um diário conforme descrito anteriormente.
1. Na Guia Rápida **Linhas do diário**, encontre a linha a ser ajustada e edite o valor na coluna **Nova quantidade mínima**. Por exemplo, você pode definir o valor de **Nova quantidade mínima** para que ele corresponda ao valor de **Quantidade mínima calculada**. Se o valor de **Quantidade mínima calculada** for *0* (zero), você poderá inserir o valor futuro desejado.

### <a name="post-the-new-minimum-quantity-and-validate-the-result"></a>Lançar a nova quantidade mínima e validar o resultado

Siga estas etapas para lançar a nova quantidade mínima e validar o resultado.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Cálculo de estoque de segurança**.
1. Abra o diário para o qual lançar novas quantidades mínimas. Como alternativa, crie um diário conforme descrito anteriormente.
1. No Painel de Ação, selecione **Lançar**.
1. Na caixa de diálogo **Diário de lançamentos**, defina o campo **Transferir todos os erros de lançamento para um novo diário**, conforme necessário. Selecione **OK** para lançar o diário.
1. Se alterou o valor de **Nova quantidade mínima** para uma linha na Guia Rápida **Linhas do diário**, você poderá confirmar a alteração seguindo estas etapas:

    1. Para a linha que você editou, selecione o link na coluna **Número do item**.
    1. Na caixa de diálogo **Informações do produto**, selecione o link no campo **Número do item** para abrir o registro de produto liberado relacionado.
    1. Selecione o item e, depois, no Painel de Ações, na guia **Plano**, clique em **Cobertura** e selecione **Cobertura do item**.
    1. Observe que o valor **Mínimo** para o local e o depósito que você ajustou usando o diário de estoque de segurança lançado foi atualizado para corresponder à sua edição.

## <a name="additional-resources"></a>Recursos adicionais

- [Atendimento de estoque de segurança para itens](safety-stock-replenishment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
