---
title: Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações
description: Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace_
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 29ee23164430f219ff3d0c94216a8be43f480ce309f6cdac3dac6ed5b6d030af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730073"
---
# <a name="youre-prompted-to-save-item-coverage-settings-even-though-you-made-no-changes"></a>Você será solicitado a salvar as configurações de cobertura do item, embora não tenha feito alterações

Número da base de dados de conhecimento: 4615588

## <a name="symptoms"></a>Sintomas

Em alguns cenários, você pode receber a seguinte mensagem ao abrir a página **Cobertura de item** depois de importar itens por meio da entidade *Cobertura de item V2*:

> Deseja salvar suas alterações antes de fechar?

Você recebe esta mensagem, embora não tenha feito nenhuma alteração.

## <a name="resolution"></a>Resolução

A página **Cobertura de item** inclui uma lógica padrão complexa que pode fazer com que a mensagem seja mostrada depois que mudanças diretas foram feitas recentemente no banco de dados, como por meio de importação de entidade. Por exemplo, o campo de entidade `AREGENERALSETTINGSOVERRIDDEN` é definido como *Não*, mas você importa um arquivo que fornece valores novos ou modificados para campos como `PRODUCTCOVERAGEGROUPID` e/ou `VENDORACCOUNTNUMBER`. Nesse caso, como o campo `AREGENERALSETTINGSOVERRIDDEN` está definido como *Não*, os valores são automaticamente apagados dos campos quando você abre a página **Cobertura de item** pela primeira vez após a importação. Se você salvar as alterações conforme as solicitações da caixa de mensagem, elas serão armazenadas no banco de dados. Caso contrário, você receberá a mesma mensagem na próxima vez que abrir a página.

Para evitar esse comportamento, mas também incluir valores para campos como `PRODUCTCOVERAGEGROUPID` por meio da importação de entidade, defina `AREGENERALSETTINGSOVERRIDDEN` como *Sim* ao importar.
