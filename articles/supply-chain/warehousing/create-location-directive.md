---
title: Criar diretivas de localização
description: Este tópico explica como criar diretivas de localização. As diretivas de localização são regras definidas pelo usuário que ajudam a identificar locais de separação e armazenamento para o movimento de estoque.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 4f634b7f526fd198b394af6d3870c43ee560813e
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016761"
---
# <a name="create-location-directives"></a>Criar diretivas de localização

[!include [banner](../includes/banner.md)]

Este tópico explica como criar diretivas de localização. As diretivas de localização são regras definidas pelo usuário que ajudam a identificar locais de separação e armazenamento para o movimento de estoque. Por exemplo, para uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão colocados.

> [!NOTE]
> Este tópico se aplica aos recursos do módulo **Gerenciamento de depósito**. Não se aplica aos recursos do módulo de [Gerenciamento de estoque](../inventory/inventory-home-page.md).

É possível usar as diretivas de localização para executar as seguintes tarefas:

- Remover itens recebidos.
- Separar e preparar itens para transações de saída.
- Separar e armazenar matéria-prima para produção.
- Reabastecer as localizações.

## <a name="prerequisites"></a>Pré-requisitos

Antes de criar uma diretiva de localização, siga estas etapas para verificar se os pré-requisitos estão em vigor.

1. Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Depósitos**.
1. Criar um depósito.
1. Na FastTab **Depósito** , defina a opção **Usar processos de gerenciamento de depósito** como *Sim*.
1. Criar localizações, tipos de localização, perfis de localização e formatos da localização. Para obter mais informações, consulte [Configurar localizações em um depósito habilitado para WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Criar sites, zonas e grupos de zonas. Para obter mais informações, consulte [Configuração do depósito](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) e [Configurar localizações em um depósito habilitado para WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Configurar

### <a name="create-location-directives"></a>Criar diretivas de localização

Para criar uma diretiva de localização, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.
1. No painel de lista, defina o campo **Tipo de ordem de serviço** como o tipo de transação de estoque para o qual está criando uma diretiva de localização.
1. No Painel de Ações, selecione **Novo** para criar uma diretiva de localização.
1. Para a nova diretiva de localização, defina os campos conforme descrito na seguinte tabela.

    | Campo | descrição |
    |---|---|
    | Número de seqüência | Insira um número inteiro que indique a posição da sequência da diretiva de localização. As posições da sequência determinam quando cada diretiva de localização será processada para o tipo de ordem de serviço selecionado. |
    | Nome | Digite um nome para a diretiva de localização. | 
    | Tipo de trabalho | Selecione o tipo de trabalho que deve ser executado. A lista de valores depende do tipo de transação de estoque que você selecionou no campo **Tipo de ordem de serviço**. Os valores a seguir podem estar disponíveis:<ul><li>**Colocar** – a diretiva de localização tentará encontrar a melhor solução para colocar ou localizar o estoque que entra no sistema por meio de recebimento, produção ou ajustes de estoque. A diretiva de localização também é usada para definir o local de colocação no estágio ou o local da remessa do baydoor final no fluxo de saída.</li><li>**Separação** – a diretiva de localização tentará encontrar os melhores locais para reservar estoque fisicamente (criar trabalho). A separação pode ser concluída (ou seja, a linha de trabalho de separação pode ser fechada), mesmo se o trabalho não for concluído. O usuário pode concluir a separação física. No sistema, essa ação é uma etapa de separação. Em seguida, o usuário poderá cancelar de um dispositivo móvel e concluir o trabalho (por exemplo, colocação) depois. Porém, o cabeçalho de trabalho é fechado pela primeira vez quando a colocação final é concluída.</li><li>**Contagem** , **Ajustes** , **Personalização** , **Alteração de status de estoque** , **Criação da placa de licença** , **Impressão** , **Alteração de status** , **Empacotar em placas de licença aninhadas** – esses valores não podem ser usados em configurações de diretivas de localização.</li></ul> |
    | Site | Selecione o site em que o trabalho deve ser concluído. |
    | Depósito | Selecione a localização do depósito em que o trabalho deve ser concluído. |
    | Código de diretiva | Selecione um código de diretiva para orientar a seleção de diretivas de localização que estão relacionadas às linhas de colocação do modelo de trabalho em que este código é atribuído. Na página **Código de diretiva** , é possível criar códigos que podem ser usados para conectar um modelo de trabalho a uma diretiva de localização. Também é possível usar essa página para estabelecer o link entre qualquer linha de modelo de trabalho e diretiva de localização (como localização de fase ou baydoor). Para obter mais informações sobre como configurar um código de diretiva com um modelo de trabalho, consulte [Controlar o trabalho do depósito usando modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md).<p>Se um código de diretiva estiver definido, o trabalho deve ser gerado, o sistema pesquisará diretivas de localização por código de diretiva e não por sequência. Dessa forma, você pode ser mais específico sobre o modelo do local usado para uma etapa específica em um modelo de trabalho, como a etapa de preparação de materiais.</p> |
    | Código de disposição | Selecione um código de disposição para redirecionar o armazenamento dos itens recebidos em um local. (Para obter mais informações, consulte [Configurar códigos de disposições](tasks/set-up-dispositions-codes.md).) Este campo está disponível somente quando o campo **Tipo de ordem de serviço** estiver definido como *Ordens de compra* , *Ordens de devolução* ou *Armazenamento de mercadorias acabadas*. |
    | Várias SKUs | Defina esta opção como *Sim* para usar várias unidades de manutenção de estoque (SKUs) em um local. Por exemplo, esta opção deve ser definida como *Sim* para o baydoor.<p>Se a opção **Várias SKUs** estiver definida como *Sim* , o local da colocação será especificado no trabalho (conforme esperado). No entanto, o local de colocação poderá manipular a colocação de vários itens somente se o trabalho incluir SKUs diferentes que devem ser separadas e colocadas, não se o trabalho incluir somente uma SKU que deve ser colocada.</p><p>Se a opção **Várias SKUs** estiver definida como *Não* , o local de colocação será especificado somente se a colocação tiver apenas um tipo de SKU.</p><p>Para usar ambas abordagens, é necessário especificar duas linhas com a mesma estrutura e configuração, mas defina a opção **Várias SKUs** como *Sim* para uma das linhas, e *Não* para outra. Em outras palavras, é necessário ter duas diretivas de localização idênticas para operações de colocação, mesmo que não precise diferenciar entre várias SKUs e SKUs únicas na ID de trabalho. Também é necessário definir uma diretiva de localização para a separação, se você tiver uma ordem com mais de um item.</p><p>**Observação:** se você definir a opção **Várias SKUs** como *Sim* para uma diretiva de localização do tipo de trabalho *Colocação* , o sistema sempre selecionará a primeira linha da diretiva de localização, independentemente de outras restrições criadas nas linhas.</p> |

1. Opcional: no Painel de Ações, selecione **Editar consulta** para selecionar os locais ou para especificar algumas restrições que se apliquem quando você selecionar uma diretiva de localização específica.
1. Na FastTab **Linhas** , crie uma ou mais linhas para especificar unidades e para atender ou reservar a quantidade em um depósito.
1. Em cada linha nova, defina os campos conforme descrito na seguinte tabela.

    | Campo | descrição |
    |---|---|
    | Número de seqüência | Insira um número inteiro que indique a posição da sequência da diretiva de localização. As posições da sequência determinam quando cada diretiva de localização é processada para o tipo de trabalho selecionado. |
    | Da quantidade | Especifique o intervalo de quantidade inicial para quando a sequência de grade intermediária deve ser selecionada. Especifique a quantidade na unidade de medida selecionada no campo **Unidade**. |
    | Quantidade final | Especifique o intervalo de quantidade final para quando a sequência de grade intermediária deve ser selecionada. Especifique a quantidade na unidade de medida selecionada no campo **Unidade**. |
    | Unidade | Selecione a unidade de medida dos itens.<p>É possível especificar uma quantidade mínima e uma quantidade máxima à qual a diretiva deve ser aplicada. Também é possível especificar se a diretiva deve ser usada para uma unidade de estoque específica. O campo **Unidade** na linha é usado somente para avaliação de quantidade.</p><p>Para determinar se uma linha de diretiva de localização é aplicável, o sistema avalia quantidades usando o valor de **Unidade** especificado na linha. Sempre que uma linha de diretiva de localização for acessada, o sistema tentará converter a unidade de demanda em uma unidade especificada na linha. Se a conversão da unidade não existir, o sistema avançará para a próxima linha.</p> |
    | Localizar quantidade | Este campo é válido somente ao tentar colocar ou localizar a quantidade no depósito. Em outras palavras, é válido apenas para o trabalho de *Colocação*. Selecione o método usado para avaliar se a quantidade está dentro do intervalo definido nos campos **Da quantidade** e **Até a quantidade**. Se a diretiva do local se destinar a uma transação de entrada, selecione uma destas opções:<ul><li>**Quantidade da placa de licença** – para avaliar se a quantidade está dentro dos intervalos de quantidade desejada, use a quantidade na placa de licença que está sendo recebida.</li><li>**Quantidade unitizada** – para avaliar se a quantidade está dentro dos intervalos de quantidade desejada, use a quantidade que está sendo unitizada durante a transação. Por exemplo, em um depósito, se puder receber uma quantidade de 1000 e dividi-la em 10 placas, cada uma delas com uma quantidade de 100, você poderá usar uma quantidade de 1000 itens, em vez de 100 placas de licença.</li><li>**Quantidade pendente** – para avaliar se a quantidade está dentro dos intervalos de quantidade desejada, use a quantidade restante a ser recebida na linha da ordem de compra que está sendo registrada no momento.</li><li>**Quantidade Esperada** – para avaliar se a quantidade está dentro dos intervalos de quantidade desejada, use a quantidade total da linha da ordem de compra, independentemente da quantidade que já foi recebida.</li></ul> |

1. Opcional: na FastTab **Linhas** , é possível definir os campos adicionais a seguir.

    | Campo | descrição |
    |---|---|
    | Restringir por unidade | Marque esta caixa de seleção para restringir as unidades de medida consideradas critérios de seleção válidos para as linhas de diretiva de localização. Quando as unidades de medida forem especificadas, somente os itens nos quais a unidade corresponde a pelo menos uma unidade definida para o grupo de sequências de unidades serão considerados como válidos para a seleção de linhas.<p>Por exemplo, a unidade está restrita a paletes e o item está associado a um grupo de sequências de unidades que inclui a unidade *paletes*. Nesse caso, os itens serão considerados como uma opção válida para a diretiva de localização.</p><p>No entanto, a caixa de seleção **Restringir por unidade** não controla a unidade ou as unidades aplicadas nas linhas de trabalho. A restrição de unidade é aplicável somente às unidades disponibilizadas por meio do grupo de sequências de unidades.</p><p>Por exemplo, um item está associado a um grupo de sequências de unidades que inclui as unidades *paletes* e *peças*. A unidade de medida foi definida, onde 1 palete = 100 peças, e a diretiva de localização usa a funcionalidade **Restringir por unidade** somente para paletes. Além disso, um modelo de trabalho foi definido para limitar a criação do cabeçalho de trabalho para 50 peças. Nesse caso, serão criadas linhas de trabalho de 50 peças.</p><p>Para especificar a unidade de medida para restrição, siga estas etapas</p><ol><li>Na FastTab **Linhas** , selecione **Restringir por unidade**. Este botão é disponibilizado somente após marcar a caixa de seleção **Restringir por unidade** na linha e selecionar **Salvar**.</li><li>No campo **Unidade** , selecione a unidade de medida para restringir os processos de separação e armazenamento.</li></ol> |
    | Arredondar para a unidade | Selecione esta opção para indicar se a separação de matéria-prima deve ser arredondada até um múltiplo da unidade de manuseio de material especificada no campo **Restringir por unidade**. Esse campo se aplica somente à separação de matéria-prima e às diretivas de localização do tipo *Separação*. |
    | Localizar quantidade da embalagem | Marque esta caixa de seleção se a quantidade de unidades de embalagem for especificada na página **Ordem de venda**. Se você marcar essa caixa de seleção, somente os locais com essa quantidade da unidade de embalagem serão selecionadas. |
    | Permitir divisão | Marque esta caixa de seleção para dividir a quantidade por vários locais. |
    | Modelo de reabastecimento imediato | Crie uma conexão a um modelo de reabastecimento para que o reabastecimento seja iniciado imediatamente se os itens não forem atribuídos. Se você deixar esse campo em branco, o reabastecimento do item não será iniciado até que todas as linhas da diretiva de localização sejam processadas.<p>Este campo está disponível somente nos tipos de ordem de serviço selecionados em que o reabastecimento é permitido, como *Ordens de venda* e *Separação de matéria-prima*.</p> |

1. No FastTab **Ações de diretiva de localização** , selecione **Novo** para selecionar o local ou o intervalo de locais.
1. O campo **Número de sequência** exibe a sequência em que a diretiva de localização será processada para o tipo de trabalho selecionado. Você pode modificar a sequência. No entanto, tenha cuidado com números de sequência para ações de diretiva de localização, pois elas serão sempre executadas nessa sequência.
1. No campo **Nome** , insira o nome da ação da diretiva de localização. Seja específico, para que fique claro qual é a ação.
1. Opcional: selecione **Editar consulta** para modificar os locais de depósito e outros critérios.
1. Opcional: é possível definir os campos adicionais a seguir para uma diretiva de localização.

    | Campo | descrição |
    |---|---|
    | Uso de localização fixa | Selecione quais locais a diretiva de localização deve considerar:<ul><li>**Localizações fixas e não fixas** – A diretiva de localização considerará todas as localizações.</li><li>**Somente localizações fixas para o produto** – A diretiva de localização considerará somente as localizações fixas dos produtos.</li><li>**Somente localizações fixas para a variante do produto** – A diretiva de localização considerará somente as localizações fixas das variantes do produto.</li></ul> |
    | Permitir estoque negativo | Marque esta caixa de seleção para permitir estoque negativo na localização de depósito especificada. |
    | Lote habilitado | Marque esta caixa de seleção para usar estratégias de lote para os itens habilitados para lotes. Se esta caixa de seleção for marcada e o campo **Estratégia** for definido como *Nenhum* , o sistema avançará para a próxima linha de ação. |
    | Estratégia | Selecione a estratégia que a diretiva de localização deve usar:<ul><li>**Nenhum** – nenhuma estratégia será usada.</li><li>**Fazer a correspondência da quantidade da embalagem** – esta estratégia verifica se um local de separação tem a quantidade de embalagem especificada. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Separação*.</li><li>**Consolidar** – esta estratégia consolida itens em um local específico quando itens semelhantes já estiverem disponíveis. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Colocação*. Em uma configuração típica para colocação, o sistema tenta consolidar na primeira linha de ação e, na segunda linha de ação, ele tenta executar a colocação sem a consolidação. A consolidação de mercadorias torna a separação posterior mais eficiente.</li><li>**Reserva de lotes FEFO** – esta estratégia é usada quando o estoque é localizado usando uma data de vencimento do lote e é alocado para reserva de lotes. A estratégia de reserva de lotes de primeiro a vencer, primeiro a sair (FEFO) também é usada quando o estoque é encontrado por meio de uma data de validade do lote além da data de vencimento. Você só pode usar essa estratégia para itens habilitados para lote. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Separação*. Ao selecionar essa estratégia, você substitui qualquer classificação de números de lote aplicada.</li><li>**Arredondar até a LP completa** – esta estratégia arredonda para cima a quantidade de estoque para corresponder à quantidade de placa de licença que é atribuída aos itens que devem ser separados. Esta estratégia pode ser usada somente para o tipo de reabastecimento de diretivas de localização e somente quando o campo **Tipo de trabalho** for definido como *Separação*.</li><li>**Local vazio sem trabalho de entrada** – esta estratégia é usada para detectar locais vazios. O local será considerado vazio se não houver estoque físico e nenhum trabalho de entrada esperado. Esta estratégia é válida somente quando o campo **Tipo de trabalho** for definido como *Colocação*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Exemplo do uso de diretivas de localização

Neste exemplo, consideraremos um processo de ordem de compra em que a diretiva de localização deve encontrar capacidade livre em um depósito para itens do estoque que acabaram de ser registrados na doca de recebimento. Primeiro, você precisa localizar a capacidade livre no depósito, consolidando o estoque disponível existente. Se a consolidação não for possível, você precisará encontrar um local vazio.

Nesse cenário, você deve definir duas ações de diretiva de localização. A primeira ação na sequência deve usar a estratégia **Consolidar** e a segunda deve usar a estratégia **Local vazio sem trabalho de entrada**. A menos que você defina uma terceira ação para lidar com um cenário de estouro de capacidade, dois resultados serão possíveis quando não houver mais capacidade no depósito: o trabalho pode ser criado mesmo que nenhum local seja definido ou o processo de criação de trabalho pode falhar. O resultado é determinado pela configuração na página **Falhas na diretiva de localização** , na qual você pode decidir se selecionará a opção **Parar de trabalhar em falha de diretiva de localização** para cada tipo de ordem de trabalho.

## <a name="next-step"></a>Próxima etapa

Depois de criar diretivas da localização, você pode associar cada código de diretiva a um código do modelo de trabalho para a criação de trabalho. Para obter mais informações, consulte [Controlar o trabalho do depósito por meio de modelos de trabalho e diretivas de localização](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Informações técnicas para administradores de sistemas

Se você não tiver acesso às páginas que são usadas para concluir essa tarefa, entre em contato com o administrador do sistema e forneça as informações que são mostradas na tabela a seguir.

| Categoria | Pré-requisito |
|---|---|
| Chaves de configuração | Vá para **Administração de sistema \> Configurar \> Configuração de licença**. Expanda a chave de licença de **Comércio** e selecione a chave de configuração **gerenciamento de Depósito e Transporte**. |
