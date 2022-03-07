---
title: Upgrade de planejamento de orçamento
description: Este tópico explica o que deve ser reconfigurado e também descreve os novos recursos que devem ser considerados após a conclusão da atualização.
author: panolte
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 272923
ms.assetid: 17cdfe74-bdfd-466a-9bdd-c12583f250c7
ms.search.region: Global
ms.author: panolte
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: c52de15faddd797d31d0875882863b8fe37a7d173b38be058e51a06b2e7fe078
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769182"
---
# <a name="upgrade-budget-planning"></a>Atualizar planejamento de orçamento

[!include [banner](../includes/banner.md)]

Há diferenças significativas no planejamento do orçamento entre o Microsoft Dynamics AX 2012 e o Dynamics 365 Finance. Alguns recursos não foram atualizados e, portanto, não requerem reconfiguração. Este tópico explica o que deve ser reconfigurado e também descreve os novos recursos que devem ser considerados após a conclusão da atualização.  

O planejamento de orçamento no Finance tem vários aprimoramentos que não estavam disponíveis no Dynamics AX 2012. Este tópico explica as alterações a serem feitas pelos clientes que estão realizando a atualização. Também indica os novos recursos que devem ser considerados no processo de atualização. Por causa da extensão das alterações, os planos de orçamento existentes não poderão ser abertos até que sejam realizadas as alterações descritas neste tópico. No entanto, os relatórios devem continuar a funcionar e não requerem alterações adicionais.

## <a name="overview-of-changes"></a>Visão geral das alterações
Alterações significativas foram realizadas no Orçamento do Finance and Operations. Essas alterações devem fazer com que o planejamento de orçamento seja mais fácil de configurar e mais reutilizável, de modo a reduzir a configuração e manutenção anual. As seguintes áreas no AX 2012 não existem mais no Finance:

-   Modelos de plano de orçamento (configuração de planejamento de orçamento)
-   Pastas de plano de orçamento (configuração de planejamento de orçamento)
-   Restrições ao cenário (configuração de planejamento de orçamento)
-   Modelos para regras de fase e modelos de planejamento de orçamento (processo de planejamento de orçamento)
-   Campos de matriz dos modelos de planilha
-   Assistente de modelo do Microsoft Excel de plano de orçamento

Alguns novos conceitos não podem ser diretamente atualizados da funcionalidade anterior. Portanto, é preciso concluir alguma reconfiguração para tratar esses conceitos novos. As seções a seguir descrevem os conceitos que substituíram os itens na lista precedente.

### <a name="columns"></a>Colunas

As colunas são um novo conceito que substitui partes do modelo do Excel e campos de matriz. Colunas podem representar um período, um mês, um trimestre, um ano ou todo o período. A referência de tempo é dinâmica. Indica um período ou ano relativos na referência ao processo de orçamento. Por exemplo, a coluna **Janeiro do Ano Anterior** faz referência ao período fiscal 1 por ano -1. Uma coluna é específica para um cenário de plano de orçamento, como valores reais ou solicitação de orçamento.

### <a name="layouts"></a>Layouts

Os layouts são um novo conceito que substitui o modelo do Excel. Os layouts contêm as colunas que definem quais períodos e dados de orçamento ou valores reais devem ser mostrados. Os layouts também são compartilhados entre o cliente e o suplemento do Excel. Sendo assim, a experiência do usuário ao inserir ou exibir dados no cliente do Finance and Operations é melhor do que a experiência do usuário no AX 2012. Para inserir dados no cliente do Finance, você não estará mais limitado a exibir e inserir um único cenário em uma exibição de transação. Em vez disso, uma exibição de comparação permite exibir e inserir facilmente valores para vários períodos e contas ao mesmo tempo. Os layouts também podem ser definidos para que você possa inserir e exibir a moeda, comentários e outros dados opcionais. Os layouts também permitem definir quais dimensões contábeis e descrições de dimensão devem ser exibidas. Além disso, os layouts incorporam restrições ao cenário para definir quais colunas em um modelo podem ser editadas e quais colunas devem estar disponíveis no Excel. Após a definição de um layout, um modelo é gerado para ele. Esse modelo, por sua vez, cria o modelo correspondente do Excel. Com isso, você pode editar o modelo do Excel para incorporar mais fórmulas e formatações e, depois, carregá-lo novamente. Os layouts são atribuídos a cada regra de fase na página **Processo de planejamento de orçamento**. Portanto, os layouts substituem os modelos, que foram atribuídos e usados de forma semelhante.

### <a name="budget-planning-processes"></a>Processos de planejamento de orçamento

Os processos de planejamento de orçamento são basicamente os mesmos do AX 2012. A mudança mais significativa é a substituição dos modelos por layouts. Se qualquer processo foi concluído anteriormente no AX 2012, ele será atualizado para um status de "em andamento" para que as alterações possam ser feitas. Você precisa atribuir layouts necessários para cada regra de fase para determinar quais cenários e períodos de tempo aparecerão quando o plano estiver no cliente. Os layouts também determinam qual modelo do Excel é aberto fora do Dynamic 365 for Finance a fim de que você possa exibir o orçamento. A **Estrutura da conta padrão** é um novo campo obrigatório do processo de planejamento de orçamento. Para cada processo de planejamento de orçamento, atribua uma estrutura de conta principal que deve ser usada no orçamento.

### <a name="attachments"></a>Anexos

No AX 2012, os documentos de justificativa foram salvos em uma pasta de anexos. Nenhum documento de justificativa anterior é atualizado. Agora os documentos de justificativa são armazenados no banco de dados. Se for preciso salvar essas informações na versão atualizada, carregue os documentos de justificativa finais de cada plano como anexo usando o botão **Justificativa** no Painel de Ação. No AX 2012, as planilhas do Excel de cada plano de orçamento foram criadas com base no modelo. No Finance, todos os planos abrem uma cópia do layout. No entanto, nenhuma alteração no arquivo do Excel é salva. Todas as fórmulas ou informações de apoio usadas por plano devem ser adicionadas por meio de comentários, documento de justificativa ou algum outro processo suplementar.

## <a name="configuring-an-upgraded-environment-from-ax-2012"></a>Configuração do ambiente atualizado no AX 2012
Para ajudar a determinar como configurar o sistema atualizado, o exemplo a seguir usa um processo de orçamento atualizado de dados de demonstração do AX 2012. Os dados de configuração padrão das colunas foram criados para ajudar no processo de atualização. É possível atualizar ou excluir esses dados padrão caso eles não atendam a seus requisitos de configuração. **Observação:** há novos campos obrigatórios que não serão definidos no sistema. Se você ficar preso em uma página, como a **Configuração de planejamento de orçamento**, e não conseguir sair, é possível fechar o navegador e depois reabri-lo em uma página diferente para inserir os detalhes na ordem correta. Há campos obrigatórios que ainda não estão definidos. Portanto, podem ocorrer problemas até que tudo esteja configurado e todos os campos obrigatórios tenham sido definidos. Este tópico explica como definir esses campos, conforme necessário. Veja aqui alguns desses campos obrigatórios:

-   Página **Processo de planejamento de orçamento**: campo **Estrutura da conta padrão**
-   Página **Processo de planejamento de orçamento**: campo **Layout** na Guia Rápida **Layouts e regras da fase de planejamento de orçamento**

### <a name="define-columns-and-layouts"></a>Definir colunas e layouts

1. Na página **Configuração de planejamento de orçamento**, clique na guia **Colunas**. Como parte da atualização, novas colunas são criadas automaticamente com base nas suas linhas de plano de orçamento. Agora as colunas usam datas dinâmicas, quando o tempo e o ano são compensados a partir do ano fiscal definido no processo de planejamento de orçamento. **Observação:** por razões de desempenho durante a atualização, presume-se que todos os ciclos de orçamento representem anos civis, não anos fiscais. Se usar anos fiscais, você deve fazer edições para mapear corretamente as colunas para o seu ano fiscal. Por exemplo, os seguintes elementos existiam no AX 2012:
   -   Cenários do plano de orçamento: valores reais, linha de base, solicitação de orçamento, orçamento aprovado
   -   Linhas de plano de orçamento para todos os cenários em 2017 e valores reais para 2017 e 2016

   As colunas a seguir serão criadas no Finance and Operations:

   | Nome da coluna    | Cenário do plano de orçamento | Período de tempo da coluna | Compensação anual |
   |----------------|----------------------|--------------------|-------------|
   | Cenário de Janeiro 1 | Reais              | 1                  | 0           |
   | Cenário de Janeiro 2 | Linha de base             | 1                  | 0           |
   | Cenário de Janeiro 3 | Solicitação de orçamento       | 1                  | 0           |
   | Cenário de Janeiro 4 | Orçamento aprovado      | 1                  | 0           |
   | Cenário de Janeiro 5 | Reais              | 1                  | -1          |
   | Cenário de fevereiro 1 | Reais              | 1                  | 0           |
   | ...            | ...                  | ...                | ...         |

   Neste exemplo, uma coluna nomeada **Cenário de Janeiro 1** é criada para os dados de transação de plano de orçamento mais recentes encontrados quando há transações em janeiro. Uma coluna semelhante é criada para cada cenário com dados. Quando houver colunas para todos os períodos desse ano, serão criadas colunas para os anos anteriores.
2. Altere os nomes e as descrições da coluna e qualquer outro detalhe manualmente no cliente ou realizando atualizações em massa por meio do suplemento do Excel que indica a entidade de dados das colunas de plano de orçamento. Qualquer filtro definido anteriormente para campos de matriz agora é definido nas colunas.
3. Crie um layout de plano de orçamento. Um layout indica várias colunas para definir a exibição que aparece no Excel e no cliente. O layout requer primeiramente que você especifique o conjunto de dimensões contábeis para determinar quais dimensões financeiras podem ser inseridas. Após a especificação do conjunto de dimensões, clique em **Descrições** para selecionar as descrições de dimensão a serem incluídas no layout.
4. Na Guia Rápida **Elementos do layout**, clique em **Adicionar** para adicionar os metadados de cada linha, como uma moeda, um comentário ou uma classe de orçamento que determina as linhas de receita versus despesa. Em seguida, adicione as colunas do período de tempo e os cenários que se aplicam a esse clico e fase de orçamento. Você pode fazer essas alterações manualmente no cliente ou por meio do suplemento do Excel que indica a entidade de dados dos elementos de layout do plano de orçamento.
5. Para cada elemento do layout, determine se a coluna deve ser editável e se ela também deve aparecer na pasta de trabalho do Excel desse layout. **Observação:** no caso dos nossos planos históricos, talvez você deseje considerar um layout que mostre 12 colunas mensais para qualquer cenário de plano de orçamento desse processo.

### <a name="update-budget-planning-processes-to-use-the-appropriate-layout-for-each-budget-stage"></a>Atualizar processos de planejamento de orçamento para usar o layout apropriado de cada fase de orçamento

1.  Na página **Processo de planejamento de orçamento**, selecione o processo a ser configurado.
2.  No Painel de Ação, clique em **Editar**.
3.  Especifique a estrutura de conta padrão desse processo de orçamento. A **Estrutura da conta padrão** é um novo campo obrigatório que deve ser definido.
4.  Na Guia Rápida **Layouts e regras da fase de planejamento de orçamento**, no campo **Layout**, selecione um layout que foi previamente configurado e que é apropriado a esse estágio.
5.  Continue a selecionar os mesmos layouts ou layouts diferentes para várias fases de planejamento de orçamento e depois salve suas alterações.

## <a name="additional-features-to-consider-in-your-budgeting-process"></a>Recursos adicionais a serem considerados no processo de orçamento
### <a name="budget-planning-workspace"></a>Espaços de trabalho do planejamento de orçamento

Esse espaço de trabalho foi desenvolvido para o proprietário de orçamento e os contribuintes individuais de orçamento. Apresenta vínculos com qualquer documento de orçamento que precise de sua atenção. Também apresenta relatórios e indicadores-chave de desempenho (KPIs) do processo de orçamento. O administrador de orçamento pode definir o processo de planejamento de orçamento atual para todos os usuários na página **Parâmetros de orçamento**. Na guia **Configurações de espaço de trabalho**, a Guia Rápida **Plano de orçamento** inclui um campo no qual você pode selecionar o processo de planejamento de orçamento.

### <a name="alternate-layouts"></a>Layouts alternativos

Os layouts alternativos são um novo recurso que permite exibir planos em diferentes layouts. Um ou mais layouts podem ser fornecidos como opções. Com isso, é possível exibir um plano de orçamento em um layout mensal ou em um layout trimestral. Defina layouts alternativos na Guia Rápida **Layouts e regras da fase de planejamento de orçamento** na página **Processo de planejamento de orçamento**.

### <a name="budget-milestones"></a>Marcos de orçamento

Como parte do processo de orçamento, é vital que você entenda os principais dados e prazos finais. Agora você pode configurar as datas para que elas tenham descrições. Os usuários de orçamento verão essas descrições ao abrirem os orçamentos para editar ou exibir qualquer coisa que seja atribuída a eles.

### <a name="copy-from-budget-plan-allocation"></a>Copiar da alocação de plano de orçamento

Um novo método de alocação permite distribuir de um plano principal a um plano secundário sem a necessidade de passar por um nível intermediário na hierarquia. Esse método é útil principalmente para clientes que criaram anteriormente a dimensão financeira apenas para distribuição e aprovação de orçamento.

### <a name="generating-budget-plans-from-new-budget-sources"></a>Gerar planos de orçamento a partir de novas fontes de orçamento

As seguintes opções foram adicionadas como processos periódicos. Essas opções permitem gerar um plano de orçamento por meio de dados existentes de outro módulo como o ponto inicial:

-   Gerar plano de orçamento a partir da previsão de demanda
-   Gerar plano de orçamento a partir da previsão de fornecimento
-   Gerar plano de orçamento a partir do projeto
-   Gerar plano de orçamento a partir do registro de orçamento

### <a name="more-complete-tracking-of-amounts"></a>Rastreamento mais completo dos valores

No AX 2012, o planejamento de orçamento apresentava um único valor de plano que era armazenado para cada valor. No Finance, o modelo de dados foi expandido. Agora há uma moeda contábil, uma moeda da transação e valores de moeda de relatório para cada valor. Durante a atualização, essas novas colunas são preenchidas automaticamente para dados existentes.

### <a name="do-not-convert-currency-in-aggregation"></a>Não converter moeda em agregação

Geralmente, quando um plano secundário é agregado ao nível principal, os valores são convertidos automaticamente da moeda de transação para a moeda contábil da organização. Ao definir a opção **Não converter moeda em agregação** como **Não**, os valores agregados permanecem na moeda original. Assim, essa opção permite ajustes mais precisos que são afetados por flutuações na taxa de câmbio.

### <a name="looking-back-from-a-budget-plan-to-other-modules-that-contributed-to-the-budget"></a>Revisão do plano de orçamento para outros módulos que contribuíram para o orçamento

Os planos de orçamento podem ser criados com base na demanda ou em previsões de fornecimento, projeto e outras áreas. A consulta Planos de orçamento por conjunto de dimensões inclui várias opções que permitem executar consultas para identificar os dados que foram a fonte do plano de orçamento.

### <a name="overwrite-or-append-to-plan-for-allocation-schedules"></a>Substituir ou anexar a um plano de agendas de alocação

Se houver várias fontes para valores que devem ser distribuídos, você pode especificar que os valores devem ser aditivos. Nesse caso, os valores não substituirão qualquer valor existente. Em vez disso, eles serão anexados aos valores existentes.

### <a name="default-financial-dimension-set-for-budget-planning-configuration"></a>Conjunto de dimensões financeiras padrão da configuração de planejamento de orçamento

A página **Configuração de planejamento de orçamento** agora inclui um campo no qual é possível especificar o conjunto de dimensões financeiras padrão. Embora esse campo seja opcional, ele pode ser necessário para determinadas consultas. Também pode ser necessário para agrupar ou filtrar o agrupamento de relatórios por conjunto de dimensões.

### <a name="data-entities"></a>Entidades de dados

Várias entidades de dados foram adicionadas para permitir a rápida implementação do planejamento de orçamento. As entidades também permitem que você faça alterações por meio do Excel. Por isso, você não precisa criar um item de cada vez por meio do cliente. Veja a lista das novas entidades de dados:

-   Nome da entidade
-   Parâmetros de orçamento
-   Parâmetro de plano de orçamento
-   Cenários do plano de orçamento
-   Fases do plano de orçamento
-   Fase do fluxo de trabalho do plano de orçamento
-   Agendas de alocação do plano de orçamento
-   Alocações de fases do plano de orçamento
-   Prioridades do plano de orçamento
-   Colunas do plano de orçamento
-   Elementos de layouts do plano de orçamento






[!INCLUDE[footer-include](../../../includes/footer-banner.md)]