---
title: "Configuração de depósito"
description: "Este artigo explica como configurar um depósito. Ele inclui informações sobre como habilitar um layout de depósito e processos de depósito."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e312f953d6a29d26b98794ed213d6ec70f6aa4b7
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="warehouse-configuration"></a>Configuração de depósito

[!include[banner](../includes/banner.md)]


Este artigo explica como configurar um depósito. Ele inclui informações sobre como habilitar um layout de depósito e processos de depósito.

**Observação:** Este artigo se aplica aos recursos no módulo de**Gerenciamento de depósito** (estoque avançado). Não se aplica aos recursos de depósito no módulo de **Gerenciamento de depósito**.

## <a name="warehouse-layout"></a>Layout do depósito
O sistema de gerenciamento de depósito no Microsoft Dynamics 365 for Operations fornece uma maneira flexível de definir o layout de depósito para atender às necessidades de modificação, de forma que você possa obter uma ótima eficiência de depósito.

-   Você pode liquidar áreas de armazenamento de alta e baixa prioridade para o posicionamento ideal de mercadorias.
-   Você pode dividir o depósito em zonas para acomodar várias necessidades de armazenamento, como requisitos de temperatura, ou várias taxas de devolução de itens.
-   Você pode especificar locais de depósito em todos os níveis (por exemplo, site, depósito, corredor, rack, prateleira e posição de compartimento).
-   Você pode agrupar locais usando as configurações de restrição de capacidade física.
-   Você pode controlar como os itens são armazenados e separados, com base em regras definidas pela consulta.

Para usar o gerenciamento de depósito no Microsoft Dynamics 365 for Operations, você deve criar um depósito e habilitá-lo para as atividades de gerenciamento de depósito mais avançados ou mais especializadas. Na página **Depósitos**, selecione a opção **Usar processos de gerenciamento de depósito**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Grupos de zonas, zonas, tipos de localização, e localizações

Como parte do processo para habilitar um layout de depósito, é preciso definir grupos de zona de depósito, e zonas, perfis de localização, tipos de localização, e locais.

-   **Grupos de zonas** – Um agrupamento lógico ou físico das zonas dentro de um depósito.
-   **Zonas** – Um agrupamento lógico ou físico das localizações dentro de um depósito.
-   **Perfis de localização** – Um agrupamento lógico ou físico dos locais com as mesmas políticas de processo de local de depósito (por exemplo, uma combinação de números de item diferentes pode ser armazenada lá, e as mesmas restrições de capacidade física se aplicam).
-   **Tipos de locais** – Um agrupamento lógico ou físico dos locais de depósito. Por exemplo, você pode criar um tipo de localização para todos os locais de preparo. As configurações obrigatórias na página **Parâmetros de gerenciamento de depósito** conduzem o processo de definição dos tipos de local de preparo e o tipo de local de entrega final.
-   **Locais** – O nível mais baixo de informações sobre o local. Os locais são usados para controlar onde o estoque disponível é armazenado e separado em um depósito.

As entidades que você cria para definir o layout de depósito são usadas nas consultas configuradas por você nos modelos de trabalho para conduzir as ordens de trabalho no depósito. Sendo assim, ao definir as zonas, tipos de local, e assim por diante, considerem como as áreas diferentes no depósito são usadas para processos diferentes. Além disso, considere os fatores como as características físicas de uma área específica. Por exemplo, pode haver áreas onde você pode usar apenas um tipo de empilhadeira. Ou, se sua empresa tiver produção e produtos acabados dentro da mesma instalação, talvez queira criar um único depósito no Dynamics 365 for Operations, mas depois separar as duas operações criando dois grupos de zona. Dê nomes descritivos a suas entidades, para que seja fácil identificá-las quando você as usa em consultas de modelo.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Limites de estoque de local, perfis de localização, e locais de separação fixos

Considere o layout físico do depósito, para determinar os recursos de armazenamento (limites de armazenamento do local e perfis de localização) como parte de suas tentativas de obter ótimos processos de depósito. 

Os limites de armazenamento do local ajudam a garantir que não será criado trabalho para solicitar que o estoque seja colocado em uma localização que não possui a capacidade física necessária para suportá-lo. Por exemplo, se alguns locais dentro de um armazém podem conter apenas um palete por local, os limites de estoque de local podem ser ativados. O valor **Quantidade **pode ser definido para **1**, e o valor **Unidade **pode ser definido para **PL** dentro de um agrupamento de perfil de localização específico. 

Se outros cálculos avançados forem necessários para controlar as restrições de capacidade da localização, as configurações de perfil de local podem ser usadas. Nesse caso, o peso e o volume são considerados quando os cálculos de capacidade são feitos. 

Para obter processos de saída ideais, você deve avaliar se deseja usar locais de separação fixos e/ou locais de embalagem. Geralmente, o reabastecimento mínimo/máximo é usado para processos de reabastecimento de uma área de atacado para os locais de separação fixos, e várias localizações de separação fixas podem ser habilitadas no mesmo depósito e para as variantes de produto. Considere a flexibilidade que você pode obter habilitando os locais dedicados de excesso de reabastecimento de demanda que são usados somente para o processamento de reabastecimento de carga/onda.

### <a name="location-setup-wizard"></a>Assistente de configuração de localização

Para criar rapidamente as localizações em um depósito, você pode usar o assistente de **Configuração da localização**. Como parte desse processo, você pode facilmente manter o formato dos nomes do local.

## <a name="warehouse-processes"></a>Processos do depósito
Como parte da configuração do depósito, é importante que você habilite os processos de depósito de acordo com as necessidades comerciais. Os componentes mais importantes que você deve configurar são os modelos de onda, modelos de trabalho, grupos de trabalho, bem como diretivas de localização.

### <a name="wave-templates"></a>Modelos de onda

Os modelos de onda ajudam a habilitar o processo "Liberar para depósito". Assim que as linhas da ordem foram liberadas (diretamente dos documentos de origem, por meio dos processos do trabalho em lotes, ou por meio de cargas que já foram criadas), a funcionalidade do modelo da onda será usada. 

É possível criar três tipos de modelos de onda: 
-   **Remessa**
-   **Ordem de produção**
-   **Kanban** 

Os parâmetros são usados para definir até onde o sistema deve ir automaticamente no processamento de trabalho de saída. Um modelo de onda é selecionado com base na sequência do modelo de onda e nos critérios especificados no modelo. Se um modelo estiver listado na parte superior da sequência, os critérios nesse modelo são verificados pela primeira vez. Se os critérios puderem ser atendidos, o modelo de onda será processado. Caso contrário, os critérios no modelo seguinte são verificados, e assim por diante. Sendo assim, é recomendável colocar o modelo que contém o critério mais específico na parte superior da lista de sequência de modelo de onda, de modo que seja processado primeiro. Por exemplo, você deseja processar todo o trabalho para uma transportadora específica e atrasar temporariamente o processamento do trabalho de outras transportadoras. Nesse caso, o modelo de onda que seleciona o trabalho para a transportadora deve estar listado acima na sequência dos outros modelos. Caso contrário, o trabalho para outras transportadoras pode ser processado antes que o trabalho dessa transportadora seja concluído. 

Você deve especificar os métodos de processo de onda em cada modelo de onda. Os métodos disponíveis variam, dependendo do tipo de modelo de onda.

### <a name="work-templates"></a>Modelos do trabalho

As definições de modelo de trabalho desempenham uma função importante na definição dos processos de trabalho de gerenciamento de depósito. Definem qual trabalho é executado, e como o trabalho é feito. Os modelos também podem conter um código de diretiva que vincula a uma diretiva de localização para determinar onde o trabalho é executado. Os modelos de trabalho incluem uma consulta que especifica os critérios para o trabalho. Cada modelo deve incluir pelo menos uma operação de separação e uma operação de inserção para conduzir a operação básica de trabalho de transferência do estoque disponível de um local para outro. 

Se diversos funcionários precisarem ser capazes de processar o trabalho para algumas de suas operações de depósito, convém usar o conceito de *preparo* para o estoque e separar a execução do trabalho em diferentes classes de trabalho.

### <a name="work-pools"></a>Pools de trabalho

Os grupos de trabalho são usados para organizar o trabalho em grupos. Por exemplo, é possível criar um pool de trabalho para classificar o trabalho que ocorre em uma localização específica do depósito. Para todos os tipos de trabalhos, com exceção da contagem, é possível atribuir um pool de trabalho para um modelo de trabalho. Para a contagem cíclica, é possível atribuir um grupo de trabalho nas seguintes páginas:

-   Planos de contagem cíclica
-   Limites de contagem cíclica
-   Trabalho de contagem cíclica por localização
-   Trabalho de contagem cíclica por item

Ao usar modelos de trabalho para criar o trabalho, o pool de trabalho é atribuído automaticamente ao trabalho. 

As IDs de grupo de trabalho também podem ser usadas para limitar o tipo de trabalho que é direcionado para um funcionário específico do depósito, dado que esta funcionalidade é configurada no item relevante do menu de dispositivos móveis.

### <a name="location-directives"></a>Diretivas de localização

Como o nome sugere, as diretivas de localização são usadas para direcionar as transações de trabalho aos locais apropriados no depósito. Ou seja, elas definem onde separar e armazenar. 

Para facilitar e agilizar a definição de ações associadas a cada linha de diretiva da localização, use uma das estratégias predefinidas. Por exemplo, você pode usar a estratégia **Esvaziar a localização sem o trabalho de entrada** para procurar locais livres em um depósito, ou você pode usar a estratégia **Reserva de lotes FEFO** para a separação de saída de vendas.

<a name="see-also"></a>Consulte também
--------

[Configurar localizações em um depósito habilitado para WMS (guia de tarefas)](https://ax.help.dynamics.com/en/wiki/configure-locations-in-a-wms-enabled-warehouse/)




