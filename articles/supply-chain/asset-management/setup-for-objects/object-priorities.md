---
title: Níveis de serviço do ativo
description: Este tópico explica níveis de serviço do ativo no Asset Management.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4163d059fda4ae0120d5c989e744c5a5fe0f5892
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808275"
---
# <a name="asset-service-levels"></a>Níveis de serviço do ativo

[!include [banner](../../includes/banner.md)]

 

Este tópico explica níveis de serviço do ativo no Asset Management. Os níveis de serviço de ativos estão relacionados a ativos, e são transferidos para solicitações de manutenção e ordens de serviço. Eles são usados para calcular a prioridade de ordens de serviço durante o agendamento da ordem de serviço. Os níveis de serviço de ativo podem ser alterados, se alterações forem necessárias.

Para obter mais informações sobre a instalação relacionadas ao cálculo de pontuações de classificação para o agendamento da ordem de serviço, consulte [Parâmetros do Asset Management](../setup-for-objects/enterprise-asset-management-parameters.md). Você deve configurar pelo menos um registro padrão para o nível de serviço de ativo. Esse registro padrão será usado se nenhuma outra correspondência for encontrada durante o agendamento da ordem de serviço.

**Exemplo 1:** o nível de serviço padrão usado caso nenhuma outra correspondência seja encontrada. Nesse registro, você seleciona apenas um nível de serviço.

**Exemplo 2:** um serviço de alto nível usado para agendar trabalhos para o motor de um caminhão Volvo. Nesse registro, você seleciona um tipo de ativo relevante (por exemplo, **Motor de Caminhão**), um fabricante (**Volvo**) e um nível de serviço.

## <a name="set-up-asset-service-levels"></a>Configurar níveis de serviço de ativo

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Níveis de serviço de ativo**.
2. Selecione **Novo** para criar um registro.
3. Dependendo do nível de detalhes necessários para o nível de serviço do ativo, faça seleções relevantes nos campos **Local funcional**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Tipo de ordem de serviço** e **Nível de serviço**.

    > [!NOTE]
    > Quando o nível de serviço de ativo é usado para solicitações de manutenção e ordens de serviço, o Asset Management examina todos os registros de nível de serviço de ativos para verificar se há uma possível correspondência. Ele sempre verifica a combinação mais específica primeiro. Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Tipo de ordem de serviço**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Ativo** e assim em diante. Como você pode perceber no layout da página **Níveis de serviço de ativo**, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência. Se nenhuma correspondência for encontrada, o registro padrão que não possui nenhuma seleção nos campos é usado.

4. No campo **Nível de serviço**, selecione um número que indique o nível de serviço (prioridade).


> [!NOTE]
> Se você alterar um registro de nível de serviço de ativo na página **Níveis de serviço de ativo** depois de já tê-lo usado em uma ordem de serviço, o nível de serviço em solicitações de manutenção e ordens de serviço não será atualizado de forma correspondente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]