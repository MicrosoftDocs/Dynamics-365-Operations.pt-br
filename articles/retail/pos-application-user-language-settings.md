---
title: Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário
description: Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e PDV em Nuvem.
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
ms.openlocfilehash: faf8cdcee70b55842072298b51789f6cd7a577af
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "336741"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="ea8a5-103">Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário</span><span class="sxs-lookup"><span data-stu-id="ea8a5-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ea8a5-104">Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="ea8a5-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="ea8a5-105">Overview</span></span>

<span data-ttu-id="ea8a5-106">Retail Modern POSRetail Modern POS (MPOS) e PDV em Nuvem suportam ambientes onde configurações de idioma e traduções podem variar entre as configurações de loja e de usuário.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="ea8a5-107">Por exemplo, a loja pode estar localizada em uma região onde o inglês é mais comum para seus clientes, mas alguns trabalhadores preferem usar o aplicativo com as traduções em francês.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="ea8a5-108">Idioma dos dados</span><span class="sxs-lookup"><span data-stu-id="ea8a5-108">Data language</span></span>

<span data-ttu-id="ea8a5-109">Independentemente das configurações do usuário, o MPOS e PDV na Nuvem sempre usarão as configurações de idioma da loja para determinar as traduções usadas para dados.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="ea8a5-110">Isso garantirá que todos usuário e clientes terão uma experiência consistente.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="ea8a5-111">Exemplos de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="ea8a5-111">Examples of data include:</span></span>

- <span data-ttu-id="ea8a5-112">Produtos</span><span class="sxs-lookup"><span data-stu-id="ea8a5-112">Products</span></span>
- <span data-ttu-id="ea8a5-113">Atributos e valores</span><span class="sxs-lookup"><span data-stu-id="ea8a5-113">Attributes and values</span></span>
- <span data-ttu-id="ea8a5-114">Nomes de categoria</span><span class="sxs-lookup"><span data-stu-id="ea8a5-114">Category names</span></span>
- <span data-ttu-id="ea8a5-115">Recibos de transação enviados por email ou impressos</span><span class="sxs-lookup"><span data-stu-id="ea8a5-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="ea8a5-116">Nomes de método de pagamento</span><span class="sxs-lookup"><span data-stu-id="ea8a5-116">Payment method names</span></span>
- <span data-ttu-id="ea8a5-117">Mensagens de exibição de linha</span><span class="sxs-lookup"><span data-stu-id="ea8a5-117">Line display messages</span></span>

<span data-ttu-id="ea8a5-118">O idioma da loja também será usado para a tela principal de login do PDV, pois o usuário não é conhecido antes do login.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="ea8a5-119">Se uma tradução não estiver disponível para o idioma da loja, o PDV reverterá para o idioma da empresa.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="ea8a5-120">Definindo a configuração do idioma da loja</span><span class="sxs-lookup"><span data-stu-id="ea8a5-120">Configuring the store's language setting</span></span>

<span data-ttu-id="ea8a5-121">A configuração do idioma da loja é definida em **Todas as lojas de varejo** na página **Loja de Varejo** em **Geral &gt; Configurações Regionais &gt; Idioma**.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-121">The store's language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="ea8a5-122">Use o menu suspenso para escolher o idioma para cada loja.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-122">Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="ea8a5-123">Idioma da interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ea8a5-123">User interface language</span></span>

<span data-ttu-id="ea8a5-124">As configurações de idioma do PDV determinam as traduções usadas na interface de usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="ea8a5-125">Isso inclui os rótulos, menus e listas que não são considerados dados.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="ea8a5-126">Uma exceção é o texto exibido em grades de botão do PDV.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="ea8a5-127">As grades de botão não oferecem suporte a traduções e, portanto, sempre mostrarão o texto como definido no botão.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="ea8a5-128">Para dar suporte aos botões traduzidos, você terá de copiar e manter as grades de botão separadas e atribuí-las aos usuários como apropriado.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="ea8a5-129">Definindo a configuração do idioma do usuário</span><span class="sxs-lookup"><span data-stu-id="ea8a5-129">Configuring the user's language setting</span></span>

<span data-ttu-id="ea8a5-130">A configuração de idioma do usuário do PDV é definida em **Todos os trabalhadores** na página **Trabalhador** em **Varejo &gt; Idioma**.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span> <span data-ttu-id="ea8a5-131">Ela não é definida na guia principal Perfil. Essa configuração não é usada pelo PDV.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="ea8a5-132">Se o idioma do usuário não for definido ou for definido como um idioma no qual as traduções não estejam disponíveis, o PDV será revertido para o idioma da loja.</span><span class="sxs-lookup"><span data-stu-id="ea8a5-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

|             | <span data-ttu-id="ea8a5-133">Idioma da interface do usuário  </span><span class="sxs-lookup"><span data-stu-id="ea8a5-133">UI language</span></span>                | <span data-ttu-id="ea8a5-134">Idioma dos dados (produtos, formatos de recibo, exibição de linha etc.)</span><span class="sxs-lookup"><span data-stu-id="ea8a5-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="ea8a5-135">**Empresa**</span><span class="sxs-lookup"><span data-stu-id="ea8a5-135">**Company**</span></span> | <span data-ttu-id="ea8a5-136">Padrão</span><span class="sxs-lookup"><span data-stu-id="ea8a5-136">Default</span></span>                    | <span data-ttu-id="ea8a5-137">Padrão</span><span class="sxs-lookup"><span data-stu-id="ea8a5-137">Default</span></span>                                                       |
| <span data-ttu-id="ea8a5-138">**Loja**</span><span class="sxs-lookup"><span data-stu-id="ea8a5-138">**Store**</span></span>   | <span data-ttu-id="ea8a5-139">Substitui a empresa</span><span class="sxs-lookup"><span data-stu-id="ea8a5-139">Overrides company</span></span>          | <span data-ttu-id="ea8a5-140">Substitui a empresa</span><span class="sxs-lookup"><span data-stu-id="ea8a5-140">Overrides company</span></span>                                             |
| <span data-ttu-id="ea8a5-141">**Usuário**</span><span class="sxs-lookup"><span data-stu-id="ea8a5-141">**User**</span></span>    | <span data-ttu-id="ea8a5-142">Substitui a loja ou a empresa</span><span class="sxs-lookup"><span data-stu-id="ea8a5-142">Overrides store or company</span></span> | <span data-ttu-id="ea8a5-143">Nunca</span><span class="sxs-lookup"><span data-stu-id="ea8a5-143">Never</span></span>                                                         |
