---
title: Solução de problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract
description: Este tópico explica como solucionar problemas ao tentar postar trabalhos no LinkedIn por meio do Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 42065f3d6b7ae9e7ad99b26c7692e41f8c36934d
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832968"
---
# <a name="troubleshoot-integration-with-linkedin-and-microsoft-dynamics-365-talent---attract"></a><span data-ttu-id="cdf85-103">Solucionar problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-103">Troubleshoot integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cdf85-104">Use as informações a seguir para ajudar a solucionar problemas que você possa ter ao tentar postar trabalhos no LinkedIn por meio do Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="cdf85-104">Use the following information to help troubleshoot issues that you might have when you try to post jobs to LinkedIn from Microsoft Dynamics 365 Talent: Attract.</span></span>

## <a name="you-cant-sign-in-to-linkedin-from-attract"></a><span data-ttu-id="cdf85-105">Não é possível entrar no LinkedIn pelo Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-105">You can't sign in to LinkedIn from Attract</span></span>

<span data-ttu-id="cdf85-106">Caso esteja tendo problemas para entrar no LinkedIn pelo Attract, tente estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cdf85-106">If you're having trouble signing in to LinkedIn from Attract, try these steps:</span></span>

1. <span data-ttu-id="cdf85-107">Verifique se as credenciais do LinkedIn que você inseriu no Attract são válidas e estão corretas.</span><span class="sxs-lookup"><span data-stu-id="cdf85-107">Verify that the LinkedIn credentials that you entered in Attract are valid and correct.</span></span>
2. <span data-ttu-id="cdf85-108">Se as credenciais forem válidas e estiverem corretas, entre em contato com o [suporte do LinkedIn](https://www.linkedin.com/help/linkedin).</span><span class="sxs-lookup"><span data-stu-id="cdf85-108">If the credentials are valid and correct, contact [LinkedIn support](https://www.linkedin.com/help/linkedin).</span></span>
3. <span data-ttu-id="cdf85-109">Se o problema persistir, entre em contato com o [suporte da Microsoft](./talent-support.md).</span><span class="sxs-lookup"><span data-stu-id="cdf85-109">If the issue persists, contact [Microsoft support](./talent-support.md).</span></span>

## <a name="job-posts-from-attract-dont-appear-on-linkedin"></a><span data-ttu-id="cdf85-110">Os lançamentos de trabalho pelo Attract não são exibidos no LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cdf85-110">Job posts from Attract don't appear on LinkedIn</span></span>

<span data-ttu-id="cdf85-111">Se os seus trabalhos não forem exibidos no LinkedIn depois de 24 horas, tente estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cdf85-111">If your job hasn't appeared on LinkedIn after 24 hours, try these steps:</span></span>

1. <span data-ttu-id="cdf85-112">Verifique se a sua ID da Empresa no LinkedIn mapeia para a página de sua empresa no LinkedIn e se foi inserida corretamente no Centro de administração do Attract.</span><span class="sxs-lookup"><span data-stu-id="cdf85-112">Make sure that your LinkedIn Company ID maps to your LinkedIn company page and is correctly entered in the Attract Admin center.</span></span> <span data-ttu-id="cdf85-113">Para obter mais informações sobre como alterar as configurações do LinkedIn no Centro de administração, consulte [Configurar a integração com o LinkedIn para o Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="cdf85-113">For more information about how to change LinkedIn settings in the Admin center, see [Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract](attract-admin-linkedin.md).</span></span> <span data-ttu-id="cdf85-114">Para obter informações sobre IDs de Empresa no LinkedIn, consulte [Associando sua ID da Empresa no LinkedIn com o quadro de trabalhos do LinkedIn — Perguntas frequentes](https://www.linkedin.com/help/linkedin/answer/98972).</span><span class="sxs-lookup"><span data-stu-id="cdf85-114">For more information about LinkedIn Company IDs, see [Associating your LinkedIn Company ID with the LinkedIn Job Board - Frequently Asked Questions](https://www.linkedin.com/help/linkedin/answer/98972).</span></span>
2. <span data-ttu-id="cdf85-115">Verifique os detalhes do trabalho no LinkedIn para garantir que o endereço esteja completo.</span><span class="sxs-lookup"><span data-stu-id="cdf85-115">Check the job details on LinkedIn to make sure that the address is complete.</span></span> <span data-ttu-id="cdf85-116">Para lançar um trabalho com êxito, o LinkedIn precisa, pelo menos, da cidade e do país ou da região do trabalho.</span><span class="sxs-lookup"><span data-stu-id="cdf85-116">To post a job successfully, LinkedIn needs at least the city and country or region of the job.</span></span>
3. <span data-ttu-id="cdf85-117">Verifique se o trabalho não é uma trabalhos de outro trabalho que foi lançado no LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="cdf85-117">Make sure that the job doesn't duplicate another job that has been posted on LinkedIn.</span></span> <span data-ttu-id="cdf85-118">O LinkedIn não lançará trabalhos que são duplicatas de Slots de Trabalho Premium ou de Listagens Limitadas do LinkedIn de outra origem.</span><span class="sxs-lookup"><span data-stu-id="cdf85-118">LinkedIn won't post jobs that are duplicates of either LinkedIn Premium Job Slots or Limited Listings from another source.</span></span> <span data-ttu-id="cdf85-119">Verifique se outra pessoa em sua empresa já não lançou o trabalho manualmente.</span><span class="sxs-lookup"><span data-stu-id="cdf85-119">Verify that another person at your company didn't already post the job manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdf85-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cdf85-120">See also</span></span>

[<span data-ttu-id="cdf85-121">Perguntas frequentes sobre a integração do Attract com o LinkedIn</span><span class="sxs-lookup"><span data-stu-id="cdf85-121">Attract integration with LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="cdf85-122">Postar trabalhos no LinkedIn usando o Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-122">Post jobs to LinkedIn from Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="cdf85-123">Contratar candidatos com o LinkedIn Recruiter no Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-123">Source candidates with LinkedIn Recruiter in Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-linkedin-recruiter.md)

[<span data-ttu-id="cdf85-124">Criar, aprovar e lançar trabalhos no Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-124">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="cdf85-125">Solucionar problemas de integração entre o LinkedIn e o Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="cdf85-125">Troubleshooting integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-troubleshoot-linkedin.md)
