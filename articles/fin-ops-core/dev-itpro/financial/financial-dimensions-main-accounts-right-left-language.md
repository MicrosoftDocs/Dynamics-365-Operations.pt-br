---
title: Dimensões financeiras e contas principais em idiomas da direita para a esquerda
description: Este tópico descreve as decisões que você deve tomar ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 26fd186415db0adf01b8c53b188171fcf86fbc88
ms.sourcegitcommit: eff3da7ea98758f100d44ff7feec17157afc2e80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111653"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a><span data-ttu-id="a180e-103">Dimensões financeiras e contas principais de idiomas da direita para a esquerda</span><span class="sxs-lookup"><span data-stu-id="a180e-103">Financial dimensions and main accounts in right-to-left languages</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a180e-104">Este tópico descreve algumas das decisões de implementação que devem ser considerados ao usar um idioma da direita para a esquerda, e você deve configurar dimensões financeiras e contas principais.</span><span class="sxs-lookup"><span data-stu-id="a180e-104">This topic describes some of the implementation decisions that you should consider when you use a right-to-left language, and you must set up financial dimensions and main accounts.</span></span>

<span data-ttu-id="a180e-105">Dimensões financeiras e contas são componentes-chave principais da fase de planejamento para uma implementação.</span><span class="sxs-lookup"><span data-stu-id="a180e-105">Financial dimensions and main accounts are key components of the planning phase for an implementation.</span></span> <span data-ttu-id="a180e-106">Após dimensões financeiras e contas principais serem criadas no sistema, elas são usadas nas páginas **Configurar estruturas de conta**, **Estruturas de regra avançada** e **Configuração de dimensão financeira para integração de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="a180e-106">After financial dimensions and main accounts are created in the system, they are used on the **Configure account structures**, **Advanced rule structures**, and **Financial dimension configuration for integrating applications** pages.</span></span> <span data-ttu-id="a180e-107">A ordem definida nas páginas é usada no sistema para a entrada de dados e o consumo.</span><span class="sxs-lookup"><span data-stu-id="a180e-107">The order that is defined on those pages is used in the system for data entry and consumption.</span></span> <span data-ttu-id="a180e-108">Em alguns locais no sistema, dimensões financeiras e contas principais são exibidas em dois campos separados.</span><span class="sxs-lookup"><span data-stu-id="a180e-108">In some places in the system, the financial dimensions and main accounts appear in separate fields.</span></span> <span data-ttu-id="a180e-109">Em outros locais, como diários, dimensões financeiras e contas principais, aparecem como uma única cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a180e-109">In other places, such as journals, the financial dimensions and main accounts appear as a single string.</span></span>

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a><span data-ttu-id="a180e-110">Práticas recomendadas para configurar dimensões financeiras e contas principais em um sistema da direita para a esquerda</span><span class="sxs-lookup"><span data-stu-id="a180e-110">Best practices for setting up financial dimensions and main accounts in a right-to-left system</span></span>

- <span data-ttu-id="a180e-111">Quando você selecionar o delimitador de gráficos de contas, selecione uma das duas opções de delimitador: hífen duplo (`--`), barra dupla (`||`) ou ponto duplo (`..`) ou barra invertida dupla (`\\`).</span><span class="sxs-lookup"><span data-stu-id="a180e-111">When you select the delimiter for charts of accounts, select one of the double delimiter options: double hyphen (`--`), double bar (`||`), double period (`..`), or double underscore (`\\`).</span></span>
- <span data-ttu-id="a180e-112">Ao criar valores de dimensão financeira e conta principal, use números somente e caracteres da direita para a esquerda de idioma.</span><span class="sxs-lookup"><span data-stu-id="a180e-112">When you create financial dimension and main account values, use only numbers and right-to-left language characters.</span></span>
- <span data-ttu-id="a180e-113">Evite o delimitador gráfico selecionado de contas nos valores da dimensão financeira e conta principal.</span><span class="sxs-lookup"><span data-stu-id="a180e-113">Avoid using the selected chart of accounts delimiter in financial dimension and main account values.</span></span>

<span data-ttu-id="a180e-114">Ao executar essas práticas recomendadas, você ajuda a garantir representação consistente do pedido definido pelo usuário ao longo do sistema.</span><span class="sxs-lookup"><span data-stu-id="a180e-114">By following these best practices, you help guarantee consistent representation of the user defined-order throughout the system.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]