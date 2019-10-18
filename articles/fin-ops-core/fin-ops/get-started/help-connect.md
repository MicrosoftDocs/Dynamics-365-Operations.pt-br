---
title: Conectar o sistema de Ajuda
description: Este tópico descreve os componentes do sistema de Ajuda de aplicativos do Finance and Operations e fornece uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 491024c9c3d6c7d20ef212e167ceab6abac8dac7
ms.sourcegitcommit: d554faca895609b8124bf2ea5aca5a55c407534a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "2537846"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="49198-103">Conectar o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="49198-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49198-104">Este tópico descreve os componentes do sistema de Ajuda de aplicativos do Finance and Operations, como Dynamics 365 Finance, Supply Chain Management, Retail e Talent.</span><span class="sxs-lookup"><span data-stu-id="49198-104">This topic describes the components of the Help system for Finance and Operations apps, such as Dynamics 365 Finance, Supply Chain Management, Retail, and Talent.</span></span> <span data-ttu-id="49198-105">Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="49198-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="49198-106">Arquitetura de ajuda</span><span class="sxs-lookup"><span data-stu-id="49198-106">Help architecture</span></span>

<span data-ttu-id="49198-107">A ilustração a seguir mostra as partes do sistema de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="49198-107">The following illustration shows the parts of the Help system.</span></span> <span data-ttu-id="49198-108">O sistema de Ajuda no produto traz artigos de https://docs.microsoft.com, bem como guias de tarefas armazenadas no Modelador de processo de negócios do Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="49198-108">The in-product Help system pulls articles from https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="49198-109">Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="49198-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="49198-110">[![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="49198-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="49198-111">Conectando o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="49198-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="49198-112">No momento, a guia **Guias de tarefas** não está disponível Dynamics 365 Talent ou no Retail.</span><span class="sxs-lookup"><span data-stu-id="49198-112">The **Task guides** tab is currently not available in Dynamics 365 Talent or Retail.</span></span> <span data-ttu-id="49198-113">Estamos trabalhando atualmente para habilitar essa funcionalidade em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="49198-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="49198-114">As guias de tarefas da experiência de Introdução ao Talent permanecerão disponíveis para a funcionalidade básica.</span><span class="sxs-lookup"><span data-stu-id="49198-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="49198-115">A ajuda de procedimento também está disponível no site docs.microsoft.com para o Retail e o Talent.</span><span class="sxs-lookup"><span data-stu-id="49198-115">Procedural help is also available on the docs.microsoft.com site for both Retail and Talent.</span></span>

<span data-ttu-id="49198-116">Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação.</span><span class="sxs-lookup"><span data-stu-id="49198-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="49198-117">[![Formulário Parâmetros do Sistema com configurações da Ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="49198-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="49198-118">Na página **Parâmetros do sistema**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="49198-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49198-119">A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="49198-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="49198-120">Clique no link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e clique em **OK** para acessar a página **Parâmetros do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="49198-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="49198-121">[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="49198-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="49198-122">Selecione o projeto do Lifecycle Services para se conectar.</span><span class="sxs-lookup"><span data-stu-id="49198-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="49198-123">Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.</span><span class="sxs-lookup"><span data-stu-id="49198-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="49198-124">Defina a ordem de exibição das bibliotecas do BPM.</span><span class="sxs-lookup"><span data-stu-id="49198-124">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="49198-125">Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="49198-125">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="49198-126">Após concluir essas etapas, você poderá abrir o painel **Ajuda** e clicar em **Guias de tarefas**. Agora você verá as guias de tarefas que se aplicam à página que você está utilizando nos aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="49198-126">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="49198-127">Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="49198-127">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="49198-128">Exibindo guias de tarefa traduzidos</span><span class="sxs-lookup"><span data-stu-id="49198-128">Showing translated task guides</span></span>

<span data-ttu-id="49198-129">Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução.</span><span class="sxs-lookup"><span data-stu-id="49198-129">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="49198-130">Nos aplicativos do Finance and Operations, para ver a ajuda da guia de tarefas localizada, certifique-se de que você está conectado à biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="49198-130">In Finance and Operations apps, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="49198-131">O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**.</span><span class="sxs-lookup"><span data-stu-id="49198-131">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="49198-132">Embora muitas guias de tarefas tenham sido traduzidas, no momento, o cliente não está mostrando os nomes de guias de tarefas traduzidos.</span><span class="sxs-lookup"><span data-stu-id="49198-132">Even though many task guides have been translated, right now the client is not showing the translated task guide names.</span></span> <span data-ttu-id="49198-133">Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="49198-133">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="49198-134">Lançaremos uma biblioteca atualizada com traduções adicionais.</span><span class="sxs-lookup"><span data-stu-id="49198-134">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="49198-135">Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="49198-135">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="49198-136">Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="49198-136">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="49198-137">Criando ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="49198-137">Creating custom help</span></span>

<span data-ttu-id="49198-138">Você pode usar guias de tarefa para criar ajuda personalizada ou conectar a um site para o painel da ajuda.</span><span class="sxs-lookup"><span data-stu-id="49198-138">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="49198-139">Criar Ajuda personalizada com guia de tarefas</span><span class="sxs-lookup"><span data-stu-id="49198-139">Create custom help with task guides</span></span>

<span data-ttu-id="49198-140">Você pode criar ajuda personalizada para o Finance, o Supply Chain Management e o Retail criando gravações de tarefas que refletem a sua implementação e salvando-as em uma biblioteca de processo comercial de LCS.</span><span class="sxs-lookup"><span data-stu-id="49198-140">You can create custom help for Finance, Supply Chain Management, and Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="49198-141">Você não pode criar guias de tarefas personalizadas para o Talent.</span><span class="sxs-lookup"><span data-stu-id="49198-141">You cannot create custom task guides for Talent.</span></span>

<span data-ttu-id="49198-142">Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes.</span><span class="sxs-lookup"><span data-stu-id="49198-142">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="49198-143">Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="49198-143">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="49198-144">Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="49198-144">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="49198-145">Conectar um site personalizado</span><span class="sxs-lookup"><span data-stu-id="49198-145">Connect a custom site</span></span>

<span data-ttu-id="49198-146">A Microsoft fornece um white paper e um código de amostra que descreve como criar e conectar um site de ajuda personalizado para o painel de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="49198-146">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="49198-147">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="49198-147">For more information, see:</span></span>

- [<span data-ttu-id="49198-148">Criar ajuda personalizada para aplicativos do Finance and Operations (white paper)</span><span class="sxs-lookup"><span data-stu-id="49198-148">Create Custom Help for Finance and Operations apps (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="49198-149">Repositório do GitHub de ajuda personalizado</span><span class="sxs-lookup"><span data-stu-id="49198-149">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="49198-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="49198-150">Additional resources</span></span>

[<span data-ttu-id="49198-151">Visão geral da ajuda</span><span class="sxs-lookup"><span data-stu-id="49198-151">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="49198-152">Visão geral do Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="49198-152">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="49198-153">Como criar um registro de tarefa para usar como documentação ou treinamento</span><span class="sxs-lookup"><span data-stu-id="49198-153">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
