---
title: Automatizar liquidações do razão
description: Este artigo fornece informações gerais sobre o recurso Automatizar processo de liquidações do razão.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708323"
---
# <a name="automate-ledger-settlements"></a>Automatizar liquidações do razão

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics 365 Finance versão 10.0.31, o recurso  **Automatizar processo de liquidações do razão** está disponível no espaço de trabalho  **Gerenciamento de recursos** . É possível habilitar o recurso **Automatizar processo de liquidações do razão** somente se o recurso **Reconhecimento entre a liquidação do razão e o fechamento do exercício** também estiver habilitado.

Liquidações do razão é o processo de combinar transações de débito e crédito na contabilidade. Organizações que realizam liquidações do razão de maneira recorrente agora podem automatizar o processo. Durante o processo automático de liquidações do razão, é possível acontecer a correspondência entre uma transação de débito e outra de crédito de maneira automática apenas quando a moeda contábil é a mesma.Por exemplo, a correspondência entre um valor de débito de US$ 1,00 e um de crédito de US$ 1,00 pode ser feita automaticamente. No entanto, um valor de débito de US$ 1,00 não pode corresponder automaticamente a dois créditos de US$ 0,50. Não há suporte para a correspondência parcial de valores de transações do razão.

A automação de liquidações do razão define o seguinte:

- Quando as liquidações do razão são executadas
- Quais critérios são usados para fazer a correspondência dos débitos e créditos que podem ser automaticamente liquidados
- Em que ordem as informações de liquidações do razão são processadas

## <a name="define-the-occurrence-of-ledger-settlements"></a>Definir a ocorrência de liquidações do razão

A automação de liquidações do razão usa a Estrutura de automação de processos. Processos comerciais diferentes usam essa estrutura para definir a recorrência de um processo selecionado. Para acessar as liquidações do razão, acesse  **Administração do sistema \> Configuração \> Automações de processos** ou **Razão geral \> Configuração do razão \> Automações de processos**.

Primeiro, selecione a opção  **Criar nova automação de processo** e  **Liquidações do razão**. Em seguida, um assistente passa orientações para configurar a automação.

## <a name="general-page"></a>Página Geral

Na página  **Geral**  do assistente, insira o nome da ocorrência de liquidação do razão que você está criando. Por exemplo, se os débitos e créditos que corresponderem entre si forem liquidados na segunda, insira um nome descritivo como  **LiquidaçãoRazão\_Seg**. O nome inserido aparece na coluna **Regra de automação**, na página  **Liquidações do razão** .

As configurações restantes na página são genéricas e usadas para definir o padrão de ocorrência das liquidações do razão. Por exemplo, se uma ocorrência for para segunda-feira, você poderá definir a execução automática semanal dela toda segunda. Você também pode inserir um tempo de planejamento antecipado, como 2:00, de forma que a automação do processo seja concluída antes do início do dia útil seguinte. Recomendamos que você programe a automação do processo para acontecer fora do horário de trabalho normal. Dessa forma, você reduz o impacto para sua equipe de contabilidade durante o expediente.

Para mais informações sobre os outros campos na página  **Geral** , consulte a documentação de automação de processos.

## <a name="ledger-settlements-match-criteria-page"></a>Página de critérios de correspondência de liquidações do razão

A próxima página do assistente é a página  **Critérios de correspondência de liquidações do razão** . Ele é usado para configurar as principais contas inclusas na ocorrência de automação do processo, e os critérios são usados para determinar a correspondência entre débitos e créditos.

### <a name="account-selection"></a>Seleção de conta

As principais contas que você definiu anteriormente como contas de liquidação do razão para a entidade legal são mostradas. (Você define as contas principais como contas de liquidações do razão em **Razão geral \> Configuração do razão \> Parâmetros do razão \> Liquidações do razão**.)

### <a name="main-account-and-posting-layer"></a>Conta principal e nível de lançamento

Os valores de  **Conta principal** e **Nível de lançamento**  são critérios obrigatórios de correspondência. Os valores de **Conta principal** e **Nível de lançamento** da transação de débito e crédito do razão precisam ser iguais para que a correspondência ocorra durante o processo automático de liquidação do razão.

### <a name="posting-type"></a>Tipo de lançamento

Selecione a opção **Tipo de lançamento** se as transações de débito e crédito precisarem ser do mesmo tipo para que a correspondência ocorra durante o processo automático de liquidação do razão.

### <a name="financial-dimensions"></a>Dimensões financeiras

Selecione a opção **Dimensões financeiras** se as transações de débito e crédito precisarem ser do mesmo tipo para que a correspondência ocorra durante o processo automático de liquidação do razão. Quando essa opção estiver selecionada, será necessário escolher os critérios dos valores de dimensão financeira na lista **Dimensões financeiras disponíveis**. A dimensão da conta principal não está na lista **Dimensões financeiras disponíveis** porque é automaticamente obrigatória como parte dos critérios de correspondência.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Conferir os resultados da automação de uma liquidação do razão

Depois que a série de automação da liquidação do razão é criada, as ocorrências de cada liquidação são mostradas na exibição semanal da automação de processos. Além disso, o status de cada ocorrência é mostrado. Os seguintes status são usados:

- **Agendada**  – a automação está agendada, mas ainda não foi executada.
- **Em execução** – a automação está em execução no momento.
- **Erro**  – a automação foi executada, mas ocorreu um erro. Você pode conferir os erros selecionando o botão  **Exibir resultados** .
- **Concluída**  – a automação foi concluída. Você pode ver os resultados da liquidação na página **Liquidações do razão**.

Para ver os resultados, acesse **Razão geral \> Tarefas periódicas \> Liquidações do razão**. O campo **Regra de automação** na página **Liquidações do razão** mostra o nome da tarefa agendada usada para liquidar a transação. Tentativas de liquidação não concluídas não atualizam o valor **Regra de automação**. Se você reverter manualmente uma transação que foi liquidada antes pelo processo de automação, o valor **Regra de automação** será removido.

O campo **Data liquidada** dos registros que apresentaram correspondência mostra a data em que o processo de automação aconteceu.

## <a name="editing-a-ledger-settlement-automation"></a>Editar uma automação de liquidação do razão

A estrutura de Automação de processos permite editar a série e as ocorrências criadas para a liquidação do razão. A série pode ser editada na página  **Automação de processos**  ou na exibição semanal de automação de processos. Por exemplo, se o gerente decidir executar liquidações do razão na quarta-feira em vez de segunda-feira, ele poderá encontrar uma ocorrência na exibição semanal e selecionar  **Exibir/Editar – Série**.

Se você editar uma série, precisará especificar se a alteração deve ser feita em todas as ocorrências atuais ou somente nas novas. As ocorrências históricas que já têm o status **Concluída** ou que foram concluídas com o status  **Erro**  permanecem iguais.

Você também pode adicionar uma nova ocorrência ou alterar uma ocorrência existente. Por exemplo, a próxima liquidação do razão está agendada para execução na quarta-feira, 1º de janeiro, mas essa data é um feriado. Você pode alterar a ocorrência na página  **Automação de processos**  ou na visualização semanal de automação de processos. Uma página aberta que mostra os detalhes da agenda e os critérios de correspondência. Aqui, você pode editar a data e a hora agendadas. Também é possível editar os critérios de correspondência quando é necessário fazer alterações. 

Você também pode desabilitar uma ocorrência ou uma série. Para desabilitar uma ocorrência e suspender o processamento dela, selecione-a na exibição de automação de processos semanal e selecione  **Desabilitar**. Você pode desabilitar uma série na página **Automação de processos** .

## <a name="security-for-ledger-settlement-automation"></a>Segurança para a automação de liquidação do razão

O direito **Manter as configurações da série de automação de liquidações do razão** foi adicionado às funções de Gerente de contabilidade e Supervisor de contabilidade, e o direito **Exibir configurações da série de automação de liquidações do razão** foi adicionado às funções de Contador, Gerente de contabilidade e Supervisor de contabilidade para a automação de liquidações do razão. Esses direitos são as configurações de segurança padrão, mas podem ser alterados com base nas necessidades da sua organização.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Parâmetros do razão geral para a automação de liquidações do razão

O campo **Saldo típico da liquidação** indica em que ordem a liquidação automática do razão será processada. Para configurar ou exibir o valor de **Saldo típico da liquidação**, acesse **Razão geral \> Configuração \> Parâmetros do razão geral** e selecione a guia **Liquidações do razão**.

Se a opção **Débito** estiver selecionada, o processo de liquidação automatizada do razão começa pelo débito e pesquisa os créditos correspondentes. Se a opção **Crédito** estiver selecionada, o processo de liquidação automatizada do razão começa pelo crédito e pesquisa os débitos correspondentes. Essa opção deve refletir o saldo típico da conta principal.

## <a name="processing-a-ledger-settlement-automation"></a>Processar uma automação de liquidação do razão

Quando a automação está em execução, o sistema seleciona as transações do razão para as contas principais definidas para a série de automação de processos. Ele ordena as transações por data usando um intervalo que vai do início do ano fiscal até a data de execução do processo. Ele faz as correspondências com base nos critérios de correspondência especificados. Os valores absolutos de moeda contábil do débito e do crédito precisam corresponder para serem liquidados.

Enquanto uma conta principal está sendo processada por uma ocorrência de uma automação de liquidação do razão, não é possível vê-la na página **Liquidações do razão**. É preciso aguardar a conclusão do processo de automação. Recomendamos que você programe a automação do processo fora do horário de trabalho para evitar conflitos.

O processo de automação incluirá todas as transações que atendem aos critérios, exceto aquelas que tiverem sido mutuamente marcadas para liquidação na página **Liquidações do razão**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Reversão das transações liquidadas pelo processo de automação

Você pode reverter uma liquidação feita pelo processo de liquidação automatizada do razão. Quando uma transação que foi liquidada antes pelo processo de automação é revertida, o valor **Regra de automação** é removido.
