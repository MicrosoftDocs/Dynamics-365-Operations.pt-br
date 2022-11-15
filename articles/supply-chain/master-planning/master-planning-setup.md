---
title: Configurar planos mestres
description: Este artigo descreve várias estratégias e parâmetros importantes que são usados para configurar os planos mestres.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 150e02916e056946016155d1b4969e99fbd47af5
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740648"
---
# <a name="set-up-master-plans"></a>Configurar planos mestres

[!include [banner](../includes/banner.md)]

Este artigo descreve várias estratégias e parâmetros importantes que são usados para configurar o planejamento mestre. Inclui uma visão geral de tipos de planos usados pelo planejamento mestre e explica qual estratégia do plano deve ser usada, dependendo dos seus requisitos de negócios. Também descreve os parâmetros principais que afetam o plano e explica como esses parâmetros influenciam as ordens planejadas que são sugeridas.

## <a name="types-of-master-plans"></a>Tipos de planos mestre

O planejamento mestre tem dois tipos de planos: estático e dinâmico. Cada tipo é criado para um uso diferente. Para melhorar o desempenho, recomendamos que você use o plano apropriado para seu cenário.

### <a name="static-plan"></a>Plano estático

O plano estático permanece inalterado, independentemente de quaisquer alterações na oferta e na demanda, até a próxima vez em que o planejamento mestre for executado.

O plano estático é usado para aprovar e confirmar ordens que são sugeridas. É um plano de operações que várias pessoas da empresa (como um comprador ou planejador de produção) podem usar como base em suas decisões e para a realização de tarefas e atividades diárias.

O plano estático também oferece suporte à regeneração. Um novo plano totalmente otimizado é calculado cada vez que o planejamento mestre for executado e as ordens existentes forem aprovadas e excluídas.

### <a name="dynamic-plan"></a>Plano dinâmico

O plano dinâmico geralmente começa como uma cópia do plano estático, mas pode ser atualizado sempre que os dados mestres forem alterados. Por exemplo, se os dados forem alterados, uma nova ordem de venda será criada.

O plano dinâmico é usado para planejamento ad hoc. Isso permite que a empresa monitore a rede de ordens em alteração e a disponibilidade de itens sem atrapalhar o plano estático que outras pessoas estão usando para seus processos de trabalho. É usado principalmente para a capacidade de comprometimento (CTP). O plano dinâmico é o plano padrão quando as necessidades líquidas são abertas das páginas de ordens (como as páginas da ordem de venda, ordem de compra ou ordem de produção).

O plano dinâmico usa a alteração líquida. Portanto, ele ajuda a garantir um tempo de execução mais rápido.

## <a name="strategies-for-using-master-plans"></a>Estratégias para usar planos mestres

Você pode usar um plano ou dois planos no planejamento mestre. A estratégia usada dependerá de seus requisitos de negócios.

### <a name="one-plan-strategy"></a>Estratégia de um plano

Para a estratégia de um plano, use o mesmo plano mestre para o plano estático e o plano dinâmico. Essa estratégia é usada para os cenários de fabricação para armazenamento, onde geralmente você não deve simular um plano que atenda uma ordem.

A estratégia de um plano é normalmente usada nos setores de varejo e distribuição, ou quando as datas de entrega das vendas são confirmadas com base nos contratos de nível de serviço (SLAs) ou nos prazos de entrega. Para o plano, o controle da data de entrega pode ser usado sem CTP.

Se você precisar fazer uma simulação, o plano pode ser executado novamente para os itens que exigem a simulação. As ordens planejadas que as simulações de ordem produzem geralmente são confirmadas.

### <a name="two-plan-strategy"></a>Estratégia de dois planos

Para a estratégia de dois planos, você usa um plano estático e um plano dinâmico diferente. A estratégia de dois planos é normalmente usada para cenários configurar para solicitar e marca a ser solicitada, onde você deve fazer simulações da ordem de venda e calcular as datas de entrega exatas para as ordens de venda, mas os cálculos não devem afetar as operações diárias. Essas simulações sempre são feitas no plano dinâmico. A estratégia de dois planos é útil nas indústrias automotiva e de fabricantes de equipamentos originais (OEM), por exemplo.

Para a estratégia de dois planos, o controle de data de entrega, tipo CTP pode ser usado. Quando o CTP é usado, ele aciona automaticamente a execução no plano dinâmico.

### <a name="setting-up-the-plans"></a>Configurando os planos

Você pode criar planos na página **Planos mestre** (**Planejamento mestre \> Configuração \> Planos \> Planos mestre**).

Você pode especificar quais planos serão usados para o plano estático e para o plano dinâmico definindo os campos **Plano mestre estático atual** e **Plano mestre dinâmico atual** na página **Parâmetros de planejamento mestre** (**Planejamento mestre \> Configuração \> Parâmetros de planejamento mestre**). Para usar a estratégia de um plano, selecione o mesmo plano nos campos **Plano mestre estático atual** e **Plano mestre dinâmico atual**.

## <a name="types-of-planning-methods"></a>Tipos de métodos de planejamento

Três métodos de cálculo podem ser usados para executar o planejamento mestre: regeneração e alteração líquida Cada método gera um plano diferente quando é executado.

Você especifica o método de planejamento na caixa de diálogo **Execução do planejamento mestre**. Para abrir esta caixa de diálogo, Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Planejamento mestre** ou selecione **Executar** no espaço de trabalho **Planejamento mestre**.

### <a name="regeneration"></a>Regeneração

O método de planejamento de regeneração exclui as ordens planejadas existentes, a menos que estejam confirmadas. Ele gera novas ordens planejadas com base em todos os requisitos. A regeneração é o único método de planejamento que está disponível para planos estáticos.

- São consideradas as alterações no fornecimento. Essas alterações incluem alterações na previsão.
- Este método respeita o código de cobertura do **Período**.
- Este método oferece suporte à funcionalidade de substituição do produto (PI).

### <a name="net-change"></a>Alteração líquida

O método de planejamento de alteração líquida gera ordens planejadas para cobrir os requisitos que foram criados ou alterados desde a última execução do planejamento mestre. As alterações no suprimento não são consideradas quando este método é executado. O sistema não considera novos suprimentos e as ordens planejadas criadas anteriormente não são excluídas se não forem mais necessárias. O método de planejamento de alteração líquida é executado mais rápido que o método de regeneração. Está disponível somente para planos dinâmicos.

- As ações e as datas futuras serão atualizadas para todas as necessidades.
- Este método não respeita do código de cobertura do **Período**.
- Este método não atende a previsão, mesmo se estiver selecionada no plano.
- Este método não oferece suporte à funcionalidade de substituição do produto (PI).

### <a name="net-change-minimized"></a>Alteração líquida minimizada

O método de planejamento de alteração líquida minimizada gera ordens planejadas para cobrir somente os requisitos que foram criados ou alterados desde a última execução do agendamento do planejamento mestre. Para este método, diferentemente do método de alteração líquida, as datas de data de ação e as futuras serão atualizadas somente para as necessidades novas ou alteradas. Este método de planejamento está disponível somente para planos dinâmicos.

## <a name="types-of-scheduling-methods"></a>Tipos de métodos de agendamento

Para cada plano, na Guia Rápida **Geral** da página **Planos mestres** (**Planejamento mestre \> Configuração \> Planos \> Planos mestre**), você deve selecionar o método de agendamento que é usado para as ordens de produção. Você pode planejar a produção no nível de operação e o nível do profissional.

### <a name="operations-scheduling"></a>Plano de operações

Você pode usar o plano de operações para fornecer uma estimativa geral do processo de produção ao longo do tempo. O agendamento de operações não detalha as operações do roteiro de produção nos trabalhos. Para obter mais informações sobre agendamento de operações, consulte [Agendamento de operações](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Agendamento de trabalho

Agendamento de trabalho é um método de agendamento mais detalhado onde cada operação é dividida em tarefas ou trabalhos individuais. O agendamento de trabalho inclui informações sobre capacidade. Geralmente é usado para agendar trabalhos individuais no chão de fábrica com um prazo imediato ou curto prazo. Para obter mais informações sobre agendamento de trabalho, consulte [Agendamento de trabalho](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Limites de tempo em dias

Para cada plano, é possível selecionar até que ponto, no futuro, os diversos requisitos e outras considerações devem ser calculados pelo planejamento mestre. O período é conhecido como *limite de tempo*. Para melhorar o desempenho do planejamento mestre, recomendamos que você ajuste os vários limites de tempo para atender às suas necessidades comerciais. Para cada plano, você pode localizar os limites de tempo na Guia Rápida **Limites de tempo em dias** da página **Planos mestres** (**Planejamento mestre \> Configuração \> Planos \> Planos mestres**).

> [!NOTE]
> Os limites de tempo indicam até que ponto, no futuro, os diversos requisitos e outras considerações são calculados pelo planejamento mestre. Os limites de tempo selecionados nesta página substituirão os limites de tempo definidos no grupo de cobertura. Isso significa que definir uma opção do limite de tempo como sim e a definição dos dias substituirão o limite de tempo definido no grupo de cobertura. Quando definido como Não, o limite de tempo será definido no grupo de cobertura. Por fim, se não quiser ou precisar usar uma opção (por exemplo, não quiser usar as mensagens de ação), defina-a como **Sim** e, em seguida, defina o limite de tempo como **0** (zero) dias.

### <a name="coverage"></a>Cobertura

O limite de tempo de cobertura representa o período de agendamento ou a que distância a demanda deve ser incluída. Em outras palavras, indica seu horizonte de planejamento.

Definindo a opção **Cobertura** como **Sim**, você pode substituir o limite de tempo de cobertura definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias que o cálculo do agendamento do planejamento mestre deve cobrir os requisitos. O limite de tempo de cobertura é calculado para a frente em relação à data atual. As necessidades ocorridas antes da data atual são sempre processadas.

> [!NOTE]
> Para melhorar o desempenho do planejamento mestre, recomendamos que você ajuste os limites de tempo de cobertura de seu horizonte de planejamento.

### <a name="freeze"></a>Congelar

O limite de tempo de congelamento representa o período em que as ordens planejadas existentes não são alteradas quando um novo agendamento do planejamento mestre é executado. As ordens planejadas são congeladas e nenhuma nova ordem planejada será sugerida.

Definindo a opção **Congelar** como **Sim**, você pode substituir o limite de tempo de congelamento definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias durante os quais a atividade de planejamento deve ser congelada. Lembre-se que, durante este período, nenhuma nova ordem planejada será gerada e as ordens planejadas existentes não poderão ser alteradas.

### <a name="firming"></a>Confirmação

O limite de tempo de confirmação indica o horizonte de tempo no qual as ordens planejadas são convertidas automaticamente para produção e ordens de compra. Esse processo também é conhecido como *confirmação automática de ordens planejadas*.

Definindo a opção **Confirmar** como **Sim**, você pode substituir o limite de tempo de confirmação definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias durante os quais as ordens de compra planejada e as ordens de produção planejadas devem ser automaticamente confirmadas. O limite de tempo de confirmação é calculado a partir da data de agendamento do planejamento mestre. A confirmação automática de uma ordem de compra planejada pode ocorrer somente se o item estiver associado a um fornecedor.

### <a name="forecast-plan"></a>Plano de previsão

O limite de tempo de plano de previsão indica até que ponto o planejamento mestre futuro cria ordens planejadas para os itens que têm demanda prevista.

Definindo a opção **Plano de previsão** como **Sim**, você pode substituir o limite de tempo de plano de previsão definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias durante os quais a previsão de vendas do plano de previsão deverá será incluída no planejamento mestre.

### <a name="capacity"></a>Capacidade

O limite de tempo de capacidade indica até que ponto no futuro o sistema considera a capacidade máxima dos recursos quando agenda as ordens. Em outras palavras, o plano agenda as ordens de produção usando a rota de produção dos itens e considera os recursos da rota de produção e a capacidade máxima de cada recurso.

Definindo a opção **Capacidade** como **Sim**, você pode substituir o limite de tempo de capacidade definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias durante os quais a capacidade deve ser planejada para as ordens de produção planejadas. O planejamento mestre utiliza o roteiro de produção ativo para o item e faz um planejamento retroativo a partir da data da necessidade. Se a data da necessidade de uma ordem de produção planejada cair fora do limite de tempo da capacidade, o prazo de entrega será determinado com base no tempo de entrega do item. O limite de tempo da capacidade é calculado a partir da data atual.

### <a name="action-message"></a>Mensagem de ação

As mensagens de ações sugerem alterações que podem ser feitas na ordem de suprimento existente para ajudar a otimizar o plano de suprimento. Por exemplo, eles podem recomendar que você avance ou adie ordens ou que você aumente ou diminua as quantidades da ordem.

Definindo a opção **Mensagem de ação** como **Sim**, você pode substituir o limite de tempo da mensagem de ação definido para o item durante o agendamento do planejamento mestre. Neste caso, insira o número de dias que o agendamento do planejamento mestre deve gerar as mensagens de ação dos requisitos. O limite de tempo da mensagem de ação é calculado a partir da data atual.

Para obter mais informações sobre as mensagens de ação, consulte [Mensagens de ação](/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> O cálculo de mensagens de ação causa um tempo de execução mais longo para o planejamento mestre. Se as mensagens de ação não forem analisadas e aplicadas regularmente (diariamente, semanalmente e assim por diante), desative o cálculo durante a execução do planejamento mestre. Para desativar o cálculo, na página **Planos mestres**, defina o intervalo de tempo da **Mensagem de ação** como **0** (zero) para o plano mestre que você está executando. Além disso, certifique-se de que a configuração **Mensagem de ação** esteja desativada para todos os grupos de cobertura.

### <a name="calculated-delays"></a>Atrasos calculados

Você pode especificar até que ponto, no futuro, possíveis atrasos nas ordens planejadas são detectados e relatados. Dessa forma, você pode agendar possíveis datas de entrega (atrasadas).

Se uma ordem planejada não puder ser atendida na data solicitada, ela será planejada para a data de término da vigência mais antiga de uma transação, com base nos prazos de entrega e na disponibilidade de material e de capacidade.

### <a name="approved-requisitions-time-fence"></a>Limite de tempo de requisições aprovadas

Você pode configurar o planejamento mestre para criar ordens planejadas para demanda de requisição. Defina a opção **Incluir requisições** como **Sim** na Guia Rápida **Geral** da página **Planos mestres**. Em seguida, quando o objetivo de uma requisição aprovada for reabastecimento, o planejamento mestre criará automaticamente uma ordem planejada correspondente para atendê-la. O método de reabastecimento é determinado pelas políticas de fornecimento que foram configuradas para os itens de sua organização. Depois que uma requisição de reabastecimento for criada e aprovada, nenhuma ação adicional do usuário será necessária.

Definindo a opção **Limite de tempo de requisições aprovadas** como **Sim** na Guia Rápida **Limites de tempo em dias**, você pode substituir o limite de tempo de requisições aprovadas definido para o item durante o agendamento do planejamento mestre. Nesse caso, insira o número de dias no passado que a demanda das requisições aprovadas que têm a finalidade de reabastecimento deve ser incluída no agendamento do planejamento mestre. Por exemplo, você pode especificar se somente a demanda atrasada e não atendida de requisições aprovadas que foram criadas nos últimos 10 dias deverá ser considerada e planejada.

### <a name="sequencing"></a>Sequenciamento

O sequenciamento permite que as ordens planejadas sejam organizadas com base nos atributos de sequenciamento associados ao produto acabado. Frequentemente é usado para preparar ordens de produção para embalagem. Por exemplo, pode ser usado para embalar caixas em uma sequência específica, com base na cor e no tamanho.

Definir a opção de **Sequenciamento** como **Sim**, você pode especificar até que ponto as operações ou tarefas devem ser sequenciadas no futuro. Tenha em mente que quanto maior o intervalo de tempo, mais tempo levará para o planejamento mestre ser executado.

### <a name="calculated-delays"></a>Atrasos calculados

As opções de atraso ajudam a garantir que as ordens tenham datas planejadas viáveis. As seguintes opções estão disponíveis na Guia Rápida **Atrasos calculados** da página **Planos mestres**:

- **Certifique-se de que as ordens planejadas não são criadas antes da data de execução do planejamento mestre** – Defina esta opção como **Sim** para ajudar a garantir que as encomendas não podem ser agendadas para datas no passado.
- **Adicionar o atraso calculado à data da necessidade** (em **Ordens de compra planejadas**) – Defina esta opção como **Sim** para adicionar o atraso calculado aos requisitos.
- **Adicionar o atraso calculado à data da necessidade** (em **Ordens de produção planejadas**) – Defina esta opção como **Sim** para adicionar o atraso calculado aos requisitos.
- **Adicionar o atraso calculado à data da necessidade** (em **Transferência planejada**) – Defina esta opção como **Sim** para adicionar o atraso calculado aos requisitos.
- **Adicionar o atraso calculado à data da necessidade** (em **Kanban planejado**) – Defina esta opção como **Sim** para adicionar o atraso calculado aos requisitos.

Quando você definir as opções **Adicionar o atraso calculado à data da requisição** como **Sim** para adicionar os atrasos aos requisitos, o sistema considera a capacidade dos recursos e cria ordens planejadas viáveis. O recálculo das datas da ordem planejada aumenta o tempo de execução do planejamento mestre. Portanto, se você não precisar usar os atrasos, defina as opções como **Não**.

## <a name="positive-and-negative-days"></a>Dias positivos e negativos

Os dias positivos e negativos afetam como o planejamento mestre irá sugerir as ordens e ações planejadas. Os dias positivos e negativos são definidos no grupo de cobertura do item. Você pode definir os vários grupos de cobertura e definir seus parâmetros na página **Grupos de cobertura** (**Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura**).

### <a name="positive-days"></a>Dias positivos

Dias positivos indicam até que ponto o planejamento mestre futuro considera o estoque ou recebimentos atuais para atender a uma demanda futura. Por exemplo, se os dias positivos forem definidos como **100**, o estoque atual poderá ser usado para atender à demanda dos próximos 100 dias. Se houver uma ordem a 150 dias da data atual, o planejamento mestre criará uma ordem planejada para atender a essa demanda, mesmo que o estoque disponível para o item possa atender à ordem. Para itens que se movem rapidamente e têm um prazo de entrega curto, talvez você não queira usar o estoque disponível para uma ordem que está longe no futuro. Neste caso de itens que se movem rapidamente, o estoque disponível atual será eliminado rapidamente, e mais ordens poderão ser feitas no futuro para atender a uma demanda futura no prazo, o que seria possível devido a um prazo de entrega curto do item.

Os dias positivos também afetam as mensagens de ação. Por exemplo, o sistema pode recomendar que você aumente uma ordem de compra planejada para que ele inclua uma demanda que esteja dentro do número de dias positivos no futuro. Se os dias positivos forem definidos como **100**, e se houver uma demanda para um item em 30 dias da data atual, o sistema criará uma ordem planejada para satisfazer essa demanda. Se houver demanda para o mesmo item em 90 dias a partir da data atual, o sistema recomendará que você aumente a quantidade da ordem em 30 dias a partir da data atual, para que a ordem também cubra a demanda em 90 dias. Porém, se houver uma demanda para o item em 150 dias a partir da data atual, o sistema não recomendará que você aumentar a quantidade da ordem que já foi planejada. Em vez disso, uma nova ordem planejada será criada.

Como regra geral, os dias positivos serão definidos para um número que esteja entre o prazo de entrega mais longo dos itens e o intervalo de tempo da cobertura. Recomendamos que você atribua itens que são regularmente supridos ou produzidos para um grupo de cobertura onde os dias positivos são iguais ao prazo de entrega do item.

### <a name="negative-days"></a>Dias negativos

Os dias negativos indicam como os recebimentos de itens atrasados serão permitidos. Eles representam o número de dias que você está disposto a esperar antes de solicitar um novo reabastecimento quando tiver um inventário negativo ou não tiver estoque suficiente. Os dias negativos respondem à pergunta: devemos criar uma nova ordem de compra para o item ou devemos usar uma compra existente, mesmo sabendo que o item chegará atrasado?

Por exemplo, você tem uma ordem de venda para um item, 15 dias a partir da data atual. Também tem uma ordem de compra para o mesmo item. Essa ordem de compra será recebida em 20 dias, a partir da data atual. Deseja que o sistema crie uma ordem de compra para essa ordem de venda ou deseja usar a ordem existente, mesmo que não seja possível cumprir a ordem de venda no prazo? Se os dias negativos forem definidos para menos que **5** para indicar que o item pode ser atrasado no máximo cinco dias, o sistema cria um novo pedido planejado para atender à ordem do cliente. Se os dias negativos forem definidos para mais que **5**, o sistema usará a ordem existente para o item.

Os dias negativos também afetam o desempenho do planejamento mestre. Se os dias negativos são definidos como um número maior, os lotes de mensagens de ações serão produzidos.

Recomendamos que você defina os dias negativos como um número menor que o prazo de entrega do item.

### <a name="dynamic-negative-days"></a>Dias negativos dinâmicos

Os dias negativos dinâmicos consideram o prazo de entrega do item e os dias negativos especificados. O sistema criará uma nova ordem de compra planejada, com base no limite de tempo de dias negativos calculado usando a seguinte fórmula:

Prazo de entrega + Dias negativos + Data atual – Data da necessidade

O sistema usa somente as ordens de fornecimento que estão dentro deste intervalo de tempo e cria uma nova ordem planejada fora dele. A vantagem dos dias negativos dinâmicos é que ele incluirá o prazo de entrega do produto individual para reutilizar as ordens existentes e evitar a criação de novas ordens planejadas que acabarão com um dia posterior, devido a atrasos causados pelo prazo de entrega. 

Para obter mais informações, consulte [Dias negativos e dias negativos dinâmicos](/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]