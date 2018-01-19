---
title: Enviar uma ordem de uma loja diferente
description: "Este tópico descreve o recurso de Envio de encargo."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-retail
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
ms.sourcegitcommit: 986ec7835dac52c326085c47313205d08b1bafa8
ms.openlocfilehash: d217bc31ad9d93c5440e5329f7b7327d089137f4
ms.contentlocale: pt-br
ms.lasthandoff: 10/10/2017

---

# <a name="ship-an-order-from-a-different-store"></a>Enviar uma ordem de uma loja diferente

Com o recurso Envio de encargos no Dynamics 365 for Retail, as ordens de cliente podem ser feitas em uma loja e ser enviadas de outra. As ordens de clientes no cliente de PDV (ponto de venda) oferecem suporte a várias opções de atendimento. Alguns exemplos de opções de atendimento incluem:
-   Separar na mesma loja em uma data diferente.
-   Separar em uma loja diferente na mesma data ou em uma data diferente.
-   Enviar do depósito de remessa padrão que está atribuído à loja e entregar em uma data específica.

O recurso Envio de encargos usa as seguintes operações de PDV: Remeter todos os produtos e Remeter produtos selecionados. Isso permite que o funcionário da loja selecione a localização "remeter de" de onde a ordem ou a linha da ordem possam ser atendidas. Por padrão, a localização "remeter de" é o depósito de remessa que está associado à loja. No entanto, o funcionário da loja pode alterar essa localização e selecionar qualquer loja que esteja definida no grupo localizador de loja atribuído à loja. 

A capacidade para selecionar endereços "Remeter para" permanece inalterada. 

Os métodos de remessa que podem ser usados para atender à linha da ordem se baseiam na configuração de modos válidos de entrega para produtos e endereços. Como as regras sobre modos válidos de entrega são mantidas somente na Sede de Varejo (HQ), o cliente PDV faz uma chamada de tempo real para buscar os modos válidos de entrega para uma linha de remessa. 


