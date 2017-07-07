---
title: Agrupamento do sistema em uma lista de trabalho aberta
description: "Este tópico descreve como filtrar a lista aberta de trabalho em um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: dbf0e49b1156c54cd37bbbe57ca564cdbc45fb2d
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="system-grouping-on-an-open-work-list"></a>Agrupamento do sistema em uma lista de trabalho aberta

[!include[banner](../includes/banner.md)]

Ao usar um campo de agrupamento de sistema, você pode filtrar uma lista de trabalho aberta sem ter que editar o item de menu do dispositivo móvel.
Onde aplicável, o agrupamento de sistemas funciona para filtrar uma lista de trabalho em um único campo de cabeçalho de trabalho. Você não pode usar o agrupamento de sistema para filtrar em campos de nível de linha.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Configurar o agrupamento do sistema em uma lista de trabalho aberta
Use estas etapas para configurar o agrupamento do sistema em uma lista de trabalho aberta.

-   Em um item de menu de dispositivo móvel, selecione **Modo: Indireto** e **Código de atividade: Exibir lista de trabalho aberta**. As seguintes opções estão disponíveis. Essas opções são necessárias para o agrupamento de sistema em uma lista de trabalho. 

| Opção        | descrição   | 
| ------------- | ------------- |
| Permitir o agrupamento do sistema   | Permite o agrupamento de sistema para um item de menu selecionado da lista de trabalho.| 
| Campo de agrupamento do sistema   | Disponível se **Permitir trabalhos de sistema** estiver definido como **Sim**. Selecione o campo que determina como o trabalho de escolha será agrupado para os trabalhadores. Por exemplo, se você selecionar o campo **ShipmentId**, o trabalhador verificará a ID da remessa para agrupar o trabalho de separação. Todo o trabalho para a remessa será então atribuído ao trabalhador. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Use o campo **Rótulo do agrupamento de sistema** para informar ao trabalhador o que verificar. |
| Etiqueta de agrupamento do sistema   | Disponível se **Permitir trabalhos de sistema** estiver definido como **Sim**. Insira as informações para o trabalhador sobre o que verificar quando o trabalho de separação for agrupado. Por exemplo, se você estiver usando o campo **ShipmentId** para agrupar o trabalho de separação por remessa, poderá inserir ID da Remessa no campo. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Você também deverá selecionar o campo para agrupar no campo **Agrupamento do sistema**.|
