---
title: Entidade de atividades do contêiner
description: Este artigo fornece informações sobre atividades de contêiner, que são usadas para rastrear o progresso de contêineres de remessa.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: b69d26ee8abaa403f6a0ef3b03d9015fe507dd5b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873946"
---
# <a name="container-activities-entity"></a>Entidade de atividades do contêiner

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

As atividades de contêiner são usadas para rastrear o progresso de contêineres de remessa. Um registro é criado para cada trecho atribuído ao modelo de jornada selecionado no momento da criação do contêiner de remessa. Os registros também são criados quando o contêiner de remessa é criado por uma entidade de dados.

As informações sobre o progresso de um contêiner de remessa em trânsito em geral são recebidas de uma fonte externa. A entidade de atividades de contêiner permite que uma fonte externa, como um controlador de frete, atualize diretamente o registro. Portanto, não é necessária atualização manual de dados.

## <a name="container-activities-itmcontaineractivityentity"></a>Atividades do contêiner (ITMContainerActivityEntity)

Você pode usar a entidade de atividades de contêiner (`ITMContainerActivityEntity`) para criar registros de atividades adicionais. Como alternativa, um controlador de frete pode passar atualizações para um valor confirmado de **Data final real**.

| Nome | Mapeamento | Tipo de dados | Chave | Obrigatório |
|---|---|---|---|---|
| Data de término real | ITMContainerActivityTable.ActualEndDate | Datetime | Número | Número |
| Modo de entrega | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | Número | Número |
| Data de término estimada | ITMContainerActivityTable.EsimatedDate | Datetime | Número | Número |
| Número da linha | ITMContainerActivityTable.LineNum | Numeric(32, 16) | **Sim** | Número |
| Notas | ITMContainerActivityTable.Notes | nvarchar(MAX) | Número | Número |
| Atividade | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | Número | **Sim** |
| Contêiner de remessa | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Sim** | **Sim** |
| Viagem | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Sim** | **Sim** |
| Trecho | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | Número | **Sim** |
| Provedor de serviços | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | Número | Número |
| Temperatura | ITMContainerActivityTable.ShipTemperature | Numeric(32, 6) | Número | Número |
| Embarcação | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | Número | Número |
| Data inicial | ITMContainerActivityTable.StartDate | Datetime | Número | Número |

## <a name="tracking-control"></a>Controle de acompanhamento

O centro de controle de acompanhamento permite que uma atualização de um campo de origem especificado seja disparada por uma atualização de um campo de destino especificado. Se o valor do campo de origem e o valor do campo de destino forem atualizados usando a entidade de atividades de contêiner, o campo de destino mostrará o valor da entidade. Esse comportamento está relacionado a registros de controle de acompanhamento com um valor **Criar tipo** de *Prazo de entrega*.

Para áreas de custo com um valor **Criar tipo** de *Atualização de status* ou *Em branco* (que é um valor definido pelo usuário), o sistema atualizará o status da viagem ou o campo de destino de acordo com a configuração do controle de acompanhamento.

## <a name="calculated-fields"></a>Campos calculados

Os valores dos campos a seguir em um registro de atividades de contêiner são calculados com base nos valores de outros campos. Embora esses campos calculados não sejam incluídos na entidade de dados, eles serão definidos se os campos em que os cálculos se baseiam forem fornecidos.

- **Dias estimados** = **Data de término estimada** – **Data de início**
- **Dias reais** = **Data de término real** – **Data de início**
