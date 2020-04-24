---
title: Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, ofício do trabalho de manutenção e listas de verificação de manutenção
description: Este tópico descreve as categorias do tipo de trabalho de manutenção e os tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, ofício do trabalho de manutenção e listas de verificação de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8dfac98e8425a270109abecaab4e5338ddabeb8a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215530"
---
# <a name="maintenance-job-type-categories-and-maintenance-job-types-maintenance-job-type-variants-maintenance-job-trades-and-maintenance-checklists"></a>Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, ofício do trabalho de manutenção e listas de verificação de manutenção

[!include [banner](../../includes/banner.md)]

 

Um tipo de ativo está associado a cada ativo. Os tipos de ativos definem os tipos de trabalho de manutenção (e portanto, os trabalhos de manutenção) que podem ser executados nos ativos. Ao criar uma ordem de serviço, você deve selecionar um tipo de trabalho de manutenção. Você pode selecionar somente os tipos de trabalho de manutenção relacionados à configuração do tipo de ativo usado para o ativo.

Para obter uma visão geral gráfica dos ativos e dos tipos de trabalho de manutenção e sua conexão às ordens de serviço, consulte [Locais funcionais e ativos](../overview/functional-locations-and-objects.md).

As grades do tipo de trabalho de manutenção podem ser configuradas em um tipo de trabalho de manutenção. As grades do tipo de trabalho de manutenção definem variações de um tipo de trabalho, como tamanho (pequeno, médio, grande) ou períodos (semanal, quinzenal, um mês, ou três meses) e as configurações (baixo padrão, flexível ou alto desempenho).

O ofício do trabalho de manutenção fornece informações sobre ofícios profissionais, como mecânicos, elétricos e hidráulicos. Os requisitos de competência podem ser configurados em um ofício do trabalho de manutenção. Todos os ofícios do trabalho de manutenção podem ser usados com relação a todos os tipos de trabalho de manutenção. A seleção de uma grade do tipo de trabalho de manutenção e/ou ofício do trabalho de manutenção em uma ordem de serviço é opcional.

Para cada tipo de trabalho de manutenção podem ser criadas variações da configuração do tipo de trabalho de manutenção. Por exemplo, se você tiver um tipo de trabalho de manutenção denominado **Serviço**, você poderá criar as seguintes variações para esse tipo de trabalho de manutenção: **Caminhões 30.000 km**, **Carros 30.000 km** e **Vans 30.000 km**.

As categorias do tipo de trabalho de manutenção são usadas para coletar um grupo de tipos de trabalho de manutenção para finalidades gerais. Exemplos de categorias do tipo de trabalho de manutenção, podem incluir **Calibração**, **Inspeção**, **Revisão**e **Instrumentação**.

Modelos de lista de verificação de manutenção e variáveis da lista de verificação de manutenção são usados para configurar listas de verificação de manutenção. As listas de verificação de manutenção são configuradas em tipos de trabalho de manutenção e usadas em ordens de serviço.

Primeiro você configura as categorias do tipo de trabalho de manutenção, as grades do tipo de trabalho de manutenção e os ofícios do trabalho de manutenção obrigatórios. Em seguida, você cria os tipos de trabalhos de manutenção. Por fim, na página **Padrões do tipo de trabalho de manutenção**, você cria todas as variações de tipos de cargos de manutenção que são necessários para seu equipamento. Nessa página, é possível configurar previsões, listas de verificação de manutenção e ferramentas para obter uma combinação de tipos de trabalho de manutenção.

> [!NOTE]
> Um tipo de trabalho de manutenção pode estar relacionado a apenas uma categoria do tipo de trabalho de manutenção.

## <a name="create-a-maintenance-job-type-category"></a>Criar uma categoria do tipo de trabalho de manutenção

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Categorias do tipo de trabalho de manutenção**.
2. Selecione **Novo**.
3. No campo **Categoria de tipo de trabalho de manutenção**, informe um ID para a categoria do tipo de trabalho de manutenção.
4. No campo **Nome**, insira um nome.

    Após relacionar as categorias do tipo de trabalho de manutenção aos tipos de trabalho de manutenção, o campo **Tipos de trabalho** mostra o número de tipos de trabalho de manutenção relacionados a esta categoria do tipo de trabalho de manutenção.

![Página Categorias do tipo de trabalho de manutenção](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Criar uma grade do tipo de trabalho de manutenção

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Variantes do tipo de trabalho de manutenção**.
2. Selecione **Novo**.
3. No campo **Grade do tipo de trabalho de manutenção**, informe um ID para a grade do tipo de trabalho de manutenção.
4. No campo **Descrição**, insira uma descrição.
5. Na Guia Rápida **Tipos de trabalho de manutenção**, selecione **Adicionar** para adicionar um tipo de trabalho de manutenção.
6. No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho de manutenção.
7. Repita as etapas 5 a 6 para adicionar mais tipos de trabalho de manutenção para a grade do tipo de trabalho de manutenção.

    Na Guia Rápida **Detalhes**, o campo **Tipos de trabalhos** mostrará o número de tipos de trabalho de manutenção que foram adicionados a essa grade do tipo de trabalho de manutenção.

![Página Variantes do tipo de trabalho de manutenção](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Criar um ofício do trabalho de manutenção

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Ofício do trabalho de manutenção**.
2. Selecione **Novo**.
3. No campo **Ofício**, insira uma ID para o ofício do trabalho de manutenção.
4. No campo **Descrição**, insira uma descrição.
5. Na Guia Rápida **Habilidades**, selecione **Adicionar** para adicionar uma nova habilidade que deve estar relacionada ao ofício do trabalho de manutenção.
6. No campo **Habilidade**, selecione a habilidade.
7. No campo **Nível**, selecione o nível da habilidade.
8. Repita as etapas 5 a 7 para adicionar mais habilidades ao ofício do trabalho de manutenção.

    Na Guia Rápida **Detalhes**, o campo **Habilidades** mostrará o número de habilidades que foram adicionadas a esse ofício do trabalho de manutenção.

9. Na Guia Rápida **Certificados**, selecione **Adicionar** para adicionar um certificado ao ofício do trabalho de manutenção.
10. No campo **Tipo de certificado**, selecione o certificado.
11. Repita as etapas 9 a 10 para adicionar mais certificados ao ofício do trabalho de manutenção.

    Na Guia Rápida **Detalhes**, o campo **Certificados** mostrará o número de certificados que foram adicionados a esse ofício do trabalho de manutenção.

![Página Ofício do trabalho de manutenção](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Crie uma variável a lista de verificação de manutenção

Quando você cria linhas da lista de verificação de manutenção no padrão do tipo de trabalho de manutenção, você deve selecionar um tipo de lista de verificação de manutenção. **Variável** é um tipo de lista de verificação de manutenção. É usada para definir um resultado possível em um intervalo em uma linha da lista de verificação de manutenção que é relacionada a uma linha de ordem de serviço. Uma variável permite criar um conjunto de resultados predefinidos sem precisar fazer uma medida exata.

**Exemplo 1:** Você pode medir o nível de óleo definindo três valores: **Nível muito alto**, **Nível muito baixo** e **Nível dentro do intervalo**. Para cada valor, defina se o resultado do valor é **Aprovado**, **Com Falha** ou **Nenhum**.

**Exemplo 2:** Você faz uma inspeção visual de um equipamento para avaliar o desgaste.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Listas de verificação de manutenção** \> **Variáveis da lista de verificação de manutenção**.
2. Selecione **Novo**.
3. No campo **Variável**, insira uma ID para a variável da lista de verificação de manutenção.
4. No campo **Nome**, insira um nome.
5. Na Guia Rápida **Geral**, selecione **Adicionar** para adicionar uma linha a uma variável.

    Um número de linha sequencial é inserido automaticamente no campo **Número da linha**. Após ter adicionado todas as linhas, você pode alterar os números da linha, conforme necessário. Quando você seleciona a linha e pressione a tecla **Seta para baixo**, o próximo número na sequência será inserido automaticamente na próxima linha.

6. No campo **Valor**, insira uma descrição do valor.
7. No campo **Resultado**, selecione um resultado da linha.

![Página Variáveis da lista de verificação de manutenção](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Criar um modelo da lista de verificação de manutenção

Os modelos da lista de verificação de manutenção podem ser usados como um conjunto comum de tarefas que um trabalhador deve executar para concluir uma ordem de serviço corretamente. Os modelos são referenciados das linhas da lista de verificação de manutenção no padrão do tipo de trabalho de manutenção. Os modelos podem ser referenciados entre várias linhas padrão do tipo de trabalho de manutenção. Portanto, você pode facilmente reutilizar um conjunto de tarefas comuns da lista de verificação de manutenção. Exemplos de modelos de lista de verificação de manutenção incluem instruções gerais de segurança e uma lista de itens e condições que devem ser verificados em uma bomba específica ou em modelos similares de uma esteira transportadora.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Listas de verificação de manutenção** \> **Modelos da lista de verificação de manutenção**.
2. Selecione **Novo**.

    Uma ID de modelo é inserido automaticamente no campo **Modelo da lista de verificação de manutenção**.

3. No campo **Nome**, insira um nome para o modelo da lista de verificação de manutenção.
4. Na Guia Rápida **Linhas da lista de verificação de manutenção**, selecione **Adicionar** para adicionar uma linha do modelo.

    Um número de linha sequencial é inserido automaticamente no campo **Número da linha**. Após ter adicionado todas as linhas, você pode alterar os números da linha, conforme necessário. Quando você seleciona a linha e pressione a tecla **Seta para baixo**, o próximo número na sequência será inserido automaticamente na próxima linha.

5. No campo **Tipo**, selecione um tipo de linha da lista de verificação de manutenção. Para cada tipo de lista de verificação de manutenção, a Guia Rápida **Detalhes da linha** mostra os campos relacionados. Os valores a seguir estão disponíveis:

    - **Texto** – A linha tem o texto que descreve o que fazer. Use este tipo de lista de verificação de manutenção se quiser que um trabalhador verifique ou inspecione algo, mas não espera um resultado específico (mensurável). Após selecionar esse tipo, insira um nome ou um cabeçalho no campo **Nome**. No campo **Instruções**, insira uma descrição do que deve ser feito. Se a etapa for obrigatória para a lista de verificação de manutenção, defina a opção **Obrigatória** como **Sim**.
    - **Cabeçalho** – A linha é usada como um cabeçalho para agrupar as linhas da lista de verificação de manutenção que aparecem abaixo dela. Este tipo é útil se você tiver diversas linhas da lista de verificação de manutenção que podem ser divididas em áreas específicas. Os cabeçalhos fornecem uma visão geral do trabalhador que concluirá uma lista de verificação de manutenção que tem várias linhas de lista de verificação de manutenção. Após selecionar esse tipo, insira um nome descritivo no campo **Nome**.
    - **Modelo** – A linha é usada para fazer referência a um modelo existente. Após selecionar esse tipo, insira um nome para o modelo no campo **Nome**. No campo **Modelo**, selecione o modelo.
    - **Variável** – A linha é usada para definir um resultado possível em um intervalo. Para obter informações sobre como configurar variáveis da lista de verificação de manutenção, consulte a seção [Criar uma variável da lista de verificação de manutenção](#create-a-maintenance-checklist-variable). Após selecionar esse tipo, insira um nome descritivo para a variável no campo **Nome**. No campo **Variável** selecione a variável. No campo **Instruções**, insira uma descrição do que deve ser feito. Se a etapa for obrigatória para a lista de verificação de manutenção, defina a opção **Obrigatória** como **Sim**.
    - **Medição** – A linha é usada para registar uma medida específica. Você pode configurar a medição que deve estar relacionada a um contador predefinido. Após selecionar esse tipo, insira um nome para o modelo no campo **Nome**. Se esta etapa for obrigatória para a lista de verificação de manutenção, defina a opção **Obrigatória** como **Sim**. Se quiser usar a linha de medição como um registro do contador, selecione o contador no campo **Contador**. O campo **Unidade** relacionada será atualizado automaticamente. Se você selecionou um contador, selecione o método de atualização no campo **Valor**. Nos campos **Valor mínimo** e **Valor máximo**, insira um intervalo de valores permitido. No campo **Instruções**, insira uma descrição do que deve ser feito.

        > [!NOTE]
        > Qualquer linha do tipo de **Medição** que não tenha uma configuração do contador é tratada como um registro de medição independente para o qual não há acompanhamento automático no Gerenciamento de Ativos. Da mesma forma, se o tipo de contador selecionado não estiver presente no ativo relacionado à ordem de serviço, a tarefa da lista de verificação de manutenção será tratada como uma medida independente. O valor do contador pode ser alterado várias vezes. Não é lançada até que o [estado do ciclo de vida da ordem de serviço](work-order-lifecycle-states.md) seja alterado para um estado no qual a opção **Processar lista de verificação de manutenção** seja definida como **Sim**.

    Na Guia Rápida **Detalhes**, o campo **Verificações** mostra o número total de linhas da lista de verificação de seu modelo. Este número inclui linhas aninhadas em qualquer modelo existente que você fizer referência em seu modelo.

![Página Modelos da lista de verificação de manutenção](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Criar um tipo de trabalho de manutenção

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Tipos de trabalho de manutenção**.
2. Selecione **Novo**.
3. No campo **Tipo de trabalho de manutenção**, insira uma ID para o tipo de trabalho de manutenção.
4. No campo **Nome**, insira um nome.

    A Guia Rápida **Detalhes** mostra uma visão geral do número de variantes do tipo de trabalho de manutenção, certificados, trabalhos subsequentes e tipos de ativos que foram criados neste tipo de trabalho de manutenção. O campo **Linhas de instalação** mostra o número de linhas padrão do tipo de trabalho de manutenção configuradas neste tipo de trabalho de manutenção. O campo **Ativos** mostra o número de ativos ativados que atualmente usam este tipo de trabalho de manutenção.

5. Na Guia Rápida **Geral**, no campo **Categoria do tipo de trabalho de manutenção**, selecione uma categoria do tipo de trabalho de manutenção.
6. Defina a opção **Atividades do tempo de inatividade de manutenção** como **Sim** se o tipo de trabalho de manutenção exigir uma parada de manutenção do equipamento antes do trabalho ser executado.
7. Na Guia Rápida **Descrição**, insira uma descrição do tipo de trabalho de manutenção.
8. Na Guia Rápida **Grades do tipo de trabalho de manutenção**, você pode adicionar grades ao tipo de trabalho de manutenção.
9. Nas Guias Rápidas **Habilidades necessárias** e **Certificados necessários**, você pode adicionar habilidades e requisitos do certificado ao tipo de trabalho de manutenção.
10. Se um tipo de trabalho de manutenção tiver que ser executado a seguir, adicione-o na Guia Rápida **Trabalhos subsequentes**. Você também pode configurar uma grade e ofício do tipo de trabalho de manutenção relacionados ao tipo de trabalho de manutenção. Se o trabalho subsequente tiver que começar em um número específico de dias antes ou depois do início do trabalho que usa este tipo de trabalho de manutenção, insira o número de dias no campo **Atraso por dias**. Números positivos representam dias após o início de trabalho relacionado e números negativos representam dias antes do início agendado do trabalho relacionado. Por exemplo, se você inserir **5**, o trabalho subsequente começará cinco dias após o início de trabalho relacionado ao tipo de trabalho de manutenção. Se você inserir **-3**, o trabalho subsequente começará três dias antes do início agendado do trabalho relacionado ao tipo de trabalho de manutenção.

    > [!NOTE]
    > Se adicionar mais de uma linha de tipo de trabalho de manutenção, a sequência de linhas indica a ordem que devem ser executadas. A sequência começa na parte superior da lista.

11. Na Guia Rápida **Tipos de ativos**, você pode adicionar tipos de ativos ao tipo de trabalho de manutenção.

![Página Tipos de trabalho de manutenção](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Crie linhas do padrão do tipo de trabalho de manutenção e previsões relacionadas, listas de verificação de manutenção, ferramentas, descrição e anexos.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Padrões do tipo de trabalho de manutenção**.

    –ou–

    Selecione **Gerenciamento de ativos** \> **Configuração** \> **Trabalhos** \> **Tipos de trabalho de manutenção**, selecione um tipo de trabalho de manutenção e, em seguida, selecione **Padrões do tipo de trabalho de manutenção**.

2. Selecione **Novo**.
3. Nos campos **Local funcional**, **Tipo de ativo**, **Fabricante**, **Modelo** e **Ativos**, selecione os valores apropriados, dependendo de quão específico o padrão do tipo de trabalho de manutenção deve ser.
4. No campo **Tipo de trabalho de manutenção**, selecione um tipo de trabalho de manutenção se não for selecionado automaticamente.
5. Nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**, selecione um grade do tipo de trabalho de manutenção e ofício do trabalho de manutenção, conforme necessário.
6. Selecione **Previsão**.
7. Na página **Previsão do padrão do tipo de trabalho de manutenção**, você pode fazer previsões em horas, itens e despesas. Nas guias relevantes, selecione **Adicionar** e faça seleções para criar previsões necessárias para o tipo de trabalho de manutenção.
8. Na guia **Previsão de item**, selecione as dimensões de estoque que devem ser mostradas na linha do item. Selecione **Estoque** \> **Dimensões**, selecione as dimensões a serem mostradas, defina a opção **Salvar configuração** como **Sim** e, em seguida, selecione **OK**.
9. Na guia **Previsão do item**, selecione **Item onde usado** para ver uma visão geral de onde o item na linha selecionada é usado no Gerenciamento de Ativos em relação aos ativos, padrão de tipo de trabalho de manutenção, peças sobressalentes e ordens de serviço. 

    A Guia Rápida **Totais da previsão de manutenção** mostra uma visão geral dos totais da previsão. Esta visão geral inclui o número total de horas e as linhas de previsão que foram criadas.

    > [!NOTE]
    > Para copiar a configuração de previsão de outro tipo de trabalho de manutenção, selecione **Copiar previsão** e selecione o tipo de trabalho de manutenção para ser copiado da configuração.

11. Selecione **Salvar** para salvar as alterações.
12. Feche a página **Previsão padrão do tipo de trabalho de manutenção** para retornar à página **Padrões do tipo de trabalho de manutenção**.
13. Selecione **Lista de verificação de manutenção**.
14. Na página **Lista de verificação dos padrões do tipo de trabalho de manutenção**, você pode adicionar linhas da lista de verificação de manutenção ao padrão do tipo de trabalho de manutenção selecionado. Na Guia Rápida **Linhas de verificação de manutenção**, selecione **Novo** para adicionar uma linha da lista de verificação de manutenção.

    Os números da linha são inseridos automaticamente no campo **Número da linha** para indicar a sequência de linhas da lista de verificação de manutenção. Você pode editar números de linha, conforme necessário. Após ter criado a primeira linha da lista de verificação de manutenção, selecione-a e pressione a tecla **Seta para baixo** para adicionar uma linha abaixo dela. Como alternativa, você pode selecionar uma linha da lista de verificação de manutenção e selecionar **Novo**. Nesse caso, uma nova linha será adicionada acima da linha da lista de verificação de manutenção selecionada.

15. No campo **Tipo**, selecione o tipo de linha e adicione as informações relacionadas ao tipo de lista de verificação de manutenção. Para obter uma descrição dos tipos disponíveis e dos campos relacionados, consulte a seção [Criar um modelo da lista de verificação de manutenção](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Para copiar a configuração de da lista de verificação de manutenção de outro tipo de trabalho de manutenção, selecione **Copiar lista de verificação de manutenção** e selecione o tipo de trabalho de manutenção a ser copiado da configuração.
    >
    > Você pode criar facilmente um modelo de uma lista de verificação de manutenção existente. Você poderá reutilizar o modelo entre várias listas de verificação de manutenção. O novo modelo será uma cópia exata da lista de verificação de manutenção ativa. Selecione **Criar modelo**, e insira o nome do modelo. Para substituir a lista de verificação de manutenção existente por uma linha única que faz referência ao novo modelo, defina a opção **Substituir** como **Sim**. Você pode exibir o conteúdo do modelo na página de detalhes **Modelos da lista de verificação de manutenção**.

16. Selecione **Salvar** para salvar as alterações.
17. Volte à página **Padrões do tipo de trabalho de manutenção**.
18. Selecione **Ferramentas**.
19. Na página **Ferramentas do padrão do tipo de trabalho de manutenção**, você pode adicionar ferramentas (recursos) que devem ser usados para o tipo de trabalho de manutenção. Selecione **Novo** e, em seguida, selecione a ferramenta no campo **Recurso**.

    > [!NOTE]
    > Para copiar a configuração da ferramenta de outro tipo de trabalho de manutenção, selecione **Copiar ferramentas** e selecione o tipo de trabalho de manutenção para ser copiado da configuração.

20. Selecione **Salvar** para salvar as alterações.
21. Volte à página **Padrões do tipo de trabalho de manutenção**.
22. Selecione **Descrição do trabalho**.
23. Na página **Descrição do trabalho**, selecione **Editar**, e adicione uma descrição que esteja relacionada ao padrão do tipo de trabalho de manutenção selecionado, conforme o necessário.
24. Selecione **Salvar** para salvar a descrição.

    Se você adicionar uma descrição do trabalho aqui, ela substituirá qualquer descrição configurada para o tipo de trabalho de manutenção na página **Tipos de trabalho de manutenção**. Se você não adicionar uma descrição de trabalho aqui, qualquer descrição configurada para o tipo de trabalho de manutenção será usada. As descrições são transferidas automaticamente para ordens de trabalho que usam o tipo de trabalho de manutenção ou o padrão do tipo de trabalho de manutenção.

25. Volte à página **Padrões do tipo de trabalho de manutenção**.
26. Para configurar anexos em uma linha padrão do tipo de trabalho de manutenção selecionado, selecione **Anexar documentos**. Os anexos configurados em uma linha padrão do tipo de trabalho de manutenção são incluídos automaticamente nas linhas de ordem de serviço que usam esta linha padrão do tipo de trabalho de manutenção.
27. Selecione **Novo** e depois um tipo de documento.
28. Carregar o documento ou o arquivo.
29. Defina os campos na página **Anexos**. A configuração do anexo usa a funcionalidade de configuração do documento padrão.
30. Selecione **Salvar** para salvar o anexo.

    > [!NOTE]
    > Os anexos em uma linha padrão do tipo de trabalho de manutenção são impressos junto com um relatório da ordem de serviço, somente se os tipos de documentos dos anexos forem selecionados na guia **Tipos de documentos** da página **Parâmetros de gerenciamento de ativos** (**Gerenciamento de ativos** \> **Configuração** \> **Parâmetros de gerenciamento de ativos**). Os exemplos de anexos incluem diretrizes que explicam como concluir uma tarefa específica ou uma lista de verificação de manutenção (se você não usar a funcionalidade da lista de verificação de manutenção para as linhas padrão do tipo de trabalho de manutenção).

    Na página **Padrões do tipo de trabalho de manutenção**, cada linha mostra o número de horas previstas, e também o número de linhas que foram criadas para itens, despesas, lista de verificação de manutenção e ferramentas. O campo **Ativos** mostra o número de ativos ativados relacionados à linha padrão do tipo de trabalho de manutenção.

31. Para copiar um padrão do tipo de trabalho de manutenção para outro, selecione a linha do padrão do tipo de trabalho de manutenção da qual será copiada a configuração, selecione **Copiar configuração** e, em seguida, selecione o padrão do tipo de trabalho de manutenção a ser copiado.
32. Para exibir uma lista de ativos, planos de manutenção ou rounds de manutenção que atualmente uma uma linha padrão do tipo de trabalho de manutenção, selecione a linha e depois selecione **Usado por**.

![Página Padrões do tipo de trabalho de manutenção](media/07-setup-for-work-orders.png)

Quando o sistema seleciona o padrão do tipo de trabalho de manutenção disponível que deve ser usado em uma linha da ordem de serviço, a seleção é baseada no ativo e na configuração do tipo de ativo relacionado. O Gerenciamento de Ativos passa por todos os registros padrão do tipo de trabalho de manutenção relacionados ao tipo de trabalho de manutenção relacionado ao tipo de ativo para verificar uma possível correspondência. Ele sempre verifica a combinação mais específica primeiro. Em outras palavras, para localizar a combinação mais específica, o Gerenciamento de Ativos primeiro verifica uma possível correspondência do campo **Ofício**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho de manutenção**. Se nenhuma correspondência for encontrada, ele verifica uma correspondência do campo **Tipo de cargo de manutenção** e assim por diante (**Ofício**, em seguida, **Grade do tipo de trabalho de manutenção**, em seguida, **Tipo de trabalho de manutenção**, em seguida, **Ativo**, **Modelo**, **Fabricante** e, em seguida, **Tipo de ativo**). Se nenhuma correspondência for encontrada, será usado o registro padrão onde somente o tipo de trabalho de manutenção está selecionado.

Uma ID de atividade do projeto é relacionada automaticamente a cada linha padrão do tipo de trabalho de manutenção que você cria. A atividade do projeto é criada no projeto de previsão que é selecionado no campo **Projeto de previsão de manutenção** na guia **Ativos** da página **Parâmetros do gerenciamento de ativos**. A finalidade da atividade do projeto é gerenciar previsões em horas, itens e despesas em relação às ordens de serviço. As previsões do tipo de trabalho de manutenção são transferidas automaticamente para a linha da ordem de serviço e são copiadas do projeto de previsão para o projeto da ordem de serviço criada para a linha da ordem de serviço. A finalidade da atividade do projeto é gerenciar previsões em relação às ordens de serviço.

Você pode configurar um trabalho em lotes para atualizar as referências padrão do tipo de trabalho de manutenção em intervalos regulares, ou pode executar o trabalho manualmente. Para criar um trabalho em lotes ou executar uma atualização manual, selecione **Gerenciamento de ativos** \> **Periódico** \> **Manutenção preventiva** \> **Atualizar referências padrão do tipo de trabalho de manutenção**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Visão geral de tipos de trabalho de manutenção relacionados a ativos

Após criar as combinações padrão do tipo de trabalho de manutenção necessárias, você pode usar a página **Todos os ativos** para obter uma visão geral do padrão do tipo de trabalho de manutenção atual que é relacionado a um ativo específico. A visão geral mostra todas as combinações padrão do tipo de trabalho de manutenção que podem ser usadas no tipo de ativo selecionado para o ativo. Essas combinações incluem as combinações que têm variações de grades do tipo de trabalho de manutenção e ofício do trabalho de manutenção.

1. Selecione **Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**.
2. Na lista, selecione o ativo para ver uma visão geral de combinações do tipo de trabalho de manutenção.
3. No Painel de Ação, na guia **Geral**, no grupo **Informações Relacionadas**, selecione **Tipos de trabalho de manutenção**.

    O painel esquerdo da página **Tipos de trabalho de manutenção do ativo** mostra uma lista de todas as combinações do tipo de trabalho de manutenção relacionadas o ativo selecionado.

4. Selecione uma combinação do tipo de trabalho de manutenção para ver a configuração relacionada das listas de verificação de manutenção, previsões e ferramentas. A seção **Detalhes** na Guia Rápida **Padrões do tipo de trabalho de manutenção** mostra o número de listas de verificação de manutenção relacionadas, horas previstas, itens etc, que estão relacionados à combinação do tipo de trabalho de manutenção selecionada.
5. Para exibir detalhes do tipo de trabalho de manutenção selecionado, selecione **Tipos de trabalhos de manutenção**. 

![Página Tipos de trabalho de manutenção do ativo](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Atualização automática das previsões do tipo de trabalho de manutenção

No Gerenciamento de Ativos, você pode atualizar automaticamente todas as alterações nas previsões do tipo de trabalho de manutenção para custos de horas, custos de itens e despesas que foram atualizadas em outros módulos. Dessa forma, você ajuda a garantir que suas previsões do tipo de trabalho de manutenção sempre usem os preços de custos mais recentes.

1. Selecione **Gerenciamento de ativos** \> **Periódico** \> **Previsão** \> **Atualizar previsão do tipo de trabalho de manutenção**.
2. Na caixa de diálogo **Atualizar previsão do tipo de trabalho de manutenção**, na Guia Rápida **Registros a serem incluídos**, você pode adicionar seleções para tipos de trabalho de manutenção específicos, conforme necessário. Selecione **Filtro** e **Selecionar** para fazer as seleções.
3. Na Guia Rápida **Executar em segundo plano**, você pode configurar a atualização automática como um trabalho em lote, conforme necessário.
4. Selecione **OK** para iniciar a atualização da previsão.
