---
title: Reconhecer receita adiada
description: Este tópico fornece informações sobre como reconhecer a receita usando o recurso Reconhecimento de receita.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8d9b5e1248497ec74e1c7125b2395c0ed4c825c2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820512"
---
# <a name="recognize-deferred-revenue"></a>Reconhecer receita adiada

[!include [banner](../includes/banner.md)]

> [!NOTE]
> O recurso Reconhecimento de receita não pode ser ativado por meio do Gerenciamento de recursos. No momento, você deve usar as chaves de configuração para ativá-lo.

Este tópico descreve o processo de reconhecer a receita na agenda de reconhecimento de receita. Após lançar uma fatura da ordem de venda, uma agenda de reconhecimento de receita é criada para cada linha da ordem de venda contendo uma agenda de receita. A agenda de receita em uma linha é usada para determinar se a receita da linha deve ser adiada.

## <a name="view-revenue-recognition-schedule-details"></a>Exibir detalhes da agenda de reconhecimento de receita

Há duas maneiras de acessar os detalhes da agenda de reconhecimento de receita.

- Você pode abrir a agenda de reconhecimento de receita diretamente de uma ordem de venda faturada. Nesse caso, as informações na agenda de receita são filtradas para mostrar apenas os detalhes da ordem de venda selecionada. Essa abordagem é útil quando estiver validando detalhes da agenda para uma ordem de venda.
- Você pode abrir a agenda de reconhecimento de receita na página **Reconhecimento de receita \> Tarefas periódicas**. Essa abordagem geralmente é usada quando a receita é reconhecida no final de um período. Ao abrir a página pela primeira vez, nenhuma informação é mostrada. Use os filtros anteriores de grade para definir critérios para os detalhes da agenda que devem ser mostrados. Você pode filtrar as datas da fatura inserindo um intervalo de datas, uma ordem de venda, um cliente, uma ID do projeto ou um estado.

[![Ilustração da página Agendas de receita](./media/revenue-recognition-schedule-page.png)](./media/revenue-recognition-schedule-page.png)

A FastTab **Dimensão financeira** abaixo da grade mostra as dimensões financeiras da linha da ordem de venda. As dimensões foram consideradas durante o lançamento da receita diferida. Também são considerados quando a receita é reconhecida. Os valores de dimensão usados dependem da estrutura de conta que é atribuída às contas principais de receita e receita adiada.

## <a name="recognize-revenue"></a>Reconhecer receita

Você reconhece a receita ao executar o processo **Criar diário** da página **Reconhecer receita**. É possível abrir essa página na ordem de venda ou em **Tarefas periódicas**. Se o processo for executado na ordem de venda, a receita é reconhecida somente para a ordem de venda selecionada. Normalmente, o processo é executado em **Tarefas periódicas**, o que permite reconhecer a receita de todas as faturas de ordem de venda.

Para definir os critérios para selecionar e lançar a receita, marque **Criar diário** para abrir a caixa de diálogo **Criar diário**.

[![Crie opções de parâmetros de diário](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

Na caixa de diálogo, use as opções no grupo de campo **Data de processamento** para definir a data de lançamento usada quando a receita é reconhecida. Se você selecionar **Data selecionada**, insira uma data de lançamento no campo **Data da transação**. Se você selecionar **Data da agenda de receita**, a data da transação não será usada. Em vez disso, o valor do campo **Reconhecer data** em cada linha da agenda é usado como a data de lançamento.

Em seguida, no campo **A partir da data**, insira a data de início para o reconhecimento de receitas. As linhas da agenda nas quais a data de reconhecimento for anterior a ou na data de início serão reconhecidas, caso não estejam em espera.

Após concluir a definição de datas, selecione **OK** na caixa de diálogo para criar o diário. Você receberá uma mensagem informativa que mostra o número de transações criadas e o diário em que foram criadas. O diário não será lançado automaticamente. Portanto, o gerente de reconhecimento de receita tem tempo para validar quais linhas da agenda estão sendo reconhecidas.

Depois que o processo é executado, as linhas na agenda que foram transferidas para o diário estarão marcadas como **Processado**. O sinalizador **Processado** indica que as linhas foram transferidas para o diário, mas podem ser lançadas ou não. Depois que o diário de reconhecimento de receita é lançado, o sinalizador **Processado** é mantido. Se o diário de reconhecimento de receita for excluído, ou se uma linha for excluída, o sinalizador **Processado** será removido. Dessa maneira, a linha pode ser reconhecida quando o processo **Criar diário** for executado novamente.

[![Página Agenda de reconhecimento de receita](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Na página **Diário de reconhecimento de receita** (**Reconhecimento de receita \> Entradas de diário \> Diário de reconhecimento de receita**), abra as **Linhas** para exibir os detalhes do que está sendo reconhecido. Uma transação separada é criada sempre para cada linha da agenda que está sendo reconhecida, mesmo que todas as linhas sejam lançadas na mesma data usando as mesmas contas contábeis.

[![Página Comprovante de diário](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

A coluna **Conta** mostra a conta contábil da receita diferida. Essa conta contábil não pode ser editada. Isso ajuda a garantir que a conta contábil da receita adiada correta seja aliviada. Essa conta contábil não é validada na estrutura de conta, pois pode ter sido alterada desde que o lançamento da referida conta contábil de receita ocorreu pela última vez.

A coluna **Contrapartida** mostra a conta contábil da receita. Por padrão, a conta contábil da receita é extraída de perfis de lançamento de estoque e as dimensões financeiras são extraídas da linha da ordem de venda. Essa conta contábil é validada na estrutura de conta atual. Entretanto, poderá ser editada se a estrutura de conta tiver sido alterada, exigindo dimensões financeiras adicionais.

O valor padrão é da linha correspondente à agenda e não pode ser alterado.

Por padrão, se a ordem de venda for uma ordem de venda em várias moedas, a taxa de câmbio será definida como a taxa de câmbio da fatura. Esse comportamento ajuda a garantir que os valores de moeda contábil e de moeda de relatório sejam aliviados integralmente. Devido ao arredondamento, a taxa de câmbio da última linha da agenda pode diferir ligeiramente da taxa na fatura.

Depois que o diário de reconhecimento de receita é lançado, o comprovante será inserido na agenda. Se houver mais de um comprovante para a mesma linha da agenda, um asterisco (\*) aparece na linha. Para exibir os comprovantes que foram lançados para essa linha, selecione **Transações de comprovante**.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Modifique os detalhes da agenda de reconhecimento de receita

A maioria dos dados nos detalhes da agenda de receita não pode ser editada. As novas linhas não podem ser adicionadas à agenda, e as linhas existentes não podem ser excluídas. Os detalhes da agenda de receita para cada linha da ordem de venda devem ser mantidos para ajudar a garantir que, ao longo do tempo, uma organização reconheça o mesmo valor adiado.

### <a name="edit-schedule-lines"></a>Editar linhas da agenda

Algumas edições são permitidas nas linhas da agenda. Os seguintes campos podem ser alterados nas linhas:

- **Em espera** — Esse sinalizador pode ser definido ou removido para que a linha seja processada. Para remover o sinalizador, selecione a linha, **Remover bloqueio**. A receita não pode ser reconhecida nas linhas que estão em espera. As linhas podem ser automaticamente colocadas em espera se a agenda da receita for configurada para bloqueios automáticos.

    [![Agendas de receita — editar linhas da agenda](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Data de reconhecimento** — A data de reconhecimento pode ser alterada antes que a linha seja processada. Ao executar o processo que cria o diário para reconhecer receitas, uma data é inserida no campo **Reconhecer receita a partir da data**. Essa data é comparada à data no campo **Data de reconhecimento** para determinar quais linhas devem ser reconhecidas.
- **Valor a ser liberado** — O valor que será liberado pode ser alterado antes que a linha seja processada. Você pode diminuir o valor da receita que foi reconhecida, mas não pode aumentá-lo. Esse campo permite que uma organização reconheça a parte da receita na data de reconhecimento. Se o valor for alterado, o valor no campo **Valor restante** mostra quantas receitas ainda devem ainda ser reconhecidas.
- **Quantidade a ser liberada** — Se a agenda de receita estiver configurada para uma ocorrência ou um mês, o campo **Quantidade a ser liberada** mostra a quantidade da linha da ordem de venda. Esse campo também pode ser editado e fornece outra maneira de reconhecer parte da receita. Por exemplo, se a quantidade na linha for 5, você poderá substituir a quantidade, de forma que seja menor que 5. O valor no campo **Valor a ser liberado** é atualizado proporcionalmente.

### <a name="update-contract-terms"></a>Atualizar termos de contrato

Os detalhes da agenda de receita são criados com base na agenda de receita atribuída à linha da ordem de venda quando a fatura é lançada. Se a agenda de receita na linha da ordem de venda estiver incorreta, ela não poderá ser alterada na ordem de venda após esta ter sido faturada. Em vez disso, use o botão **Atualizar termos de contrato** para alterar a agenda de receita. A agenda de receita pode ser alterada antes ou depois que a receita for reconhecida.

Para alterar a agenda, selecione qualquer linha da agenda para o item que você está alterando. Nesta ilustração, a linha do item S0008 lançado usando uma agenda de receita de 12 meses está selecionada. Quando você selecionar **Atualizar termos de contrato**, uma caixa de diálogo exibe as datas de início e término de contrato e a agenda de receita.

[![Datas de início e término do contrato](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Altere as datas de início e término de contrato para que reflitam o intervalo de datas atual. Ao alterar o intervalo de datas, o valor no campo **Número de ocorrências** deve corresponder uma agenda de receita definida no sistema. Neste exemplo, como o contrato foi alterado para um contrato de 24 meses, uma agenda de receita de 24 meses deve ser definida. Como existe uma agenda de receita de 24 meses, ela é inserida por padrão e o contrato pode ser alterado. Se não existir uma agenda de receita com um número de ocorrências correspondente, o contrato não poderá ser alterado. Depois de concluir a atualização dos termos de contrato e a agenda de receita conforme o necessário, selecione **OK** na caixa de diálogo para salvar as alterações.

[![Intervalo de datas do contrato atualizado](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

As alterações de contrato têm os seguintes efeitos nos detalhes da agenda de receita:

- Se nenhuma receita for reconhecida para o produto, os detalhes da agenda anterior serão removidos e substituídos pelos novos detalhes da agenda de receita. Por exemplo, o item S0008 tinha originalmente 12 linhas nos detalhes da agenda. As 12 linhas são removidas e substituídas por 24 linhas, com base na nova agenda de receita.
- Se a receita tiver sido reconhecida para o produto, algumas receitas terão sido reconhecidas incorretamente, pois o reconhecimento se baseava na agenda de receita incorreta. Essas linhas devem ser revertidas e reconhecidas novamente, com base na nova agenda. Nesse cenário, as novas linhas da agenda de receita são criadas com valores negativos na data de reconhecimento original. Em seguida, novas linhas são criadas para reconhecer os valores com base na nova agenda de receita. Por exemplo, em 8 de agosto de 2019 você reconheceu a receita de US$ 10,53. Em 8 de setembro de 2019 você reconheceu a receita de US$ 13,16. Portanto, duas novas linhas são criadas nas mesmas datas. Uma linha é para -US$ 10,53 e a outra é para -US$ 13,16. São criadas 24 linhas novas e a receita diferida total de US$ 160,61 é alocada nelas. Você pode lançar linhas do estorno ao executar o processo **Criar diário** .

[![Agenda de reconhecimento de receita](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]