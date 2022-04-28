---
title: Agendas de adiamentos em adiamentos de receita e despesa
description: Este tópico descreve agendas de adiamentos em adiamentos de receita e despesa.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 953347500f83a4a16f43331b572d2029027a5f59
ms.sourcegitcommit: d0e99545d722c924db57ae2bd06f72154a1f1f97
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2022
ms.locfileid: "8558081"
---
# <a name="deferral-schedules"></a>Agendas de adiamento

As agendas de adiamento são criadas depois que uma transação é lançada.

Você pode usar a página **Todas as agendas de adiamento** ou **Agendas de adiamento ativas** para revisar os detalhes sobre uma agenda de adiamento. As informações exibidas dependem do tipo de agenda de adiamento (linear ou baseada em evento) e do tipo de transação. Inclui as linhas da agenda de adiamento e os valores totais para a agenda de adiamento. Você pode usar a página para modificar a agenda de adiamento.

## <a name="recognize-revenue"></a>Reconhecer receita

> [!NOTE]
> - Para reconhecer a receita de uma agenda de adiamento, comece na etapa 1.
> - Para reconhecer a receita de vários adiamentos, comece na etapa 2.

1. Na página **Todas as agendas de adiamento**, na grade **Linhas da agenda**, selecione as linhas que deseja reconhecer e selecione **Reconhecer**.
2. Na página **Processamento de reconhecimento**, defina o campo **Ação de reconhecimento** como **Criar diário de reconhecimento**.
3. No campo **Data de fechamento**, selecione a data de fechamento. O processamento só incluirá as linhas em que a data final é anterior ou igual à data de fechamento selecionada.
4. Selecione **Filtrar** e adicione filtros de dados para que a lista mostre somente o intervalo de registros desejado.
5. Selecione **Exibir pré-visualização** para exibir as linhas.
6. Na lista de linhas, selecione as linhas que não deseja processar e, em seguida, selecione **Remover**.
7. Selecione se deseja resumir a entrada de diário de reconhecimento.
8. Na seção **Data da transação** você pode substituir a data da transação por uma data específica para processar a transação. A data da transação pode ser especificada para períodos fechados.
9. Para executar o processamento como parte de um lote, selecione **Lote**. Na caixa de diálogo **Processamento em lote** defina os parâmetros do lote e, em seguida, selecione **OK** para voltar à página **Processamento de reconhecimento**. O reconhecimento de receita será processado posteriormente, quando o lote for processado.
10. Selecione **Processar**. Se você não adicionou a transação a um lote, todas as linhas serão processadas imediatamente. Caso contrário, as linhas serão processadas quando o lote for processado.

## <a name="modify-a-schedule"></a>Modificar uma agenda

Para modificar uma agenda de adiamento, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Contabilidade \> Modificar agenda**.
2. Na página **Modificar agenda** edite as opções que deseja alterar. Dependendo da agenda de adiamento, você não poderá editar todas as opções.
3. Selecione **Visualizar** para revisar as alterações na agenda de adiamento.
4. Selecione **OK**.

### <a name="straight-line-deferral-schedules"></a>Agendas de adiamento linear

Se a agenda de adiamento não tiver linhas reconhecidas ou lançadas externamente, você poderá modificar toda a agenda de adiamento, incluindo a data de início.

Se a agenda de adiamento tiver linhas reconhecidas ou externas, e você modificar a agenda de adiamento, o comportamento resultante da agenda de adiamento dependerá da data de recálculo e da data final de adiamento das linhas reconhecidas. Por padrão, o primeiro período que não foi reconhecido determina a data final de adiamento.

Para usar a data de reconhecimento, selecione um dos seguintes valores no campo **Início da agenda**: 
- **Acumulado** – o valor depois que todas as linhas reconhecidas são recalculadas.
- **Estorno** – todas as linhas depois da data de recálculo são revertidas usando o nome de diário e a data de lançamento especificados. O valor depois da data de recálculo é então recalculado.

Se um modelo for usado, os períodos ignorados serão ignorados e o modelo será usado apenas para calcular a data de término.

### <a name="event-based-deferral-schedules"></a>Agendas de adiamento com base em eventos

Para uma agenda de adiamento baseada em evento, você pode modificar todas as linhas não reconhecidas.

Se a agenda de adiamento tiver linhas reconhecidas ou lançadas externamente, você não poderá modificar o modelo e o tipo de alocação da agenda de adiamento. Quando você modifica uma agenda de adiamento existente, não é possível alterar o valor do campo **Criar eventos separados por unidade**.

Se uma linha for reconhecida ou lançada externamente, a caixa de seleção **Reconhecida** é selecionada.

## <a name="modify-a-deferral-or-recognition-account"></a>Modificar uma conta de adiamento ou de reconhecimento

Para modificar a conta de adiamento ou de reconhecimento para uma agenda de adiamento, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Contabilidade \> Modificar conta**.
2. Na página **Modificar Conta**, selecione a conta que você deseja alterar (adiamento, curto prazo ou reconhecimento).
3. No campo **Nova conta**, selecione a nova conta.
4. Selecione se as alterações na conta criarão entradas do diário de ajuste.
5. Se você definir a opção como **Sim** na etapa anterior, selecione o nome do diário no campo **Nome do diário** e especifique a data da transação no campo **Data da transação**.
6. Selecione **OK**.

## <a name="put-a-deferral-schedule-on-hold"></a>Colocar uma agenda de adiamento em espera

Para colocar uma agenda de adiamento em espera, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Espera \> Colocar em espera**.
2. Na página **Colocar em espera**, selecione se deseja transferir o saldo da conta de adiamento ou da conta em espera.
3. Se você optou por transferir o saldo, selecione o nome do diário no campo **Nome do diário**, selecione a conta em espera no campo **Conta em espera** e especifique a data da transação no campo **Data da transação**.
4. Selecione **OK**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Remover uma espera de uma agenda de adiamento

Para remover uma agenda de adiamento de uma espera, siga estas etapas.

1. Na lista **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Espera \> Remover espera**.
2. No campo **Nome do diário**, selecione o nome do diário.
3. No campo **Data da transação**, especifique a data da transação.
4. Selecione **OK**.

## <a name="cancel-unrecognized-amounts"></a>Cancelar valores não reconhecidos

> [!NOTE]
> Qualquer linha que já tenha sido reconhecida ou lançada externamente será excluída desse processo.

Para cancelar valores não reconhecidos em uma agenda de adiamento, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Cancelar \> Valores não reconhecidos**.
2. Na página **Cancelar valor não reconhecido**, selecione se quer criar entradas de cancelamento.
3. Se você optou por criar entradas de cancelamento, selecione o nome do diário no campo **Nome do diário**, selecione a conta de cancelamento no campo **Conta de cancelamento** e especifique a data da transação no campo **Data da transação**.
4. Selecione **OK**.

## <a name="cancel-a-completed-schedule"></a>Cancelar uma agenda concluída

Use a página **Todas as agendas de adiamento** para reverter os valores reconhecidos ou publicados externamente e cancelar a agenda de adiamento para evitar o reconhecimento.

Para cancelar toda uma agenda de adiamento, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento e depois **Cancelar \> Concluir agenda**.
2. Na página **Cancelar agenda concluída**, selecione se quer criar entradas de cancelamento.
3. Se você optou por criar entradas de cancelamento, selecione o nome do diário no campo **Nome do diário**, selecione a conta no campo **Conta de cancelamento** e especifique a data da transação no campo **Data da transação**.
4. Selecione **OK**.

## <a name="reverse-transactions"></a>Reverter transações

> [!NOTE]
> - Para reverter o reconhecimento da receita de uma agenda de adiamento, comece na etapa 1.
> - Para reverter o reconhecimento da receita para várias agendas, comece na etapa 2.

1. Na página **Todas as agendas de adiamento**, na grade **Linhas da agenda**, selecione as linhas que deseja parar de reconhecer e selecione **Reverter**.
2. Na página **Processamento de reconhecimento**, defina o campo **Ação de reconhecimento** como **Reverter diário de reconhecimento**.
3. No campo **Data de fechamento**, selecione a data de fechamento. O processamento só incluirá as linhas em que a data de término é anterior ou igual à data de fechamento especificada.
4. Selecione **Filtrar** e adicione filtros de dados para que a lista mostre somente o intervalo de registros desejado.
5. Selecione **Exibir pré-visualização** para exibir as linhas.
6. Na lista de linhas, selecione as linhas que não deseja processar e, em seguida, selecione **Remover**.
7. Os campos **Nome** e **Descrição** são atualizados automaticamente com o nome e a descrição do diário padrão. Você pode alterar os valores, conforme desejado. Você também pode selecionar se deseja resumir a entrada de diário de reconhecimento.
8. Na seção **Data da transação** você pode substituir a data da transação por uma data específica para processar a transação. A data da transação pode ser especificada para períodos fechados.
9. Para executar o processamento como parte de um lote, selecione **Lote**. Na caixa de diálogo **Processamento em lote** defina os parâmetros do lote e, em seguida, selecione **OK** para voltar à página **Processamento de reconhecimento**. A reversão do reconhecimento de receita será processada posteriormente, quando o lote for processado.
10. Selecione **OK**. Se você não adicionou a transação a um lote, todas as linhas serão processadas imediatamente. Caso contrário, as linhas serão processadas quando o lote for processado.

## <a name="apply-or-unapply-a-credit-note"></a>Aplicar ou cancelar a aplicação de uma nota de crédito

Para aplicar uma nota de crédito, siga estas etapas.

> [!NOTE]
> Quando você cria uma nota de crédito na página **Adiamento da transação da ordem de venda** e define a opção **Ajustar agenda existente** como **Sim**, a nota de crédito é automaticamente aplicada a agenda quando a nota de crédito for lançada.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento.
2. Na lista **Criar ajustes**, selecione uma linha e depois **Aplicar**.
3. Na página **Aplicar nota de crédito (adiamentos)**, especifique a data de recálculo no campo **Data de recálculo** e a data de término no campo **Data de término**.
4. Na lista **Cabeçalho**, selecione a **Ordem de venda** que tem notas de crédito.
5. Na lista **Linhas**, selecione a linha.
6. Selecione **OK**.
7. Selecione **Sim**.

> [!NOTE]
> Para aplicar uma nota de crédito a vários itens individuais de faturas diferentes, você deve repetir essas etapas.

Para cancelar a aplicação de uma nota de crédito, siga estas etapas.

1. Na página **Todas as agendas de adiamento**, selecione a agenda de adiamento.
2. Na lista **Criar ajustes**, selecione a fatura e depois **Cancelar aplicação**.
3. Selecione **Sim**.

## <a name="fields"></a>Campos

A página **Todas as agendas de adiamento** contém os campos a seguir.

| Campos | Descrição |
|--------|-------------|
| **Cabeçalho** | |
| **Agendar** | |
| Tipo de alocação | O tipo de alocação, para adiamentos com base em eventos: **Porcentagem** ou **Valor**. |
| Data de reclassificação | <p>A data mais recente na qual a reclassificação de curto prazo para uma agenda de adiamento foi processada. Essa data é atualizada toda vez que a **Reclassificação do evento de curto prazo** é usada para a agenda de adiamento.</p>Este campo está disponível apenas quando o método de adiamento de períodos anteriores ou de curto prazo de ano fixo é usado. |
| **Conta** | |
| Conta de adiamento | A conta usada para o valor de adiamento. |
| Conta de reconhecimento | A conta usada para o valor de reconhecimento. |
| Tipo de reconhecimento | O tipo de reconhecimento. |
| Tipo de distribuição | O tipo de distribuição. |
| **Transação** | |
| Origem da criação | A origem na qual a transação foi criada. |
| Tipo de transação | O tipo de transação. |
| Ordem de venda | O número da ordem de venda. |
| Fatura | O número da fatura. |
| Item | O número do item. |
| **Agenda de cobrança** | |
| Número de agenda de cobrança | O número da agenda de cobrança correspondente. |
| Status da linha de cobrança | O status do item de linha da agenda de cobrança correspondente. |
| Referências externas | Informações sobre referências externas da agenda de cobrança: **Externa** e **Número da linha**. |
| Totais | <p>Valores totais da agenda de adiamento:</p><ul><li>**Longo prazo** – a soma dos valores adiados a longo prazo. Esse valor está disponível somente quando o campo **Método de adiamento de curto prazo** está definido como **Nenhum** na página **Parâmetros de adiamentos de receita e despesa**, ou o valor de curto prazo é maior do que 0 (zero).</li><li>**Curto prazo** – a soma dos valores adiados a curto prazo. Esse valor está disponível somente quando o campo **Método de adiamento de curto prazo** está definido como **Nenhum** na página **Parâmetros de adiamentos de receita e despesa**, ou o valor de curto prazo é maior do que 0 (zero).</li><li>**Não reconhecidos** – a soma de valores não reconhecidos de todas as linhas.</li><li>**Esboçado** – a soma de valores publicados externamente para todas as linhas.</li><li>**Reconhecidos** – a soma de valores reconhecidos de todas as linhas.</li><li>**Lançados externamente e reconhecidos** – a soma de valores enviados externamente e reconhecidos de todas as linhas.</li><li>**Valor total** – a soma de valores de todas as linhas.</li></ul> |
| **Linhas de agenda** | |
| Linha | O número de sequência da linha. |
| Data inicial de adiamento | A data de início da agenda de adiamento. |
| Data final de adiamento | A data de término da agenda de adiamento. |
| Valor | O valor do adiamento. |
| Lançado externamente | Um valor que indica se a linha foi publicada externamente. |
| Reconhecido | Um valor que indica se a linha foi reconhecida. |
| Número do lote do diário | O número de lote no qual o valor foi reconhecido. |
| Descrição do Evento | Uma descrição do evento. Este campo está disponível somente para agendas de adiamento com base em eventos. |
| **Ajustes de crédito** | |
| Fatura | <p>O número da fatura.</p><p>O valor indica a fatura do ajuste da nota de crédito que já foi aplicada à agenda de adiamento.</p> |
| Valor aplicado | O valor de ajuste de crédito que já foi aplicado à agenda de adiamento. |
| Data da aplicação | A data em que o ajuste de crédito foi aplicado. |
| **Ajuste** | Os valores de ajuste só aparecerão se um memorando de crédito tiver sido processado para a agenda de adiamento. Se nenhuma nota de crédito tiver sido processada, esses valores serão ocultos. |
| Valor do ajuste | O valor total do ajuste, calculado como *Valor original* – *Valor da agenda*. |
| Data de término original | A data de término original da agenda de adiamento. |
| Valor da agenda original | O total da agenda de adiamento original. |
