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
ms.search.scope: Core, Operations
ms.custom: 12234
ms.assetid: b878478c-0e04-4a1e-a037-6fdbb345a9a3
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-01-09
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2112e7131281cd485b580fd71536981c1ba4aefd
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2020
ms.locfileid: "4422650"
---
# <a name="transportation-management-zone-master"></a><span data-ttu-id="78c03-103">Mestre de zona de gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="78c03-103">Transportation management zone master</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78c03-104">O gerenciamento de transporte permite dividir localizações geográficas em zonas.</span><span class="sxs-lookup"><span data-stu-id="78c03-104">Transport management lets you divide geographic locations into zones.</span></span> <span data-ttu-id="78c03-105">Dividir locais em zonas pode ajudar a:</span><span class="sxs-lookup"><span data-stu-id="78c03-105">Dividing locations into zones can help to:</span></span>

- <span data-ttu-id="78c03-106">**Simplificar o preço do transporte**: o preço por zona pode ser mais simples do que o preço individual baseado em localização, especialmente quando os locais de transporte estão espalhados.</span><span class="sxs-lookup"><span data-stu-id="78c03-106">**Simplify transportation pricing** – Zone-wise pricing can be simpler than individual location-based pricing, especially when transportation locations are scattered.</span></span>
- <span data-ttu-id="78c03-107">**Otimizar o planejamento de carga**: consolidando cargas por zonas.</span><span class="sxs-lookup"><span data-stu-id="78c03-107">**Optimize load planning** – By consolidating loads by zones.</span></span>
- <span data-ttu-id="78c03-108">**Otimizar o planejamento de rotas**: atribuindo planos de rota específicos para zonas específicas.</span><span class="sxs-lookup"><span data-stu-id="78c03-108">**Optimize route planning** – By assigning specific route plans to specific zones.</span></span>

<span data-ttu-id="78c03-109">Você define zonas com base nos valores de campo de metadados (como país, intervalo de código postal ou serviço da operadora) que qualificam cada zona.</span><span class="sxs-lookup"><span data-stu-id="78c03-109">You define zones based on the metadata field values (such as country, zip code range, or carrier service) that qualify each zone.</span></span> <span data-ttu-id="78c03-110">As definições de zona não são necessárias se o preço do transporte não empregar um conceito de zona.</span><span class="sxs-lookup"><span data-stu-id="78c03-110">Zone definitions aren't required if your transportation pricing doesn't employ a zone concept.</span></span>
