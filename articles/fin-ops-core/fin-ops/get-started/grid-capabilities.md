---
title: Recursos de grade
description: Este tópico descreve vários recursos avançados do controle de grade. O novo recurso de grade deve estar habilitado para ter acesso a esses recursos.
author: jasongre
manager: AnnBe
ms.date: 01/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b49d7823f48bcc9cdbb56b87d5fa72d46ddfa15c
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019631"
---
# <a name="grid-capabilites"></a>Recursos de grade

[!include [banner](../includes/banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que podem ser usados para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

-  Calculando totais
-  Agrupamento de dados
-  Digitação à frente do sistema
-  Avaliação de expressões matemáticas 

## <a name="calculating-totals"></a>Calculando totais
Nos aplicativos do Finance and Operations, os usuários podem ver os totais na parte inferior das colunas numéricas em grades. Esses totais são mostrados em uma seção de rodapé na parte inferior da grade. 

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Cada grade tabular nos aplicativos do Finance and Operations tem uma área de rodapé na parte inferior que pode mostrar informações valiosas relacionadas aos dados que estão sendo exibidos. Essas informações incluem: 
-  O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
-  Totais gerais na parte inferior das colunas numéricas configuradas
-  O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas pode ser facilmente ativado. Para mostrar o rodapé de uma grade, clique com o botão direito do mouse em um cabeçalho de coluna na grade e selecione a opção **Mostrar rodapé**. Depois que o rodapé tiver sido ativado para uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé, o que pode ser feito clicando com o botão direito do mouse em um cabeçalho de coluna e selecionando **Ocultar rodapé**.  Observe que o posicionamento da ação **Mostrar rodapé/Ocultar rodapé** deve ser realocado em uma atualização futura. 

### <a name="specifying-columns-with-totals"></a>Especificando colunas com totais
No momento, nenhuma coluna será configurada para mostrar os totais por padrão. Pelo contrário, essa atividade é considerada de configuração única, semelhante ao ajuste das larguras das colunas em grades. Após especificação de que deseja ver os totais de uma coluna, essa configuração será lembrada na próxima vez que você visitar a página.  

Há duas maneiras de configurar uma coluna para mostrar um total: 
1.  Clique com o botão direito do mouse na coluna na qual você está interessado em ver um total e selecione **Totalizar esta coluna**. Essa ação terá três consequências. Primeira, ela tornará o rodapé visível. Segunda, ela salvará sua preferência para ver um total nessa coluna. Terceira, essa ação iniciará um cálculo de totais para essa coluna e quaisquer outras anteriormente configuradas para ver os totais. O tempo necessário para que um total seja mostrado está diretamente relacionado ao tamanho do conjunto de dados que você está totalizando.  

2.  Depois que o rodapé for exibido, se desejar, você poderá clicar no botão **Mostrar total** na região do rodapé, na parte inferior da coluna da qual você está interessado em ver o total. Se não houver colunas configuradas, o botão **Mostrar total** ficará visível para todas as colunas numéricas. Depois que houver pelo menos uma coluna configurada para totais, os botões **Mostrar total** só ficarão disponíveis com a passagem do mouse ou na focalização. Essa ação simplesmente salva sua preferência de ver um total nessa coluna para futuras visitas a essa página, e esse estado é indicado pelo traço que aparece no rodapé dessa coluna (ou um total será mostrado imediatamente se o conjunto de dados for suficientemente pequeno).

Se você cometer um erro e não quiser mais ver um total em uma determinada coluna, clique com o botão direito do mouse na coluna e selecione **Ocultar total** ou selecione o botão **Ocultar total** no rodapé dessa coluna. Essa preferência também será salva para futuras visitas à página. 

### <a name="calculating-totals"></a>Calculando totais
Quando você acessa uma página com o rodapé visível e as colunas já configuradas para totais, os totais podem ou não ser mostrados no rodapé. O comportamento depende do tamanho do conjunto de dados na página. Se o conjunto de dados for suficientemente pequeno, os totais serão mostrados automaticamente, com o número de linhas no conjunto de dados. Se houver traços no rodapé sob as colunas que você configurou para os totais, significa que o conjunto de dados é muito grande para que o sistema mostre os totais imediatamente e uma ação explícita é necessária para calcular os totais. Para isso, clique no botão **Calcular**, no rodapé, ou clique com o botão direito do mouse em uma coluna para a qual deseja o total e selecione **Totalizar esta coluna**.  

Se o cálculo estiver demorando muito, você poderá cancelar a operação selecionando o botão **Cancelar**. Às vezes, no entanto, o conjunto de dados será grande demais para calcular os totais (um limite imposto pela sua organização) e você será notificado para filtrar mais os dados.

Os totais serão atualizados automaticamente à medida que você atualizar, excluir ou criar linhas no conjunto de dados.  

## <a name="grouping-data"></a>Agrupamento de dados
Geralmente, os usuários corporativos precisam executar análises ad hoc de dados. Embora isso possa ser feito por meio da exportação de dados do Microsoft Excel e usando tabelas dinâmicas, o recurso **Agrupamento** nas grades tabulares permite que os usuários organizem seus dados de modos atrativos em seus aplicativos do Finance and Operations. Como esse recurso estende o recurso **Totais** , o **Agrupamento** também permite obter insights significativos sobre os dados fornecendo subtotais no nível de grupo.

Para usar esse recurso, clique com o botão direito do mouse na coluna pela qual deseja agrupar e selecione **Agrupar por esta coluna**. Essa ação vai classificar os dados pela coluna selecionada, adicionar uma nova coluna Agrupar por ao início da grade e inserir "linhas do cabeçalho" no início de cada grupo. Essas linhas de cabeçalho fornecem as seguintes informações sobre cada grupo: 
-  Valor de dados para o grupo 
-  Rótulo da coluna. Isso será especialmente útil quando houver suporte para vários níveis de agrupamento.  
-  Número de linhas de dados neste grupo
-  Subtotais de qualquer coluna configurada para mostrar totais

Com [Exibições salvas](saved-views.md) habilitadas, esse agrupamento pode ser salvo por personalização como parte de uma exibição para acesso rápido na próxima vez que você visitar a página.  

Se você selecionar **Agrupar por esta coluna** em uma coluna diferente, o agrupamento original será substituído, pois só há suporte para o nível de agrupamento na versão 10.0.9/Atualização 33 da plataforma.

Para desfazer o agrupamento em uma grade, clique com o botão direito do mouse na coluna de agrupamento e selecione **Desagrupar**.  


## <a name="evaluating-math-expressions"></a>Avaliação de expressões matemáticas
Como um acelerador de produtividade, o usuário pode inserir fórmulas matemáticas em células numéricas de uma grade, em vez de fazer cálculos em um aplicativo fora do sistema. Por exemplo, você pode inserir **=15\*4** e usar tab para sair do campo. O sistema avaliará a expressão e salvará um valor de "60" para o campo.

Para que o sistema reconheça um valor como uma expressão, inicie o valor com um sinal de igualdade (**=**). Para obter mais detalhes sobre os operadores e a sintaxe permitidos, consulte [Símbolos matemáticos permitidos](http://redhivesoftware.github.io/math-expression-evaluator/#supported-maths-symbols).  
