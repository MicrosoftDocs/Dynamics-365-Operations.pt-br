---
title: Confirmação de separação de peças
description: Este tópico descreve como configurar e aplicar a confirmação de separação de peças de um dispositivo móvel.
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm, WHSRFMenuItem
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b85414dd1385dc3d8c97632eaaeb252759590ff
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562895"
---
# <a name="piece-picking-confirmation"></a>Confirmação de separação de peças

[!include [banner](../includes/banner.md)]

A separação de peças permite que você confirme cada peça de estoque por meio do trabalho de separação ou de contagem em um dispositivo móvel. Referente às separações, é possível confirmar desde a quantidade de trabalho a ser processado até a quantidade especificada no trabalho a ser separado. Referente ao trabalho de contagem, é possível verificar o estoque que você está contando e rastrear o valor total.

Ao habilitar a separação de peças, a confirmação do produto é automaticamente selecionada. Referente às separações por tipo de trabalho, o número máximo de peças é habilitado. Isso permite definir um número máximo de peças a ser confirmado durante o processo de trabalho. A quantidade máxima é baseada na unidade de trabalho atual que está sendo processada. O tipo de trabalho de contagem não permite uma quantidade máxima.

Você também pode usar a quantidade e a unidade de medida (UOM) associadas a um código de barras verificado. Isso colaborará para o recebimento em fluxos de entrada, incluindo o recebimento de placa de licença mista, item da ordem de compra, item da ordem de transferência e o item de carga. Também colaborará para a separação de peças em que verificar o código de barras adicionará a quantidade ao número total de peças confirmadas na conversão entre a UOM no código de barras e a unidade de trabalho. Se, ao contar a UOM no código de barras, for confirmado que a quantidade é permitida para contagem no grupo de foco de sequência, a quantidade será adicionada à contagem total.

## <a name="where-it-applies"></a>Aplica-se a

Trabalhos de separação de peças para todos os trabalhos de contagem e para a separação inicial relativa a qualquer tipo de trabalho. A separação de peças não se aplica se o item for controlado por números de série ou for uma produção ou uma separação kanban de um local de LP (placa de licença) e o item estiver definido para preparo.

## <a name="set-up-piece-picking"></a>Configurar separação de peças

1.  No item de menu do dispositivo móvel, abra o formulário de configuração para a confirmação de trabalho: Gerenciamento de depósito > **Gerenciamento de depósito** > **Configuração** > **Dispositivo móvel** > **Itens de menu do dispositivo móvel**. 
2. Do item de menu de dispositivo móvel, abra a configuração de Confirmação de trabalho.

As seguintes opções tornam-se disponíveis para seleção quando o tipo de trabalho é separação e contagem.


|           Opção           |                                                                            descrição                                                                            |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Confirmação de separação de peças | Disponível para tipos de trabalho de separação e contagem. A confirmação de produto é selecionada automaticamente. Permite a você confirmar cada peça de estoque do dispositivo móvel. |
|  Número máximo de peças  |                   Disponível para trabalho de separação se a confirmação de separação de peças estiver habilitada. Define um limite para o número de peças que você deve confirmar.                   |

