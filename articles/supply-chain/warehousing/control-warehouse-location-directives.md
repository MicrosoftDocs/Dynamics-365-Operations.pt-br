---
title: Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização
description: Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito.
author: perlynne
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 36471cf76615e22c2ca80163756e2fd05aaf6a0f
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911263"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização

[!include [banner](../includes/banner.md)]

Este tópico descreve como usar modelos de trabalho e diretivas de localização para determinar como e onde o trabalho será executado no depósito.

As instruções recebidas pelos funcionários do depósito em um dispositivo móvel são determinadas pelos modelos de trabalho do Dynamics 365 Supply Chain Management que você configura para definir os vários processos e tarefas do depósito. Os modelos de trabalho determinam como o trabalho será executado em cada processo de depósito. Ao vincular uma diretiva de localização a modelos de trabalho, você garantirá que o trabalho ocorrerá em áreas específicas dos depósitos.

## <a name="work-templates"></a>Modelos do trabalho

A página **Modelos de trabalho** permite definir quais operações de trabalho devem ser executadas no depósito. Normalmente, as operações de trabalho de depósito consistem em duas ações: um trabalhador do depósito coleta o estoque disponível em um local e descarrega o estoque coletado em outro local. 

Os modelos de trabalho consistem em um cabeçalho e linhas associadas. Cada modelo de trabalho destina-se a um *tipo de ordem de trabalho* específico. Vários tipos de ordem de trabalho são associadas a documentos de origem, como ordens de compra ou de venda. Entretanto, outros tipos de ordem de trabalho representam processos de depósito específicos, como a contagem cíclica. A *ID de grupo de trabalho* permite organizar o trabalho em grupos. 

Use as configurações na definição do cabeçalho de trabalho para determinar quando uma nova frente de trabalho deve ser criada. Por exemplo, você pode definir um número máximo de linhas de separação e um tempo de separação máximo estimado. Assim, se o trabalho em um processo de coleta de ordem de venda exceder qualquer um desses valores, esse trabalho será dividido em duas frentes de trabalho.

Use o botão **Quebras de cabeçalho de trabalho** para definir quando o sistema deve criar novos cabeçalhos de trabalho. Por exemplo, para criar um cabeçalho de trabalho para cada _número da ordem_, selecione **Editar consulta** no Painel de Ações e, depois, adicione o campo **Número da ordem** à guia **Classificação** do editor de consultas. Os campos adicionados à guia **Classificação** estão disponíveis para seleção como *campos de agrupamento*. Para definir campos de agrupamento, selecione **Quebras de cabeçalho de trabalho** no Painel de Ações. Para cada campo a ser usado como um campo de agrupamento, marque a caixa de seleção na coluna **Agrupar por este campo**.

As linhas de trabalho representam as tarefas físicas que são necessárias para processar o trabalho. Por exemplo, em um processo de depósito de saída, talvez haja uma linha para coletar os itens no depósito e outra linha para colocar esses itens em uma área de preparo. Assim, é possível existir mais uma linha para coletar os itens na área de preparo e outra linha para colocar os itens no caminhão, como parte do processo de carregamento. Você pode definir um *código de diretiva* nas linhas de modelo de trabalho. Um código de diretiva é vinculado a uma diretiva de localização e, portanto, ajuda a garantir que o trabalho de depósito seja processado no local correto do depósito.

Você pode configurar uma consulta para determinar quando um modelo de trabalho específico será usado. Por exemplo, você pode definir uma limitação de modo que um determinado modelo só possa ser usado para trabalhos em um depósito específico. Como alternativa, você pode ter vários modelos para criar trabalho para processamento de ordens de venda de saída, dependendo da origem da venda. O sistema usa o campo **Número sequencial** para determinar a ordem em que os modelos de trabalho disponíveis serão avaliados. Portanto, se você tiver uma consulta muito específica para um determinado modelo de trabalho, atribua um número sequencial baixo a ela. Essa consulta será avaliada antes das outras mais genéricas.

> [!NOTE]
> Para evitar que o sistema substitua automaticamente *números de sequência* do modelo de trabalho após a exclusão de um modelo, ative o recurso *Preservar números de sequência de modelos de trabalho na exclusão* em [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para interromper ou pausar um processo de trabalho, use a configuração **Parar trabalho** na linha de trabalho. Nesse caso, o trabalhador que está executando o trabalho não será solicitado a realizar a próxima etapa da linha de trabalho. Para avançar para a próxima etapa, esse ou outro trabalhador deve selecionar o trabalho novamente. Você também pode separar as tarefas em uma frente de trabalho usando uma *ID de classe de trabalho* diferente nas linhas do modelo de trabalho.

## <a name="location-directives"></a>Diretivas de localização

As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque. Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão armazenados. As diretivas de localização consistem em um cabeçalho e linhas associadas, e você pode criá-los na página **Diretivas de localização**.

No cabeçalho, cada diretiva de localização deve estar associada a um *tipo de ordem de trabalho* que especifica para qual tipo de transação de estoque essa diretiva será usada, como ordens de venda, reabastecimento ou separação de matéria-prima. O *tipo de trabalho* especifica se a diretiva de localização será usada para trabalho de separação ou armazenamento ou para qualquer outro processo de depósito, como contagem ou alterações de status do estoque. Você também deve especificar um *local* e um *depósito*. Um *código de diretiva* que você especifica no cabeçalho pode ser usado para vincular a diretiva de localização a um ou mais modelos de trabalho. 

Assim como nos modelos de trabalho, você pode configurar uma consulta para determinar quando uma determinada diretiva de localização será usada. Por exemplo, você pode especificar que, quando o comércio eletrônico for a origem de uma ordem de venda, o estoque deverá ser coletado de uma área dedicada no depósito. O sistema usa o campo **Número de sequência** para determinar a ordem que as diretivas disponíveis de localização são avaliadas.

Linhas das diretivas definem local restrições adicionais no aplicativo do local que encontra regras. Você pode especificar uma quantidade mínima e máxima ao qual a diretiva deve ser aplicada; você pode especificar ainda que a diretiva se refere a uma unidade específica do estoque. Por exemplo, se a unidade de medida for paletes, os itens em paletes poderão ser colocados em um local específico. Você também pode especificar se a quantidade pode ser dividida entre vários locais. Como o cabeçalho diretivo localização, de cada linha da localização diretiva tiver um número de sequência que determina a ordem em que as linhas sejam avaliadas.

As diretivas da localização com o nível de detalhes adicionais: *diretiva de ações da localização*. Você pode definir várias ações de diretiva de localização para cada linha. Mais uma vez, um número sequencial é usado para determinar a ordem em que as ações serão avaliadas. Nesse nível, você pode configurar uma consulta para definir como encontrar o melhor local no depósito. Você também pode usar configurações de **estratégia** predefinidas para encontrar um local ideal.

Para obter mais informações sobre como criar e configurar diretivas de localização, consulte [Criar uma diretiva de localização](create-location-directive.md).

### <a name="how-location-directives-work"></a>Como diretivas de localização funcionam

As diretivas de localização determinam *onde* itens devem ser coletados e *onde* eles devem ser colocados. O sistema avalia uma diretiva de localização em relação a cada linha de trabalho e seleciona um local com base nos detalhes da linha de trabalho. O sistema primeiro encontra todas as diretivas de localização que correspondam a uma linha de trabalho específica (por exemplo, elas são para o depósito correto e coincidem com a consulta). Depois, ele avalia em sequência as diretivas encontradas.

> [!NOTE]
> Há casos especiais em que o local de coleta ou o local de colocação é pré-selecionado. Por exemplo, durante o _registro de compra_, a primeira coleta é sempre do local em que ocorre o registro. Outro exemplo é *movimentação de estoque por modelo*, em que o trabalhador do depósito seleciona a localização de coleta. Apenas os locais de colocação são encontrados por meio das diretivas de localização.

## <a name="additional-resources"></a>Recursos adicionais

- Vídeo: [Detalhamento da configuração de gerenciamento de depósito](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Tópico de ajuda: [Trabalhar com diretivas de localização](create-location-directive.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]