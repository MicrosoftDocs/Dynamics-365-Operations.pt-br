---
title: Mestre de zona de gerenciamento de transporte
description: Este tópico explica como o gerenciamento de transporte permite dividir localizações geográficas em zonas.
author: Henrikan
manager: ''
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSZoneMaster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6527c4887ccd3085d63dd64c104a94e6354f536b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996443"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="f5aaf-103">Mestre de zona de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="f5aaf-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5aaf-104">O gerenciamento de transporte permite dividir localizações geográficas em zonas.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="f5aaf-105">Dividir locais em zonas pode ajudar a:</span><span class="sxs-lookup"><span data-stu-id="f5aaf-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="f5aaf-106">**Simplificar o preço do transporte**: o preço por zona pode ser mais simples do que o preço individual baseado em localização, especialmente quando os locais de transporte estão espalhados.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="f5aaf-107">**Otimizar o planejamento de carga**: consolidando cargas por zonas.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="f5aaf-108">**Otimizar o planejamento de rotas**: atribuindo planos de rota específicos para zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="f5aaf-109">Você define zonas com base nos valores de campo de metadados (como país, intervalo de código postal ou serviço da operadora) que qualificam cada zona.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="f5aaf-110">As definições de zona não são necessárias se o preço do transporte não empregar um conceito de zona.</span><span class="sxs-lookup"><span data-stu-id="f5aaf-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>