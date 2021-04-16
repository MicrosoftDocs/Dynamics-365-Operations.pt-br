---
title: Agrupamento do sistema em uma lista de trabalho aberta
description: Este tópico descreve como filtrar a lista aberta de trabalho em um dispositivo móvel.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a4faa358fc598859bf3b226b48b57594317f37d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831089"
---
# <a name="system-grouping-on-an-open-work-list"></a>Agrupamento do sistema em uma lista de trabalho aberta

[!include [banner](../includes/banner.md)]

Ao usar um campo de agrupamento de sistema, você pode filtrar uma lista de trabalho aberta sem ter que editar o item de menu do dispositivo móvel.
Onde aplicável, o agrupamento de sistemas funciona para filtrar uma lista de trabalho em um único campo de cabeçalho de trabalho. Você não pode usar o agrupamento de sistema para filtrar em campos de nível de linha.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Configurar o agrupamento do sistema em uma lista de trabalho aberta
Use estas etapas para configurar o agrupamento do sistema em uma lista de trabalho aberta.

-   Em um item de menu de dispositivo móvel, selecione **Modo: Indireto** e **Código de atividade: Exibir lista de trabalho aberta**. As seguintes opções estão disponíveis. Essas opções são necessárias para o agrupamento de sistema em uma lista de trabalho. 

|        Opção         |                                                                                                                                                                                                                                                                         descrição                                                                                                                                                                                                                                                                         |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Permitir o agrupamento do sistema |                                                                                                                                                                                                                                                 Permite o agrupamento de sistema para um item de menu selecionado da lista de trabalho.                                                                                                                                                                                                                                                  |
| Campo de agrupamento do sistema | Disponível se <strong>Permitir trabalhos de sistema</strong> estiver definido como <strong>Sim</strong>. Selecione o campo que determina como o trabalho de escolha será agrupado para os trabalhadores. Por exemplo, se você selecionar o campo <strong>ShipmentId</strong>, o trabalhador verificará a ID da remessa para agrupar o trabalho de separação. Todo o trabalho para a remessa será então atribuído ao trabalhador. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Use o campo <strong>Rótulo do agrupamento de sistema</strong> para informar ao trabalhador o que verificar. |
| Etiqueta de agrupamento do sistema |                       Disponível se <strong>Permitir trabalhos de sistema</strong> estiver definido como <strong>Sim</strong>. Insira as informações para o trabalhador sobre o que verificar quando o trabalho de separação for agrupado. Por exemplo, se você estiver usando o campo <strong>ShipmentId</strong> para agrupar o trabalho de separação por remessa, poderá inserir ID da Remessa no campo. Este campo requer que você crie um item de menu para usar o trabalho existente agrupado pelo sistema. Você também deverá selecionar o campo para agrupar no campo <strong>Agrupamento do sistema</strong>.                       |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]