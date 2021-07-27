---
title: Trabalhar com diretivas de localização
description: Este tópico descreve como trabalhar com diretivas de localização. As diretivas de localização são regras definidas pelo usuário que ajudam a identificar locais de separação e armazenamento para o movimento de estoque.
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: a896953a5603d9766f2c4938158088fc9424d5bf
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343739"
---
# <a name="work-with-location-directives"></a>Trabalhar com diretivas de localização

[!include [banner](../includes/banner.md)]

As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque. Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão armazenados. As diretivas de localização consistem em um cabeçalho e linhas associadas. Elas são criadas para *tipos de ordem de serviço* específicos.

> [!NOTE]
> Este tópico se aplica aos recursos do módulo **Gerenciamento de depósito**. Não se aplica aos recursos do módulo de [Gerenciamento de estoque](../inventory/inventory-home-page.md).

É possível usar as diretivas de localização para executar as seguintes tarefas:

- Remover itens recebidos.
- Separar e preparar itens para transações de saída.
- Separar e armazenar matéria-prima para produção.
- Reabastecer as localizações.

## <a name="prerequisites"></a>Pré-requisitos

Antes de criar uma diretiva de localização, siga estas etapas para verificar se os pré-requisitos estão em vigor.

1. Verifique se a chave de licença necessária está ativada. Vá para **Configuração do sistema \> Configuração \> Configuração de licença**, expanda a chave de licença **Comercial** e selecione a chave de configuração **Gerenciamento de Depósito e Transporte**. Observe que o acesso administrativo é necessário para esta etapa.
1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Criar um depósito.
1. Na FastTab **Depósito**, defina a opção **Usar processos de gerenciamento de depósito** como *Sim*.
1. Criar localizações, tipos de localização, perfis de localização e formatos da localização. Para obter mais informações, consulte [Configurar localizações em um depósito habilitado para WMS](./tasks/configure-locations-wms-enabled-warehouse.md).
1. Criar sites, zonas e grupos de zonas. Para obter mais informações, consulte [Configuração do depósito](../../commerce/channels-setup-warehouse.md) e [Configurar localizações em um depósito habilitado para WMS](./tasks/configure-locations-wms-enabled-warehouse.md).

## <a name="work-order-types-for-location-directives"></a>Tipos de ordem de serviço para diretivas de localização

Muitos dos campos que podem ser definidos para diretivas de localização são comuns a todos os tipos de ordem de serviço. No entanto, outros campos são específicos de determinados tipos de ordem de serviço.

![Tipos de ordem de serviço de diretivas de localização.](media/Location_Directives_Work_Order_Types.png "Tipos de ordem de serviço de diretivas de localização")

> [!NOTE]
> Dois tipos de ordem de serviço, *Trabalho cancelado* e *Contagem cíclica*, são usados somente pelo sistema. Não é possível criar diretivas de localização para esses tipos de ordem de serviço.

As tabelas nas subseções a seguir listam os campos de tipo de ordem comum e de trabalho, que estão disponíveis quando você configura uma diretiva de localização.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Campos comuns a todos os tipos de ordem de serviço

A tabela a seguir lista os campos que são comuns a todos os tipos de ordem de serviço.

| FastTab | Campo |
|---|---|
| Diretivas de localização | Tipo de trabalho |
| Diretivas de localização | Site |
| Diretivas de localização | Depósito |
| Diretivas de localização | Código de diretiva |
| Diretivas de localização | Várias SKUs |
| Linhas | Número de seqüência |
| Linhas | Da quantidade |
| Linhas | Quantidade final |
| Linhas | Unidade |
| Linhas | Localizar quantidade |
| Linhas | Restringir por unidade |
| Linhas | Arredondar para a unidade |
| Linhas | Localizar quantidade da embalagem |
| Linhas | Permitir divisão |
| Ações de Diretiva de Localização | Número de seqüência |
| Ações de Diretiva de Localização | Organização |
| Ações de Diretiva de Localização | Uso de localização fixa |
| Ações de Diretiva de Localização | Permitir estoque negativo |
| Ações de Diretiva de Localização | Lote habilitado |
| Ações de Diretiva de Localização | Estratégia |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Campos específicos de tipos de ordem de serviço

A tabela a seguir lista os campos que são específicos de tipos de ordem de serviço em particular.

| FastTab | Campo | Tipo de ordem de serviço |
|---|---|---|
| Diretivas de localização | Localizar por | Ordens de Compra |
| Diretivas de localização | Código de disposição aplicável | Ordens de Compra |
| Diretivas de localização | Código de disposição | Ordens de Compra |
| Diretivas de localização | Código de disposição aplicável | Armazenamento de mercadorias acabadas |
| Diretivas de localização | Código de disposição | Armazenamento de mercadorias acabadas |
| Diretivas de localização | Código de disposição aplicável | Ordens de Devolução |
| Diretivas de localização | Código de disposição | Ordens de Devolução |
| Diretivas de localização | Código de disposição aplicável | Armazenamento kanban |
| Diretivas de localização | Código de disposição aplicável | Separação kanban |
| Linhas | Modelo de reabastecimento imediato | Ordens de Venda |
| Linhas | Modelo de reabastecimento imediato | Separação de matéria-prima |
| Linhas | Modelo de reabastecimento imediato | Transferir saída |
| Linhas | Modelo de reabastecimento imediato | Separação kanban |

## <a name="open-the-location-directives-page"></a>Abrir a página Diretivas de localização

Para abrir a página **Diretivas de localização**, vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.

A partir daí, você pode exibir, criar e editar diretivas de localização usando os comandos no Painel de Ações. Consulte as seções restantes deste tópico para obter informações sobre como usar todos os campos disponíveis na página.

## <a name="action-pane"></a>Painel de Ação

O Painel de Ações na página **Diretivas de localização** contém botões que podem ser usados para criar, editar e excluir diretivas (**Editar**, **Novo** e **Excluir**). Ele também contém os seguintes botões que permitem ajustar a sequência em que a diretiva de localização é processada e configurar uma consulta que define os critérios para a aplicação da diretiva de localização:

- **Mover para cima** – mova a diretiva de localização selecionada para cima na sequência. Por exemplo, você pode movê-la da sequência número 4 para a sequência número 3.
- **Mover para baixo** – mova a diretiva de localização selecionada para baixo na sequência. Por exemplo, você pode movê-la da sequência número 4 para a sequência número 5.
- **Editar consulta** – abra uma caixa de diálogo na qual você possa definir as condições em que a diretiva de localização selecionada deve ser processada. Por exemplo, talvez você deseje que ele seja aplicado somente a um depósito específico.

## <a name="location-directives-header"></a>Cabeçalho de diretivas de localização

O cabeçalho da diretiva de localização inclui os seguintes campos para o número de sequência e nome descritivo da diretiva de localização:

- **Número de sequência** – este campo indica a sequência à qual o sistema tenta aplicar cada diretiva de localização para o tipo de ordem de serviço selecionada. Os números baixos são aplicados primeiro. Você pode alterar a sequência usando os botões **Mover para cima** e **Mover para baixo** no Painel de Ações.
- **Nome** – insira um nome descritivo para a diretiva de localização. Esse nome deve ajudar a identificar a finalidade geral da diretiva. Por exemplo, insira *Separação da ordem de venda no depósito 24*.

## <a name="location-directives-fasttab"></a>FastTab de diretivas de localização

Os campos na FastTab **Diretivas de localização** são específicos do tipo de ordem de serviço selecionado no campo **Tipo de ordem de serviço** no painel de lista.

- **Tipo de trabalho** – selecione o tipo de trabalho que deve ser executado. Os valores disponíveis dependem do tipo de transação de estoque selecionado no campo **Tipo de ordem de serviço**. Selecione um dos seguintes valores:

    - **Armazenamento** – a diretiva de localização tentará encontrar a localização ideal para armazenar ou localizar o estoque que entra no sistema com recebimento, produção ou ajustes de estoque. Ela também pode ser usada para definir o armazenamento no local de espera ou no local de remessa da porta da baía.
    - **Separação** – a diretiva de localização tentará encontrar os locais ideais para reservar estoque fisicamente (ou seja, criar trabalho). A separação poderá ser concluída (ou seja, a linha de trabalho de separação pode ser fechada), mesmo se o trabalho não for concluído. O usuário pode concluir a separação física. No sistema, essa ação é uma etapa de separação. O usuário pode cancelar o dispositivo móvel e concluir o trabalho depois. Porém, o cabeçalho de trabalho é fechado pela primeira vez quando a colocação final é concluída.

    > [!IMPORTANT]
    > Os outros valores no campo **Tipo de trabalho** não são relevantes para diretivas de localização. Elas aparecem apenas porque o campo não está filtrado para corresponder ao tipo de ordem de serviço selecionado.

- **Site** – este campo é obrigatório porque a diretiva do localização deve ser capaz de determinar o site e o depósito válido.
- **Depósito** – este campo é obrigatório porque a diretiva do localização deve ser capaz de determinar o site e o depósito válido.
- **Código de diretiva** – selecione o código de diretiva para associar a um modelo de trabalho ou a um modelo de reabastecimento. Na página **Código de diretiva**, é possível criar códigos que podem ser usados para conectar modelos de trabalho ou modelos de reabastecimento a diretivas de localização. Também é possível usar códigos de diretiva para estabelecer um vínculo entre qualquer linha de modelo de trabalho e uma diretiva de localização (como local de espera ou porta da baía).

    > [!TIP]
    > Se um código de diretiva estiver definido, o sistema não pesquisará diretivas de localização por número de sequência quando o trabalho precisar ser gerado. Ele pesquisará por código de diretiva. Dessa forma, você pode ser mais específico sobre a diretiva de localização usado para uma etapa específica em um modelo de trabalho, como a etapa de preparo de materiais.

- **Várias SKUs** – defina esta opção como *Sim* para habilitar várias unidades de manutenção de estoque (SKUs) a serem usadas em um local. Por exemplo, várias SKUs devem ser habilitadas para o local da porta da baía. Se você habilitar várias SKUs, o local de armazenamento será especificado no trabalho, conforme esperado. No entanto, o local de armazenamento poderá tratar somente um armazenamento de vários itens (se o trabalho incluir diferentes SKUs que devam ser separadas e armazenadas). Não será possível tratar um armazenamento com um única SKU. Se você definir esta opção como *Não*, seu local de armazenamento só será especificado se o armazenamento tiver apenas um tipo de SKU.

    > [!IMPORTANT]
    > Para poder fazer a instalação de vários itens e de uma única SKU, você deve especificar duas linhas com a mesma estrutura e configuração, mas deve definir a opção **Várias SKUs** como *Sim* para uma linha e *Não* para a outra. Portanto, para operações de armazenamento, é necessário ter duas diretivas de localização idênticas, mesmo que não precise diferenciar SKUs únicas e várias SKUs em uma ID de trabalho. Geralmente, se você não configurar essas duas diretivas de localização, os locais de processos comerciais inesperados serão obtidos da diretiva de localização aplicada. Você deverá usar uma configuração semelhante para diretivas de localização que tenham um **Tipo de trabalho** de *separação*, caso você precise processar ordens que incluam várias SKUs.

    Use a opção **Várias SKUs** para linhas de trabalho que tratam mais de um número de item. (O número do item ficará em branco nos detalhes do trabalho e será mostrado como **Múltiplo** nas páginas de processamento no aplicativo móvel de Gerenciamento de Depósito).

    Em um cenário de exemplo típico, um modelo de trabalho é configurado de forma que tenha mais de um par separação/armazenamento. Nesse caso, talvez você queira procurar um local de preparo específico a ser usado em linhas com um **Tipo de trabalho** de *Armazenamento*.

    > [!NOTE]
    > Se a opção **Várias SKUs** for definida como *Sim*, você não poderá selecionar **Editar consulta** no Painel de Ações, pois a consulta não poderá ser avaliada no nível do item quando houver vários itens. Para garantir que a diretiva de localização desejada esteja selecionada, use o campo **Código de diretiva** para orientar a seleção da diretiva de localização relacionada às linhas em que o código de diretiva está atribuído no modelo de trabalho.

    A menos que você sempre trabalhe com operações de item único ou de itens mistos, é importante definir duas diretivas de localização para o tipo de trabalho *Armazenamento*: uma em que a opção **Várias SKUs** esteja definida como *Sim* e outra em que esteja definida como *Não*.

- **Código de disposição aplicável** – especifique se o código de disposição da diretiva de localização deve corresponder ao código de disposição que é aplicado quando o item é recebido ou se a diretiva de localização pode ser selecionada com base em qualquer código de disposição. Se você selecionar *Correspondência exata* e o campo **Código de disposição** estiver em branco, somente os códigos de disposição em branco serão considerados para essa diretiva de localização.

    > [!NOTE]
    > Este campo está disponível apenas para os tipos de ordem de serviço selecionados em que o reabastecimento é permitido. Para obter uma lista completa, consulte a seção [Campos específicos de tipos de ordem de serviço](#fields-specific-types), citados antes neste tópico.

- **Localizar por** – especifique se a quantidade de armazenamento deve ser a quantidade total na placa de licença ou se deve ser item por item. Use este campo para ajudar a garantir que todo o conteúdo de uma placa de licença seja armazenado em um local e que o sistema não sugira que você divida o conteúdo em vários locais para o **ASN** (recebimento de placa de licença) e os processos de recebimento **Placa de licença mista** e **Cluster**. (O processo de recebimento de **Cluster** exige que o recurso *Armazenamento de cluster* esteja ativado.) O comportamento da consulta de diretiva de localização, as linhas e as ações da diretiva de localização variam de acordo com o valor selecionado. A FastTab **Linhas** é usada apenas quando **Localizar por** está definido como *Item*.

    > [!NOTE]
    > Este campo está disponível apenas para os tipos de ordem de serviço selecionados em que o reabastecimento é permitido. Para obter uma lista completa, consulte a seção [Campos específicos de tipos de ordem de serviço](#fields-specific-types).

- **Código de disposição** – este campo é usado para diretivas de localização que têm um tipo de ordem de serviço de *Ordens de compra*, *Armazenamento de mercadorias acabadas* ou *Ordens de devolução* e um tipo de trabalho *Armazenamento*. Use-o para orientar o fluxo a fim de usar uma diretiva de localização específica, dependendo do código de disposição que um trabalhador selecionou no aplicativo móvel de Gerenciamento de Depósito. Por exemplo, você pode direcionar as mercadorias devolvidas para um local de inspeção antes da devolução para o estoque. Um código de disposição pode ser vinculado a um status de estoque. Dessa forma, ele pode ser usado para alterar o status do estoque como parte de um processo de recebimento. Por exemplo, você tem um código de disposição, *QA*, que define o status do estoque como *QA*. Você poderá ter uma diretiva de localização separada para mover esse estoque para um local de quarentena.

    > [!NOTE]
    > Este campo está disponível apenas para os tipos de ordem de serviço selecionados em que o reabastecimento é permitido. Para obter uma lista completa, consulte a seção [Campos específicos de tipos de ordem de serviço](#fields-specific-types).

## <a name="lines-fasttab"></a>FastTab Linhas

Use a FastTab **Linhas** para estabelecer condições para aplicar as ações relacionadas especificadas na FastTab **Ações da diretiva de localização**. Para cada linha, você pode especificar a quantidade mínima e a quantidade máxima às quais as ações devem ser aplicadas. Também é possível especificar se as ações devem ser aplicadas a uma unidade de estoque específica.

- **Número de sequência** – insira a sequência em que a linha de diretiva de localização deve ser processada para o tipo de trabalho selecionado. Você pode alterar a sequência necessária usando os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas.
- **Quantidade inicial** – especifique o início do intervalo de quantidades ao qual a linha se aplica. Especifique a quantidade na unidade de medida selecionada no campo **Unidade**.
- **Quantidade final** – especifique o final do intervalo de quantidades ao qual a linha se aplica. Especifique a quantidade na unidade de medida selecionada no campo **Unidade**.
- **Unidade** – selecione a unidade de medida dos itens. Você pode especificar uma quantidade mínima e máxima ao qual a diretiva deve ser aplicada; você pode especificar ainda que a diretiva se refere a uma unidade específica do estoque. O campo **Unidade** é usado *somente* para avaliação de quantidade. Para determinar se a linha de diretiva de localização é aplicável a todos, o sistema usa a quantidade na unidade especificada nessa linha. Sempre que uma linha de diretiva de localização for atingida, o sistema tentará converter a unidade de demanda em uma unidade especificada na linha. Se não existir a conversão da unidade de medida, o sistema passará para a próxima linha.
- **Localizar quantidade** – este campo é usado somente durante as tentativas de armazenar ou localizar itens no depósito. (Portanto, ele se aplica somente quando o campo **Tipo de trabalho** é definido como *Armazenamento*). Selecione um dos valores a seguir para especificar a quantidade que é usada para avaliar se uma quantidade está no intervalo de **Quantidade inicial** até **Quantidade final**.

    - **Quantidade da placa de licença** – use a quantidade na placa de licença que está sendo recebida.
    - **Quantidade unitária** – use a quantidade usada durante a transação. Por exemplo, você recebe uma quantidade de 1.000 em um depósito e a divide em 10 placas de licença, cada uma com uma quantidade de 100. Nesse caso, você pode usar uma quantidade de 1.000 itens em vez da quantidade da placa de licença de 100.
    - **Quantidade pendente** – use a quantidade que ainda deve ser recebida na linha da ordem de compra que está sendo processada.
    - **Quantidade esperada** – use a quantidade total da linha da ordem de compra, independentemente do que já foi recebido.

- **Restringir por unidade** – esta caixa de seleção permite que você crie a linha de diretiva de localização específica para uma unidade de medida ou várias unidades de medida. Marque-a para restringir as unidades de medida consideradas critérios de seleção válidos para as linhas de diretiva de localização. Essa funcionalidade funciona somente para diretivas de localização em que o campo **Tipo de trabalho** está definido como *Separação*.

    Por exemplo, ao reservar quantidades, você deseja reservar paletes somente de um conjunto específico de locais. Nesse caso, as linhas restringirão essa sequência a paletes de tal forma que qualquer quantidade menor do que um palete não será selecionada para a diretiva de localização.

    Note que a caixa de seleção **Restringir por unidade** não controla a unidade ou as unidades aplicadas nas linhas de trabalho. A restrição de unidade é aplicável somente às unidades disponibilizadas por meio do grupo de sequências de unidades. Por exemplo, um item está associado a um grupo de sequências de unidades que inclui a unidade *paletes* e as unidades *peças*. A unidade de medida foi definida, onde 1 palete = 100 peças e a diretiva de localização usa a funcionalidade **Restringir por unidade** somente para paletes. Além disso, um modelo de trabalho foi definido para limitar a criação do cabeçalho de trabalho para 50 peças. Nesse caso, serão criadas linhas de trabalho de 50 peças. Para especificar a unidade de medida para restrição, siga estas etapas:

    1. Na FastTab **Linhas**, selecione **Restringir por unidade** na barra de ferramentas. (Este botão é disponibilizado somente após marcar a caixa de seleção **Restringir por unidade** na linha e selecionar **Salvar**.)
    1. Na página **Restringir por unidades**, no campo **Unidade**, selecione a unidade de medida que você deseja restringir para os processos de separação e armazenamento.

- **Arredondar para unidade** – este campo funciona junto com a caixa de seleção **Restringir por unidade**. Por exemplo, se **Restringir por unidade** e **Arredondar para a unidade** forem selecionados na linha de diretiva de localização, o trabalho gerado da diretiva de separação de material bruto deverá ser arredondada para um múltiplo de uma unidade de manuseio de material especificada na página **Restringir por unidade**.

    > [!NOTE]
    > Essa configuração de **Arredondar para a unidade** funciona somente para o tipo de ordem de serviço *Separação de matéria-prima* e somente para diretivas de localização em que o campo **Tipo de trabalho** está definido como *Separação*.

- **Localizar Quantidade da Embalagem** – se você especificar uma quantidade de embalagem em uma ordem de venda, ordem de transferência ou ordem de produção, esta caixa de seleção permitirá que você restrinja o sistema de forma que possa selecionar somente locais que tenham pelo menos essa quantidade de embalagem.

    > [!NOTE]
    > Essa funcionalidade só funciona com diretivas de localização do tipo *Separação*.

- **Permitir Divisão** – especifique se a diretiva do localização pode dividir a quantidade que está sendo recebida ou reservada em várias localizações de depósitos, ou se a quantidade inteira deve estar localizada em um único local ou ser reservada de um único local para criar trabalho.
- **Modelo de abastecimento imediato** – use este campo para criar uma conexão com um modelo de alocados. Se você deixar esse campo em branco, o reabastecimento do item não será iniciado até que todas as linhas da diretiva de localização sejam processadas.

    > [!NOTE]
    > Este campo está disponível apenas para os tipos de ordem de serviço selecionados em que o reabastecimento é permitido. Para obter uma lista completa, consulte a seção [Campos específicos de tipos de ordem de serviço](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>FastTab de ações de diretivas de localização

Você pode definir várias ações de diretiva de localização para cada linha. Mais uma vez, um número sequencial é usado para determinar a ordem em que as ações serão avaliadas. Nesse nível, você pode configurar uma consulta para definir como o melhor local no depósito é encontrado. Você também pode usar valores de **estratégia** predefinidos para encontrar um local ideal.

- **Número de sequência** - este campo mostra a sequência em que as ações são processadas para o tipo de trabalho selecionado. Você pode alterar a sequência usando os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas.
- **Nome** – insira o nome da ação da diretiva de localização. Seja específico para que a ação executada seja clara pelo nome.
- **Uso de local fixo** – especifica quais locais a diretiva de localização deve considerar. Selecione um dos seguintes valores:

    - **Localizações fixas e não fixas** – A diretiva de localização considerará todas as localizações.
    - **Somente localizações fixas para o produto** – A diretiva de localização considerará somente as localizações fixas dos produtos.
    - **Somente localizações fixas para a variante do produto** – A diretiva de localização considerará somente as localizações fixas das variantes do produto.

- **Permitir estoque negativo** – marque esta caixa de seleção para permitir estoque negativo na localização de depósito especificada em diretivas de localização.
- **Lote Habilitado** – marque esta caixa de seleção para usar estratégias de lote para os itens habilitados para lotes. É importante que você marque esta caixa de seleção para processos que usam diretivas de localização para encontrar locais para separar itens rastreados por número de lote. Dessa forma, é incluída a pesquisa de localizações que mantêm itens rastreados por número de lote. Se esta caixa de seleção for marcada e o campo **Estratégia** for definido como *Nenhum*, o sistema avançará para a próxima linha de ação.
- **Estratégia** – para definir de forma mais fácil e rápida as ações associadas a cada linha de diretiva da localização, você pode selecionar uma das seguintes estratégias predefinidas:

    - **Nenhum** – nenhuma estratégia será usada.
    - **Fazer a correspondência da quantidade da embalagem** – esta estratégia verifica se um local de separação tem a quantidade de embalagem especificada. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Separação*.
    - **Consolidar** – esta estratégia consolida itens em um local específico quando itens semelhantes já estiverem disponíveis. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Armazenamento*. Uma configuração típica de armazenamento tenta se consolidar na primeira linha de ação e, na segunda linha, tenta armazenar sem consolidação. A consolidação de mercadorias torna a separação posterior mais eficiente.
    - **Reserva de lotes FEFO** – essa estratégia usa as reservas de lotes de primeira a vencer, primeiro a sair (FEFO). Use-a quando o estoque for localizado usando uma data de vencimento do lote e for alocado para reserva de lotes. Você só pode usar essa estratégia para itens habilitados para lote. Ela será válida somente quando o campo **Tipo de trabalho** for definido como *Separação*.
    - **Arredonde para o lote completo de LP e FEFO** – essa estratégia combina os elementos das estratégias *Reserva de lotes FEFO* e *Arredondar até a LP completa*. Ele só é válido para itens habilitados para lotes e diretivas de localização que têm um tipo de trabalho de *Separação*. A linha deve ser habilitada para lotes a fim de usar a estratégia *Reserva de lotes FEFO*. A estratégia *Arredondar até a LP completa* pode ser usada somente para reabastecimento. Se essa estratégia for configurada junto com um limite de estoque de localização, ela poderá fazer com que o local de trabalho de armazenamento selecionado fique sobrecarregado e os limites de estoque sejam ignorados.
    - **Arredondar até a LP completa** – esta estratégia é usada para arredondar para cima a quantidade de estoque para corresponder à quantidade de placa de licença que é atribuída aos itens que devem ser separados. Você só pode usar essa estratégia para diretivas de localização de reabastecimento do tipo *Separação*. Se essa estratégia for configurada junto com um limite de estoque de localização, ela poderá fazer com que o local de trabalho de armazenamento selecionado fique sobrecarregado e os limites de estoque sejam ignorados.
    - **Placa de licença guiada** – Use esta estratégia quando você liberar a ordem para o depósito para criar o trabalho de separação e armazenamento. Você pode usar essa abordagem para várias placas de licença. Esta estratégia tentará reservar e criar um trabalho de separação em relação aos locais que mantêm as placas de licença solicitadas que foram associadas às linhas da ordem de transferência. No entanto, se essas ações não puderem ser concluídas, mas você ainda desejar criar um trabalho de separação, retorne a outra estratégia para as ações de diretiva de localização. De acordo com as necessidades de processo comercial, talvez você também queira pesquisar o estoque em outra área do depósito.
    - **Local vazio sem trabalho de entrada** – use esta estratégia para detectar locais vazios. O local será considerado vazio se não houver estoque físico e nenhum trabalho de entrada esperado. Você só pode usar essa estratégia para diretivas de localização com um tipo de trabalho de *Colocar*.
    - **Classificação por vencimento local FIFO** – Use a estratégia FIFO (primeiro a entrar, primeiro a sair) para enviar itens rastreados por lote e itens não rastreados por lote, com base na data em que o estoque deu entrada no depósito. Esse recurso pode ser especialmente útil para estoque não rastreado por lote, no qual nenhuma data de vencimento está disponível para uso para classificação. A estratégia FIFO encontra o local que contém a data de classificação por vencimento mais antiga e aloca a separação com base nessa data.
    - **Classificação por vencimento local LIFO** – Use a estratégia LIFO (último a entrar, último a sair) para enviar itens rastreados por lote e itens não rastreados por lote, com base na data em que o estoque deu entrada no depósito. Esse recurso pode ser especialmente útil para estoque não rastreado por lote, no qual nenhuma data de vencimento está disponível para uso para classificação. A estratégia LIFO encontra o local que contém a data de classificação por vencimento mais recente e aloca a separação com base nessa data.

## <a name="example-using-location-directives"></a>Exemplo: uso de diretivas de localização

Neste exemplo, consideraremos um processo de ordem de compra em que a diretiva de localização deve encontrar capacidade livre em um depósito para itens do estoque que acabaram de ser registrados na doca de recebimento. Primeiro, você precisa localizar a capacidade livre no depósito, consolidando o estoque disponível existente. Se a consolidação não for possível, você precisará encontrar um local vazio.

Nesse cenário, você deve definir duas ações de diretiva de localização. A primeira ação na sequência deve usar a estratégia *Consolidar* e a segunda deve usar a estratégia *Local vazio sem trabalho de entrada*. A menos que você defina uma terceira ação para lidar com um cenário de estouro de capacidade, dois resultados serão possíveis quando não houver mais capacidade no depósito: o trabalho pode ser criado mesmo que nenhum local seja definido ou o processo de criação de trabalho pode falhar. O resultado é determinado pela configuração na página **Falhas na diretiva de localização**, na qual você pode decidir se selecionará a opção **Parar de trabalhar em falha de diretiva de localização** para cada tipo de ordem de serviço.

## <a name="next-step"></a>Próxima etapa

Depois de criar diretivas da localização, você pode associar cada código de diretiva a um código do modelo de trabalho para a criação de trabalho. Para obter mais informações, consulte [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](./control-warehouse-location-directives.md).

## <a name="additional-resources"></a>Recursos adicionais

- Vídeo: [Detalhamento da configuração de gerenciamento de depósito](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Tópico de ajuda: [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]