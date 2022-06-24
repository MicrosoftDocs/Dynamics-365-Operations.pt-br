---
title: Tarefas periódicas na cobrança de contrato recorrente
description: Este artigo descreve as tarefas periódicas que estão disponíveis em Cobrança de contrato recorrente.
author: JodiChristiansen
ms.date: 04/29/2022
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
ms.openlocfilehash: d834d1d7aa34448b4ef21606974538eb294b5d7d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904778"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Tarefas periódicas na cobrança de contrato recorrente

Este artigo descreve as tarefas periódicas que estão disponíveis em Cobrança de contrato recorrente.

## <a name="generate-invoice"></a>Gerar fatura

Use a página **Gerar faturas** para criar faturas recorrentes mensais em massa usando as informações que você configurou nas páginas **Todas as agendas de cobrança** e **Exibir detalhe de cobrança**. Quando uma fatura é criada, a descrição do item para a linha de processamento do pedido de venda é atualizada com a descrição do item e as datas de início e término da cobrança para a linha de agenda cobrada.

## <a name="generate-invoice-batch-processing"></a>Gerar processamento em lotes de fatura

Use a página **Gerar processamento em lote de faturas** para criar faturas recorrentes por meio de um processo em lote recorrente. Os parâmetros disponíveis são os mesmos da página **Gerar faturas**, mas podem ser salvos em um processo em lote que pode ser executado várias vezes.

## <a name="price-update"></a>Atualização de preço

Use o utilitário de atualização de preço para atualizar os preços de vários itens em várias agendas de cobrança em uma única ação. Os preços podem ser atualizados com base em uma porcentagem especificada ou em um valor especificado. A lista de linhas mostra apenas os preços unitários atuais dos itens. Não mostra os preços após a atualização de preços.

Observe os seguintes pontos sobre o utilitário de atualização de preço:

- Se o pedido de venda para um ano específico já foi criado (ou seja, os itens foram cobrados), o preço dos itens de linha não é afetado.
- O utilitário Atualização de preço pode ser usado para itens de linha com status **Ativo** ou **Em espera**. Para itens que estão em espera, a opção **Ajustar agenda** deve ter sido definida como **Não** quando a retenção foi feita.
- O utilitário de atualização de preço não pode ser usado para itens de linha que são itens de uso e utilizam escalonamento, cobrança por etapa ou divisão de receita.

### <a name="price-update-example"></a>Exemplo de atualização de preço

Uma agenda de cobrança é criada e um item de renovação é adicionado. O preço unitário é de U$ 750. O primeiro ano do item é pago em 15 de dezembro de 2021. A agenda de cobrança é criada para o período de 1º de janeiro até 31 de dezembro de 2022.

No momento da renovação, o processo **Gerar fatura** cria o pedido de venda para o ano de 2022. Após a execução do utilitário de atualização de preço, o preço é atualizado de US$ 750 para US$ 800.

O pedido de venda e a agenda de cobrança de 2022 não são afetados e o preço unitário permanece U$ 750, porque a agenda de cobrança de 2022 já foi cobrada. A linha de agenda de cobrança e os detalhes da linha para 2023 são atualizados para US$ 800, porque a agenda de cobrança para 2023 ainda não foi cobrada.

### <a name="update-prices--flat-pricing-method"></a>Atualizar preços – Método de precificação simples

Ao atualizar os preços de itens que usam o método de precificação simples, você pode especificar uma porcentagem ou valor para aumentar o preço.

Para executar o utilitário de atualização de preços para itens que usam o método de precificação simples, siga estas etapas.

1. Na página de utilitário de **Atualização de preço**, selecione o método de precificação **Simples**.
2. No campo **Método de aumento**, selecione o método de aumento usado para atualizar o preço dos itens.
3. Dependendo do método de aumento selecionado, especifique a porcentagem no campo **Porcentagem** ou o valor no campo **Valor**.
4. Na guia rápida **Registros a serem incluídos**, use o botão **Filtro** para adicionar filtros de dados.
5. Selecione **Exibir versão preliminar** para exibir o intervalo de registros.
6. Se você não quiser processar algumas das linhas, marque-as e selecione **Remover**.
7. Selecione **OK**.

### <a name="update-prices--standard-pricing-method"></a>Atualizar preços – Método de precificação padrão

Se o preço de um item tiver sido alterado no registro do item, ele poderá ser atualizado para todas as linhas de agenda de cobrança se o item usar o método de precificação padrão.

1. Na página de utilitário de **Atualização de preço**, selecione o método de precificação **Padrão**.
2. Na guia rápida **Registros a serem incluídos**, use o botão **Filtro** para adicionar filtros de dados.
3. Selecione **Exibir versão preliminar** para exibir o intervalo de registros.
4. Se você não quiser processar algumas das linhas, marque-as e selecione **Remover**.
5. Selecione **OK**.

## <a name="mass-hold-processing"></a>Processamento de bloqueio em massa

Use a página **Espera em massa** para aplicar opções de retenção a várias agendas de cobrança ao mesmo tempo.

Para colocar apenas uma agenda de cobrança ou uma linha de agenda de cobrança em espera, abra a página **Todas as agendas de cobrança** e selecione **Colocar em espera**. Para remover uma espera, use a página **Remover bloqueio**.

### <a name="put-billing-schedules-on-hold"></a>Colocar agendas de cobrança em espera

Para colocar várias agendas de cobrança em espera, siga estas etapas.

1. Na página **Bloqueio em massa**, defina o campo **Opção de processo** como **Aplicar espera**.
2. No campo **Código da razão**, selecione um código de motivo.
3. Defina a opção **Ajustar agenda**:

    - **Sim** – Se você definir a opção como **Sim**, especifique uma data de espera no campo **Data de espera**. Quaisquer linhas de agenda de cobrança após a data de retenção são removidas.
    - **Não** – As linhas de agenda de cobrança não são alteradas. Somente o status é alterado. É atualizado para **Em espera**.

4. Na guia rápida **Registros a serem incluídos**, use o botão **Filtro** para adicionar filtros de dados.
5. Selecione **Exibir versão preliminar** para exibir o intervalo de registros.
6. Se você não quiser processar algumas das linhas, marque-as e selecione **Remover**.
7. Selecione **OK**.

Ao retornar à lista de agendas de cobrança, você deverá ver que o status das agendas de cobrança foi alterado para **Em espera**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Remover uma espera de várias agendas de cobrança

1. Na página **Bloqueio em massa**, defina o campo **Opção de processo** como **Remover bloqueio**.
2. No campo **Código da razão**, insira um código de motivo.
3. No campo **Remover data**, selecione a data em que a espera deve ser removida.
4. Defina os campos **Data de retomada** e **Data de adiamento** conforme necessário. A data de adiamento é adicionada a todas as linhas que são adiáveis.
5. Na guia rápida **Registros a serem incluídos**, use o botão **Filtro** para adicionar filtros de dados.
6. Selecione **Exibir versão preliminar** para exibir o intervalo de registros.
7. Se você não quiser processar algumas das linhas, marque-as e selecione **Remover**.
8. Selecione **OK**.

> [!NOTE]
> Para remover uma espera, você deve definir o valor **Substituição de grupo de usuários de remoção de bloqueio** na página **Parâmetros de cobrança de contrato recorrentes**.

Por exemplo, uma linha de cobrança tem uma data de início em 1º de fevereiro de 2022 e uma data de término em 28 de fevereiro de 2022. O valor de cobrança é US$ 200. O campo **Data de espera** está definido para 10 de fevereiro de 2022. Portanto, o período de fevereiro é ajustado para excluir qualquer data após 10 de fevereiro. O novo período é de 1º de fevereiro a 9 de fevereiro e o valor é de US$ 64,29 (por rateio diário). Todas as linhas de agenda de cobrança em ou após 10 de fevereiro são removidas.

Se o processo **Remover bloqueio** for concluído e o campo **Remover data** estiver definido para 10 de fevereiro de 2022, haverá dois períodos de cobrança. O primeiro período de cobrança é de 1º a 9 de fevereiro e o valor é de US$ 64,29. O segundo período de cobrança é de 10 a 28 de fevereiro e o valor é de US$ 135,71.

## <a name="mass-termination-processing"></a>Processamento de finalização em massa

Use a página **Encerramento em massa** para encerrar as linhas de agenda de cobrança que são exibidas no momento especificando uma data de encerramento.

Se você estiver usando diferimentos de receitas e despesas, as agendas de cobrança em que o campo **Data de encerramento** estiver definido como **Ajustar agenda** na página **Todas as agendas de cobrança** estarão qualificadas para reembolso.

As agendas de cobrança que usam a alocação de vários elementos (MEA) não aparecem na página **Encerramento em massa**. Você ainda pode encerrar uma agenda de cobrança individual usando a funcionalidade de encerramento na agenda de cobrança.

> [!NOTE]
> As linhas de agenda de cobrança que estão atualmente incluídas em um lote **Gerar fatura** não estão disponíveis para este processo.

Para obter informações sobre cada campo e o processo, consulte [Encerrar agendas de cobrança](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Processo de arquivamento em massa

Use a página **Arquivo em massa** para arquivar várias agendas de cobrança. Somente agendas de cobrança encerrados podem ser arquivados.

Após o arquivamento de uma agenda de cobrança, ocorrem os seguintes eventos:

- O estado é alterado para **Arquivado**.
- As agendas de cobrança estão permanentemente bloqueadas.
- As linhas de agenda de cobrança não estão mais disponíveis nas páginas de consulta.

> [!NOTE]
> O arquivamento de uma agenda de cobrança é uma ação permanente e não pode ser revertida.

Para arquivar agendas de cobrança, siga estas etapas.

1. Na página **Arquivo em massa**, no campo **Data de término da cobrança**, especifique uma data de término de cobrança. Para exibir todas as agendas de cobrança encerradas, deixe este campo em branco.
2. Na guia rápida **Registros a serem incluídos**, use o botão **Filtro** para limitar os registros que são mostrados.
3. Selecione **Exibir versão preliminar**.
4. Se você não quiser arquivar alguns dos registros, marque-os e selecione **Remover**.
5. Selecione **OK** para arquivar os registros na página.

## <a name="mass-stubbing-process"></a>Processo de fragmentação em massa

Use a página **Esboço em massa** para marcar todas as linhas de agenda de cobrança selecionadas como cobradas (esboço) ou não cobradas (esboço reverso). O esboço ou o esboço reverso são executados com mais frequência em linhas de agenda de cobrança importadas que foram cobradas anteriormente em outro sistema. As linhas de agenda de cobrança com esboço aparecem como esboço e não criam uma fatura para o cliente.

### <a name="stub-records"></a>Registros de esboço

1. Na página **Esboço em massa**, no campo **Opções de Processo**, selecione **Esboço**.
2. No campo **Data de fechamento**, defina uma data limite para especificar as linhas às quais você deseja aplicar o processo. Serão exibidos apenas os registros em que a data de início da cobrança for igual ou anterior à data de fechamento especificada.
3. Selecione **Exibir versão preliminar** para mostrar as linhas que você deseja esboçar.
4. Para excluir uma linha do processo, marque-a e selecione **Remover**.
5. Selecione **Processo** para esboçar s linhas.

### <a name="reverse-stub-records"></a>Registros de esboço reverso

1. Na página **Esboço em massa**, no campo **Opções de Processo**, selecione **Esboço reverso**.
2. No campo **Data de fechamento**, defina uma data limite para especificar as linhas às quais você deseja aplicar o processo. Serão exibidos apenas os registros em que a data de início da cobrança for igual ou anterior à data de fechamento especificada.
3. Selecione **Exibir versão preliminar** para mostrar as linhas a que você deseja aplicar esboço reverso.
4. Para excluir uma linha do processo, marque-a e selecione **Remover**.
5. Selecione **Processo** para criar um esboço reverso das linhas.

## <a name="update-completion-date-process"></a>Atualizar processo de data de conclusão

Use a página **Atualizar data de conclusão** para atualizar a data de conclusão de itens de etapa específicos para várias agendas de cobrança ou usuários. Você também pode atualizar a porcentagem de conclusão de itens em modelos de etapa que usam o método **Porcentagem concluída**.

1. Na página **Atualizar data de conclusão**, vá até **Processamento de etapas** e selecione **Atualizar porcentagem de conclusão**.
2. No campo **Valor percentual**, insira a porcentagem total que foi concluída.
3. Selecione o número do item relacionado ao modelo de etapa.
4. Na guia rápida **Registros a serem incluídos**, selecione **Filtro** para selecionar um valor específico **Conta de usuário final**, **Número de agenda de cobrança** ou **Números de item** como critério de filtro.
5. Selecione **Ok** para processar a mudança. Quando o processamento é concluído, uma nova linha é adicionada à alocação de etapa. Esta linha representa a porcentagem que foi concluída para o modelo de etapa.

## <a name="unbilled-revenue-mass-processing"></a>Processamento em massa de receita não faturada

Use a página **Processamento em massa de receita não cobrada** para criar a entrada de diário de receita não cobrada ou esboçar a entrada de diário para uma ou mais agendas de cobrança ou linhas de detalhes de cobrança selecionadas.

- **Criar entrada de diário** – Crie entradas de diário de receita não cobrada para várias linhas de agenda de cobrança. Use o botão **Filtro** na guia rápida **Registros a serem incluídos** para selecionar o intervalo de registros que aparecem na lista. A lista mostra apenas as linhas de agenda de cobrança para as quais as entradas de diário não cobradas não foram criadas. As entradas de diário iniciais são criadas. Para itens de adiamento, as agendas de adiamento também são criadas.
- **Entrada de diário de esboço** – Marque as linhas de agenda de cobrança para as quais as entradas de diário não cobradas já foram criadas. Esta opção é usada se a entrada de diário não cobrada já foi lançada em outro sistema. Ela marca o diário de receita não cobrada como esboço e não lança uma transação na contabilidade.
- **Entrada de diário de esboço reverso** – Entradas de diário de esboço reverso que foram processadas. Se um erro foi cometido durante o processamento de **Entrada de diário de esboço**, esta opção desmarcará a caixa de seleção **Esboçado** para a linha de agenda de cobrança.
- **Linha de detalhes de cobrança de esboço** – Use este processo quando a receita não cobrada foi processada em um sistema externo e algumas das linhas de detalhe de cobrança já foram cobradas. Esse processo garantirá que o valor correto apareça nas contas de receita não cobrada.
- **Linha de detalhes de cobrança de esboço reverso** – Reverta quaisquer ações **Linha de detalhes de cobrança de esboço**.

O campo **Nome do diário** é usado para lançar **Criar entrada de diário** na contabilidade.

> [!NOTE]
> O processo de esboço não lança valores na contabilidade. O campo **Nome do diário** não está disponível para todos os processos de esboço e esboço reverso.

### <a name="unbilled-revenue-stub-example"></a>Exemplo de esboço de receita não cobrada

Uma agenda de cobrança é configurada para um ano, de outubro de 2021 a setembro de 2022. A receita não cobrada já foi processada em um sistema externo. Nove meses da agenda de cobrança já foram cobrados. O valor para cada período de cobrança é de US$ 250. No início do ano, o valor total lançado na receita não cobrada é de US$ 3.000. Após nove meses, US$ 2.250 já foram cobrados e US$ 750 em receita não cobrada permanecem.

Para configurar a agenda de cobrança onde restam apenas três meses de receita não cobrada, siga estas etapas.

1. Na página **Exibir detalhe de cobrança**, crie uma agenda de cobrança para o período de outubro de 2021 a setembro de 2022, número do item S0001 e um valor de US$ 250 por mês.
2. Selecione **Criar entrada de diário** para a agenda de cobrança. O valor de U$ 3.000 é lançado na receita não cobrada.
3. Selecione **Linha de detalhes de cobrança de esboço** e especifique uma data de transação de junho de 2022 (nove meses). As linhas de agenda de cobrança não aparecerão na versão preliminar. As linhas afetadas são baseadas na data da transação.
4. Selecione **OK**.

Os primeiros nove meses que foram cobrados são esboços.

[![Visualize o esboço das linhas de detalhes de cobrança.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

Os US$ 3.000 são revertidos da receita não cobrada e os US$ 750 restantes da receita não cobrada são lançados. Para exibir os lançamentos de receita não cobrada, selecione **Auditoria de entrada de diário de receita não cobrada** na guia **Renovações** da página de detalhes da linha.

[![Auditoria de entrada de diário de receita não cobrada.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> A entrada no diário de receita não cobrada pode ser criada para qualquer período de renovação, desde que todas as linhas de detalhes de cobrança do período anterior tenham sido cobradas. Por exemplo, uma linha de agenda de cobrança tem uma frequência de cobrança mensal por um período de 12 meses, de janeiro a dezembro de 2021. A linha tem três períodos: o período inicial, um período termo (janeiro a dezembro de 2022) e um terceiro período (janeiro a dezembro de 2023). Depois que a fatura for criada para todas as linhas de detalhes de cobrança dos 12 meses iniciais de 2021, a entrada de diário de receita não cobrada poderá ser criada para o segundo período.
>
> Para itens de adiamento que usam o recurso de receita não cobrada, a linha de cobrança e as linhas de desconto são processadas. Para esses itens, são criados a entrada de diário de receita não cobrada e a agenda de adiamento para a linha de cobrança e a linha de desconto.
>
> As entradas de diário que são criadas para itens não adiáveis e itens adiáveis lançam um crédito em diferentes contas de receita.
