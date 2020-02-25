---
title: Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário
description: Este tópico descreve como alterar as configurações de idioma no Modern POS (MPOS) e PDV em Nuvem.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 49bfcaa4c05ea8e6cc6bf0a8f855f2474cea35bc
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021666"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="13b4c-103">Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário</span><span class="sxs-lookup"><span data-stu-id="13b4c-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="13b4c-104">Este tópico descreve como alterar as configurações de idioma no Modern POS (MPOS) e PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="13b4c-104">This topic describes how to change language settings in Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="13b4c-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="13b4c-105">Overview</span></span>
<span data-ttu-id="13b4c-106">O Modern POS (MPOS) e o PDV em Nuvem dão suporte a ambientes em que configurações de idioma e traduções podem variar entre as configurações de loja e de usuário.</span><span class="sxs-lookup"><span data-stu-id="13b4c-106">Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="13b4c-107">Por exemplo, a loja pode estar localizada em uma região onde o inglês é mais comum para seus clientes, mas alguns trabalhadores preferem usar o aplicativo com as traduções em francês.</span><span class="sxs-lookup"><span data-stu-id="13b4c-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="13b4c-108">Idioma dos dados</span><span class="sxs-lookup"><span data-stu-id="13b4c-108">Data language</span></span>

<span data-ttu-id="13b4c-109">Independentemente das configurações do usuário, o MPOS e PDV na Nuvem sempre usarão as configurações de idioma da loja para determinar as traduções usadas para dados.</span><span class="sxs-lookup"><span data-stu-id="13b4c-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="13b4c-110">Isso garantirá que todos usuário e clientes terão uma experiência consistente.</span><span class="sxs-lookup"><span data-stu-id="13b4c-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="13b4c-111">Exemplos de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="13b4c-111">Examples of data include:</span></span>

- <span data-ttu-id="13b4c-112">Produtos</span><span class="sxs-lookup"><span data-stu-id="13b4c-112">Products</span></span>
- <span data-ttu-id="13b4c-113">Atributos e valores</span><span class="sxs-lookup"><span data-stu-id="13b4c-113">Attributes and values</span></span>
- <span data-ttu-id="13b4c-114">Nomes de categoria</span><span class="sxs-lookup"><span data-stu-id="13b4c-114">Category names</span></span>
- <span data-ttu-id="13b4c-115">Recibos de transação enviados por email ou impressos</span><span class="sxs-lookup"><span data-stu-id="13b4c-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="13b4c-116">Nomes de método de pagamento</span><span class="sxs-lookup"><span data-stu-id="13b4c-116">Payment method names</span></span>
- <span data-ttu-id="13b4c-117">Mensagens de exibição de linha</span><span class="sxs-lookup"><span data-stu-id="13b4c-117">Line display messages</span></span>

<span data-ttu-id="13b4c-118">O idioma da loja também será usado para a tela principal de login do PDV, pois o usuário não é conhecido antes do login.</span><span class="sxs-lookup"><span data-stu-id="13b4c-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="13b4c-119">Se uma tradução não estiver disponível para o idioma da loja, o PDV reverterá para o idioma da empresa.</span><span class="sxs-lookup"><span data-stu-id="13b4c-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="13b4c-120">Definindo a configuração do idioma da loja</span><span class="sxs-lookup"><span data-stu-id="13b4c-120">Configuring the store's language setting</span></span>

<span data-ttu-id="13b4c-121">A configuração do idioma da loja é definida em **Todas as lojas** na página **Loja** em **Geral &gt; Configurações Regionais &gt; Idioma**.</span><span class="sxs-lookup"><span data-stu-id="13b4c-121">The store's language setting is set from **All stores** on the **Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="13b4c-122">Use a lista suspensa para escolher o idioma para cada loja.</span><span class="sxs-lookup"><span data-stu-id="13b4c-122">Use the drop-down list to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="13b4c-123">Idioma da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="13b4c-123">User interface language</span></span>

<span data-ttu-id="13b4c-124">As configurações de idioma do PDV determinam as traduções usadas na interface de usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="13b4c-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="13b4c-125">Isso inclui os rótulos, menus e listas que não são considerados dados.</span><span class="sxs-lookup"><span data-stu-id="13b4c-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="13b4c-126">Uma exceção é o texto exibido em grades de botão do PDV.</span><span class="sxs-lookup"><span data-stu-id="13b4c-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="13b4c-127">As grades de botão não oferecem suporte a traduções e, portanto, sempre mostrarão o texto como definido no botão.</span><span class="sxs-lookup"><span data-stu-id="13b4c-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="13b4c-128">Para dar suporte aos botões traduzidos, você terá de copiar e manter as grades de botão separadas e atribuí-las aos usuários como apropriado.</span><span class="sxs-lookup"><span data-stu-id="13b4c-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="13b4c-129">Definindo a configuração do idioma do usuário</span><span class="sxs-lookup"><span data-stu-id="13b4c-129">Configuring the user's language setting</span></span>

<span data-ttu-id="13b4c-130">A configuração de idioma do usuário do PDV é definida em **Todos os trabalhadores** na página **Trabalhador** em **Varejo e Comércio &gt; Idioma**.</span><span class="sxs-lookup"><span data-stu-id="13b4c-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail and Commerce &gt; Language**.</span></span> <span data-ttu-id="13b4c-131">Ela não é definida na guia principal Perfil. Essa configuração não é usada pelo PDV.</span><span class="sxs-lookup"><span data-stu-id="13b4c-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="13b4c-132">Se o idioma do usuário não for definido ou for definido como um idioma no qual as traduções não estejam disponíveis, o PDV será revertido para o idioma da loja.</span><span class="sxs-lookup"><span data-stu-id="13b4c-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

|             | <span data-ttu-id="13b4c-133">Idioma da interface do usuário  </span><span class="sxs-lookup"><span data-stu-id="13b4c-133">UI language</span></span>                | <span data-ttu-id="13b4c-134">Idioma dos dados (produtos, formatos de recibo, exibição de linha etc.)</span><span class="sxs-lookup"><span data-stu-id="13b4c-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="13b4c-135">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="13b4c-135">**Company**</span></span> | <span data-ttu-id="13b4c-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="13b4c-136">Default</span></span>                    | <span data-ttu-id="13b4c-137">Padrão</span><span class="sxs-lookup"><span data-stu-id="13b4c-137">Default</span></span>                                                       |
| <span data-ttu-id="13b4c-138">**Loja**</span><span class="sxs-lookup"><span data-stu-id="13b4c-138">**Store**</span></span>   | <span data-ttu-id="13b4c-139">Substitui a empresa</span><span class="sxs-lookup"><span data-stu-id="13b4c-139">Overrides company</span></span>          | <span data-ttu-id="13b4c-140">Substitui a empresa</span><span class="sxs-lookup"><span data-stu-id="13b4c-140">Overrides company</span></span>                                             |
| <span data-ttu-id="13b4c-141">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="13b4c-141">**User**</span></span>    | <span data-ttu-id="13b4c-142">Substitui a loja ou a empresa</span><span class="sxs-lookup"><span data-stu-id="13b4c-142">Overrides store or company</span></span> | <span data-ttu-id="13b4c-143">Nunca</span><span class="sxs-lookup"><span data-stu-id="13b4c-143">Never</span></span>                                                         |
