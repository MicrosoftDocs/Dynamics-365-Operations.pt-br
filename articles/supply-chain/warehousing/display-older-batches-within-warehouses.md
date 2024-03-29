---
title: Configurar Exibir lotes mais antigos no depósito em um dispositivo móvel
description: Este artigo descreve como configurar um dispositivo móvel para exibir uma lista de locais com lotes mais antigos do que o local atual de uma linha de trabalho.
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
ms.openlocfilehash: 5788b42483f2c3046b0d20f45115b98d62cce213
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900525"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>Configurar para exibir lotes mais antigos no depósito em um dispositivo móvel

[!include [banner](../includes/banner.md)]

A configuração **Exibir lotes mais antigos no depósito** permite exibir uma lista de locais com lotes mais antigos do que o local atual da linha de trabalho. A lista de locais exibidos inclui informações sobre os lotes mais antigos no local com a data de vencimento e o estoque físico de cada lote. Você pode optar por separar de um novo local ou por continuar separando do local atual. 
- Separação de um novo local- se você selecionar um novo local de separação, a linha de trabalho atual será atualizada para usar o novo local e o trabalho continuará como de costume com o novo local. Para que o novo local seja válido, ele deverá ter a quantidade disponível suficiente para a linha de trabalho inteira. Se a quantidade necessária não estiver disponível, a linha de trabalho não será atualizada, e a lista será exibida. 
- Continuar separando do local atual - se você continuar com o local da linha de trabalho atual, as quantidades da linha de trabalho continuarão a ser separadas do local original.

## <a name="where-it-applies"></a>Aplica-se a
Exibir lotes mais antigos no depósito é configurado em itens de menu de dispositivo móvel e afeta a seleção dos itens abaixo do lote.

## <a name="set-up-display-older-batches-within-warehouse"></a>Configurar Exibir lotes mais antigos no depósito
A configuração **Exibir lotes mais antigos no depósito** estará disponível em itens de menu de dispositivo móvel quando a opção **Separar lote mais antigo** estiver definida como **Avisar**.

- Em **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu de dispositivo móvel**, defina **Usar rede existente** como **Sim** para o item de menu e selecione **Avisar** no campo **Escolher lote mais antigo**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]