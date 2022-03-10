---
title: Zonas de quarentena para não conformidades
description: Este tópico descreve como criar e usar zonas de quarentena para não conformidades.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 207950a2ff4057853488f75d0e302a049d228b76
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578455"
---
# <a name="quarantine-zones-for-nonconformances"></a>Zonas de quarentena para não conformidades

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar e usar zonas de quarentena para não conformidades.

Use a página **Zonas de quarentena** para definir zonas que podem ser atribuídas a não conformidades. Ao criar uma não conformidade, você pode definir os campos **Zona de quarentena** e **Tipo de quarentena** na guia **Geral** da página **Não conformidades**. O campo **Zona de quarentena** normalmente indica a área ou o local em que o item está localizado. O campo **Tipo de quarentena** define o item como *Uso restrito* ou *Inutilizável*.

Ao imprimir um relatório de não conformidade ou de correções para uma não conformidade, você pode exibir a zona de quarentena na qual o item está localizado.

Você também pode imprimir um rótulo de não conformidade para uma não conformidade. Este relatório mostra a zona de quarentena atribuída e informações sobre o uso para fornecer orientações sobre como manusear material defeituoso. As zonas de quarentena podem corresponder a locais de estoque ou recursos de operações.

## <a name="examples-of-quarantine-zones"></a>Exemplos de zonas de quarentena

### <a name="example-1"></a>Exemplo 1

Você trabalha em uma empresa de fabricação de eletrônicos que produz e distribui televisões, alto-falantes e players de mídia. Nesse caso, você pode configurar uma zona de quarentena para representar cada tipo de produto.

### <a name="example-2"></a>Exemplo 2

Três compartimentos e dois racks são usados para armazenar itens que não estão em conformidade. Nesse caso, você pode configurar cinco zonas de quarentena, uma para cada compartimento e cada rack.

## <a name="create-a-quarantine-zone"></a>Criar uma zona de quarentena

1. Acesse **Gerenciamento de estoque \> Configuração \> Gerenciamento de qualidade \> Zonas de quarentena**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Zona de quarentena** – Insira um nome ou uma ID exclusiva para a zona de quarentena.
    - **Descrição** – Insira uma descrição detalhada da zona de quarentena.

1. Feche a página.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Trabalhadores responsáveis por aprovar não conformidades](quality-responsible-workers.md)
- [Tipos de problema para não conformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](quality-charges.md)
- [Operações para não conformidades](quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
