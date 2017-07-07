---
title: "Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização"
description: "Este artigo descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f8bcdcf70089aaed06ba0f88cdbec8dfdf9121d1
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017


---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização

[!include[banner](../includes/banner.md)]


Este artigo descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito.

As instruções que os trabalhadores de depósito recebem em um dispositivo móvel são determinadas pelos modelos de trabalho configurados no Microsoft Dynamics 365 for Finance and Operations para definir os vários processos e tarefas do depósito. Os modelos de trabalho determinam como o trabalho será executado em cada processo de depósito. Ao vincular uma diretiva de localização a modelos de trabalho, você garantirá que o trabalho ocorrerá em áreas específicas dos depósitos.

## <a name="work-templates"></a>Modelos do trabalho
A página **Modelos de trabalho** permite definir quais operações de trabalho devem ser executadas no depósito. Normalmente, as operações de trabalho de depósito consistem em duas ações: um trabalhador do depósito coleta o estoque disponível em um local e descarrega o estoque coletado em outro local. 

Os modelos de trabalho consistem em um cabeçalho e linhas associadas. Cada modelo de trabalho destina-se a um *tipo de ordem de trabalho* específico. Vários tipos de ordem de trabalho são associadas a documentos de origem, como ordens de compra ou de venda. Entretanto, outros tipos de ordem de trabalho representam processos de depósito específicos, como a contagem cíclica. A *ID de grupo de trabalho *permite organizar o trabalho em grupos. 

As configurações na definição do cabeçalho de trabalho podem ser usadas para determinar quando uma nova frente de trabalho deve ser criada. Por exemplo, você pode definir um número máximo de linhas de separação e um tempo de separação máximo estimado. Assim, se o trabalho em um processo de coleta de ordem de venda exceder qualquer um desses valores, esse trabalho será dividido em duas frentes de trabalho. 

As linhas de trabalho representam as tarefas físicas são necessárias para processar o trabalho. Por exemplo, em um processo de saída do depósito, talvez haja uma linha de trabalho para coletar os itens no depósito e uma outra linha para colocar esses itens em uma área de preparo. Assim, poderia haver mais uma linha para coletar os itens na área de preparo, e outra linha para alocar os itens dentro do caminhão, como parte do processo de carregamento. Você pode definir um *código de diretiva *nas linhas de modelo de trabalho. Um código de diretiva é vinculado a uma diretiva de local e, portanto, ajuda a garantir que o trabalho de depósito será processado no local correto do depósito. 

Você pode configurar uma consulta para determinar quando um modelo de trabalho específico será usado. Por exemplo, você pode definir uma limitação de modo que um determinado modelo só possa ser usado para trabalhos em um depósito específico. Como alternativa, você poderia ter vários modelos usados para criar trabalho para processamento de ordens de venda de saída, dependendo da origem da venda. O sistema usa o campo **Número sequencial** para determinar a ordem em que os modelos de trabalho disponíveis serão avaliados. Portanto, se você tiver uma consulta muito específica para um determinado modelo de trabalho, atribua um número sequencial baixo a ela. Então, essa consulta será avaliada antes de outras mais genéricas. 

Para interromper ou pausar um processo de trabalho, use a configuração **Parar trabalho** na linha de trabalho. Nesse caso, o trabalhador que está executando o trabalho não será solicitado a realizar a próxima etapa da linha de trabalho. Para avançar para a próxima etapa, esse ou outro trabalhador deve selecionar o trabalho novamente. Você também pode separar as tarefas em uma frente de trabalho usando uma *ID de classe de trabalho *diferente nas linhas do modelo de trabalho.

## <a name="location-directives"></a>Diretivas de localização
As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque. Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão armazenados. As diretivas de localização consistem em um cabeçalho e linhas associadas, e você pode criá-los na página **Diretivas de localização**. 

No cabeçalho, cada diretiva de localização deve estar associada a um *tipo de ordem de trabalho *que especifica para qual tipo de transação de estoque essa diretiva será usada, como ordens de venda, reabastecimento ou separação de matéria-prima. O *tipo de trabalho *especifica se a diretiva de localização será usada para trabalho de separação ou armazenamento ou para qualquer outro processo de depósito, como contagem ou alterações de status do estoque. Você também deve especificar um *local *e um *depósito*. Um *código de diretiva *que você especifica no cabeçalho pode ser usado para vincular a diretiva de localização a um ou mais modelos de trabalho. 

Assim como nos modelos de trabalho, você pode configurar uma consulta para determinar quando uma determinada diretiva de localização será usada. Por exemplo, você pode especificar que, quando o comércio eletrônico for a origem de uma ordem de venda, o estoque deverá ser coletado de uma área dedicada no depósito. O sistema usa o campo **Número de sequência** para determinar a ordem que as diretivas disponíveis de localização são avaliadas. 

Linhas das diretivas definem local restrições adicionais no aplicativo do local que encontra regras. Você pode especificar uma quantidade mínima e máxima ao qual a diretiva deve ser aplicada; você pode especificar ainda que a diretiva se refere a uma unidade específica do estoque. Por exemplo, se a unidade de medida for paletes, os itens em paletes poderão ser colocados em um local específico. Você também pode especificar se a quantidade pode ser dividida entre vários locais. Como o cabeçalho diretivo localização, de cada linha da localização diretiva tiver um número de sequência que determina a ordem em que as linhas sejam avaliadas. 

As diretivas da localização com o nível de detalhes adicionais: *diretiva de ações da localização*. Você pode definir várias ações de diretiva de localização para cada linha. Mais uma vez, um número sequencial é usado para determinar a ordem em que as ações serão avaliadas. Nesse nível, você pode configurar uma consulta para definir como encontrar o melhor local no depósito. Você também pode usar configurações de **estratégia** predefinidas para encontrar um local ideal.

### <a name="example-of-the-use-of-location-directives"></a>Exemplo do uso de diretivas de localização

Neste exemplo, consideraremos um processo de ordem de compra em que a diretiva de localização deve encontrar capacidade livre em um depósito para itens do estoque que acabaram de ser registrados na doca de recebimento. Primeiro, queremos tentar localizar a capacidade livre no depósito consolidando o estoque disponível existente. Se a consolidação não for possível, procuraremos identificar um local vazio. 

Nesse cenário, devemos definir duas ações de diretiva de localização. A primeira ação na sequência deve usar a estratégia **Consolidar** e a segunda deve usar a estratégia **Local vazio sem trabalho de entrada**. A menos que definamos uma terceira ação para lidar com um cenário de estouro de capacidade, dois resultados serão possíveis quando não houver mais capacidade no depósito: o trabalho pode ser criado mesmo que nenhum local seja definido ou o processo de criação de trabalho pode falhar. O resultado é determinado pela configuração na página **Falhas na diretiva de localização**, na qual você pode decidir se selecionará a opção **Parar de trabalhar em falha de diretiva de localização** para cada tipo de ordem de trabalho.




