---
title: "Criar um questionário"
description: "Este tópico descreve o processo para criar um questionário. A primeira etapa é criar o questionário. Ao criar um questionário, você grava não apenas as perguntas e respostas, mas também pode criar a estrutura que permite que as respostas sejam registradas e tabuladas."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cc25f4fde93df03145baedafb9c6b093659594d0
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="design-a-questionnaire"></a>Criar um questionário

[!include [banner](includes/banner.md)]

Este tópico descreve o processo para criar um questionário. A primeira etapa é criar o questionário. Ao criar um questionário, você grava não apenas as perguntas e respostas, mas também pode criar a estrutura que permite que as respostas sejam registradas e tabuladas. 

Um questionário cuidadosamente desenvolvido pode ajudar a aumentar a qualidade dos dados coletados. Por meio da criação cuidadosa, você pode selecionar melhor as opções adequadas no tempo apropriado de um questionário. Os seguintes pontos podem ajudá-lo a planejar um questionário eficaz:

-   Defina claramente a finalidade do questionário para ajudar a garantir que as perguntas ofereçam suporte à finalidade.
-   Determine a pessoa ou o grupo de pessoas que deve preencher o questionário.
-   Escreva as perguntas que aparecerão no questionário e inclua as opções de resposta, se aplicável.
-   Verifique se o questionário flui logicamente, de modo que os participantes permaneçam engajados.
-   Organize perguntas e respostas na ordem que elas devem ser apresentadas aos entrevistados.
-   Decida como os resultados devem ser avaliados, se aplicável.
-   Decida se você precisa de recursos adicionais. Por exemplo, determine se e como os resultados devem ser categorizados, se um limite de tempo é necessário, ou se todas as perguntas são obrigatórias.

A fase de criação inclui quatro categorias de tarefas que devem ser concluídas nesta ordem:

1.  Configurar pré-requisitos, conforme necessário.
2.  Configurar grupos de respostas e respostas, se aplicável.
3.  Configurar perguntas e sua associação aos grupos de respostas.
4.  Configurar o questionário em si e anexar perguntas a ele.

## <a name="prerequisites"></a>Pré-requisitos
Alguns pré-requisitos devem ser atendidos antes que seja possível criar questionários, respostas e perguntas. No entanto, nem todos os pré-requisitos são necessários para a funcionalidade completa.

### <a name="required"></a>Necessário

| Pré-requisito        | Descrição                |
|---------------------|----------------------------|
| Tipos de questionários | Categorizar questionários. |
| Tipos de perguntas      | Categorizar perguntas.      |

### <a name="optional"></a>Opcional

| Pré-requisito             | Descrição                                                    |
|--------------------------|----------------------------------------------------------------|
| Parâmetros de questionário | Modificar controles básicos e configurações padrão de questionários. |

### <a name="questionnaire-types"></a>Tipos de questionários

Os tipos de questionário são necessários e devem ser atribuídos ao criar um questionário. Os tipos de questionário ajudam você a gerenciar e classificar o questionário de maneira mais fácil. Use os tipos de questionário para classificar os questionários e diferenciá-los uns dos outros. Por exemplo, se você tiver vários questionários para selecionar, você pode filtrá-los por tipo para ajudar a facilitar a localização de um questionário específico. Veja aqui alguns exemplos de tipo de questionário:

-   Desenvolvimento de recursos humanos
-   Pesquisas sobre clientes
-   Processo de avaliação

### <a name="question-types"></a>Tipos de perguntas

Os tipos de pergunta são necessários e devem ser atribuídos ao criar uma pergunta. 

Use os tipos de pergunta para categorizar as perguntas do relatório. Os tipos de pergunta facilitam a localização de perguntas, pois é possível usar tipos como filtros na página **Perguntas**. Veja aqui alguns exemplos de tipo de pergunta:

-   Recursos humanos
-   Gerenciamento de negócios
-   Avaliação do curso

### <a name="questionnaire-parameters"></a>Parâmetros de questionário

Os parâmetros de questionário são opcionais. Você não pode usá-los, dependendo das necessidades da sua empresa. 

Os parâmetros de questionário definem o anonimato, os códigos de sequência numérica e os tipos de referência de um questionário. Quando uma organização distribuir um questionário, a opção para que os entrevistados permaneçam anônimos pode ser considerada. 

Os códigos de sequência numérica que são usados para organizar perguntas e respostas. Com base nos códigos de sequência numérica, os valores são atribuídos automaticamente aos itens. 

É preciso definir todos os parâmetros antes de começar a criar seus dados. Você pode alterar as configurações de parâmetros de questionário a qualquer momento.

## <a name="questionnaire-components"></a>Componentes do questionário
Os questionários compõem três principais elementos: grupos de respostas que contêm as respostas para questões de múltipla escolha, perguntas e o questionário em si. Se preferir, você pode agrupar as perguntas de um questionário em grupos de resultados. Os grupos de resultados permitem categorizar perguntas e fornecer uma análise mais detalhada do questionário. 

[![QuestionnaireComponents](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Grupos de respostas e respostas

Os participantes podem responder uma pergunta de duas maneiras, dependendo do assunto da pergunta:

-   As perguntas abertas não exigem respostas em um formato específico. Os participantes podem digitar uma resposta como texto, um número, uma data, ou hora. Essas perguntas tipicamente requerem que os participantes forneçam informações subjetivas nas respostas, como uma opinião, descrição, avaliação, ou uma previsão.
-   As perguntas fechadas exigem que o participante selecione uma resposta em uma lista de possíveis respostas corretas.

Para fornecer uma lista de respostas possíveis para perguntas fechadas, você pode criar respostas na página **Grupos de respostas**. 

Os grupos de respostas e as respostas são componentes que compõem o corpo principal de informações a partir do qual as perguntas são criadas. Depois que você criar um grupo de resposta, poderá associá-lo a uma pergunta no campo **Grupo de respostas** na página **Perguntas**. 

Um grupo de respostas pode ser usado para mais de uma pergunta no mesmo questionário e em mais de uma questionário. 

**Observação:** Se você alterar o texto de resposta nos grupos de respostas que já foram usados em questionários preenchidos, os dados podem se tornar difíceis de avaliar, e os resultados do questionário podem não mais ser válidos. Se você precisar alterar um grupo de respostas, considere criar um novo grupo de respostas em vez de alterar o existente. Não é possível excluir grupos de resposta anexados a uma pergunta ou a uma resposta, ou que foram respondidos.

### <a name="questions"></a>Perguntas

Um questionário deve conter perguntas. As perguntas podem ser abertas ou fechadas.

-   As perguntas abertas não são controladas, e os respondentes poderão digite as respostas.
-   As perguntas fechadas exigem uma lista de opções pré-definidas de respostas, e as perguntas podem ser estruturas para permitir que o participante selecione múltiplas respostas. As perguntas devem ser criadas para extrair informações específicas de um participante e devem estar vinculadas a um grupo de respostas que fornece opções de respostas para cada pergunta fechada. 
     -  **Observação:** Para poder configurar perguntas fechadas, você deve criar grupos de respostas e respostas.

As perguntas podem ser organizadas em uma hierarquia de perguntas condicionais, de tal modo que as perguntas secundárias sejam dependentes da resposta selecionada por um participante para a pergunta anterior. Você pode escrever as perguntas primeiro e então organizá-las em uma hierarquia posteriormente.

## <a name="setting-up-questionnaires"></a>Configurando questionários
**Observação:** Para poder configurar um questionário, você deve configurar as respostas, perguntas e pré-requisitos. 

Para cada questionário, você pode especificar as informações a seguir:

-   O tempo total ou o limite de tempo para responder às perguntas obrigatórias.
-   Se todas as perguntas são obrigatórias.
-   Se deseja calcular pontos em um questionário.
-   Como categorizar os resultados.
-   Se o questionário ficará disponível em um conjunto restrito de participantes.
-   Se um modelo de formulário deve ser exibido como plano de fundo de cada página do questionário.
-   Se observações adicionais forem necessárias para esclarecer o objetivo do questionário aos participantes.
-   Se deseja exibir as perguntas em uma sequência fixa ou selecioná-las aleatoriamente em um grupo.
-   Se as perguntas forem feitas somente se as respostas anteriores específicas forem fornecidas.

### <a name="set-up-a-questionnaire"></a>Configurar um questionário

A página principal que você usa para configurar um questionário é página **Questionários**. Para configurar um questionário, conclua as seguintes tarefas na ordem:

1.  Criar um questionário.
2.  Siga uma dessas etapas para anexar perguntas ao questionário:
    -   Se você estiver usando grupos de resultados, você pode anexar perguntas a um questionário usando grupos de resultados. Primeiro, configure os grupos de resultados para o questionário e, em seguida, adicione perguntas a eles.
    -   Se você não usar grupos de resultados, você pode anexar perguntas diretamente no questionário.

3.  Configurar uma hierarquia de pergunta condicional, se necessário.
4.  Teste o questionário.

Na página **Questionários**, clique em **Validar** para testar se o questionário está agrupado corretamente. No entanto, também é recomendado que você preencha o questionário e o teste você mesmo antes de distribuir.

### <a name="modify-a-questionnaire"></a>Modificar um questionário

Você pode concluir as seguintes tarefas na página **Questionários**:

-   Modificar informações no questionário, como os grupos de resultados e perguntas.
-   Excluir e adicionar perguntas.
-   Fazer alterações nos grupos de resultados e no número de seqüência. 

**Atenção:** Tenha cuidado ao alterar os questionários já respondidos. As alterações podem reduzir a precisão da estatísticas e, consequentemente, torná-las uma base insuficiente para a avaliação. Considere a criação de uma nova pergunta em vez de alterar uma pergunta que foi respondida anteriormente.

Em um questionário, você não pode excluir os seguintes tipos de pergunta:

-   Perguntas anexadas a um questionário
-   Perguntas que já foram respondidas e que aparecem na caixa de diálogo **Respostas**.

### <a name="result-groups"></a>Grupos de resultados

Os grupos de resultados são opcionais ao anexar perguntas a um questionário. 

Um grupo de resultados é usado para calcular pontos e categorizar os resultados de um questionário. Se você usar grupos de resultados, você pode executar as seguintes tarefas:

-   Avaliar o questionário com base nos resultados das estatísticas de ponto.
-   Avaliar a contagem de um participante para cada grupo de resultado que você configurou.
-   Gere estatísticas para cada grupo de resultados para ajudar na análise dos resultados.
-   Imprimir um relatório que mostre os resultados para cada grupo de resultados e também pontos/textos opcionais que são baseados nos pontos obtidos em cada grupo de resultado.

**Observação:** Antes de configurar grupos de resultados, você deve concluir as seguintes tarefas:

-   Perguntas fechadas de configuração. Para uma pergunta fechada, o tipo de entrada na página **Perguntas** deve ser **Caixa de seleção**, **Botão alternativo**, ou **Caixa de combinação**.
-   Definir pontos para respostas nos grupos de respostas que são atribuídos a cada pergunta.
-   Configurar um questionário.

Para anexar perguntas a um questionário usando grupos de resultados, primeiro configure os grupos de resultados do questionário e adicione questões aos grupos de resultados. Se você não usar grupos de resultados, você pode anexar perguntas diretamente no questionário. 

Você pode configurar vários grupos de resultados para avaliar os pontos obtidos por um participante em cada categoria. Depois que um questionário é concluído, você pode exibir os pontos que foram obtidos para cada grupo de resultados. 

**Dica:** Para avaliar um questionário usando os pontos mas não separar categorias, você pode adicionar todas as perguntas a um único grupo de resultados. 

Para cada grupo de resultados, você também pode configurar uma ou mais mensagens baseadas em pontuação que são exibidas a um participante após a conclusão de um questionário. O texto exibido pode variar de acordo com a pontuação atingida pelo participante em um grupo de resultados. Para usar mensagens baseadas em pontuação, você deve definir intervalos de pontos e uma descrição de cada intervalo. Quando um participante alcança uma pontuação em um intervalo específico, o texto referente ao intervalo é incluído no relatório de resultados. 

Como um grupo de resultados está relacionado aos pontos associados a conjuntos específicos de perguntas em um questionário, você também pode usar somente um grupo de resultados específicos para um questionário.

#### <a name="example-pointstexts-for-result-group-3"></a>Exemplo: Pontos/textos para um grupo de resultados 3

Você estiver usando um questionário para um teste de liderança com 15 perguntas em três categorias. Crie três grupos de resultados e adicione cinco perguntas para cada um deles. Os pontos são totalizados em três grupos. Os três grupos de resultados são os seguintes:

-   Habilidades criativas
-   Habilidades de liderança
-   Habilidades técnicas

Para usar as mensagens baseadas em pontuação, configure intervalos de texto para cada grupo de resultados. Cada pergunta equivale a dois pontos. Portanto, o total máximo de pontos em cada grupo de resultados é 10. 

A tabela mostra as mensagens baseadas em ponto que você define para o grupo de resultado "habilidades de liderança".

| Intervalo de pontos | Texto                                       |
|----------------|--------------------------------------------|
| 1 a 3         | Você tem as capacidades médias de liderança.     |
| 4 a 7         | Você tem boas capacidades de liderança.        |
| 8 a 10        | Você tem excelentes capacidades de liderança. |

Você pode configurar intervalos e textos de pontos para cada grupo de resultados de um questionário. Os textos que correspondem à pontuação de cada participante são exibidos para cada grupo de resultados. 

**Observação:** Você pode alterar intervalos e textos. Contudo, depois que um questionário for concluído, as alterações poderão causar diferenças entre relatórios de resultados anteriores e novos.

### <a name="conditional-question-hierarchies"></a>Hierarquias de perguntas condicionais

As hierarquias de perguntas condicionais são opcionais quando você configura um questionário. 

**Observação:** Antes que você possa definir uma hierarquia de perguntas condicionais, você deve anexar as perguntas com os grupos de resposta atribuídos ao questionário. 

Para usar perguntas condicionais para criar uma hierarquia de perguntas em um questionário, você pode fazer a sequência em que as perguntas são apresentadas de acordo com as respostas selecionadas por um participante para cada pergunta. Ao basear a sequência das perguntas na seleção de resposta do participante, você pode modificar o questionário conforme o participante o conclui.

#### <a name="examples"></a>Exemplos

Uma entidade legal oferece serviços e itens para seus clientes. Como normalmente ocorre em tais casos, alguns clientes adquirem apenas itens, alguns adquirem apenas serviços, e alguns adquirem itens e serviços. Portanto, quando a entidade legal distribui uma pesquisa de satisfação de cliente, ela aplica uma estrutura condicional ao questionário para impedir que os clientes que só adquirem serviços não precisem responder perguntas sobre itens. 

Como alternativa, você pode definir um questionário para que se um participante selecionar a resposta A para a pergunta 1, a pergunta 2 seja a próxima na sequência de perguntas. No entanto, se o participante selecionar a resposta B para a pergunta 1, a pergunta 5 será a próxima.

<a name="additional-resources"></a>Recursos adicionais
--------

[Usando questionários](questionnaires.md)

[Distribuindo e preenchendo questionários](distribute-questionnaires.md)

[Exibindo e avaliando os resultados dos questionários](evaluate-questionnaire-results.md)


