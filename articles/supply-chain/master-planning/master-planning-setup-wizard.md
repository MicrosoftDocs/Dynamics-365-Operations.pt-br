---
title: Assistente de configuração do planejamento mestre (contém vídeo)
description: Este tópico descreve como executar o assistente de configuração do planejamento mestre para configurar o planejamento mestre.
author: ChristianRytt
ms.date: 10/21/2019
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
ms.openlocfilehash: 453184a3fed567b3a09e5e45e7f904bcf855dd6d
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937624"
---
# <a name="master-planning-setup-wizard"></a>Assistente de configuração do planejamento mestre

[!include [banner](../includes/banner.md)]

Este tópico fornece um guia para o **Assistente de configuração do planejamento mestre**. Ele explica como sugestões de parâmetro são calculadas e também oferece exemplos para mostrar como empresas diferentes configuram o planejamento mestre com base nas necessidades comerciais.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

O vídeo [Assistente de configuração do planejamento mestre no Dynamics 365 Supply Chain Management](https://youtu.be/c-e6n-8rZb4) (mostrado acima) está incluído na [playlist do Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.


## <a name="specific-requirements-of-your-company"></a>Requisitos específicos da empresa

A primeira página do assistente solicita os requisitos específicos da empresa. As respostas para essas perguntas não precisam ser precisas, mas você deve ser capaz fornecer uma estimativa aproximada do número de itens e de ordens planejadas que haverá para a entidade legal. As respostas são usadas para configurar os parâmetros que se aplicam à sua entidade legal, não apenas ao planejamento mestre selecionado. As seções a seguir descrevem os parâmetros que são calculados e as fórmulas usadas.

### <a name="number-of-threads"></a>Número de threads

- **Se você fabrica qualquer um dos itens:** Número de threads = Número de ordens planejadas ÷ 1.000
- **Se você não fabrica qualquer um dos itens:** Número de threads = Número de itens ÷ 1.000

Se o número de threads calculado exceder 75% do número de threads disponíveis, ele será limitado a 75% do número de threads disponíveis para cada cliente. (O número de threads disponíveis será determinado para cada cliente).

Para obter mais informações, consulte [Número de threads](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Tamanho do pacote

O tamanho de pacote será definido como **1**. O valor é normalmente o aconselhável, já que ele ajuda a melhorar o desempenho do planejamento mestre.

Para obter mais informações, consulte [Número de tarefas no pacote de tarefas auxiliares](/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Como confirmar o tamanho do pacote

- **Se você fabrica qualquer um dos itens:** o tamanho de pacote de confirmação será definido como o maior destes dois valores: **10** e o cálculo do pacote
- **Se você não fabrica qualquer um dos itens:** o tamanho de pacote de confirmação será definido como o maior destes dois valores: **50** e o cálculo do pacote

Cálculo do pacote = (Número de ordens planejadas × (Limite de tempo de confirmação ÷ Limite de tempo de cobertura) ÷ Número de threads) ÷ 10

### <a name="cache-size"></a>Tamanho do cache

O tamanho do cache será definido como **Máximo**. O valor é normalmente o aconselhável, já que ele ajuda a melhorar o desempenho do planejamento mestre.

Para obter mais informações, consulte [Alocar tempo para trabalhos em um pacote de trabalho](/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Configuração de fabricação

Se você fabrica itens, será exibida uma página **Configuração de fabricação** posteriormente no assistente.

## <a name="scope-of-the-current-plan"></a>Escopo do plano atual

Na página **Escopo do plano atual** do assistente, você responderá a perguntas relacionadas a que ponto no futuro diversos requisitos serão considerados e calculados no planejamento mestre. Cada pergunta verifica se você deseja usar um recurso e como deseja configurá-lo.

Por exemplo, para o recurso do plano de previsão, o assistente pergunta: "Você deseja usar um plano de previsão no planejamento mestre de forma que as ordens planejadas sejam sugeridas para o atendimento da demanda esperada?”

As opções a seguir estão disponíveis:

- **Não** – o planejamento mestre não sugerirá ordens planejadas para atender a uma previsão. Na guia **Limites de tempo** da página **Planos mestres** (**Planejamento mestre \> Configuração \> Planos \> Planos mestres**), o assistente definirá a opção **Plano de previsão (limite de tempo)** como **Sim** e o número de dias como **0** (zero). Essa configuração substituirá o limite de tempo especificado no grupo de cobertura. Como o número de dias é definido como **0** (zero), o recurso não será usado.
- **Sim, como definido no plano mestre** – o campo ficará disponível, onde você poderá inserir o número de dias que o planejamento mestre irá sugerir ordens planejadas para atender à demanda de previsão. O assistente definirá a opção **Plano de previsão (limite de tempo)** como **Sim** e definirá o número de dias como o número de dias inserido no campo **Plano de previsão** da guia **Limites de tempo** da página **Planos mestres**. Essa configuração substituirá os valores definidos nos grupos de cobertura.
- **Sim, como definido na cobertura** – o assistente definirá a opção **Plano de previsão (limite de tempo)** como **Não**. Os limites de tempo especificados no grupo de cobertura são usados para especificar por quanto tempo você planejará a previsão.

As perguntas restantes nessa página e as respostas acompanham o mesmo esquema:

- **Não** – a opção **Plano de previsão (limite de tempo)** será definida como **Sim** e o número de dias será **0** (zero).
- **Sim, como definido neste plano mestre** – a opção **Plano de previsão (limite de tempo)** será definida como **Sim**. O número de dias inserido será usado e substituirá os valores definidos nos grupos de cobertura.
- **Sim, como definido no grupo de cobertura** – a opção **Plano de previsão (limite de tempo)** será definida como **Não**.

Para obter mais informações, consulte [Planejamento de trabalho](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Opções de agendamento

A página **Opções de programação** só será exibida se você tiver respondido **Sim** para a pergunta "Você fabrica qualquer um dos itens planejados?" na primeira página do assistente.

Sua resposta para a primeira a pergunta nessa página ("Você precisa agendar operações divididas em trabalhos individuais?") determina o método de agendamento na guia **Geral** da página **Planos mestres**.

- **Sim** – o planejamento de trabalho será usado.
- **Não** – o planejamento de operações será usado.

Para obter mais informações, consulte [Planejamento de operações](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) e [Planejamento de trabalho](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Atualizações de demanda e fornecimento

As perguntas na página **Atualizações de fornecimento e demanda** estão relacionadas a confirmação, mensagens de ação e atrasos.

A configuração do planejamento mestre será atualizada com base nas respostas, de acordo com o mesmo esquema descrito na seção anterior:

- **Não** – a opção **Limite de tempo** na página **Planos mestres** será definida como **Sim** e o número de dias será definido como **0** (zero).
- **Sim, como definido neste plano mestre** – a opção **Limite de tempo** será definida como **Sim**. O número de dias inserido será usado e substituirá os valores definidos nos grupos de cobertura.
- **Sim, como definido no grupo de cobertura** – a opção **Limite de tempo** será definida como **Não**.

Para atrasos calculados, suas respostas para as perguntas no assistente atualizarão parâmetros correspondentes na guia **Atrasos calculados** da página **Planos mestres**.

## <a name="summary-of-your-changes"></a>Resumo das alterações

A última página do assistente mostra as alterações recomendadas com base nas respostas. Mostra o valor em sua configuração (**Configuração atual**) e o valor que o assistente recomenda (**Nova configuração**).

Também é possível modificar os parâmetros na nova configuração. Os parâmetros estão separados em parâmetros que se aplicam à sua entidade legal e parâmetros que se aplicam somente ao planejamento mestre selecionado. Para exibir todos os parâmetros de configuração que podem ser alterados usando o assistente, selecione **Mostrar todos os parâmetros** na parte inferior da página. Você poderá alterar os parâmetros então.

Por fim, quando você selecionar **Concluir**, a nova configuração será aplicada. Se você selecionar **Cancelar**, nenhuma das alterações será aplicada.

## <a name="examples"></a>Exemplos

Esta seção descreve a configuração de duas empresas fictícias para mostrar como a configuração pode mudar de acordo com as necessidades de cada empresa.

### <a name="example-1-contoso-manufacturer"></a>Exemplo 1: Contoso Manufacturer

A Contoso Manufacturer é uma fábrica que produz alto-falantes. Ela compra várias matérias-primas e componentes usados para os alto-falantes finais de vários fornecedores. Veja a seguir algumas das características de fornecimento e fabricação:

- Os itens finais que a empresa fabrica têm uma estrutura de lista de materiais (BOM).
- Todos os itens e componentes finais são planejados pelo planejamento mestre. Não é feito o planejamento manual.
- Um roteiro de operações é definido para a produção de cada item final.
- A fábrica produz os itens finais. Ela tem um número definido de máquinas de trituração e perfuração usadas para processar os componentes. Os diversos componentes devem ser processados por essas máquinas.
- Há vários fornecedores. O prazo de entrega médio de itens é de uma semana. Um grupo de itens do mesmo fornecedor terá um prazo de entrega de sete semanas.

No assistente, os valores a seguir são inseridos para a Contoso Manufacturer:

- **Cobertura:**

    - **Pergunta:** "Você deseja especificar o número de dias do seu horizonte de planejamento?"
    - **Resposta:** "Sim, como definido nos grupos de cobertura."

    Como o prazo de entrega para itens é muito diferente, a Contoso não precisa planejar todos os itens para o mesmo período no futuro. Os grupos de cobertura para os itens são criados. Os itens que possuem um prazo de entrega semelhante são atribuídos ao mesmo grupo de cobertura. O horizonte de planejamento para cada grupo de cobertura (isto é, o limite de tempo de cobertura) é de aproximadamente o prazo de entrega mais uma margem de uma semana. O planejamento mestre garante então que os itens sejam planejados com antecedência, com base no prazo de entrega.

    Portanto, dois grupos de cobertura serão criados neste exemplo. Um grupo de cobertura terá um limite de tempo de cobertura de duas semanas e o outro terá um limite de tempo de cobertura de oito semanas.

    Se **Sim, como definido no plano mestre** for selecionado como a resposta, o número de dias inserido deverá exceder o prazo de entrega mais longo de todos os itens. Entretanto, já que vários itens não precisam ser planejadas com tanta antecedência, muitas ordens planejadas serão calculadas mas nunca usadas. Dessa forma, o tempo de execução do planejamento mestre aumentará.

- **Agendamento:**

    - **Pergunta:** "Você precisa agendar operações divididas em trabalhos individuais?"
    - **Resposta:** "Sim."

    A Contoso Manufacturing deve planejar e agendar os trabalhos individuais que serão executados na fábrica. Portanto, ela usará o planejamento de trabalho.

- **Capacidade:**

    - **Pergunta:** "Você deseja agendar usando a capacidade de recursos?"
    - **Resposta:** "Sim, como definido no plano mestre." **10 dias** é inserido.

    O número de máquinas de trituração e perfuração é limitado. O planejamento de produção deve considerar a limitação e organizar os trabalhos em tempo hábil de acordo com a capacidade de recursos. Ou seja, os trabalhos agendados serão replanejados com base nas limitações dos recursos. O planejamento usará o prazo de entrega além do período definido. (As ordens de produção planejadas podem ficar sobrepostas). Como o prazo de entrega de produção para os itens é de sete dias, a capacidade de recursos para planejamento mestre será considerada durante 10 dias.

- **Sequenciamento:**

    - **Pergunta:** "Você deseja sequenciar ordens planejadas usando os valores de sequência do produto?"
    - **Resposta:** "Sim, como definido nos grupos de cobertura."

    Um roteiro é definido para a produção de cada item final. Dessa forma, o planejamento mestre agendará ordens a tempo de acordo com os roteiros definidos.

- **Detalhamento:**

    - **Pergunta:** "Deseja planejar ordens para todos os elementos em uma lista de materiais (planejar o pai e todos os itens secundários)?”
    - **Resposta:** "Sim, como definido nos grupos de cobertura."

    Todos os itens usados para a produção devem ser planejados. Como os itens têm prazos de entrega muito diferentes, o planejamento mestre terá um desempenho melhor quando usar os grupos de cobertura. Novamente, uma margem de uma semana pode ser inserida e o detalhamento pode ser concluído pelo mesmo tempo que a cobertura.

### <a name="example-2-contoso-retailer"></a>Exemplo 2: Contoso Retailer

A Contoso Retailer é uma empresa de distribuição na indústria de moda. Ela usa o planejamento mestre para calcular quando as ordens de compra devem ser feitas com base nas vendas esperadas. Veja alguma de suas características:

- A Contoso Retailer usa uma previsão de demanda para prever vendas. As ordens de compra serão planejadas de acordo com a previsão.
- As lojas usam requisições para o reabastecimento.
- O prazo de entrega do depósito principal para cada loja é de aproximadamente duas semanas para todos os itens.

No assistente, os valores a seguir são inseridos para a Contoso Retailer:

- **Previsão de demanda:**

    - **Pergunta:** "Você deseja usar um plano de previsão no planejamento mestre de forma que as ordens planejadas sejam sugeridas para atender à demanda prevista?"
    - **Resposta:** "Sim, como definido no plano mestre."

    A Contoso incluiu uma previsão de demanda para prever as vendas. Portanto, o planejamento mestre deve recomendar as ordens planejadas para atender à previsão.

- **Confirmação:**

    - **Pergunta:** "Você deseja que o planejamento mestre confirme automaticamente as ordens planejadas em documentos de ordem, por exemplo, ordens de produção ou de compra?"
    - **Resposta:** "Sim, como definido no plano mestre." **1 dia** é inserido.

    Como o Contoso Retailer criará ordens de compra diretamente das ordens de compra planejadas, será útil se as ordens de compra planejadas forem confirmadas automaticamente. Como a empresa executa o planejamento mestre todos os dias, um limite de tempo de confirmação de um dia confirmará automaticamente todas as ordens necessárias para o dia seguinte.

- **Requisições aprovadas:**

    - **Pergunta:** "Você deseja incluir a demanda das requisições aprovadas para reabastecer as lojas de varejo?"
    - **Resposta:** "Sim, como definido no plano mestre." **1 dia** é inserido.

    A Contoso usa as requisições aprovadas de suas lojas para criar ordens de compra planejadas para reabastecer essas lojas. Como o planejamento mestre é executado todos os dias, as requisições do último dia serão incluídas no planejamento.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]