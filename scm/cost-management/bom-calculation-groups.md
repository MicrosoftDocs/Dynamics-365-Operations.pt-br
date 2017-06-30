---
title: "Grupos de cálculos de BOM"
description: "Este artigo fornece informações sobre grupos de cálculos para listas de materiais (BOMs) e como configurá-las. Para executar um cálculo de BOM, você deve configurar grupos de cálculo e atribuí-los a itens individuais ou definir um grupo de cálculo padrão. As configurações de cálculo a partir do grupo de cálculo são usadas como valores padrão na página Cálculo de BOM no momento do cálculo de BOM."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3372c22d6ed90e7669f1335fdd3366b8e167ad27
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="bom-calculations-groups"></a>Grupos de cálculos de BOM

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre grupos de cálculos para listas de materiais (BOMs) e como configurá-las. Para executar um cálculo de BOM, você deve configurar grupos de cálculo e atribuí-los a itens individuais ou definir um grupo de cálculo padrão. As configurações de cálculo a partir do grupo de cálculo são usadas como valores padrão na página Cálculo de BOM no momento do cálculo de BOM. 

Um grupo de cálculo padrão é necessário na página **Parâmetros de gerenciamento de estoque e de depósito** ou um grupo de cálculo específico do produto é necessário na página **Divulgou detalhes do produto**. O sistema primeiro procura a configuração do grupo de cálculo na página **Divulgou detalhes do produto**. Se ele não localizar um grupo de cálculo, procura na página **Parâmetros de gerenciamento de estoque e de depósito**. Se o sistema não puder encontrar um grupo de cálculo, o usuário recebe uma mensagem de erro durante o cálculo. Um grupo de cálculo contém as regras para o modelo de preço de custo, o modelo de preço de venda e a lista de verificação de avisos. As configurações de cálculo a partir do grupo de cálculo são usadas como valores padrão na página **Cálculo de BOM** no momento do cálculo de BOM.

## <a name="purposes-of-bom-calculation-groups"></a>Fins de grupos de cálculo de BOM
Atribuir um grupo de cálculo de BOM a itens por vários motivos:

-   Ao definir o campo **Modelo de preço de custo**, você indica a fonte dos dados de contribuição de custo de componente adquirido durante o cálculo do custo planejado de um item fabricado. Alguns fabricantes calculam os custos planejados usando os contratos comerciais de preço de compra para componentes comprados ou outra base, como os registros de preço de compra em uma versão de avaliação de custo.
-   Ao definir o campo **Modelo de preço de vendas**, você indica como os dados de item são usados para calcular um preço de vendas sugerido. Você pode especificar o preço de venda do item ou o grupo de custos. Alguns fabricantes desejam calcular o preço de venda sugerido para itens fabricados. O preço de venda calculado pode refletir uma abordagem de preço acumulado baseada no registro de preço de venda do componente. De forma alternativa, o preço de venda calculado pode refletir uma abordagem de custo mais marcação com base no custo e na porcentagem de lucro aplicável do componente, que está associada com o grupo de custo do item.
-   Ao usar o campo **Para explosão**, você indica que um item fabricado deve ser tratado como um item comprado para fins de acúmulo de custo durante o cálculo do BOM. As situações típicas incluem um item comprado que é fabricado ocasionalmente ou um item fabricado que está sendo comprado. O item é inicialmente designado como fabricado para definir informações sobre a BOM e o roteiro, também para dar suporte às ordens de produção do item. No entanto, o sinalizador **Parar explosão** impede que os cálculos de custo usem a BOM e o roteiro do item. Em vez disso, o cálculo de BOM usará os custos do item especificado.

## <a name="calculation-groups"></a>Grupos de cálculo
Definir grupos de cálculo em **Configuração de políticas de custo pré-determinado** em Gerenciamento de custos. Grupos de cálculo são atribuídos aos itens e permitem que você especifique como custo ou preço de venda de componentes, conforme descrito pelo grupo de cálculo é originado do cálculo. Na página **Grupos de cálculo**, você pode definir um modelo de preço de custo, um modelo de preço de custo alternativo, um modelo de preço de venda e avisos.

### <a name="cost-price-model"></a>Modelo de preço de custo

Há quatro opções para o campo **Modelo de preço de custo**:

-   **Preço de custo de item** – o preço de custo da tabela **Produto lançado** é usado, ou a combinação de dimensões de item é usada como o preço de custo.
-   **Preço de compra do item** – o preço de compra do campo **Preço de custo** da guia **Compra** da página **Lista de produtos liberados** é usada.
-   **Contratos comerciais** – você pode configurar contratos comerciais para combinações específicas de itens e fornecedores, ou para sites específicos. Em seguida, quando você seleciona a opção **Contratos comerciais** aqui, o contrato comercial que você criou para o preço de compra com o item será usado.
-   **Preço de estoque** – o valor do estoque atual do item é usado para calcular o custo unitário no cálculo de BOM. Um preço de custo unitário é calculado apenas se a quantidade lançada e a quantidade física forem maior que 0 (zero).

### <a name="alternative-cost-price"></a>Preço de custo alternativo

O campo **Alternar preço de custo** tem as mesmas opções como o campo **Modelo de preço de custo**. No entanto, este campo é usado somente quando um preço não pode ser encontrado no modelo de preço de custo primário.

### <a name="sales-price-model"></a>Modelo de preço de venda

Há duas opções para o cálculo do campo **Preços de vendas**:

-   **Grupo de custos** – quando esta opção for selecionada, o preço de venda é calculado com base no preço de custo e a porcentagem de definição de lucro a partir do grupo de custos.
-   **Preço de venda do item** – quando esta opção for selecionada, as vendas de preços na Guia Rápida **Vender** da tabela do produto liberado é usada.

### <a name="stop-explosion"></a>Parar detalhamento

A caixa de seleção **Parar explosão** é usada para indicar quando um item fabricado deve ser tratado como um item de compra. Normalmente, você deixará a caixa de seleção **Parar explosão** desmarcada. Marque a caixa de seleção para indicar que um item fabricado deve ser tratado como um componente comprado, em vez de como um componente fabricado, para fins de cálculo de BOM. Dependendo do site, os custos do item ainda podem ser estimados usando cálculos de BOM. Explosão de produção e ordens de compra planejadas está parado em BOM cujos componentes estão associados com o cálculo de grupo para o qual a caixa de seleção **Parar explosão** está marcada. O planejamento mestre gera as ordens planejadas na própria linha da BOM, e não nos itens incluídos na BOM. Basicamente, marcando essa caixa de seleção, você especifica que um custo não será adicionado para o cálculo de BOM para itens com esse grupo de cálculo.

### <a name="warnings"></a>Avisos

Na Guia Rápida **Avisos**, você seleciona as opções para as mensagens de aviso que devem ser recebidos pelos usuários quando eles fazem cálculos de BOM. Por exemplo, se você selecionar a caixa de seleção **BOM não**, o usuário receberá um aviso se nenhuma versão da BOM ativa for encontrada para os componentes ou o item pai executado para o cálculo de BOM. Se você selecionar a caixa de seleção **Sem roteiro**, o usuário recebe um aviso se nenhuma versão de roteiro ativa for encontrada. Se você estiver usando recursos em suas operações e roteiros, você pode instruir o sistema para verificar esses recursos. Em seguida, se um recurso não for encontrado em cada linha na rota ativa, o usuário receberá um aviso. Você também pode verificar e marcar para consumo. O consumo é a quantidade de uma rota específica. Normalmente, ele representa a quantidade de tempo que é necessário para executar uma operação específica por um processo de produção. Você pode verificar se um item não tem nenhum custo. Se não houver nenhum preço de custo ativo para um item, sem custo adicional é adicionado para o cálculo de BOM. Você também pode marcar e verificar a idade do preço de custo. Por exemplo, digite **60** para indicar que o preço de custo unitário deve ser reavaliado após 60 dias. Se esse limite for atingido, o sistema gera um aviso. Por exemplo, um preço de custo foi inserido para um item em janeiro deste ano. Se agora for agosto, que é mais de 60 dias após o preço de custo inserido, o usuário receberá um aviso quando o cálculo de BOM for executado. Você pode inserir uma porcentagem no campo **Margem de contribuição mínima**. Esse valor indica o ponto em que a margem mínima de contribuição não está sendo atendida. Se a margem de contribuição para um componente específico não for atendida, o usuário receberá um aviso. Portanto, este campo ajuda a garantir que você não vai competir com os custos e os custos adicionais que podem ser necessários para os itens.
Configuração padrão nos parâmetros de gerenciamento de estoque e depósito
--------------------------------------------------------------

Como os grupos de cálculo são necessários para executar cálculos, você deve configurar um grupo de cálculo padrão nos parâmetros de gerenciamento de estoque. Essa configuração permite que as empresas tenham um grupo de custo padrão e a configuração de todos os itens de lucro. Em seguida, se um determinado item tiver requisitos especiais de cálculo, o usuário pode atribuir um grupo de cálculo diferente para esse item. Normalmente, você pode definir grupos de cálculo em itens de componente BOM em vez de itens de BOM. No entanto, quando as mensagens de aviso são exibidas, grupos de cálculo podem ser aplicados. Um grupo de cálculo que é atribuído aos itens substitui o valor padrão definido nos parâmetros de gerenciamento de estoque. Você pode configurar o parâmetro padrão em **Gerenciamento de custo** &gt; **Configuração de políticas de contabilização de estoque** &gt; **Parâmetros** &gt; **Estatísticas de estoque** &gt; **Grupo de cálculo**. Ao configurar um grupo de configurações padrão, você também pode configurar as condições de aviso que solicitam aos usuários durante o processo de cálculo de BOM, se os componentes selecionados podem causar erros de cálculo.
Exibir mensagens de aviso na página concluída
------------------------------------------

Um cálculo de BOM gera mensagens de aviso. Você pode ver os avisos sobre um item selecionado. Por exemplo, em vendas e marketing, crie uma nova ordem de venda para o item D0001. Em seguida, na linha da ordem de venda, sobre o menu **Atualizar linha**, clique em **Calcular com base em BOM/fórmula** para exibir os detalhes de cálculo e avisos. Você também pode exibir resultados de cálculo BOM na página **Concluído**. Par aas mensagens de erro, apenas duas condições de aviso só se aplicam a itens fabricados e quatro condições de aviso se aplicam a qualquer item:
-   Identifique quando um item fabricado não tem uma BOM ativa.
-   Identifique quando um item fabricado não tem um roteiro ativo.
-   Identifique um aviso quando o item em uma linha de BOM tem uma quantidade de 0 (zero).
-   Identifique um aviso quando o item em uma linha de BOM tem um custo de 0 (zero) ou quando não tem um registro de custo.
-   Identifique um aviso quando o item em uma linha de BOM tem um custo desatualizado. O aviso refletirá uma comparação da data de cálculo para os dias especificados para uma idade máxima do custo.
-   Identifique um aviso quando o item em uma linha de BOM tem menos a porcentagem de lucratividade que você deseja.

Você pode definir vários grupos de cálculo de BOM, dependendo dos seus requisitos para variações em mensagens de aviso. Por exemplo, um grupo de cálculo de BOM pode ser suficiente, com condições de aviso sobre uma BOM ativa, uma quantidade e custo 0 (zero) de componente. As condições de aviso aplicáveis associadas com o grupo de cálculo de BOM podem ser substituídas opcionalmente ao iniciar um cálculo de BOM. Você pode adicionar ou remover uma condição de aviso aplicável. Por exemplo, você pode remover a condição de aviso aplicável sobre um roteiro ativo quando a situação específica não envolve dados de roteiro. **Observação:** tempo e presença incluem uma página **Grupos de cálculo**, mas a página não tem relação com os grupos de cálculo de BOM. Em Horário e presença, os funcionários podem ser atribuídos a grupos de cálculo que refletem o agrupamento de trabalhadores associados com o mesmo supervisor ou gerente. O cálculo dos registros de trabalhadores pode ser feito de forma automática ou manual por um supervisor ou um gerente.




