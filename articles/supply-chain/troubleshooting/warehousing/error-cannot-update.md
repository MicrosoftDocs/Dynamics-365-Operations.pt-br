---
title: Um erro ocorre quando o local é selecionado durante um registro de lista de retirada
description: Um erro ocorre quando o local é selecionado durante um registro de lista de retirada.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b7fc579821f9a80d94aea949fcc0301b9d8f6935
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026253"
---
# <a name="an-error-occurs-when-the-location-is-selected-during-picking-list-registration"></a><span data-ttu-id="95f45-103">Um erro ocorre quando o local é selecionado durante um registro de lista de retirada</span><span class="sxs-lookup"><span data-stu-id="95f45-103">An error occurs when the location is selected during picking list registration</span></span>

<span data-ttu-id="95f45-104">Número da base de dados de conhecimento: 4613106</span><span class="sxs-lookup"><span data-stu-id="95f45-104">KB number: 4613106</span></span>

## <a name="symptoms"></a><span data-ttu-id="95f45-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="95f45-105">Symptoms</span></span>

<span data-ttu-id="95f45-106">Este problema ocorre quando seu sistema está configurado para reservar pedidos de venda automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95f45-106">This issue occurs when your system is configured to automatically reserve sales orders.</span></span> <span data-ttu-id="95f45-107">Se você tentar selecionar o local para uma linha de registro de lista de retirada, você recebe a seguinte mensagem de erro ao usar os processos de reserva do gerenciamento de armazém (WMS):</span><span class="sxs-lookup"><span data-stu-id="95f45-107">If you try to select the location for a picking list registration line, you receive the following error message when you use warehouse management (WMS) reservation processes:</span></span>

> <span data-ttu-id="95f45-108">Não é possível atualizar a quantidade com as novas dimensões</span><span class="sxs-lookup"><span data-stu-id="95f45-108">Can't update quantity with new dimensions</span></span>

<span data-ttu-id="95f45-109">Este problema pode ocorrer porque você não tem inventário em mãos suficiente em um local específico.</span><span class="sxs-lookup"><span data-stu-id="95f45-109">This issue can occur because you don't have enough on-hand inventory at a specified location.</span></span>

## <a name="resolution"></a><span data-ttu-id="95f45-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="95f45-110">Resolution</span></span>

<span data-ttu-id="95f45-111">O sistema está agindo como esperado.</span><span class="sxs-lookup"><span data-stu-id="95f45-111">The system is behaving as designed.</span></span>

<span data-ttu-id="95f45-112">Em situações em que você usa o processo de reserva em nível de armazém, se o inventário em mãos não puder ser reservado em todos os níveis de dimensão do inventário, e você não tem inventário em mãos suficiente em um local específico, recomendamos que você use o processo de reserva manual na linha de retirada.</span><span class="sxs-lookup"><span data-stu-id="95f45-112">In scenarios where you use the warehouse-level reservation process, if the on-hand inventory won't be reserved on all inventory dimension levels, and you don't have enough on-hand inventory at a specified location, we recommend that you use the manual reservation process from the picking line.</span></span> <span data-ttu-id="95f45-113">Você pode então usar a função *Reservar lote* para distribuir as reservas inferiores, tal como local, para todas as quantidades em mãos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="95f45-113">You can then use the *Reserve lot* function to distribute the lower reservations, such as location, for all the available on-hand quantities.</span></span>
