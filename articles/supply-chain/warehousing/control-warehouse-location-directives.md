---
title: Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização
description: Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito.
author: perlynne
manager: AnnBe
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 74e7c36fb912f35252d6e40d17477ac2962cbc23
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558795"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito.

As instruções recebidas pelos funcionários do depósito em um dispositivo móvel são determinadas pelos modelos de trabalho configurados no Microsoft Dynamics 365 for Finance and Operations para definir os vários processos e tarefas do depósito. Os modelos de trabalho determinam como o trabalho será executado em cada processo de depósito. Ao vincular uma diretiva de localização a modelos de trabalho, você garantirá que o trabalho ocorrerá em áreas específicas dos depósitos.

## <a name="work-templates"></a>Modelos do trabalho
A página **Modelos de trabalho** permite definir quais operações de trabalho devem ser executadas no depósito. Normalmente, as operações de trabalho de depósito consistem em duas ações: um trabalhador do depósito coleta o estoque disponível em um local e descarrega o estoque coletado em outro local. 

Os modelos de trabalho consistem em um cabeçalho e linhas associadas. Cada modelo de trabalho destina-se a um *tipo de ordem de trabalho* específico. Vários tipos de ordem de trabalho são associadas a documentos de origem, como ordens de compra ou de venda. Entretanto, outros tipos de ordem de trabalho representam processos de depósito específicos, como a contagem cíclica. A *ID de grupo de trabalho* permite organizar o trabalho em grupos. 

As configurações na definição do cabeçalho de trabalho podem ser usadas para determinar quando uma nova frente de trabalho deve ser criada. Por exemplo, você pode definir um número máximo de linhas de separação e um tempo de separação máximo estimado. Assim, se o trabalho em um processo de coleta de ordem de venda exceder qualquer um desses valores, esse trabalho será dividido em duas frentes de trabalho. 

As linhas de trabalho representam as tarefas físicas são necessárias para processar o trabalho. Por exemplo, em um processo de saída do depósito, talvez haja uma linha de trabalho para coletar os itens no depósito e uma outra linha para colocar esses itens em uma área de preparo. Assim, poderia haver mais uma linha para coletar os itens na área de preparo, e outra linha para alocar os itens dentro do caminhão, como parte do processo de carregamento. Você pode definir um *código de diretiva* nas linhas de modelo de trabalho. Um código de diretiva é vinculado a uma diretiva de local e, portanto, ajuda a garantir que o trabalho de depósito será processado no local correto do depósito. 

Você pode configurar uma consulta para determinar quando um modelo de trabalho específico será usado. Por exemplo, você pode definir uma limitação de modo que um determinado modelo só possa ser usado para trabalhos em um depósito específico. Como alternativa, você poderia ter vários modelos usados para criar trabalho para processamento de ordens de venda de saída, dependendo da origem da venda. O sistema usa o campo **Número sequencial** para determinar a ordem em que os modelos de trabalho disponíveis serão avaliados. Portanto, se você tiver uma consulta muito específica para um determinado modelo de trabalho, atribua um número sequencial baixo a ela. Então, essa consulta será avaliada antes de outras mais genéricas. 

Para interromper ou pausar um processo de trabalho, use a configuração **Parar trabalho** na linha de trabalho. Nesse caso, o trabalhador que está executando o trabalho não será solicitado a realizar a próxima etapa da linha de trabalho. Para avançar para a próxima etapa, esse ou outro trabalhador deve selecionar o trabalho novamente. Você também pode separar as tarefas em uma frente de trabalho usando uma *ID de classe de trabalho* diferente nas linhas do modelo de trabalho.

## <a name="location-directives"></a>Diretivas de localização
As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque. Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão armazenados. As diretivas de localização consistem em um cabeçalho e linhas associadas, e você pode criá-los na página **Diretivas de localização**. 

No cabeçalho, cada diretiva de localização deve estar associada a um *tipo de ordem de trabalho* que especifica para qual tipo de transação de estoque essa diretiva será usada, como ordens de venda, reabastecimento ou separação de matéria-prima. O *tipo de trabalho* especifica se a diretiva de localização será usada para trabalho de separação ou armazenamento ou para qualquer outro processo de depósito, como contagem ou alterações de status do estoque. Você também deve especificar um *local* e um *depósito*. Um *código de diretiva* que você especifica no cabeçalho pode ser usado para vincular a diretiva de localização a um ou mais modelos de trabalho. 

Assim como nos modelos de trabalho, você pode configurar uma consulta para determinar quando uma determinada diretiva de localização será usada. Por exemplo, você pode especificar que, quando o comércio eletrônico for a origem de uma ordem de venda, o estoque deverá ser coletado de uma área dedicada no depósito. O sistema usa o campo **Número de sequência** para determinar a ordem que as diretivas disponíveis de localização são avaliadas. 

Linhas das diretivas definem local restrições adicionais no aplicativo do local que encontra regras. Você pode especificar uma quantidade mínima e máxima ao qual a diretiva deve ser aplicada; você pode especificar ainda que a diretiva se refere a uma unidade específica do estoque. Por exemplo, se a unidade de medida for paletes, os itens em paletes poderão ser colocados em um local específico. Você também pode especificar se a quantidade pode ser dividida entre vários locais. Como o cabeçalho diretivo localização, de cada linha da localização diretiva tiver um número de sequência que determina a ordem em que as linhas sejam avaliadas. 

As diretivas da localização com o nível de detalhes adicionais: *diretiva de ações da localização*. Você pode definir várias ações de diretiva de localização para cada linha. Mais uma vez, um número sequencial é usado para determinar a ordem em que as ações serão avaliadas. Nesse nível, você pode configurar uma consulta para definir como encontrar o melhor local no depósito. Você também pode usar configurações de **estratégia** predefinidas para encontrar um local ideal.

## <a name="location-directives-configuration-details"></a>Detalhes de configuração das diretivas da localização 

 ### <a name="sequence-number"></a>Número de sequência
 
Este número indica a sequência na qual uma diretiva de local é processada para um tipo de ordem selecionado. Pode ser alterado usando **Mover para cima** e **Mover para baixo** no menu.
 
 ### <a name="work-type"></a>Tipo de trabalho
 
Este é o tipo de trabalho a ser executado. O tipo de trabalho disponível é baseado no tipo de transação de estoque que você selecionou no campo **Tipo de ordem de trabalho**.
-   **Colocado** - Um tipo de trabalho **Colocado** significa que a diretiva de localização encontrará o local ideal para colocar ou localizar o estoque do sistema, de recebimento, produção, ou de ajustes de estoque. Também pode ser usado para definir uma colocação em uma localização de fase ou em um local de remessa de baydoor final.
-   **Separação** - Um tipo de trabalho **Separação** significa que o depósito encontrará o local ideal para reservar o estoque fisicamente (criar trabalho). A separação pode ser concluída (a linha de trabalho de separação pode ser fechada), mesmo se o trabalho não for concluído. O usuário pode concluir a separação física, que é uma etapa de separação. Em seguida, o usuário poderá cancelar de um dispositivo móvel e concluir o trabalho depois. Porém, o cabeçalho de trabalho é fechado quando a colocação final é concluída. 
-   **Contagem, ajustes, personalização, alteração de status de estoque, criação da placa de licença, impressão, alteração de status, Empacotar em placas de licença aninhadas** - Não são usados em nenhuma configuração de diretivas de localização. É uma enumeração, então não há filtragem conectada ao tipo de ordem de trabalho. 

### <a name="directive-code"></a>Código de diretiva

Selecione o código de diretiva para associar a um modelo de trabalho ou a um modelo de reabastecimento. No formulário **Código diretivo** , você pode criar novos códigos que podem ser usados para conexões entre um modelo de reabastecimento e uma diretiva de localização do modelo de trabalho. Também pode ser usada para estabelecer o link entre qualquer linha de modelo de trabalho e diretiva de localização (como localização de fase ou baydoor).

Observe que se o código for definido, enquanto o trabalho for gerado, o sistema não pesquisará a diretiva do local por sequência, a sequência será por código de diretiva. Isso significa que você pode ser mais específico sobre qual modelo do local será usado para uma determinada etapa em um modelo de trabalho, como o preparo de materiais. 

### <a name="site"></a>Site

O site é um campo obrigatório porque a diretiva do local precisa do site e do depósito que é válido. 

### <a name="warehouse"></a>Depósito

Depósito é um campo obrigatório porque a diretiva do local precisa do site e do depósito que é válido.

### <a name="multiple-sku"></a>Várias SKUs

Isso permite várias Unidades de Manutenção de Estoque (SKU) em um local, como o baydoor. Se você selecionar **Várias SKU**, o local de colocação será especificado no trabalho (que é esperado), mas ele somente poderá tratar várias colocações de item (se o trabalho tiver diferentes SKUs a serem selecionados e colocados, não uma única colocação de SKU). Se você não selecionar **Várias SKUs**, o local de colocação somente será especificado se a colocação tiver somente um tipo de SKU. Para usar as duas ações, você precisará especificar duas linhas, uma com várias SKUs ativadas e outra com várias SKUs desativadas. Elas precisam ter a mesma estrutura e configuração. Para operações de colocação, é necessário ter diretivas de local que são idênticas, mesmo que você não diferencie entre várias SKUs e SKUs únicas no ID de trabalho. Você também precisa configurar a separação, se você tiver uma ordem com mais de um item.

### <a name="sequence-number"></a>Número de sequência

Informe a sequência na qual a linha da diretiva do local é processada para o tipo de trabalho selecionado. Você também pode alterar a sequência, se necessário, usando **Mover para cima** e **Mover para baixo**.

### <a name="fromto-quantity"></a>Quantidade De/Para

Fornece a capacidade de especificar um intervalo de quantidade para o qual a sequência de grade do meio deve ser selecionada. Você pode especificar intervalo De/Até na Quantidade na respectiva unidade.

### <a name="unit"></a>Unidade

Você pode especificar uma quantidade mínima e máxima ao qual a diretiva deve ser aplicada; você pode especificar ainda que a diretiva se refere a uma unidade específica do estoque. O campo de unidade na linha é usado somente para avaliação de quantidade.

Ao verificar se a linha da diretiva de local é aplicável, isso será baseado na quantidade da respectiva unidade especificada na linha da diretiva do local. Sempre que uma linha de diretiva do local for atingida, o sistema tentará converter a unidade de demanda em uma unidade especificada na linha. Se a conversão de UOM não existir, ela continuará na próxima linha. 

### <a name="locate-quantity"></a>Localizar quantidade

Esta opção é usada apenas para colocar/localizar quantidade no depósito. Só é efetuada para o tipo de trabalho de colocação. Os valores válidos são:

-   **Quantidade da Placa de Licença** - Ao avaliar se a quantidade está dentro dos intervalos de quantidade "De" e "Até", use a quantidade na placa de licença que está sendo recebida.
-   **Quantidade unitizada** - Ao avaliar se a quantidade está dentro dos intervalos de quantidade "De" e "Até", use a quantidade que está sendo unitizada durante a transação específica.
-   **Quantidade Pendente** - Ao avaliar se a quantidade está dentro dos intervalos "De" e "Até", use a quantidade restante a ser recebida na linha da ordem de compra que está sendo registrada no momento.
-   **Quantidade Esperada** - Ao avaliar se a quantidade está dentro dos intervalos "De" e "Até", use a quantidade total da linha da ordem de compra, independente do que já foi recebido

### <a name="restrict-by-unit"></a>Restringir por unidade

Isso permite que uma linha de diretiva de local seja específica para uma unidade de medida ou várias unidades de medida. Ao reservar a quantidade, se você quiser reservar paletes apenas de um conjunto específico de locais, então a sequência da grade intermediária restringiria essa sequência específica a "PL", de modo que qualquer quantidade menor que um palete não selecionaria a sequência. Selecione **Restringir por unidade** para configurar as unidades. Também é possível restringir a linha a mais de uma unidade. Isso funciona somente diretivas de local do tipo separação. 

### <a name="round-up-to-unit"></a>Arredondar para a unidade

Este campo trabalha em conjunto com o campo **Restringir por unidade**. Se a linha de diretiva de localização **Restringir por unidade** for definida como "caixa," selecionar **Arredondar para a unidade** indica que o trabalho gerado da diretiva de seleção de material bruto deve ser arredondada para um múltiplo de uma unidade de manuseio de material (especificada em **Restringir por unidade**). Observe que isso funciona somente para a separação de matéria-prima e somente com diretivas de local do tipo separação.

### <a name="locate-packing-qty"></a>Localizar quantidade da embalagem

Se a quantidade de embalagem estiver especificada em uma ordem de venda, ordem de transferência, ou em uma ordem de produção, isso restringirá o sistema para selecionar somente os locais com uma quantidade de embalagem no local. Isso funciona somente diretivas de local do tipo separação.

### <a name="allow-split"></a>Permitir divisão

Isso especifica se uma diretiva do local será permitida para dividir a quantidade que está sendo recebida ou a quantidade que está sendo reservada em várias localizações de depósitos, ou se a quantidade inteira deve estar localizada em um único local ou ser reservada de um único local para criar trabalhos. 

### <a name="sequence-number"></a>Número de sequência

Este número é a sequência na qual a diretiva de localização é processada para o tipo de trabalho selecionado. Você pode modificar a sequência, se necessário. Entretanto, seja cauteloso ao usar números sequenciais, pois o processamento sempre será executado em sequência. 

### <a name="name"></a>Nome

Digite um nome para a ação da diretiva de local. Seja específico ao escolher um nome.

### <a name="fixed-location-usage"></a>Uso de localização fixa 

-   **Localizações fixas e não fixas** - A diretiva de localização considerará todas as localizações.
-   **Somente localizações fixas para o produto** - A diretiva de localização considerará somente as localizações fixas dos produtos.
-   **Somente localizações fixas para a variante do produto** - A diretiva de localização considerará somente as localizações fixas das variantes do produto.

### <a name="allow-negative-inventory"></a>Permitir estoque negativo

Selecione esta opção para permitir estoque negativo na localização de depósito especificada em diretivas de localização. 

### <a name="batch-enabled"></a>Lote habilitado 

Selecione para usar estratégias de lote para os itens habilitados para lotes. Se uma linha for acessada onde **Habilitado por lote** for definida sem item de lote, o processo continuará até a próxima linha de ação. 

### <a name="strategy"></a>Estratégia

-   **Consolidar** - Essa estratégia é usada para consolidar itens em um local específico quando itens semelhantes já estiverem disponíveis. Isso funciona somente para o tipo de colocação da diretiva de localização. A configuração comum para o tipo Colocação será consolidada na primeira linha de ação e, em seguida, na segunda tentativa para colocar sem consolidação. A consolidação de mercadorias torna a separação posterior mais eficiente.
-   **Fazer a correspondência da quantidade da embalagem** - Essa estratégia é usada para verificar se um local de separação tem a quantidade de embalagem especificada. Isso funciona somente para diretiva de local do tipo Separação. 
-   **Reserva de lotes FEFO** - Esta estratégia é usada quando o estoque é localizado usando uma data de vencimento do lote e é alocado para reserva de lotes. Você só pode usar essa estratégia para itens habilitados para lote. Isso funciona somente para diretiva de local do tipo de trabalho de Separação. 
-   **Arredondar até a LP completa** - Essa estratégia é usada para arredondar para cima a quantidade de estoque para corresponder à quantidade de placa de licença (LP) que é atribuída aos itens a serem separados. Você só pode usar essa estratégia para o tipo de reabastecimento de diretiva de localização do tipo Separação. 
-   **Local vazio sem trabalho de entrada** - Esta estratégia é usada para detectar locais vazios. O local será considerada vazio se não houver estoque físico e nenhum trabalho de entrada esperado. Essa estratégia é usada somente em um tipo de Colocação de diretiva de localização. 

### <a name="example-of-the-use-of-location-directives"></a>Exemplo do uso de diretivas de localização

Neste exemplo, consideraremos um processo de ordem de compra em que a diretiva de localização deve encontrar capacidade livre em um depósito para itens do estoque que acabaram de ser registrados na doca de recebimento. Primeiro, você precisa localizar a capacidade livre no depósito, consolidando o estoque disponível existente. Se a consolidação não for possível, você precisará encontrar um local vazio. 

Nesse cenário, você deve definir duas ações de diretiva de localização. A primeira ação na sequência deve usar a estratégia **Consolidar** e a segunda deve usar a estratégia **Local vazio sem trabalho de entrada**. A menos que você defina uma terceira ação para lidar com um cenário de estouro de capacidade, dois resultados serão possíveis quando não houver mais capacidade no depósito: o trabalho pode ser criado mesmo que nenhum local seja definido ou o processo de criação de trabalho pode falhar. O resultado é determinado pela configuração na página **Falhas na diretiva de localização**, na qual você pode decidir se selecionará a opção **Parar de trabalhar em falha de diretiva de localização** para cada tipo de ordem de trabalho.
