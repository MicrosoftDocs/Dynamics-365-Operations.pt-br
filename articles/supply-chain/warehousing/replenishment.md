---
title: Reabastecimento
description: "Este tópico descreve as estratégias de reabastecimento que estão disponíveis para os depósitos que usam a funcionalidade que está disponível no Gerenciamento de depósito."
author: Mirzaab
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSReplenishmentTemplates
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 90043
ms.assetid: 49fa97eb-8e10-49a5-9261-1e393159f178
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 41f77a837f446e0ef263f1554a333d6e48248a0e
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="replenishment"></a>Reabastecimento

[!include [banner](../includes/banner.md)]

Este tópico descreve as estratégias de reabastecimento que estão disponíveis para os depósitos que usam a funcionalidade que está disponível no Gerenciamento de depósito. As informações deste tópico não se aplicam à solução de armazenamento disponível no Gerenciamento de estoque.

As seguintes estratégias de reabastecimento estão disponíveis:

- **Reabastecimento baseado em demanda** – essa estratégia cria o trabalho de reabastecimento para ordens de saída ou cargas, caso o estoque não esteja disponível quando o trabalho for criado pela onda. Por exemplo, se a quantidade necessária para uma ordem de venda não estiver disponível quando uma onda for processada, será possível criar o trabalho de reabastecimento.
- **Reabastecimento mín./máx.** – essa estratégia usa limites mínimo e máximo de estoque para determinar quando as localizações deverão ser reabastecidas. Os critérios de item e localização definem o estoque avaliado para reabastecimento. Modelos de reabastecimento mín./máx. são o principal mecanismo para manter os níveis ideais em locais de separação. Para ajudar a garantir que estoque nominal escolhido suficiente esteja disponível para ser compatível com a demanda da onda, você pode usar a demanda de reabastecimento como um suplemento entre ciclos de reabastecimento mín./máx.
- **Carregar o reabastecimento por demanda** – essa estratégia soma a demanda por várias cargas e cria o trabalho de reabastecimento necessário para os locais de separação relevante de ações. Essa estratégia ajuda a garantir que as cargas criadas possam ser separadas no depósito depois que elas são lançadas.
- **Reabastecimento imediato** – Esta estratégia reabastece o estoque antes de uma onde ser executada, se a alocação falhar para uma linha de diretiva de localização que tem o modelo de reabastecimento. 

Todas as quatro estratégias criam trabalho de reabastecimento, com base em um modelo de reabastecimento.

## <a name="wave-demand-replenishment"></a>Reabastecimento de demanda de onda
O reabastecimento de demanda de onda cria um trabalho de reabastecimento, baseado na demanda, se a quantidade que é necessária para ordens de produção, kanbans, ordens de saída ou carregamentos não está disponível quando uma onda cria trabalho. O modelo de reabastecimento contém informações sobre os critérios de item, a unidade de medida, o incremento de demanda e o local. 

Diretivas locais são usadas para determinar qual local deve ser reabastecido. Você vincula essas diretivas de local ao modelo de reabastecimento usando o campo **Código de diretiva**. Se o campo **Código de diretiva** não for definido, as consultas são usadas para determinar qual diretiva local deve ser usada. Observe que se não for especificado um código de diretiva no modelo de reabastecimento e a diretiva local tiver um código de diretiva, a diretiva local será ignorada, mesmo se a consulta na diretiva local estiver correta. Escolha diretivas locais que são usadas para determinar de onde obter o estoque para o reabastecimento. 

Além de criar um modelo, você deve especificar algumas configurações de reabastecimento no modelo de onda. O modelo de onda deve conter uma etapa de onda para reabastecimento executada somente se um item não for alocado com sucesso. Esta etapa de onda de reabastecimento usa um código de etapa de onda para determinar qual modelo de reabastecimento deve ser usado. Além de ter uma etapa de onda para reabastecimento, você deve garantir que o **Reabastecimento** seja selecionado na seção **Métodos** do modelo de onda. 

A página **Modelo de reabastecimento** inclui uma caixa de seleção **Permitir que a demanda de onda use quantidades não reservadas**. Marca esta caixa de seleção se o reabastecimento de demanda tiver que deduzir quantidades de trabalho não reservadas geradas do modelo selecionado de reabastecimento. Selecione esta caixa de seleção para cada modelo existente de reabastecimento para permitir que modelos de reabastecimento de demanda usem esta lógica. Quando o reabastecimento de demanda é disparado no depósito, ele deduzirá a demanda de trabalho de reabastecimento existente com quantidades não reservadas, se o trabalho for gerado por modelos de reabastecimento com a caia de seleção **Permitir que a demanda da onda use quantidades não reservadas** selecionada.

O reabastecimento de demanda é suportado para pedidos de vendas, ordens de transferência, ordens de produção e kanbans. 

## <a name="minmax-replenishment"></a>Reabastecimento mín./máx.
No reabastecimento mín./máx., estoque é reabastecido para que esteja também entre os limites máximo e mínimo que foram definidos. Normalmente, este processo ocorre uma vez por dia para ajudar a garantir que todos os locais de separação são preenchidos para o nível máximo antes da separação ser iniciada. 

Os valores mínimo e máximo são definidos em um modelo de reabastecimento. Muitas das configurações no modelo são semelhantes as configurações nos modelos que são usadas no reabastecimento de demanda da onda. O modelo deve conter uma linha para cada item e localização. Quando você executa o reabastecimento usando o trabalho em lotes, o Microsoft Dynamics 365 for Finance and Operations avalia se o reabastecimento é necessário usando a sequência na qual as linhas estão organizadas. 

Observe que a estratégia de reabastecimento mínima/máxima não pode reabastecer um local vazio, a menos que o local esteja definido como o local fixo para o item. Se a localização que deve ser reabastecida não estiver em um local fixo, o sistema não poderá determinar qual item deverá ser reabastecido. Portanto, pelo menos alguma quantidade disponível é necessária antes de reabastecimento.

## <a name="load-demand-replenishment"></a>Reabastecimento de demanda de carga
Carregar o reabastecimento por demanda soma a demanda por várias cargas e cria o trabalho de reabastecimento necessário para os locais de separação relevante de ações. Reabastecimento de demanda de carga semelhante ao reabastecimento de demanda de onda de várias maneiras. A principal diferença é como e quando o reabastecimento de demanda de carga e reabastecimento de demanda de onda são executados. Como o reabastecimento mín./máx., reabastecimento de demanda de carga é executado por meio de um trabalho em lotes. Para configurar o trabalho em lotes, na página **Carregar reabastecimento por demanda**, selecione o modelo de reabastecimento para usar e definir uma consulta de filtro para especificar quais cargas são usadas para determinar a demanda. A consulta local define os locais que qualquer quantidade disponível será subtraída para atender à demanda de cargas agregada.

## <a name="immediate-replenishment"></a>Reabastecimento imediato
Em vez de ter que somar a demanda no final de um processo de alocação e fazer o reabastecimento com base na quantidade resumida, você pode aplicar a estratégia instantânea de reabastecimento. Quando você usa esta estratégia, o estoque pode ser reabastecido imediatamente após a linha da diretiva da localização falhar. Portanto, você pode configurar o reabastecimento de maneira que ele seja restrito por unidades específicas, e de forma que ele use as quantidades que são definidas para locais específicos.

## <a name="replenishment-prerequisites"></a>Pré-requisitos de reabastecimento

|      Pré-requisito       |                                                                                                                                descrição                                                                                                                                 |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          Item           |                                                                                                        O item deve ser habilitado para os processos de gerenciamento de depósito.                                                                                                        |
|        Depósito        | O depósito deve ser habilitado para os processos de gerenciamento de depósito. Para habilitar um depósito para processos de gerenciamento de depósito, na página <strong>Depósitos</strong>, selecione o depósito e selecione a opção <strong>Usar processos de gerenciamento de depósito</strong>. |
| Modelos de reabastecimento |                                                                   Pelo menos um modelo de reabastecimento deve ser configurado para reabastecimento mín./máx., reabastecimento de demanda de onda ou reabastecimento de demanda de carga.                                                                   |
|        Locais        |                                                                                                       Locais devem ser criados e conectados a um perfil de local.                                                                                                       |
|    Perfis de localização    |                                                                                                        Perfis de local são necessários para criar locais.                                                                                                        |
|   Diretivas de localização   |                                                       Diretivas de localização são necessárias para orientar o trabalho para os locais onde o reabastecimento é necessário e para os locais de onde o estoque é originário.                                                        |
|     Modelos do trabalho      |                                                   Modelos de trabalho do tipo <strong>Reabastecimento</strong> são necessários para criar o trabalho de reabastecimento para que o estoque possa ser movido para os locais desejados.                                                    |


