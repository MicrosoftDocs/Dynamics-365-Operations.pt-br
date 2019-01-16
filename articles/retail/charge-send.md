---
title: Enviar pedidos de outra loja usando o recurso Envio de encargos
description: "Este tópico descreve o recurso de Envio de encargo."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: e5351086c56d13ef98937aec066be00cdf88fd37
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Enviar pedidos de outra loja usando o recurso Envio de encargos

[!include [banner](includes/banner.md)]

Com o recurso Envio de encargos no Dynamics 365 for Retail, as ordens de cliente podem ser feitas em uma loja e ser enviadas de outra.

As ordens de clientes no cliente de PDV (ponto de venda) oferecem suporte a várias opções de atendimento. Alguns exemplos de opções de atendimento incluem:

- Separar na mesma loja em uma data diferente.
- Separar em uma loja diferente na mesma data ou em uma data diferente.
- Enviar do depósito de remessa padrão que está atribuído à loja e entregar em uma data específica.

O recurso Envio de encargos usa as seguintes operações de PDV: Remeter todos os produtos e Remeter produtos selecionados. Isso permite que o funcionário da loja selecione o local "remeter de" de onde a ordem ou a linha da ordem possa ser atendida. Por padrão, a localização "remeter de" é o depósito de remessa que está associado à loja. No entanto, o funcionário da loja pode alterar essa localização e selecionar qualquer loja que esteja definida no grupo localizador de loja atribuído à loja.

A capacidade de selecionar endereços "remeter para" permanece inalterada.

Os métodos de remessa que podem ser usados para atender à linha da ordem se baseiam na configuração de modos válidos de entrega para produtos e endereços. Como as regras sobre modos válidos de entrega são mantidas somente na Sede de Varejo (HQ), o cliente PDV faz uma chamada de tempo real para buscar os modos válidos de entrega para uma linha de remessa.

