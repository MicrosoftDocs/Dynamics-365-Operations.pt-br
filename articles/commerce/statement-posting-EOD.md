---
title: Aprimoramentos na funcionalidade de postagem de demonstrativo
description: Este artigo descreve as melhorias feitas no recurso de postagem do demonstrativo.
author: analpert
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2018-04-30
ms.openlocfilehash: 33b4f17cd46338b62bed96f0a285e7b9634cc87a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067810"
---
# <a name="improvements-to-statement-posting-functionality"></a>Aprimoramentos na funcionalidade de postagem de demonstrativo

[!include [banner](includes/banner.md)]

Este artigo descreve o primeiro conjunto das melhorias feitas no recurso de postagem do demonstrativo. As melhorias estão disponíveis no Microsoft Dynamics 365 Finance 7.3.2.

## <a name="activation"></a>Ativação

Por padrão, durante a implantação do aplicativo de finanças e operações 7.3.2, o programa é configurado para usar o recurso herdado para postagens do demonstrativo. Para habilitar o recurso aprimorado de postagem da instrução, você deve ativar a chave de configuração para ele.

- Acesse **Administração de sistemas** \> **Configuração** \> **Configuração de licença**, e depois, no nó **Retail e Commerce**, desmarque a caixa de seleção **Demonstrativos (herdados)**, e marque a caixa de seleção **Demonstrativos**.

Quando a nova chave de configuração **Demonstrativos** é ligada, um novo item de menu nomeado **Demonstrativos** está disponível. Esse item de menu permite criar, calcular e lançar demonstrativos manualmente. Qualquer instrução que cause um erro quando o processo de postagem de lotes é usado também estará disponível por meio deste item de menu. (Quando a chave de configuração **Demonstrativos (herdado)** é ligada, o item de menu é nomeado **Demonstrativos abertos**.)

Commerce inclui as seguintes validações relacionadas às chaves de configuração:

- As duas chaves de configuração não podem ser alternadas simultaneamente.
- As mesmas chaves de configuração devem ser usadas para todas as operações executadas em um demonstrativo específico durante o ciclo de vida, (Criar, Calcular, Limpar, Lançar e etc.) Por exemplo, você não pode criar e calcular o demonstrativo quando a chave de configuração **Demonstrativos (herdados)** está ativada, e depois tentar lançá-la ao mesmo demonstrativo quando a chave de configuração **Demonstrativos** estiver ativada.

> [!NOTE]
> Recomenda-se usar a chave de configuração **Demonstrativos** para o recurso aprimorado de postagem do demonstrativo, a menos que você tenha motivos plausíveis para usar a chave de configuração **Demonstrativos (herdados)** em vez disso. A Microsoft continuará a investir em recursos novos e aprimoradas de postagem de demonstrativo, e é importante que você troque para ele assim que puder para receber seus benefícios. O recurso herdado de postagem do demonstrativo fica obsoleto a partir da versão 8.0.

## <a name="setup"></a>Configurar

Como parte das melhorias ao recurso de lançamento do demonstrativo, os três parâmetros foram apresentados na Guia Rápida **Demonstrativo**, na guia **Lançamento** da página **Parâmetros de Commerce**:

- **Desabilitar instrução limpar** – Essa opção é aplicável apenas para o recurso herdado de postagem do demonstrativo. Recomendamos que você defina esta opção como **Não** para impedir os usuários de limpar os demonstrativos que estão em estado pendente de lançamento. Se os demonstrativos que estão em estado pendente são limpos, os dados se tornam corrompidos. Você deve definir esta opção como **Sim** apenas em circunstâncias excepcionais.
- **Reservar estoque durante o cálculo** – Recomendamos que você use o trabalho em lotes de **Lançar estoque** para reserva de estoque, e que você defina essa opção como **Não**. Quando esta opção é definida como **Não**, o recurso aprimorado de lançamento de demonstrativo não tenta criar entradas de reserva de estoque no momento do cálculo (se as entradas ainda não tiverem sido criadas por meio do trabalho em lotes de **Lançar estoque**). Em vez disso, o recurso cria entradas reserva de estoque somente no momento de lançamento. Esta implementação foi uma escolha de design e foi baseada no fato de que a janela de tempo entre o processo de cálculo e o processo de lançamento é geralmente pequena. Entretanto, se você deseja reservar estoque no momento do cálculo, você pode definir esta opção como **Sim**.

    O recurso de lançamento de demonstrativo herdado sempre reserva estoque durante o processo de cálculo do demonstrativo (se a reserva ainda não tiver sido feita por meio do trabalho em lotes de **Lançar estoque**), independentemente se essa opção foi configurada.

- **Desabilitar contagem necessária** – Quando esta opção está definida como **Sim**, o processo de postagem de uma instrução continua, mesmo que a diferença entre o valor contado e o valor de transação no extrato esteja fora do limite definido na Guia Rápida do **Demonstrativo** para Lojas.

> [!NOTE]
> A partir da versão 10.0.14 do Commerce, quando o recurso **Demonstrativos de varejo - Fluxo constante** estiver habilitado, o trabalho em lotes **Lançar estoque** não é mais aplicável e não pode ser executado.

## <a name="processing"></a>Processamento

As instruções podem ser calculadas e lançadas no lote com os itens de menu **Calcular instruções em lote** e **Lançar demonstrativos em lote**. Alternativamente, as instruções podem ser calculadas manualmente e lançadas usando o item de menu **Demonstrativos** que o recurso aprimorado de postagem de demonstrativo fornece.

O processo e as etapas para calcular e lançar demonstrativos em um lote são os mesmos no recurso herdado de postagem do demonstrativo. Entretanto, as melhorias significativas foram feitas no back-end principal processando os demonstrativos. Essas melhorias tornam o processo mais resiliente e fornecem uma melhor visibilidade nos estados e informações de erro. Portanto, os usuários podem solucionar o motivo principal dos erros e continuar o processo de postagem sem causar corrupção dos dados e sem causar a necessidade de corrigir dados.

As seções a seguir descrevem algumas das principais melhorias para o recurso de lançamento de demonstrativo que aparecem na interface do usuário para demonstrativos e demonstrativos postados.

### <a name="status-details"></a>Detalhes do status

Um novo modelo de estado foi introduzido em uma rotina de lançamento de demonstrativo entre o cálculo e os processos de lançamento.

A tabela a seguir descreve vários estados e a ordem durante o processo de cálculo.

| Ordem do estado | Estadual      | descrição |
|-------------|------------|-------------|
| 1           | Iniciado    | O demonstrativo foi criado e está pronto para ser calculado. |
| 2           | Marcado     | As transações que estão no escopo do demonstrativo são identificadas com base nos parâmetros de demonstrativo, e elas são marcadas com a ID do demonstrativo. |
| 3           | Calculado | As linhas do demonstrativo foram computadas e exibidas. |

A tabela a seguir descreve vários estados e a ordem durante o processo de lançamento.

| Ordem do estado | Estadual                   | descrição |
|-------------|-------------------------|-------------|
| 1           | Verificado                 | Várias validações são feitas relacionadas a parâmetros (por exemplo, o encargo de disposição), e a instrução e linhas de demonstrativo (por exemplo, a diferença entre o valor contado e o valor da transação). |
| 2           | Agregado              | As transações de venda para clientes nomeados e sem nome são agregadas com a configuração. Cada transação agregada é eventualmente convertida em uma ordem de venda. |
| 3           | Ordem de cliente criada  | Com base na transação agregada, ordens de venda são criadas no sistema. |
| 4           | Ordem de cliente faturada | Ordens de venda foram faturadas. |
| 5           | Descontos lançados        | Diários periódicos de desconto são lançados com a configuração. |
| 6           | Renda/despesa lançada   | Transações de renda/despesa são lançadas como comprovantes. |
| 7           | Comprovantes vinculados         | Diários de pagamentos são criados e vinculados à nota fiscal correspondente. |
| 8           | Pagamentos lançados         | Diários de pagamentos são lançados. |
| 9           | Cartões-presente lançados       | As transações de cartão-presente são lançadas como comprovantes. |
| 10          | Postado                  | O demonstrativo é marcado como lançado. |

Cada estado nas tabelas anteriores são independentes por natureza, e uma dependência hierárquica é construída entre os estados. Essa dependência flui de cima para baixo. Se o sistema encontrar quaisquer erros enquanto processa um estado, o status do demonstrativo é revertido para o estado prévio. Qualquer repetição de tentativa subsequente de processo continua a partir do estado que falhou e continua a mover para frente. Esta abordagem tem estes benefícios:

- O usuário tem a visibilidade do estado em que o erro ocorreu.
- Corrupção de dados será impedida. Por exemplo, no recurso herdado de lançamento do demonstrativo, houve instâncias em que as ordens de venda forem faturadas mas outras foram deixadas abertas. Houve também instâncias em que alguns diários de pagamento não tiveram uma nota fiscal correspondente para liquidar, pois o lançamento fiscal tinha um erro.
- Os usuários podem consultar o estado atual do demonstrativo usando o botão **Detalhes de status** no grupo **Detalhes de execução** do demonstrativo. A página de detalhes do status tem três seções:

    - A primeira seção mostra o status atual do demonstrativo, juntamente com o código de erro e uma mensagem de erro detalhada, se um erro ocorreu.
    - A segunda seção mostra vários estados do processo de cálculo. As indicações visuais mostram os estados que foram executados com sucesso, estados que não puderam ser executados por conta de erros e estados que ainda não foram executados.
    - A terceira seção mostra vários estados do processo de postagem. As indicações visuais mostram os estados que foram executados com sucesso, estados que não puderam ser executados por conta de erros e estados que ainda não foram executados.

Além disso, o cabeçalho da segunda e terceira seções mostram o estado geral do processo relevante.

### <a name="event-logs"></a>Logs de eventos

Um demonstrativo passa por várias operações (por exemplo, Criar, Calcular, Limpar e Lançar), e múltiplas instâncias da mesma operação podem ser chamadas durante o ciclo de vida do demonstrativo. Por exemplo, após um demonstrativo ser criado e calculado, um usuário pode limpar o demonstrativo e calculá-lo novamente. O botão **Logs de eventos** no grupo **Detalhes de execução** do demonstrativo fornece uma trilha de auditoria completa de várias operações que são chamadas em um demonstrativo, com informações sobre quando as operações foram chamadas.

### <a name="aggregated-transactions"></a>Transações agregadas

Durante o processo de lançamento, as transações cash-and-carry são agregadas por cliente e produto. Portanto, o número de ordens de venda e de linhas criadas é reduzido. As transações agregadas são armazenadas no sistema e usadas para criar ordens de vendas. Cada transação agregada cria uma ordem de venda correspondente no sistema. 

Se um demonstrativo não for totalmente lançado, você poderá exibir as transações agregadas no demonstrativo. No Painel de Ações, na guia **Demonstrativo**, no grupo **Detalhes da execução**, selecione **Transações agregadas**.

![Botão Transações agregadas para um demonstrativo que não foi totalmente lançado.](media/aggregated-transactions.png)

Para os demonstrativos lançados, você poderá exibir as transações agregadas na página **Demonstrativos lançados**. No Painel de Ações, selecione **Consultas** e, em seguida, selecione **Transações agregadas**.

![Comando Transações agregadas para demonstrativos lançados.](media/aggregated-transactions-posted-statements.png)

A Guia Rápida **Detalhes da ordem de venda** de uma transação agregada mostra as seguintes informações:

- **ID de registro** O ID da transação agregada.
- **Número de demonstrativo** – O demonstrativo a qual a transação agregada pertence.
- **Data** – A data na qual a transação agregada foi criada.
- **ID de vendas** – Quando uma ordem de venda é criada a partir da transação agregada, o ID de ordem de venda. Se este campo estiver em branco, a ordem de venda correspondente não foi criada.
- **Número de linhas agregadas** – O número total de linhas da transação agregada e ordem de vendas.
- **Status** – O status mais recente da transação agregada.
- **ID de fatura** – Quando a ordem de vendas da transação agregada é faturada, o ID de fatura das vendas. Se este campo estiver em branco, a fatura da ordem de venda não foi postada.
- **Código de erro** – esse campo é definido se a agregação estiver em um estado de erro.
- **Mensagem de erro** – esse campo é definido se a agregação estiver em um estado de erro. Ele mostra detalhes sobre o que causou a falha do processo. Você pode usar as informações no código de erro para corrigir o problema e reiniciar o processo manualmente. Dependendo do tipo de resolução, pode ser necessário excluir as vendas agregadas e processá-las em um novo demonstrativo.

![Campos na Guia Rápida Detalhes da ordem de venda de uma transação agregada.](media/aggregated-transactions-error-message-view.png)

A Guia Rápida **Detalhes da transação** de uma transação agregada exibe todas as transações que foram colocadas na transação agregada. As linhas agregadas na transação agregada mostram todos os registros agregados das transações. As linhas agregadas também mostram detalhes como item, variante, quantidade, preço, valor líquido, unidade e depósito. Basicamente, cada linha agregada corresponde a uma linha de ordem de venda.

![Guia Rápida Detalhes da transação de uma transação agregada.](media/aggregated-transactions-sales-details.png)

Em algumas situações, pode haver falha nas transações agregadas durante o lançamento da ordem de venda consolidada. Nessas situações, um código de erro será associado ao status do demonstrativo. Para exibir somente as transações agregadas com erros, você pode habilitar o filtro **Mostrar somente as falhas** na exibição de transações agregadas, marcando a caixa de seleção. Ao habilitar esse filtro, você limita os resultados a transações agregadas com erros que exigem resolução. Para obter informações sobre coo corrigir esses erros, consulte [Editar e auditar transações da ordem do cliente assíncronas e ordem online](edit-order-trans.md).

![Caixa de seleção do filtro Mostrar somente falhas na exibição de transações agregadas.](media/aggregated-transactions-failure-view.png)

Na página **Transações agregadas**, você pode baixar o XML para uma transação agregada específica selecionando **Exportar dados da agregação**. Você pode examinar o XML em qualquer formatador XML para ver os detalhes reais de dados que envolvem a criação e o lançamento da ordem de venda. A funcionalidade para baixar o XML de transações agregadas não está disponível para instruções lançadas.

![Exportar dados da agregação na página Transações agregadas.](media/aggregated-transactions-export.png)

No caso de não ser possível corrigir o erro corrigindo dados na ordem de venda ou os dados que oferecem suporte à ordem de venda, um botão **Excluir ordem do cliente** estará disponível. Para excluir uma ordem, selecione a transação agregada com falha e selecione **Excluir ordem do cliente**. A transação agregada e a ordem de venda correspondente serão excluídas. Agora você pode examinar as transações usando a funcionalidade de edição e auditoria. Como alternativa, elas podem ser reprocessadas por meio de um novo demonstrativo. Depois que todas as falhas forem corrigidas, você poderá continuar o lançamento do demonstrativo executando a função Lançar demonstrativo para o demonstrativo relevante.

![Botão Excluir ordem do cliente na exibição de transações agregadas.](media/aggregated-transactions-delete-cust-order.png)

A exibição de transações agregadas fornece os seguintes benefícios:

- O usuário tem visibilidade nas transações agregadas que falharam durante a criação das ordens de venda e ordens de venda que falharam durante o faturamento.
- O usuário tem a visibilidade de como as transações são agregadas.
- O usuário tem uma trilha de auditoria concluída, das transações, ordens de venda, a notas fiscais de vendas. Essa trilha de auditoria não está disponível no recurso herdado de lançamento do demonstrativo.
- O arquivo XML agregado facilita a identificação de problemas durante a criação e faturamento da ordem de venda.

> [!NOTE]
> Quando as transações são agregadas, o membro da equipe atribuído à transação não está mais disponível no **Relatório de vendas da equipe principal**, o que significa que o **Relatório de vendas da equipe principal** não mostrará todas as transações. Recomendamos que você não use o **Relatório de vendas da equipe principal** com transações agregadas.

### <a name="journal-vouchers"></a>Comprovantes de diário

O botão **Comprovantes de diário** no grupo **Detalhes de execução** do demonstrativo mostra todas as várias transações de comprovantes que são criadas para um demonstrativo, e que são relacionadas a descontos, contas de renda/despesa, cartões-presente, e assim por diante.

Atualmente, o programa exibirá somente esses dados para demonstrativos lançados.

### <a name="payment-journals"></a>Diários de pagamentos

O botão **Diários de pagamento** no grupo **Detalhes de execução** do demonstrativo mostra todos vários diários de pagamento criados para um demonstrativo.

Atualmente, o programa exibirá somente esses dados para demonstrativos lançados.

## <a name="other-improvements"></a>Outras melhorias

Além disso, melhorias finais que os usuários podem ver foram feitas no recurso de postagem do demonstrativo. Eis alguns exemplos:

- A agregação não considera a equipe, o terminal e as entidades de turno. Como existem menos parâmetros de agregação, menos linhas de ordem de venda devem ser processadas.
- A ocorrência de deadlock em tabelas de transação é reduzida introduzindo tabelas de extensão adicionais e inserindo operações em vez de operações de atualização nas tabelas da transação.
- O número de tarefas do lote da execução foi parametrizado e limitado. Portanto, esse número pode ser ajustado especificamente ao ambiente de um cliente. No recurso herdado de postagem do demonstrativo, um número ilimitado de tarefas de lote foi criado ao mesmo tempo. Os resultados foram cargas, custos indiretos e inimagináveis no servidor do lote.
- Os demonstrativos são enfileirados de forma eficiente para processando priorizando demonstrativos com o número máximo de transações.
- Processos em lote como **Calcular demonstrativos em lote** e **Lançar demonstrativos em lote** são executados apenas no modo em lote. No recurso de lançamento de demonstrativo herdado, os usuários podem escolher executar esses processos em lote em um modo interativo como operação de único thread, diferentemente dos processos em lote que tem vários threads.
- No recurso herdado de postagem do demonstrativo, qualquer falha de uma tarefa de lote coloca os trabalhos em lotes inteiros um estado de erro. No recurso melhorado, falhas de tarefa de lote não colocam o trabalho em lotes em um estado de erro se outras tarefas em lotes foram concluídas com sucesso. Você deve avaliar o status de postagem de uma execução de lote usando a página **Demonstrativos**, na qual você pode ver todos os demonstrativos que não sejam postados devido a erros.
- No recurso herdado de postagem do demonstrativo, a primeira ocorrência de uma falha de demonstrativo causa a falha inteira do lote. Os demonstrativos restantes não são processados. No recurso aprimorado, o processo de lotes continua a processar todas as instruções, se uma das instruções falha. Um benefício é que os usuários ganham a visibilidade em número exato de demonstrativos que têm erros. Portanto, os usuários não precisam ficar presos em um loop contínuo de correção de erros e execução do processo de lançamento de demonstrativo até que todas as instruções sejam lançadas.

## <a name="general-guidance-about-the-statement-posting-process"></a>Orientações gerais sobre o processo de lançamento de demonstrativo

- Recomendamos que você execute o processo de postagem do demonstrativo em um lote, porque as definições de lote se aproveitam da estrutura de lotes em termos de multithreading. Multithreading é necessário para tratar os enormes volumes de transações que normalmente são vistos nos lançamentos de demonstrativos.
- Recomendamos que você ative o estoque físico negativo no grupo de modelo de item, para que você tenha uma experiência de lançamento perfeita. Em algumas situações, demonstrativos negativos não conseguirão ser lançados a menos que houvesse um estoque físico negativo. Por exemplo, em tese, se houver apenas uma unidade de um item em estoque e ela for uma transação de venda e uma transação de devolução do item, a transação deverá ser capaz ser lançada se o estoque negativo estiver ativado. Porém, como o processo de postagem de demonstrativo recebe a transação de vendas e a transação de devolução em uma única ordem de cliente, não há garantia de que a linha de vendas será lançada primeiro, acompanhada por linha de devolução. Portanto, erros podem ocorrer. Se o estoque negativo for ativado neste cenário, a postagem da transação não é afetada negativamente e o sistema refletirá corretamente o estoque.
- Recomenda-se usar a agregação enquanto você calcula e lança demonstrativos. Portanto, as seguintes configurações são recomendadas para alguns dos parâmetros de agregação:

    - Acesse **Varejo e Comércio** \> **Configuração do headquarters** \> **Parâmetros** \> **Parâmetros de comércio**. Depois, na guia **Lançamento**, na Guia Rápida **Atualização de estoque**, no campo **Nível de detalhes**, selecione **Resumo**.
    - Acesse **Varejo e Comércio** \> **Configuração do headquarters** \> **Parâmetros** \> **Parâmetros de comércio**. Em seguida, na guia **Lançamento**, na guia Rápida **Agregação**, defina a opção **Transações de comprovante** como **Sim**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]

