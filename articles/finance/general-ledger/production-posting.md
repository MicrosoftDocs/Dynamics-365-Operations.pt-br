---
title: Lançamento de pedido de produção
description: Este artigo fornece informações sobre diferentes tipos de lançamento de pedido de produção.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d41725325a82b24c1e5aa6bd2c1a5322f3078ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879614"
---
# <a name="production-postings"></a>Lançamentos de produção

Este artigo fornece informações sobre diferentes tipos de lançamento no processo de pedido de produção.


## <a name="material-consumption"></a>Consumo de materiais

Os materiais são registradas como consumidos durante a produção quando o diário de listas de separação de produção é lançado. Isso cria transações que deduzem o estoque disponível. Nos **Parâmetros de produção**, você pode especificar se os valores de matérias-prima que estão em andamento (chamado WIP) devem ser lançados no razão.

O valor das matérias-primas em andamento (WIP) é lançado nas contas **Custo estimado de materiais consumidos** e **Custo estimado de materiais consumidos, WIP**. O processo de lista de separação para o pedido de produção é uma atualização física das transações de estoque relacionadas ao pedido de produção. Quando um pedido de produção é registrado como encerrado, as transações físicas são revertidas e as transações de estoque relacionadas são atualizadas financeiramente. Quando o diário final é lançado, os tipos de lançamento **Custo dos materiais consumidos** e **Custo dos materiais consumidos, WIP** são usados.

A guia **Produção** na página **Perfis de lançamento de estoque** controla como os pedidos de produção são lançados na contabilidade. Isso é usado quando o campo **Lançamento contábil** é definido como **Item e recurso** ou **Item e categoria** na página **Parâmetros de controle da produção**. 

Para que um diário de lista de separação seja lançado na contabilidade para um pedido de produção, as seguintes condições devem ser atendidas:

-   A caixa de seleção **Lançar lista de separação no razão** deve ser marcada na página **Parâmetros de controle da produção**. Essa configuração pode ser substituída para um local específico na página **Parâmetros de controle de produção por local**.
-   A caixa de seleção **Lançar estoque físico** deve ser marcada na página **Grupos de modelos de item** para o item selecionado na linha do pedido de compra.
-   As contas principais devem ser especificas na página **Perfil de lançamento de estoque** para os seguintes tipos de lançamento:
    -   **Custo estimado de materiais consumidos**
    -   **Custo estimado de materiais consumidos, WIP**

## <a name="time-consumption"></a>Consumo de tempo

O tempo que os trabalhadores passam em trabalhos de produção são registrados no **Diário de cartão de roteiro** ou no **Diário de ficha de trabalho**. Quando esses diários são lançados, o lançamento contábil para uma conta dedicada para recursos que estão em andamento (WIP) é processado. Esse lançamento representa o valor do tempo gasto na ordem de produção. Depois que a ordem de produção é registrada como concluída, as contas WIP são liquidadas.

Existem três maneiras possíveis de lançar o consumo de tempo, dependendo da opção selecionada no campo **Lançamento do razão** na página **Parâmetros de controle da produção**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Relatar mercadorias concluídas e quantidades de erro

Quando um pedido de produção é **Relatado como concluída**, as mercadorias concluídas são atualizadas no estoque por meio do diário **Relatar como concluído**. Se você estiver usando a contabilidade WIP, um diário-razão será lançado para reduzir as contas WIP e aumentar o estoque das mercadorias concluídas. O diário usa o custo padrão foi definido para o produto. Se a opção **Usar preço de custo estimado** for selecionada na página **Parâmetros de controle da produção**, será usado o custo estimado do pedido de produção.

O valor das matérias-primas em andamento (WIP) é lançado nas contas **Custo estimado de fabricação** e **Custo estimado de fabricação, WIP**. O processo **Relatar como concluído** para o pedido de produção é uma atualização física das transações de estoque relacionadas ao pedido de produção. Quando um pedido de produção é encerrado, as transações físicas são revertidas e as transações de estoque relacionadas são atualizadas financeiramente. Quando o diário final é lançado, os tipos de lançamento **Custo de fabricação** e **Custo de fabricação, WIP** são usados.

A guia **Produção** na página **Perfis de lançamento de estoque** é usada para controlar como os pedidos de produção serão lançados na contabilidade. Isso é usado quando o campo **Lançamento contábil** é definido como **Item e recurso** ou **Item e categoria** na página **Parâmetros de controle da produção**. A guia rápida **Razão-Itens** na página **Grupos de produção** pode ser usada para controlar o lançamento de pedidos de produção quando o campo estiver definido como **Perfis de produção**.

Para que um diário **Relatar como concluído** seja lançado na contabilidade para um pedido de produção, as seguintes condições devem ser atendidas:
-   A caixa de seleção **Lançar relatório como concluído no razão** deve ser marcada na página **Parâmetros de controle da produção**. Essa configuração pode ser substituída para um local específico na página **Parâmetros de controle de produção por local**.
-   A caixa de seleção **Lançar estoque físico** deve ser marcada na página **Grupos de modelos de item** para o item selecionado na linha do pedido de compra.
-   As contas principais devem ser especificas na página **Perfil de lançamento de estoque** para os seguintes tipos de lançamento:
    -   **Custo estimado de fabricação**
    -   **Custo estimado de fabricação, WIP**

## <a name="ending-the-production-order"></a>Terminar a ordem de produção

Antes de um pedido de produção ser encerrado, são calculados os custos reais referentes à quantidade produzida. Todos os custos previstos de material, mão-de-obra e custos gerais indiretos são revertidos e substituídos por custos reais. O custo geral do item finalizado será debitado da conta **Custo de fabricação** e creditado na conta **Custo de fabricação, WIP**. Os materiais que foram consumidos durante o pedido de produção são creditados no **Custo dos materiais consumidos** e debitados na conta **Custo de materiais, WIP**.

Se você marcar a caixa de seleção **Trabalho final** ao executar o cálculo de custos, o status da ordem de produção mudará para **Concluído**. Esse status evita que custos adicionais sejam lançados acidentalmente em uma ordem de produção concluída. Você pode especificar que o valor das quantidades de erro relatado como concluído devem ser alocados com as quantidades de mercadoria relatadas como concluídas. Como alternativa, você pode especificar que o valor das quantidades de erros seja lançado em uma conta de sucata dedicada. 

Para especificar uma conta de sucata específica, siga estas etapas:
1.  Vá para **Controle de produção** > **Configuração** > **Parâmetros de controle de produção**.
2.  Selecione a guia **Atualização padrão**.
3.  No campo **Método de sucata**, selecione **Conta de sucata**.
4.  No campo **Conta de sucata**, selecione a conta principal onde a quantidade de sucata para erro deve ser lançada quando o pedido de produção for encerrado. Por exemplo, selecione uma conta de despesas como 510380: sucata de produção.

Para que um diário final seja lançado na contabilidade para um pedido de produção, as seguintes condições devem ser atendidas:
-   As contas principais devem ser especificas na página **Perfil de lançamento de estoque** ou **Grupos de produção** para os seguintes tipos de lançamento:
    -   **Custo de materiais consumidos**
    -   **Custo de materiais consumidos, WIP**
    -   **Custo de fabricação**
    -   **Custo de fabricação, WIP**
-   As contas principais devem ser especificadas na página **Categorias de custo**, **Recursos** ou **Grupos de recursos** para os seguintes tipos:
    -   **Custo de fabricação absorvido**
    -   **Custo de fabricação consumida, WIP**

## <a name="indirect-costs-for-production-orders"></a>Custos indiretos para pedidos de produção

Ao processar transações para um pedido de produção, você pode configurar custos indiretos para capturar custos indiretos ou taxas adicionais na contabilidade. As transações físicas para custos indiretos são reconhecidas no estoque quando você lança um diário de lista de separação ou relatório como diário concluído. As transações financeiras para custos indiretos são reconhecidas no estoque quando você lança o diário final.

Você pode reconhecer custos indiretos em seu consumo de tempo relacionados a diários **Cartão de rota** ou **Ficha de trabalho**. Essas transações são revertidas e lançadas nas contas financeiras quando você encerra o pedido de produção. Para obter mais informações, vá para [Folhas de custos](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Controle do nível de lançamento contábil

Na página **Parâmetros de controle de produção**, você pode usar o campo **Lançamento contábil** para definir o nível de lançamento contábil para processos de produção. 

Os seguintes campos estão disponíveis:

### <a name="item-and-resource"></a>Item e recurso

Quando você seleciona a opção **Item e recurso** no campo **Lançamento contábil**, as contas de lançamento vêm do recurso ou grupo de recursos em operação no roteiro. As contas no recurso específico serão a primeira opção de lançamento. Se uma conta não for especificada, as contas especificadas no grupo de recursos serão usadas. Cada linha de operação em um roteiro pode ter um recurso especificado como **Recurso de avaliação de custo**. Esse recurso é utilizado para determinar a conta a ser utilizada. Essa opção é comumente usada quando uma organização atribui custos operacionais aos recursos. Os custos geralmente são mais altos para os recursos e são usados para ajudar a tomar decisões "fazer versus comprar". Essa é a configuração de lançamento mais detalhada e permite o controle mais granular dos lançamentos e análises muito detalhadas do processo de produção.

### <a name="item-and-category"></a>Item e categoria

Quando você seleciona a opção **Item e categoria** no campo **Lançamento contábil**, as contas de lançamento virão da página **Categoria de custo** relacionada a cada linha no roteiro. Cada linha de operação no roteiro pode ter três categorias de custo: **Tempo de preparação**, **Tempo de execução** e **Quantidade**. Essa opção é comumente usada quando o foco principal de sua organização é a eficiência do processo e a duração da atividade. Essa opção é uma forma mais resumida de lançamento e ainda fornece uma maneira de agrupar os custos em categorias.

### <a name="production-group"></a>Perfil de produção

Quando você seleciona a opção **Grupos de produção** no campo **Lançamento contábil**, as contas de lançamento vêm da página **Grupos de produção**. **Grupos de produção** são geralmente usados quando mais de uma linha de produção executa produtos semelhantes ou possui equipamentos semelhantes. Você pode usar essa opção para comparar os custos entre dois grupos de produção diferentes.  
  
> [!NOTE]
> Se for usado o método padrão para calcular o custo do item finalizado, as transações finais refletirão esse fato. Se os custos reais e os custos calculados utilizando o método padrão forem diferentes, as diferenças são lançadas na conta que mostra lucros ou perdas.

### <a name="route-groups-and-ledger-posting"></a>Grupos de roteiros e lançamento contábil

Cada linha de operação em um roteiro tem um **Grupo de roteiros** especificado. Os campos **Tempo de preparação**, **Tempo de execução** e **Quantidade** no **Grupo de roteiros** no grupo **Estimativa e custo** são usados para controlar se o tempo será usado para precificação e custo ao lançar um **Ficha de trabalho** ou **Diário de cartão de roteiro** no pedido de produção. Se as opções estiverem desabilitadas, não será criado um comprovante na contabilidade para o consumo de tempo.

Para que um **Cartão de rota** ou **Diário de ficha de trabalho** seja lançado na contabilidade para um pedido de produção, as seguintes condições devem ser atendidas:

-   O campo **Tempo de preparação**, **Tempo de execução** ou **Quantidade** deve ser selecionado no grupo **Estimativa e custo** na página **Grupo de roteiros**.
-   As contas principais devem ser especificadas na página **Categoria de custo**, **Roteiro**, **Grupo de roteiros** ou **Grupos de produção** para os seguintes tipos de lançamento:
    -   Custo estimado de fabricação absorvido
    -   Custo estimado de fabricação consumida, WIP

O diagrama a seguir mostra a relação do grupo de roteiros com o cálculo do custo total de cada operação (linha de roteiro) em determinado roteiro. Cada linha de roteiro tem um grupo de roteiros. O grupo de roteiros controla os parâmetros de tempo de configuração, tempo de execução e quantidade. A guia **Categoria de custo** tem três opções para **Configuração**, **Execução** e **Quantidade** que são ativadas com base na configuração dos grupos de roteiros. A guia rápida **Tempos** tem três campos baseados no grupo de roteiros.

A fórmula usada depende se a opção está habilitada no grupo de roteiros. O custo da categoria de custo selecionada é multiplicado pela quantidade que foi inserida nos tempos para calcular o custo total.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="A relação dos grupos de roteiros com o custo total calculado.":::
A relação dos grupos de roteiros com o custo total calculado. Cada linha de roteiro tem um grupo de roteiros. O grupo de roteiros controla os parâmetros de tempo de configuração, tempo de execução e quantidade. A guia Categoria de custo tem três opções para Configuração, Execução e Quantidade que são ativadas com base na configuração dos grupos de roteiros. A guia rápida Tempos tem três campos que são habilitados e custeados com base no grupo de roteiros. A fórmula usada depende se a opção está habilitada no grupo de roteiros. O custo da categoria de custo selecionada é multiplicado pela quantidade que foi inserida nos tempos para calcular o custo total.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Exemplo de configuração de perfil de lançamento

A tabela a seguir mostra exemplos dos tipos de lançamento padrão com as principais contas e descrições da amostra. 

 - A coluna **Débito/crédito** indica se a transação normalmente Debita ou Credita ou em alguns casos, pode lançar. 
 - A coluna **Conta de compensação** indica se o tipo de lançamento é uma conta de compensação. O valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada. 
 - A coluna **P/F** indica **P** para lançamento físico e **F** para lançamento financeiro. 
 - A coluna **Seguir** indica se a conta principal para um tipo de lançamento específico é geralmente igual a outro tipo de lançamento. O valor na coluna indica o tipo de lançamento que geralmente é seguido.

> [!NOTE]
> As contas principais sugeridas e os nomes de conta principal são sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.


| Tipo de lançamento  | Exemplo de conta principal | Exemplo de nome de conta principal| Tipo de conta | Débito/Crédito? | Conta de compensação | Físico ou Financeiro | Seguir | Descrição |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Custo estimado de materiais consumidos      | 140100               | Estoque de Materiais        | Ativo        | Crédito         | Y                | S                     | Custo de materiais consumidos                | Essa conta é usada quando você lança um diário de lista de separação para um pedido de produção. A contrapartida para esta conta é o custo estimado de materiais, WIP. O valor nessa conta é revertido automaticamente quando o pedido de produção é encerrado. Essa conta representa a conta de estoque no balanço patrimonial.       |
| Custo estimado de materiais consumidos, WIP | 150150               | Produção WIP - Materiais | Ativo        | Débito          | Y                | S                     | Custo estimado de fabricação, WIP          | Essa conta é usada quando você lança um diário de lista de separação para um pedido de produção. A contrapartida para esta conta é o custo estimado dos materiais consumidos. O valor nessa conta é revertido automaticamente quando um pedido de produção é encerrado. Esta conta representa o WIP em seu balanço.                  |
| Custo estimado de fabricação               | 140200               | Estoque de mercadorias concluídas   | Ativo        | Débito          | Y                | S                     | Custo de fabricação                         | Essa conta é usada quando você lança um relatório como diário concluído para um pedido de produção. A contrapartida para esta conta é o custo de fabricação estimado, WIP. O valor nessa conta é revertido automaticamente quando o pedido de produção é encerrado. Essa conta representa a conta de estoque no balanço patrimonial. |
| Custo estimado de fabricação, WIP          | 150150               | Produção WIP - Materiais | Ativo        | Crédito         | Y                | S                     | Custo de fabricação, WIP                    | Essa conta é usada quando você lança um relatório como diário concluído para um pedido de produção. A contrapartida para esta conta é o custo de fabricação estimado. O valor nessa conta é revertido automaticamente quando um pedido de produção é encerrado. Esta conta representa o WIP em seu balanço.                     |
| Custo de materiais consumidos                | 140100               | Estoque de Materiais        | Ativo        | Crédito         | N                 | S                     | Custo estimado de materiais consumidos      | Esta conta é usada para reconhecer os materiais que são consumidos no pedido de produção durante o processo final. A contrapartida desta conta é o custo dos materiais consumidos, WIP.                                                                                                    |
| Custo de materiais consumidos, WIP           | 150150               | Produção WIP - Materiais | Ativo        | Débito          | N                 | S                     | Custo estimado de materiais consumidos, WIP | Esta conta é usada para reconhecer os materiais em WIP que são consumidos no pedido de produção durante o processo final. A contrapartida desta conta é o custo dos materiais consumidos.                                                |
| Custo de fabricação                         | 140200               | Estoque de mercadorias concluídas   | Ativo        | Débito          | N                 | S                     | Custo estimado de fabricação               | Esta conta é usada para reconhecer o custo da mercadoria concluída que é produzida por um pedido de produção quando você encerra esse pedido de produção. A contrapartida para esta conta é o custo de fabricação, conta WIP.                                                                  |
| Custo de fabricação, WIP                    | 150150               | Produção WIP - Materiais | Ativo        | Crédito         | N                 | S                     | Custo estimado de fabricação, WIP          | Esta conta é usada para reconhecer o custo da mercadoria concluída em WIP que é produzida por um pedido de produção quando você encerra esse pedido de produção. A contrapartida para esta conta é a conta de custo fabricação.                                     |

> [!NOTE]
> O **Recibo WIP de serviço enxuto** e a **Conta de compensação WIP de serviço enxuto** são usados com custos de fluxo inverso para fabricação enxuta. Para obter mais informações, vá para [Custos de fluxo inverso](/supply-chain/cost-management/backflush-costing.md).

