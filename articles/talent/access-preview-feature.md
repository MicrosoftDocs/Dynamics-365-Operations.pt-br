---
title: Gerenciar recursos
description: Este tópico descreve como um administrador poderá habilitar os recursos de exibição no Microsoft Dynamics 365 Talent e listar os recursos que estão habilitados atualmente para visualização.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.1.0, Talent
ms.openlocfilehash: d818e9e04ce88e5ab285ef8176334809447fb477
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460380"
---
# <a name="manage-features"></a><span data-ttu-id="4135f-103">Gerenciar recursos</span><span class="sxs-lookup"><span data-stu-id="4135f-103">Manage features</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4135f-104">Como parte de liberação contínua de funcionalidades de gerenciamento de capital humano (HCM) do Microsoft Dynamics 365 Human Resources, queremos que nossos clientes aproveitem novos recursos o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="4135f-104">As part of our continuous rollout of human capital management (HCM) capabilities for Microsoft Dynamics 365 Human Resources, we want to let customers experience new features as soon as possible.</span></span> <span data-ttu-id="4135f-105">Os administradores podem consultar e usar recursos de exibição nos ambientes.</span><span class="sxs-lookup"><span data-stu-id="4135f-105">Administrators can see and use preview features in their environments.</span></span> <span data-ttu-id="4135f-106">Esses recursos estão quase prontos para disponibilidade geral e passam por um teste extenso.</span><span class="sxs-lookup"><span data-stu-id="4135f-106">These features are almost ready for general availability and have gone through extensive testing.</span></span> <span data-ttu-id="4135f-107">Estamos procurando apenas um círculo final de comentários de cliente e validação antes de liberá-los para disponibilidade geral.</span><span class="sxs-lookup"><span data-stu-id="4135f-107">We're just looking for a final round of customer feedback and validation before we release them for general availability.</span></span>

<span data-ttu-id="4135f-108">Este tópico descreve como você poderá habilitar os recursos de exibição, e listar os recursos que estão disponíveis atualmente para visualização.</span><span class="sxs-lookup"><span data-stu-id="4135f-108">This topic describes how you can enable preview features, and it lists the features that are currently available for preview.</span></span> <span data-ttu-id="4135f-109">A lista será atualizada conforme os recursos são liberados para disponibilidade geral e conforme novos recursos são liberados para visualização.</span><span class="sxs-lookup"><span data-stu-id="4135f-109">This list will be updated as features are released to general availability and as new features are released to preview.</span></span> <span data-ttu-id="4135f-110">Nenhuma notificação é dada quando novos recursos são liberados para visualização.</span><span class="sxs-lookup"><span data-stu-id="4135f-110">No notification is given when new features are released to preview.</span></span> <span data-ttu-id="4135f-111">Os usuários começarão a ver apenas os recursos.</span><span class="sxs-lookup"><span data-stu-id="4135f-111">Users will just start to see the features.</span></span> <span data-ttu-id="4135f-112">Para obter mais informações sobre novos recursos no Talent, consulte [Novidades ou alterações no Dynamics 365 Talent](./whats-new.md) e [Notas de versão do Dynamics 365 e da Power Platform](https://docs.microsoft.com/business-applications-release-notes).</span><span class="sxs-lookup"><span data-stu-id="4135f-112">For more information about new features in Talent, see [What's new or changed in Dynamics 365 Talent](./whats-new.md) and [Dynamics 365 and Power Platform Release Notes](https://docs.microsoft.com/business-applications-release-notes).</span></span>

## <a name="enable-or-disable-preview-features"></a><span data-ttu-id="4135f-113">Habilitar ou desabilitar recursos de visualização</span><span class="sxs-lookup"><span data-stu-id="4135f-113">Enable or disable preview features</span></span>

<span data-ttu-id="4135f-114">Para acessar os recursos de visualização, primeiro é preciso ativá-los no ambiente.</span><span class="sxs-lookup"><span data-stu-id="4135f-114">To access preview features, you must first enable them in your environment.</span></span> <span data-ttu-id="4135f-115">A habilitação ou desabilitação de recursos de visualização é específica do ambiente.</span><span class="sxs-lookup"><span data-stu-id="4135f-115">Enabling or disabling preview features is environment-specific.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4135f-116">Ao ativar a configuração de **Recursos de visualização**, você habilita recursos de visualização para todos os usuários da organização que estão no ambiente.</span><span class="sxs-lookup"><span data-stu-id="4135f-116">When you turn on the **Preview Features** setting, you enable preview features for all users in your organization who are in that environment.</span></span> <span data-ttu-id="4135f-117">Ao desativar a configuração, você desabilita recursos de visualização e os torna inacessíveis a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="4135f-117">When you turn off the setting, you disable preview features and make them inaccessible to your users.</span></span> <span data-ttu-id="4135f-118">Os recursos de visualização limitaram o suporte em Talent.</span><span class="sxs-lookup"><span data-stu-id="4135f-118">Preview features have limited support in Talent.</span></span> <span data-ttu-id="4135f-119">Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço (SLA) de Talent.</span><span class="sxs-lookup"><span data-stu-id="4135f-119">They might use fewer privacy and security measures, and they aren't included in the Talent service level agreement (SLA).</span></span> <span data-ttu-id="4135f-120">Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.</span><span class="sxs-lookup"><span data-stu-id="4135f-120">You should not use preview features to process personal data (that is, any information that could identify you), or to process other data that is subject to legal or regulatory compliance requirements.</span></span>

### <a name="attract"></a><span data-ttu-id="4135f-121">Attract</span><span class="sxs-lookup"><span data-stu-id="4135f-121">Attract</span></span>

1. <span data-ttu-id="4135f-122">Entre no Microsoft Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="4135f-122">Sign in to Microsoft Dynamics 365 Talent: Attract.</span></span>
2. <span data-ttu-id="4135f-123">No menu **Configuração** (símbolo de engrenagem) no canto superior direito, selecione **Centro de administração**.</span><span class="sxs-lookup"><span data-stu-id="4135f-123">On the **Setup** menu (the gear symbol) in the upper-right corner, select **Admin center**.</span></span>
3. <span data-ttu-id="4135f-124">Na guia **Gerenciamento de recursos**, selecione a opção próxima a **Recursos de visualização** para que se torne azul e informe **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="4135f-124">On the **Feature management** tab, select the option next to **Preview features** so that it turns blue and says **On**.</span></span>

    ![Habilitar recursos de visualização no Attract](./media/attract-enable-preview-features.png)

4. <span data-ttu-id="4135f-126">Selecione ou cancele a seleção de recursos de visualização individuais.</span><span class="sxs-lookup"><span data-stu-id="4135f-126">Select or cancel the selection of individual preview features.</span></span> <span data-ttu-id="4135f-127">Se você não fizer nada, todos os recursos de visualização disponíveis estarão habilitados.</span><span class="sxs-lookup"><span data-stu-id="4135f-127">If you do nothing, all available preview features are enabled.</span></span>
5. <span data-ttu-id="4135f-128">Atualize seu navegador para começar a exibir os recursos novos.</span><span class="sxs-lookup"><span data-stu-id="4135f-128">Refresh your browser to start to see the new features.</span></span> <span data-ttu-id="4135f-129">Quaisquer usuários que já estão conectados verão os recursos na próxima vez que se conectarem, eles podem atualizar o navegador para consultar os recursos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4135f-129">Any users who are already signed in will see the features the next time they sign in, or they can refresh their browser to see the features immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="4135f-130">Alguns recursos de visualização podem exigir configuração adicional.</span><span class="sxs-lookup"><span data-stu-id="4135f-130">Some preview features might require additional configuration.</span></span> <span data-ttu-id="4135f-131">Siga os links ao lado do recurso de visualização para concluir a configuração dele.</span><span class="sxs-lookup"><span data-stu-id="4135f-131">Follow the links next to the preview feature to complete the setup for it.</span></span>

## <a name="feedback"></a><span data-ttu-id="4135f-132">Comentários</span><span class="sxs-lookup"><span data-stu-id="4135f-132">Feedback</span></span>

<span data-ttu-id="4135f-133">Queremos saber sua experiência com qualquer um desses recursos de visualização.</span><span class="sxs-lookup"><span data-stu-id="4135f-133">We want to hear from you about your experience with any of these preview features.</span></span> <span data-ttu-id="4135f-134">É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos:</span><span class="sxs-lookup"><span data-stu-id="4135f-134">We encourage you to regularly post your feedback on the following sites as you use these or any other features:</span></span>

- <span data-ttu-id="4135f-135">[Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.</span><span class="sxs-lookup"><span data-stu-id="4135f-135">[Community](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – This site is a great resource where users can discuss use cases, ask questions, and get community help.</span></span>
- <span data-ttu-id="4135f-136">Conte para nós os recursos que você deseja ver no produto ou as alterações que você acha que devemos fazer nos recursos existentes.</span><span class="sxs-lookup"><span data-stu-id="4135f-136">Let us know about features that you want to see in the product, or let us know about any changes you think we should make to existing features.</span></span> <span data-ttu-id="4135f-137">Sugira ideias de produtos nos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="4135f-137">Suggest product ideas on the following sites:</span></span>

    - [<span data-ttu-id="4135f-138">Ideias do Attract</span><span class="sxs-lookup"><span data-stu-id="4135f-138">Attract ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [<span data-ttu-id="4135f-139">Ideias do Onboard</span><span class="sxs-lookup"><span data-stu-id="4135f-139">Onboard ideas</span></span>](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

<span data-ttu-id="4135f-140">Não deixe de incluir dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto.</span><span class="sxs-lookup"><span data-stu-id="4135f-140">Make sure that you don't include personal data (any information that could identify you) in your feedback or product review submissions.</span></span> <span data-ttu-id="4135f-141">Informações coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade.</span><span class="sxs-lookup"><span data-stu-id="4135f-141">Collected information might be analyzed further and isn't used to answer requests under applicable privacy laws.</span></span> <span data-ttu-id="4135f-142">Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/privacystatement).</span><span class="sxs-lookup"><span data-stu-id="4135f-142">Personal data that is collected separately under these programs is subject to the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span>

> [!TIP]
> <span data-ttu-id="4135f-143">Marque esse tópico e o revise com frequência para se manter atualizado sobre novos lançamentos de recursos conforme os lançamos.</span><span class="sxs-lookup"><span data-stu-id="4135f-143">Bookmark this topic, and check back often to stay up to date about new preview features as we release them.</span></span>

## <a name="see-also"></a><span data-ttu-id="4135f-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4135f-144">See also</span></span>

- [<span data-ttu-id="4135f-145">Experimente ou compre aplicativos do Talent</span><span class="sxs-lookup"><span data-stu-id="4135f-145">Try or buy Talent apps</span></span>](https://dynamics.microsoft.com/talent/overview/)
- [<span data-ttu-id="4135f-146">Novidades ou alterações no Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="4135f-146">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="4135f-147">Planos de versão</span><span class="sxs-lookup"><span data-stu-id="4135f-147">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="4135f-148">Obter suporte para o Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="4135f-148">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
