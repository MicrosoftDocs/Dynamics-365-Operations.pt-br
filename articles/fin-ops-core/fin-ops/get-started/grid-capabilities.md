---
title: Recursos de grade
description: Este tópico descreve vários recursos avançados do controle de grade. O novo recurso de grade deve estar habilitado para ter acesso a esses recursos.
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
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
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036256"
---
# <a name="grid-capabilities"></a>Recursos de grade

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O novo controle de grade fornece vários recursos úteis e eficientes que podem ser usados para melhorar a produtividade do usuário, construir exibições mais interessantes dos dados e obter insights significativos sobre seus dados. Este artigo abordará os seguintes recursos: 

-  Calculando totais
-  Agrupamento de dados
-  Digitação à frente do sistema
-  Avaliação de expressões matemáticas 

## <a name="calculating-totals"></a>Calculando totais
Nos aplicativos do Finance and Operations, os usuários podem ver os totais na parte inferior das colunas numéricas em grades. Esses totais são mostrados em uma seção de rodapé na parte inferior da grade. 

### <a name="showing-the-grid-footer"></a>Mostrando o rodapé da grade
Existe uma área de rodapé na parte inferior de cada grade tabular nos aplicativos do Finance and Operations. O rodapé pode mostrar informações valiosas relacionadas aos dados que aparecem na grade. Veja alguns exemplos dessas informações:

- O número de linhas selecionadas na tabela (quando mais de um registro é selecionado)
- Totais gerais na parte inferior das colunas numéricas configuradas
- O número de linhas no conjunto de dados 

Esse rodapé é ocultado por padrão, mas pode ser facilmente ativado. Para mostrar o rodapé de uma grade, clique com o botão direito do mouse em um cabeçalho de coluna na grade e selecione a opção **Mostrar rodapé**. Depois que o rodapé tiver sido ativado para uma determinada grade, essa configuração será lembrada até que o usuário opte por ocultar o rodapé, o que pode ser feito clicando com o botão direito do mouse em um cabeçalho de coluna e selecionando **Ocultar rodapé**.  Observe que o posicionamento da ação **Mostrar rodapé/Ocultar rodapé** deve ser realocado em uma atualização futura. 

### <a name="specifying-columns-with-totals"></a>Especificando colunas com totais
No momento, nenhuma coluna será configurada para mostrar os totais por padrão. Pelo contrário, essa atividade é considerada de configuração única, semelhante ao ajuste das larguras das colunas em grades. Após especificação de que deseja ver os totais de uma coluna, essa configuração será lembrada na próxima vez que você visitar a página.  

Há duas maneiras de configurar uma coluna para mostrar um total: 

- Clique com o botão direito do mouse na coluna da qual você deseja ver um total e selecione **Totalizar esta coluna**. Essa ação causa três eventos:

    1. O rodapé fica visível. 
    2. Sua preferência para ver um total dessa coluna é salva. 
    3. Um cálculo de totais é iniciado para essa coluna e quaisquer outras colunas que você configurou anteriormente para ver totais. O tempo necessário para mostrar um total depende do tamanho do conjunto de dados que você está totalizando.

- Depois que o rodapé estiver visível, selecione **Mostrar total** na área do rodapé na parte inferior da coluna da qual você deseja ver um total. Se não houver colunas configuradas, o botão **Mostrar total** estará disponível para todas as colunas numéricas. 

    Depois que houver pelo menos uma coluna configurada para totais, os botões **Mostrar total** só ficarão disponíveis com a passagem do mouse ou na focalização. A ação de selecionar **Mostrar total** só salva sua preferência para ver um total nesta coluna, a fim de que a preferência seja aplicada durante futuras visitas à página. No rodapé, esse estado é indicado por um traço que aparece na coluna. (Como alternativa, se o conjunto de dados for pequeno o suficiente, um total será mostrado imediatamente.)

Se você cometer um erro e não quiser mais ver um total em uma determinada coluna, clique com o botão direito do mouse na coluna e selecione **Ocultar total** ou selecione o botão **Ocultar total** no rodapé dessa coluna. Essa preferência também será salva para futuras visitas à página. 

### <a name="calculating-totals"></a>Calculando totais
Quando você acessa uma página com o rodapé visível e as colunas já configuradas para totais, os totais podem ou não ser mostrados no rodapé. O comportamento depende do tamanho do conjunto de dados na página. Se o conjunto de dados for suficientemente pequeno, os totais serão mostrados automaticamente, com o número de linhas no conjunto de dados. Se houver traços no rodapé sob as colunas que você configurou para os totais, significa que o conjunto de dados é muito grande para que o sistema mostre os totais imediatamente e uma ação explícita é necessária para calcular os totais. Para isso, clique no botão **Calcular**, no rodapé, ou clique com o botão direito do mouse em uma coluna para a qual deseja o total e selecione **Totalizar esta coluna**.  

Se o cálculo estiver demorando muito, você poderá cancelar a operação selecionando o botão **Cancelar**. Às vezes, no entanto, o conjunto de dados será grande demais para calcular os totais (um limite imposto pela sua organização) e você será notificado para filtrar mais os dados.

Os totais serão atualizados automaticamente à medida que você atualizar, excluir ou criar linhas no conjunto de dados.  

## <a name="grouping-data"></a>Agrupamento de dados
Geralmente, os usuários corporativos precisam executar análises ad hoc de dados. Embora isso possa ser feito por meio da exportação de dados do Microsoft Excel e usando tabelas dinâmicas, o recurso **Agrupamento** nas grades tabulares permite que os usuários organizem seus dados de modos atrativos em seus aplicativos do Finance and Operations. Como esse recurso estende o recurso **Totais** , o **Agrupamento** também permite obter insights significativos sobre os dados fornecendo subtotais no nível de grupo.

Para usar esse recurso, clique com o botão direito do mouse na coluna pela qual deseja agrupar e selecione **Agrupar por esta coluna**. Essa ação vai classificar os dados pela coluna selecionada, adicionar uma nova coluna Agrupar por ao início da grade e inserir "linhas do cabeçalho" no início de cada grupo. Essas linhas de cabeçalho fornecem as seguintes informações sobre cada grupo: 
-  Valor de dados para o grupo 
-  Etiqueta da coluna (Essas informações serão especialmente úteis depois que vários níveis de agrupamento forem compatíveis.)
-  Número de linhas de dados neste grupo
-  Subtotais de qualquer coluna configurada para mostrar totais

Com [Exibições salvas](saved-views.md) habilitadas, esse agrupamento pode ser salvo por personalização como parte de uma exibição para acesso rápido na próxima vez que você visitar a página.  

Se você selecionar **Agrupar por esta coluna** em uma coluna diferente, o agrupamento original será substituído, pois só há suporte para um nível de agrupamento na versão 10.0.9 com atualização 33 da plataforma.

Para desfazer o agrupamento em uma grade, clique com o botão direito do mouse na coluna de agrupamento e selecione **Desagrupar**.  


## <a name="evaluating-math-expressions"></a>Avaliação de expressões matemáticas
Como um acelerador de produtividade, os usuários podem inserir fórmulas matemáticas em células numéricas em uma grade. Eles não precisam fazer o cálculo em um aplicativo fora do sistema. Por exemplo, se você digitar **=15\*4** e pressionar a tecla **Tab** para sair do campo, o sistema avaliará a expressão e salvará um valor de **60** para o campo.

Para que o sistema reconheça um valor como uma expressão, inicie o valor com um sinal de igualdade (**=**). Para obter mais detalhes sobre os operadores e a sintaxe permitidos, consulte [Símbolos matemáticos permitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).  
