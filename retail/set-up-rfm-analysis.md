---
title: "Configurar análise RFM"
description: "Este tópico explica como configurar uma análise Recente, Frequência, e Monetária (RFM) dos clientes."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b95d2c4d7d78e8c5ed8d3a04efdd2f8dfe8393ba
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-rfm-analysis"></a>Configurar análise RFM

[!include[banner](includes/banner.md)]


Este tópico explica como configurar uma análise Recente, Frequência, e Monetária (RFM) dos clientes.

A análise RFM (recency, frequência e monetária) é uma ferramenta de marketing que a organização pode usar para avaliar os dados gerados pelas compras dos clientes. Depois de configurar a análise RFM, os clientes são atribuídos a uma contagem de RFM calculada quando eles fazem compras. A contagem de RFM pode ser uma previsão de três dígitos ou um número agregado, dependendo de como sua organização configurou a análise RFM. Se a organização usar uma classificação de três dígitos para a pontuação, o primeiro dígito será a classificação de recency do cliente (quando foi a última vez que o cliente fez uma compra na sua organização). O segundo dígito é a classificação de frequência do cliente (com que frequência o cliente faz compras na sua organização). O terceiro dígito é uma classificação monetária do cliente (quanto o cliente gasta quando faz compras na sua organização). Por exemplo, a organização definiu as classificações em uma escala de 1 a 5, em que 5 representa a classificação mais alta. Nesse caso, a classificação 535 fornece a você as seguintes informações sobre o cliente:

-   **Classificação de recency 5** – O cliente fez uma compra recentemente.
-   **Classificação de frequência 3** – O cliente compra produtos da sua organização com frequência moderada.
-   **Classificação monetária 5** – Quando o cliente faz uma compra, ela gasta um montante significativo

Se sua organização usar um número agregado para a pontuação, as classificações individuais serão adicionadas juntas. No mesmo exemplo, o cliente obtém a classificação 13 (5 + 3 + 5).



