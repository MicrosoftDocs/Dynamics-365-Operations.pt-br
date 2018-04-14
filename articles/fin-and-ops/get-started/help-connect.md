---
title: Conectar o sistema de Ajuda
description: "Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Finance and Operations, fornecendo uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 2deb2aea7dce889a655fbd5dec5ec928e0f10bb8
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="connect-the-help-system"></a><span data-ttu-id="21671-103">Conectar o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="21671-103">Connect the Help system</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="21671-104">Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21671-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="21671-105">Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="21671-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span> 

## <a name="help-architecture"></a><span data-ttu-id="21671-106">Arquitetura de ajuda</span><span class="sxs-lookup"><span data-stu-id="21671-106">Help architecture</span></span>
<span data-ttu-id="21671-107">A ilustração a seguir mostra as partes do sistema de Ajuda do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21671-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="21671-108">O sistema de Ajuda do produto traz artigos do site do Finance and Operations em https://docs.microsoft.com, bem como guias de tarefas armazenadas no Modelador de processo de negócios do Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="21671-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span> 
> [!NOTE]
> <span data-ttu-id="21671-109">Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="21671-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span> <span data-ttu-id="21671-110">[![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="21671-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>


## <a name="connecting-the-help-system"></a><span data-ttu-id="21671-111">Conectando o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="21671-111">Connecting the Help system</span></span>
> [!NOTE]
> <span data-ttu-id="21671-112">A guia **Guias de tarefas** não está disponível no Microsoft Dynamics 365 for Talent e no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="21671-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="21671-113">Estamos trabalhando atualmente para habilitar essa funcionalidade em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="21671-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="21671-114">As guias de tarefas da experiência de Introdução ao Talent permanecerão disponíveis para a funcionalidade básica.</span><span class="sxs-lookup"><span data-stu-id="21671-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="21671-115">A ajuda de procedimento também está disponível no site docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) para ambos, Retail e Talent.</span><span class="sxs-lookup"><span data-stu-id="21671-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>


<span data-ttu-id="21671-116">Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação.</span><span class="sxs-lookup"><span data-stu-id="21671-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span> <span data-ttu-id="21671-117">[![Formulário de parâmetros do sistema com configurações de ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na página **Parâmetros do sistema**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21671-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21671-118">A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="21671-118">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="21671-119">Certifique-se de clicar no link no meio do formulário, aguarda a conexão, feche a caixa de diálogo e, em seguida, clique em **OK** para ir para a página **Parâmetros do Sistema**.[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="21671-119">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1.  <span data-ttu-id="21671-120">Selecione o projeto do Lifecycle Services para se conectar.</span><span class="sxs-lookup"><span data-stu-id="21671-120">Select the Lifecycle Services project to connect to.</span></span>
2.  <span data-ttu-id="21671-121">Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.</span><span class="sxs-lookup"><span data-stu-id="21671-121">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
    - <span data-ttu-id="21671-122">Referente ao Finance and Operations, conteúdo da Microsoft, selecione a Biblioteca Unificada APQC mais recente para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21671-122">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span> 
    - <span data-ttu-id="21671-123">Para o Retail, liberaremos uma biblioteca em breve.</span><span class="sxs-lookup"><span data-stu-id="21671-123">For Retail, we will be releasing a library in the near future.</span></span> 
    - <span data-ttu-id="21671-124">Não é necessário selecionar uma biblioteca para o Talent - a conexão com a biblioteca correta é estabelecida para você.</span><span class="sxs-lookup"><span data-stu-id="21671-124">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span> 

3.  <span data-ttu-id="21671-125">Defina a ordem de exibição das bibliotecas do BPM.</span><span class="sxs-lookup"><span data-stu-id="21671-125">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="21671-126">Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="21671-126">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="21671-127">Após completar essas etapas, você pode abrir o painel de **Ajuda** e clicar em **Guias de tarefa**. Agora você verá as guias de tarefas que se aplicam à página que está sendo atualmente usada no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="21671-127">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you’re currently on in Finance and Operations.</span></span> <span data-ttu-id="21671-128">Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21671-128">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="21671-129">Exibindo guias de tarefa traduzidos</span><span class="sxs-lookup"><span data-stu-id="21671-129">Showing translated task guides</span></span>

<span data-ttu-id="21671-130">Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução.</span><span class="sxs-lookup"><span data-stu-id="21671-130">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="21671-131">No Finance and Operations, para ver a ajuda da guia de tarefas localizada, certifique-se de que você está conectado à biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="21671-131">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="21671-132">O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**.</span><span class="sxs-lookup"><span data-stu-id="21671-132">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span> 

> [!NOTE]
> <span data-ttu-id="21671-133">Embora muitas guias de tarefas tenham sido traduzidas, agora o Finance and Operations não está exibindo os nomes das guias de tarefas traduzidos.</span><span class="sxs-lookup"><span data-stu-id="21671-133">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="21671-134">Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="21671-134">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="21671-135">Lançaremos uma biblioteca atualizada com traduções adicionais.</span><span class="sxs-lookup"><span data-stu-id="21671-135">We will release an updated library with additional translations.</span></span>
> -   <span data-ttu-id="21671-136">Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="21671-136">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> -   <span data-ttu-id="21671-137">Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="21671-137">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="21671-138">Criando ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="21671-138">Creating custom help</span></span>
<span data-ttu-id="21671-139">Você pode criar ajuda personalizada para o Finance and Operations e para o Retail criando gravações de tarefas que refletem a sua implementação, e salvando-as em uma biblioteca de processo comercial de LCS.</span><span class="sxs-lookup"><span data-stu-id="21671-139">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="21671-140">Você não pode criar guias de tarefas personalizadas para o Talent.</span><span class="sxs-lookup"><span data-stu-id="21671-140">You cannot create custom task guides for Talent.</span></span> 

<span data-ttu-id="21671-141">Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes.</span><span class="sxs-lookup"><span data-stu-id="21671-141">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="21671-142">Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="21671-142">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="21671-143">Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="21671-143">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

<a name="see-also"></a><span data-ttu-id="21671-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="21671-144">See also</span></span>
--------

[<span data-ttu-id="21671-145">Visão geral da ajuda</span><span class="sxs-lookup"><span data-stu-id="21671-145">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="21671-146">Visão geral do Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="21671-146">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="21671-147">Como criar um registro de tarefa para usar como documentação ou treinamento</span><span class="sxs-lookup"><span data-stu-id="21671-147">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)





