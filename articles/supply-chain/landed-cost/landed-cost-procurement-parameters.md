---
title: Parâmetros de compras e fornecimento para custo de entrega
description: Este tópico descreve como configurar os parâmetros relevantes de Compras e fornecimento ao usar o módulo Custo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: df91fcb97794be32924707fcecf2b5fb34844596
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833920"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="0f501-103">Parâmetros de compras e fornecimento para custo de entrega</span><span class="sxs-lookup"><span data-stu-id="0f501-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0f501-104">A página **Parâmetros de compras e fornecimento** tem algumas configurações que são especialmente relevantes ao usar o módulo **Custo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="0f501-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="0f501-105">Use a caixa de diálogo **Atualizar linhas de ordem** que é aberta na página **Parâmetros de compras e fornecimento** para especificar se as linhas da ordem de compra devem ser atualizadas automaticamente quando são feitas alterações no cabeçalho da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="0f501-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="0f501-106">Para concluir essa configuração, siga essas etapas.</span><span class="sxs-lookup"><span data-stu-id="0f501-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="0f501-107">Vá para **Compras e fornecimento \> Configuração \> Parâmetros de compras**.</span><span class="sxs-lookup"><span data-stu-id="0f501-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="0f501-108">Na guia **Geral**, selecione o link **Atualizar linhas da ordem**.</span><span class="sxs-lookup"><span data-stu-id="0f501-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="0f501-109">A caixa de diálogo **Atualizar linhas da ordem** lista os campos no cabeçalho da ordem que também podem aplicar atualizações automáticas a campos relacionados nas linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="0f501-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="0f501-110">Defina cada campo na lista com um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="0f501-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="0f501-111">**Sempre** – As linhas de ordem devem ser atualizadas automaticamente quando o cabeçalho da ordem é atualizado.</span><span class="sxs-lookup"><span data-stu-id="0f501-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="0f501-112">**Nunca** – As linhas de ordem nunca devem ser atualizadas quando o cabeçalho da ordem é atualizado.</span><span class="sxs-lookup"><span data-stu-id="0f501-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="0f501-113">**Aviso** – O usuário será solicitado a selecionar se as linhas da ordem devem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="0f501-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
