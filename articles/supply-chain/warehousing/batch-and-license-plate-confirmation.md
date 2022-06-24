---
title: Confirmação de lote e placa de licença
description: Este artigo descreve como configurar e aplicar a confirmação de lote e placa de licença em um dispositivo móvel.
author: Mirzaab
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef0d528d23c1ee9424e35e29d39121d42ba548e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903714"
---
# <a name="batch-and-license-plate-confirmation"></a>Confirmação de lote e placa de licença

[!include [banner](../includes/banner.md)]

A confirmação do lote permite que você confirme se o lote correto está sendo separado do dispositivo móvel. Na seleção inicial do trabalho somente para itens *Lote acima\[local\]*, no qual o lote acima indica que o lote é colocado acima da localização na hierarquia de pesquisa, você deve verificar se o lote escolhido corresponde ao lote da linha de trabalho.

A confirmação da placa de licença permite que você confirme se a placa de licença correta está sendo selecionada no dispositivo móvel. Ao escolher o trabalho de um local de espera, você deve verificar se a placa de licença selecionada corresponde à placa de licença associada ao trabalho. Se o trabalho for iniciado pela verificação de uma placa de licença, a etapa de confirmação será ignorada.

## <a name="where-it-applies"></a>Aplica-se a

A confirmação aplica-se nos seguintes cenários:

- A confirmação de lote aplica-se às seleções iniciais de trabalho dos itens acima do lote.
- A confirmação de placa de licença se aplica a separações nos locais de espera.

> [!IMPORTANT]
> O reabastecimento não tem suporte para a confirmação da placa de licença. Ao executar o trabalho de reabastecimento, nenhuma etapa de confirmação da placa de licença é criada.

## <a name="set-up-batch-and-license-plate-confirmation"></a>Configurar confirmação de lote e placa de licença

Você pode configurar a confirmação de lote e de placa de licença dos itens de menu de dispositivo móvel.

1. Dos itens de menu de dispositivo móvel, insira a configuração de confirmação de trabalho.  
1. Selecione a opção para o lote ou a confirmação da placa de licença. As duas opções disponíveis para as separações por tipo de trabalho que não têm uma confirmação automática ativada.  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
