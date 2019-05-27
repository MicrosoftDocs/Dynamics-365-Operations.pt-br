---
title: Usar novamente configurações de produto
description: Você pode especificar se deseja reutilizar automaticamente uma configuração existente para um produto. Então, quando o usuário concluir uma sessão de configuração, o sistema verifica se já existe uma configuração correspondente às seleções do usuário. Se uma configuração correspondente for encontrada, a ID de configuração, a lista de materiais (BOM) correspondente e o roteiro serão reutilizados.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 18a3e5fb583ed620c825164f2628a26b6b0cb469
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560200"
---
# <a name="reuse-product-configurations"></a><span data-ttu-id="ec500-105">Usar novamente configurações de produto</span><span class="sxs-lookup"><span data-stu-id="ec500-105">Reuse product configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec500-106">Você pode especificar se deseja reutilizar automaticamente uma configuração existente para um produto.</span><span class="sxs-lookup"><span data-stu-id="ec500-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="ec500-107">Então, quando o usuário concluir uma sessão de configuração, o sistema verifica se já existe uma configuração correspondente às seleções do usuário.</span><span class="sxs-lookup"><span data-stu-id="ec500-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="ec500-108">Se uma configuração correspondente for encontrada, a ID de configuração, a lista de materiais (BOM) correspondente e o roteiro serão reutilizados.</span><span class="sxs-lookup"><span data-stu-id="ec500-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="ec500-109">Requisitos para reutilizar as configurações</span><span class="sxs-lookup"><span data-stu-id="ec500-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="ec500-110">Para habilitar as configurações a ser reutilizadas, você deve especificar as seguintes informações para os componentes e atributos na página **Detalhes do modelo de configuração de produto**:</span><span class="sxs-lookup"><span data-stu-id="ec500-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="ec500-111">**Componentes e subcomponentes** – Na Guia Rápida **Geral**, no campo **Configurações de reutilização**, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ec500-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="ec500-112">**Atributos** – Na Guia Rápida **Atributos**, selecione a opção **Incluir reutilização**.</span><span class="sxs-lookup"><span data-stu-id="ec500-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="ec500-113">Essa opção aparece somente quando o componente relacionado estiver habilitado para reutilização.</span><span class="sxs-lookup"><span data-stu-id="ec500-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="ec500-114">Se você não selecionar nenhum atributo para reutilização, a configuração sempre será reutilizada, independentemente das seleções do usuário durante uma sessão de configuração.</span><span class="sxs-lookup"><span data-stu-id="ec500-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="ec500-115">Os valores de atributos da configuração existente devem corresponder às seleções do usuário.</span><span class="sxs-lookup"><span data-stu-id="ec500-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="ec500-116">Por exemplo, se o usuário selecionar a cor **Azul** durante uma sessão de configuração, o sistema verificará se uma configuração existente do componente tem a cor azul.</span><span class="sxs-lookup"><span data-stu-id="ec500-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="ec500-117">Redefinir reutilização da configuração</span><span class="sxs-lookup"><span data-stu-id="ec500-117">Resetting configuration reuse</span></span>
<span data-ttu-id="ec500-118">Quando você redefine a reutilização de configuração, as configurações criadas anteriormente são consideradas não.</span><span class="sxs-lookup"><span data-stu-id="ec500-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="ec500-119">Talvez seja conveniente redefinir a reutilização de configuração se a BOM ou o roteiro foram alterados, mas nenhum atributo relacionada foi alterado.</span><span class="sxs-lookup"><span data-stu-id="ec500-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="ec500-120">Você redefine a reutilização de configuração **Geral** em FastTab do componente.</span><span class="sxs-lookup"><span data-stu-id="ec500-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>



