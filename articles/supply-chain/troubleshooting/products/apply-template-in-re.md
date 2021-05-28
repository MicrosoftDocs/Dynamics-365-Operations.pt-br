---
title: Não é possível aplicar um modelo a um produto liberado
description: Não é possível aplicar um modelo a um produto liberado.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026262"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="0dba0-103">Não é possível aplicar um modelo para criar um produto liberado</span><span class="sxs-lookup"><span data-stu-id="0dba0-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="0dba0-104">Número de KB: 4612097</span><span class="sxs-lookup"><span data-stu-id="0dba0-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="0dba0-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="0dba0-105">Symptoms</span></span>

<span data-ttu-id="0dba0-106">Ao criar um novo produto liberado usando a caixa de diálogo **Novo produto liberado**, você pode selecionar um modelo.</span><span class="sxs-lookup"><span data-stu-id="0dba0-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="0dba0-107">O modelo deve fornecer configurações padrão para muitos campos do novo produto liberado.</span><span class="sxs-lookup"><span data-stu-id="0dba0-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="0dba0-108">No entanto, alguns ou todos os campos não são definidos após a seleção do modelo.</span><span class="sxs-lookup"><span data-stu-id="0dba0-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="0dba0-109">Causa</span><span class="sxs-lookup"><span data-stu-id="0dba0-109">Cause</span></span>

<span data-ttu-id="0dba0-110">Muitas páginas no Microsoft Dynamics 365 Supply Chain Management permitem que você crie um modelo que estabelece as configurações iniciais para os registros mostrados nessas páginas.</span><span class="sxs-lookup"><span data-stu-id="0dba0-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="0dba0-111">Você pode criar um desses modelos, selecionando **Informações sobre registro** na guia **Opções** do Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="0dba0-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="0dba0-112">No entanto, os produtos liberados são muito mais complexos do que a maioria dos outros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="0dba0-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="0dba0-113">Embora você possa selecionar **Informações sobre registro** na página **Produtos liberados** para criar um modelo e, embora possa selecionar esse modelo ao criar um produto liberado, o modelo não fornecerá os valores de campo esperados para o novo produto liberado.</span><span class="sxs-lookup"><span data-stu-id="0dba0-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="0dba0-114">Portanto, não é possível usar os modelos de "informações sobre registro" para produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="0dba0-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="0dba0-115">Em vez disso, você deve criar modelos de produto dedicados.</span><span class="sxs-lookup"><span data-stu-id="0dba0-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="0dba0-116">Resolução</span><span class="sxs-lookup"><span data-stu-id="0dba0-116">Resolution</span></span>

<span data-ttu-id="0dba0-117">Para criar um modelo de produto, use o menu **Modelo** da guia **Produto** do Painel de Ações, não o botão **Informações sobre registro** na guia **Opções**.</span><span class="sxs-lookup"><span data-stu-id="0dba0-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="0dba0-118">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="0dba0-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="0dba0-119">No Painel de Ações, na guia **Produto**, no grupo **Novo**, selecione **Modelo** e selecione **Criar modelo pessoal** ou **Criar modelo compartilhado**, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="0dba0-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
