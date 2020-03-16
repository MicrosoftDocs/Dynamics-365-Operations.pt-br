---
title: Aprimoramentos na funcionalidade de postagem de demonstrativo
description: Este tópico descreve as melhorias feitas no recurso de postagem do demonstrativo.
author: josaw1
manager: AnnBe
ms.date: 05/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 68abef8f28c04a4f6f88e638c8abf944d06a32c4
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057246"
---
# <a name="improvements-to-statement-posting-functionality"></a>Aprimoramentos na funcionalidade de postagem de demonstrativo

[!include [banner](includes/banner.md)]

Este tópico descreve o primeiro conjunto das melhorias feitas no recurso de postagem do demonstrativo. As melhorias estão disponíveis no Microsoft Dynamics 365 for Finance and Operations 7.3.2.

## <a name="activation"></a>Ativação

Por padrão, durante a implementação de Finance and Operations 7.3.2, o programa é configurado para usar o recurso herdado para postagens do demonstrativo. Para habilitar o recurso aprimorado de postagem da instrução, você deve ativar a chave de configuração para ele.

- Vá para **Administração de sistemas** \> **Configuração** \> **Configuração de licença**, e depois, no nó **Retail e Commerce**, desmarque a caixa de seleção **Demonstrativos (herdados)**, e marque a caixa de seleção **Demonstrativos**.

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

Além disso, os parâmetros a seguir foram introduzidos na Guia Rápida **Processamento de lote** na guia **Postagem** da página **Parâmetros do Commerce**: 

- **Número máximo de lançamentos paralelos de demonstrativos** – Esse campo define o número de tarefas de lote que serão usados para postar múltiplos demonstrativos. 
- **Thread máximo para processamento de pedido por demonstrativo** – Esse campo representa o número máximo de threads usado por um trabalho de lote de postagem de demonstrativo para criar e faturar ordens de venda para um único demonstrativo. O número total de threads que serão usados pelo processo de postagem de demonstrativo serão computador com base no valor nesse parâmetro multiplicado pelo valor no parâmetro **Número máximo de lançamentos paralelos de demonstrativos**. Definir o valor desse parâmetro muito alto pode afetar negativamente o desempenho do processo de postagem do demonstrativo.
- **Linhas de transação máxima incluída na agregação** – Esse campo define o número de linhas de transação que serão incluídas em uma única transação agregada antes de uma nova ser criada. As transações agregadas são criadas com base em critérios de agregação diferentes como cliente, data do negócio ou dimensões financeiras. É importante observar que as linhas de uma única transação não serão divididas entre transações agregadas diferentes. Isso significa que há uma possibilidade de que o número de linhas em uma transação agregada é levemente maior ou menor com base nos fatores como o número de produtos distintos.
- **Número máximo de threads para validar transações de loja** – Esse campo define o número de threads que serão usados para validar transações. Validar transações é uma etapa obrigatória que precisa acontecer antes das transações serem recebidas nos demonstrativos. Você também precisa definir um **Produto para o cartão-presente** na Guia Rápida **Cartão-presente** na guia **Lançamento** da página **Parâmetros do Commerce**. Isso precisa ser definido até se cartões-presente não forem usados pela organização.

> [!NOTE]
> Todas as configurações e os parâmetros relacionados às postagens de demonstrativo, e definidos em lojas do Commerce na página **Parâmetros do Commerce**, são aplicáveis ao recurso aprimorado de postagem do demonstrativo.

## <a name="processing"></a>Processando

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

Durante o processo de lançamento, as transações de venda são agregadas na configuração. Essas transações agregadas são armazenadas no sistema e usadas para criar ordens de vendas. Cada transação agregada cria uma ordem de venda correspondente no sistema. Você pode exibir as transações agregadas usando o botão **Transações agregadas** no grupo **Detalhes de execução** do demonstrativo.

A guia **Detalhes da ordem de venda** de uma transação agregada mostra as seguintes informações:

- **ID de registro** O ID da transação agregada.
- **Número de demonstrativo** – O demonstrativo a qual a transação agregada pertence.
- **Data** – A data na qual a transação agregada foi criada.
- **ID de vendas** – Quando uma ordem de venda é criada a partir da transação agregada, o ID de ordem de venda. Se este campo estiver em branco, a ordem de venda correspondente não foi criada.
- **Número de linhas agregadas** – O número total de linhas da transação agregada e ordem de vendas.
- **Status** – O status mais recente da transação agregada.
- **ID de fatura** – Quando a ordem de vendas da transação agregada é faturada, o ID de fatura das vendas. Se este campo estiver em branco, a fatura da ordem de venda não foi postada.

A guia **Detalhes de transação** de uma transação agregada exibe todas as transações que foram colocadas na transação agregada. As linhas agregadas na transação agregada mostram todos os registros agregados das transações. As linhas agregadas também mostram detalhes como item, variante, quantidade, preço, valor líquido, unidade e depósito. Basicamente, cada linha agregada corresponde a uma linha de ordem de venda.

Na página **Transações agregadas**, você pode baixar o XML para uma transação agregada específica usando o botão **XML da ordem de venda de exportação**. Você pode usar o XML para depurar problemas que envolvam a criação e postagem da ordem de venda. Apenas baixe o XML, carregue-o a um ambiente de teste e depure o problema no ambiente de teste. A funcionalidade para baixar o XML de transações agregadas não está disponível para instruções lançadas.

A exibição agregada de transação a seguir fornece os benefícios:

- O usuário tem visibilidade nas transações agregadas que falharam durante a criação das ordens de venda e ordens de venda que falharam durante o faturamento.
- O usuário tem a visibilidade de como as transações são agregadas.
- O usuário tem uma trilha de auditoria concluída, das transações, ordens de venda, a notas fiscais de vendas. Essa trilha de auditoria não está disponível no recurso herdado de lançamento do demonstrativo.
- O arquivo XML agregado facilita a identificação de problemas durante a criação e faturamento de ordem de venda.

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

    - Vá para **Varejo e Comércio** \> **Configuração da sede** \> **Parâmetros** \> **Parâmetros de comércio**. Depois, na guia **Lançamento**, na Guia Rápida **Atualização de estoque**, no campo **Nível de detalhes**, selecione **Resumo**.
    - Vá para **Varejo e Comércio** \> **Configuração da sede** \> **Parâmetros** \> **Parâmetros de comércio**. Em seguida, na guia **Lançamento**, na guia Rápida **Agregação**, defina a opção **Transações de comprovante** como **Sim**.
