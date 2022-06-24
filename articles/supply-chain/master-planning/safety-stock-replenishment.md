---
title: Atendimento de estoque de segurança para itens
description: Este artigo discute o atendimento de estoque de segurança e como configurar a quantidade de estoque de segurança para itens.
author: t-benebo
ms.date: 8/23/2021
ms.topic: article
ms.search.form: ReqSafetyKey, ReqItemTableSetup, ReqItemJournalName, ReqItemTable, EcoResProductDetailsExtended, ReqSafetyKeyDefaultDataWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 70461ad1de94c984cb41e6b1d46af9e310a928d6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887389"
---
# <a name="safety-stock-fulfillment-for-items"></a>Atendimento de estoque de segurança para itens

[!include [banner](../includes/banner.md)]

O estoque de segurança indica uma quantidade adicional de um item mantido em estoque para reduzir o risco de que o item ficará esgotado. O estoque de segurança é usado como um estoque de reserva se as ordens de venda chegarem e o fornecedor não conseguir entregar os itens adicionais para atender à data de remessa solicitada do cliente. Quando o estoque de segurança for usado para atender a uma ordem de venda, o estoque de segurança será reduzido. Você pode usar o planejamento mestre para trazer automaticamente o estoque de volta ao nível de segurança.

## <a name="set-up-safety-stock-levels-for-items"></a>Configurar níveis de estoque de segurança para os itens

O estoque de segurança é configurado como parte da cobertura do item na página **Cobertura de item** em **Produtos liberados \> Plano \> Cobertura**.

No campo **Minimo**, insira o nível de estoque de segurança que você deseja manter para o item. O valor é expresso em unidades de estoque. Se o campo ficar em branco, o valor padrão será zero. Este campo fica disponível quando você seleciona **Período**, **Necessidade** ou **Mín./máx.** na lista **Código de cobertura**. O limite do nível de estoque é aplicado ao estoque disponível, o que significa que as reservas e as marcações podem disparar o reabastecimento do estoque de segurança antes que a quantidade física fique abaixo do nível do mínimo especificado.

> [!NOTE]
> Você deve definir todas as outras dimensões planejadas de cobertura antes de definir o campo **Mínimo**. Isso evita que um registro inválido seja usado durante o planejamento mestre. Essa situação pode ocorrer se, por exemplo, um grupo de dimensões for estendido com uma dimensão planejada de cobertura adicional para a qual as quantidades mínima e máxima de estoque ainda não estão definidas.

Você pode usar as chaves mínimas para tratar flutuações sazonais na demanda. Por exemplo, você pode diminuir o nível de estoque mínimo de um item na baixa temporada e aumentar gradualmente o nível durante os outros meses. Você cria uma chave mínima indo para **Planejamento mestre \> Configuração \> Cobertura \> Chaves de mínimo/máximo**. Você especifica a chave mínima para ajustar o nível de estoque de segurança por sazonalidade no campo **Chave de mínimo** na página **Cobertura de item**.

## <a name="example-minimum-key"></a>Exemplo: Chave de mínimo

O procedimento a seguir é um exemplo que mostra como configurar uma chave de mínimo que conta para a demanda sazonal crescente durante os meses de primavera e verão.

1. Acesse **Planejamento mestre \> Configuração \> Cobertura \> Chaves de mínimo/máximo**.
1. Selecione **Novo** para criar uma chave de mínimo/máximo.
1. No campo **Chave de mínimo ou máximo**, insira um identificador para a chave. No campo **Nome**, digite um nome para a chave.
1. Defina a opção **Usar a data de efetivação** como *Sim* e deixe o campo **Data de efetivação** em branco para fazer com que a chave seja válida a partir do primeiro dia do ano atual.

    > [!NOTE]
    > A combinação das configurações **Usar a data de efetivação** e a **Data de efetivação** define a data a partir da qual a chave é válida.
    >
    > - Quando a opção **Usar a data de efetivação** é definida como *Não*, a chave é válida a partir da data atual ou da data do sistema.
    > - Quando a opção **Usar a data de efetivação** estiver definida como *Sim*, a chave será válida a partir da data definida no campo **Data da efetivação**.

1. Na seção **Períodos**, crie 12 linhas e defina os valores a seguir para elas:

    - **Alterar** – atribui a cada linha um número exclusivo de 1 a 12. Esse campo indica a alteração incremental na unidade de tempo definida pelo campo **Unidade**.
    - **Unidade** – selecione *Meses* para cada linha.
    - **Data inicial**, **Data final** e **Mês** – esses campos são definidos automaticamente, com base nas configurações de **Alteração** e **Unidade**. Os períodos mensais começam a partir do primeiro dia do ano atual.
    - **Fator** – insira os valores que são descritos na tabela a seguir. Esse campo define o fator pelo qual você deseja multiplicar o estoque mínimo.

        | Linha (Alterar) | Fator | Resultado |
        |---|---|---|
        | 1–3 | 1 | O estoque mínimo se baseia na configuração para Janeiro a Março na página **Cobertura de item**. |
        | 4–5 | 2 | O estoque mínimo é multiplicado pelo fator 2 para os meses de abril a maio. |
        | 6–8 | 2.5 | O estoque mínimo é multiplicado pelo fator 2,5 nos meses de junho a agosto. |
        | 9–12 | 1 | O estoque mínimo é revertido para a configuração para setembro a dezembro na página **Cobertura do item**. |

    Agora, as configurações deverão ser semelhantes às das ilustrações a seguir.

    ![Períodos de chave de mínimo ou máximo.](media/min-max-key-periods.png "Períodos de chave de mínimo ou máximo")

> [!NOTE]
> Você também pode usar um assistente para criar e configurar uma chave de mínimo/máximo. Na página **Chaves de mínimo ou máximo**, no Painel de Ações, selecione **Assistente** para abrir o assistente de **Chaves de Mínimo/Máximo**. O assistente guiará você passo a passo durante o processo de criação e configuração da chave de mínimo/máximo.

Se o código de cobertura for *Mín/Máx*, você poderá especificar a quantidade de estoque máximo que você deseja manter para um item. O valor também é expresso em unidades de estoque. Se o estoque disponível projetado ficar abaixo da quantidade mínima, o planejamento mestre irá gerar uma ordem planejada para atender a todas as necessidades em aberto e fazer o estoque disponível subir até a quantidade máxima especificada. Da mesma forma que configura a quantidade mínima de estoque, você deverá definir todas as outras dimensões de cobertura planejada antes de definir o campo **Máximo**.

## <a name="example-minmax-coverage-code"></a>Exemplo: Código mínimo/máximo de cobertura

A quantidade mínima é 10, a quantidade máxima é 15. O estoque disponível atual é 4. Isso gera um requisito de quantidade mínima de 6. Porém, como a quantidade máxima é 15, o planejamento mestre gera uma ordem planejada de 11 itens.

Para os itens que seguem demandas sazonais, você também precisa manter níveis máximos diferentes. Para fazer isso, é necessário definir **Chaves de máximo** indo para **Planejamento mestre \> Configuração \> Cobertura \> Chaves de mínimo/máximo**. Preencha o campo **Chave máxima** na página **Cobertura de item**. Você pode exibir informações sobre níveis de estoque de segurança, definidos nas chaves mínimas na guia **Mínimo/máximo**, na página **Cobertura de item**. Você precisa ter certeza de que, para um dado período, os valores mínimo e máximo são mantidos na sincronização.

## <a name="safety-stock-fulfillment"></a>Atendimento de estoque de segurança

O parâmetro **Mínimo de preenchimento** permite selecionar a data ou o período durante o qual o nível de estoque deve atender a quantidade especificada no campo **Mínimo**. Este campo fica disponível quando você seleciona **Período**, **Necessidade** ou **Mín./máx.** na lista **Código de cobertura**.

Se **Chaves mínimas** forem usadas, marque a caixa de seleção **Períodos mínimos** para preencher o nível de estoque mínimo para todos os períodos configurados na chave mínima. Se você desmarcar a caixa de seleção, o estoque mínimo será atendido somente para o período atual.

O cenário a seguir mostra como este parâmetro funciona e quais as diferenças entre os valores.

> [!NOTE]
> Para todas as ilustrações deste artigo, o eixo x representa o estoque, o eixo y representa dias, as barras representam o nível de estoque, as setas representam as transações, como linhas de ordem de venda, linhas de ordem de compra ou ordens planejadas.

[![Cenário comum atendimento de estoque de segurança para itens.](media/Scenario1.png)](media/Scenario1.png)

O parâmetro **Fornecimento mínimo** pode ter os seguintes valores:

### <a name="todays-date"></a>Data atual

A quantidade mínima especificada é atendida na data em que o planejamento mestre é executado. O sistema tenta atender ao limite de estoque de segurança o quanto antes, mesmo que isso não seja realista devido ao prazo de entrega.

[![Requisito na data de hoje.](media/TodayReq.png)](media/TodayReq.png)

A ordem planejada P1 é criada para a data de hoje para deixar o estoque disponível acima do nível do estoque de segurança nesta data. As linhas da ordem de venda S1 a S3 continuam diminuindo o nível de estoque. A ordens planejadas P2 a P4 são geradas pelo planejamento mestre, de modo que o nível de estoque seja trazido de volta ao limite de segurança após cada necessidade de ordem de venda.

Quando a cobertura **Necessidade** é usada, são criadas várias ordens planejadas. Sempre é recomendável usar a cobertura do **Período** ou do **Mínimo/máximo** para itens e materiais em demanda frequente para agrupar o reabastecimento. A ilustração a seguir mostra um exemplo do código de cobertura **Período**.

[![Período. Data de hoje.](media/TodayPeriod.png)](media/TodayPeriod.png)

A ilustração a seguir mostra um exemplo do código de cobertura **Mín/Máx**.

[![Mín./Máx. Data de hoje.](media/TodayMinMax.png)](media/TodayMinMax.png)

### <a name="todays-date--procurement-time"></a>Data atual + tempo de compras

A quantidade mínima especificada é atingia na data em que o planejamento mestre é executado, acrescido do prazo de entrega de compra ou produção. Esse prazo inclui quaisquer margens de segurança. Se o item tiver um contrato comercial e a caixa de seleção **Localizar contratos comerciais** estiver marcada na página **Parâmetros de planejamento mestre**, o prazo de entrega do contrato comercial não será considerado. Os prazos de entrega são obtidos das configurações de cobertura do item ou do item.

Esse modo de atendimento criará planos com menos atrasos e menos ordens planejadas, independentemente do grupo de cobertura configurado no item.

A ilustração a seguir mostra o resultado do plano, se o código de cobertura for **Necessidade** ou **Período**.

[![Requisito ou Período. Data de hoje e prazo de entrega.](media/TodayPLTReq.png)](media/TodayPLTReq.png)

A ilustração a seguir mostra o resultado do plano, se o código de cobertura for **Mín/Máx**.

[![Mín./Máx. Data de hoje e prazo de entrega.](media/TodayPLTMinMax.png)](media/TodayPLTMinMax.png)

### <a name="first-issue"></a>Primeira saída

A quantidade mínima especificada é atingida na data em que o estoque disponível fica abaixo do nível mínimo, conforme mostrado na ilustração a seguir. Mesmo que o estoque disponível fique abaixo do nível mínimo na data em que o planejamento mestre for executado, a **Primeira saída** não tentará cobri-la até a próxima exigência.

A ilustração a seguir mostra um exemplo do código de cobertura **Exigência**.

[![Planejamento de um item com o código de cobertura Requisito e o atendimento Primeira saída.](media/FirstIssueReq.png)](media/FirstIssueReq.png)

A ilustração a seguir mostra um exemplo do código de cobertura **Período**.

[![Planejamento de um item com o código de cobertura Período e o atendimento Primeira saída.](media/FirstIssuePeriod.png)](media/FirstIssuePeriod.png)

A ilustração a seguir mostra um exemplo do código de cobertura **Mín/Máx**.

[![Planejamento de um item com o código de cobertura MínMáx e o atendimento Primeira saída.](media/FirstIssueMinMax.png)](media/FirstIssueMinMax.png)

Na data em que o planejamento mestre é executado, se o estoque disponível já estiver sob o limite de estoque de segurança, **Data de hoje** e **Data de hoje + tempo de aquisição** acionarão o reabastecimento imediatamente. **Primeira saída** esperará até que haja outra transação de saída, como requisito de ordem de venda e de linha de BOM e depois acionam o reabastecimento na data dessa transação.

Na data em que o planejamento mestre é executado, se o estoque disponível não estiver no limite de estoque de segurança, **Data de hoje** e **Primeira saída** fornecerão o resultado exatamente igual, conforme mostra a ilustração a seguir.

[![Não está abaixo do limite.](media/ReqFirstIssue.png)](media/ReqFirstIssue.png)

Na data em que o planejamento mestre é executado, se o estoque disponível não estiver no limite do estoque de segurança **Data de hoje + tempo de aquisição** fornecerão o seguinte resultado porque adiam o atendimento até o fim do prazo de entrega da aquisição.

![Atendimento adiado até o final do prazo de entrega da compra.](media/ReqTodayLT.png)

### <a name="coverage-time-fence"></a>Limite de tempo de cobertura

A quantidade mínima especificada é atendida durante o período que é especificado no campo **Limite de tempo de cobertura**. Essa opção é útil quando o planejamento mestre não permite que o estoque disponível seja usado para ordens reais, como vendas ou transferências, na tentativa de manter o nível de segurança. Porém, em uma versão futura, este modo de reabastecimento não será necessário, e essa opção será substituída.

## <a name="plan-safety-stock-replenishment-for-first-expired-first-out-fefo-items"></a>Planejar o reabastecimento do estoque de segurança para itens FEFO (Primeiro a vencer, primeiro a sair)

Em qualquer momento, o recebimento de estoque com a data de vencimento mais recente será usado para o estoque de segurança para permitir demanda real, como linhas de venda ou linhas de BOM, para serem atendidas na ordem FEFO (Primeiro a vencer, primeiro a sair).

Para mostrar como isso funciona, considere o cenário a seguir.

[![Cenário FEFO.](media/FEFOScenario.png)](media/FEFOScenario.png)

Quando o planejamento é executado, ele cobre a primeira ordem de venda do estoque disponível existente e uma ordem de compra adicional para a quantidade restante.

[![FEFO 1.](media/FEFO1.png)](media/FEFO1.png)

Uma ordem planejada é criada para garantir que o estoque disponível retorne ao limite de segurança.

[![FEFO 2.](media/FEFO2.png)](media/FEFO2.png)

Quando a segunda ordem de venda é planejada, a ordem planejada criada anteriormente que cobre o estoque de segurança é usada para cobrir esta quantidade. Portanto, o estoque de segurança está girando constantemente.

[![FEFO 3.](media/FEFO3.png)](media/FEFO3.png)

Por fim, outra ordem planejada é criada para cobrir o estoque de segurança.

[![FEFO 4.](media/FEFO4.png)](media/FEFO4.png)

Todos os lotes vencem adequadamente e as ordens planejadas serão criadas para reabastecer o estoque de segurança depois que ele tiver expirado.

## <a name="how-master-planning-handles-the-safety-stock-constraint"></a>Como o planejamento mestre trata a restrição de estoque de segurança

O estoque de segurança é rastreado no sistema como um tipo de requisito, assim como requisitos de BOM ou de linhas de venda. Você pode ver a linha de requisito de estoque de segurança na página **Requisitos líquidos**, se remover o filtro padrão na coluna **Tipo de requisito**.

O atendimento da transação de requisito de estoque de segurança tem a prioridade cancelada, se o sistema determinar que isso causa atraso no atendimento da demanda real, como linhas de vendas, linhas de BOM, requisitos de transferência ou linhas de previsão de demanda. Caso contrário, certificar-se de que o estoque disponível está acima da quantidade de estoque de segurança tem a mesma prioridade que qualquer outro tipo de demanda. Isso garante que não haverá atrasos para as transações reais e ajuda a evitar reabastecimento excessivo ou antecipado do estoque de segurança.

Durante a fase de cobertura de planejamento mestre, o reabastecimento do estoque de segurança não terá mais a prioridade cancelada. O estoque disponível poderá ser usado antes de qualquer outro tipo de demanda. Durante o cálculo de atraso, uma nova lógica será adicionada para verificar as linhas de vendas em atraso, os requisitos da linha de BOM e todos os outros tipos de demanda para determinar se podem ser enviadas no prazo, considerando que este estoque de segurança será usado. Se o sistema identificar que isso pode minimizar atrasos usando o estoque de segurança, então as linhas de vendas ou as linhas da BOM substituirão a cobertura inicial com o estoque de segurança, e o sistema acionará o reabastecimento do estoque de segurança.

Se plano ou item não for configurado para o cálculo atrasado, então a restrição de estoque de segurança terá a mesma prioridade que outros tipos de demanda. Isso significa que há uma reserva de disponível e de outro estoque disponível antes de outros tipos de demanda.

## <a name="additional-resources"></a>Recursos adicionais

- [Usar o diário de estoque de segurança para atualizar a cobertura mínima para os itens](safety-stock-journal.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
