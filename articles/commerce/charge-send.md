---
title: Enviar pedidos de outra loja usando o recurso Envio de encargos
description: Este tópico descreve o recurso de Envio de encargo.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: b9e0c4f55fd823bf7471edfe6ce1d424b0179d21
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800462"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Enviar pedidos de outra loja usando o recurso Envio de encargos

[!include [banner](includes/banner.md)]

Com o recurso de envio de encargos do Commerce, as ordens de clientes podem ser feitas em uma loja e enviadas de outra.

As ordens de clientes no cliente de PDV (ponto de venda) oferecem suporte a várias opções de atendimento. Alguns exemplos de opções de atendimento incluem:

- Separar na mesma loja em uma data diferente.
- Separar em uma loja diferente na mesma data ou em uma data diferente.
- Enviar do depósito de remessa padrão que está atribuído à loja e entregar em uma data específica.

O recurso Envio de encargos usa as seguintes operações de PDV: Remeter todos os produtos e Remeter produtos selecionados. Isso permite que o funcionário da loja selecione o local "remeter de" de onde a ordem ou a linha da ordem possa ser atendida. Por padrão, a localização "remeter de" é o depósito de remessa que está associado à loja. No entanto, o funcionário da loja pode alterar essa localização e selecionar qualquer loja que esteja definida no grupo localizador de loja atribuído à loja.

A capacidade de selecionar endereços "remeter para" permanece inalterada.

Os métodos de remessa que podem ser usados para atender à linha da ordem se baseiam na configuração de modos válidos de entrega para produtos e endereços. Como as regras sobre modos de entrega válidos são mantidas somente no Headquarters (HQ), o cliente de PDV faz uma chamada em tempo real para buscar os modos de entrega válidos para uma linha de remessa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]