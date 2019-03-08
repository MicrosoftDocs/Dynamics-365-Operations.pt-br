---
title: Conectar o sistema de Ajuda
description: Este tópico descreve os componentes do sistema de ajuda do Microsoft Dynamics 365 for Finance and Operations e fornece uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada.
author: margoc
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
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
ms.openlocfilehash: 673b01648127fe1d19fb3c75c4d6812c4f22c761
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317720"
---
# <a name="connect-the-help-system"></a><span data-ttu-id="58de5-103">Conectar o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="58de5-103">Connect the Help system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58de5-104">Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58de5-104">This topic describes the components of the Help system for Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="58de5-105">Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="58de5-105">It provides an overview of how to connect these components and a summary of how to create custom help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="58de5-106">Arquitetura de ajuda</span><span class="sxs-lookup"><span data-stu-id="58de5-106">Help architecture</span></span>

<span data-ttu-id="58de5-107">A ilustração a seguir mostra as partes do sistema de Ajuda do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58de5-107">The following illustration shows the parts of the Finance and Operations Help system.</span></span> <span data-ttu-id="58de5-108">O sistema de Ajuda do produto traz artigos do site do Finance and Operations em https://docs.microsoft.com, bem como guias de tarefas armazenadas no Modelador de processo de negócios do Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="58de5-108">The in-product Help system pulls articles from the Finance and Operations site on https://docs.microsoft.com, as well as task guides stored in Business Process Modeler in Lifecycle Services (LCS).</span></span>

> [!NOTE]
> <span data-ttu-id="58de5-109">Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="58de5-109">The features listed in the diagram with an asterisk (\*) are planned, but are not available yet.</span></span>

<span data-ttu-id="58de5-110">[![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="58de5-110">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

## <a name="connecting-the-help-system"></a><span data-ttu-id="58de5-111">Conectando o sistema de Ajuda</span><span class="sxs-lookup"><span data-stu-id="58de5-111">Connecting the Help system</span></span>

> [!NOTE]
> <span data-ttu-id="58de5-112">A guia **Guias de tarefa** não está disponível atualmente no Microsoft Dynamics 365 for Talent e no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="58de5-112">The **Task guides** tab is currently not available in Microsoft Dynamics 365 for Talent and Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="58de5-113">Estamos trabalhando atualmente para habilitar essa funcionalidade em uma versão futura.</span><span class="sxs-lookup"><span data-stu-id="58de5-113">We are currently working to enable this functionality in a future release.</span></span> <span data-ttu-id="58de5-114">As guias de tarefas da experiência de Introdução ao Talent permanecerão disponíveis para a funcionalidade básica.</span><span class="sxs-lookup"><span data-stu-id="58de5-114">The Task guides in the Getting Started experience in Talent remain available to cover basic functionality.</span></span> <span data-ttu-id="58de5-115">A ajuda de procedimento também está disponível no site docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) para ambos, Retail e Talent.</span><span class="sxs-lookup"><span data-stu-id="58de5-115">Procedural help is also available on the docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) for both Retail and Talent.</span></span>

<span data-ttu-id="58de5-116">Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação.</span><span class="sxs-lookup"><span data-stu-id="58de5-116">Using the **System Parameters** page, system administrators connect the pieces of the Help system for an implementation.</span></span>

<span data-ttu-id="58de5-117">[![Formulário Parâmetros do Sistema com configurações da Ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="58de5-117">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="58de5-118">Na página **Parâmetros do sistema**, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="58de5-118">On the **System parameters** page, follow these steps:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58de5-119">A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="58de5-119">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="58de5-120">Clique no link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e clique em **OK** para acessar a página **Parâmetros do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="58de5-120">Be sure to click the link in the middle of the form, wait for the connection, close the dialog box, and then click **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="58de5-121">[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="58de5-121">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="58de5-122">Selecione o projeto do Lifecycle Services para se conectar.</span><span class="sxs-lookup"><span data-stu-id="58de5-122">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="58de5-123">Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.</span><span class="sxs-lookup"><span data-stu-id="58de5-123">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>

    - <span data-ttu-id="58de5-124">Referente ao Finance and Operations, conteúdo da Microsoft, selecione a Biblioteca Unificada APQC mais recente para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58de5-124">For Finance and Operations, for Microsoft content, select the most recent APQC Unified Library for Finance and Operations.</span></span>
    - <span data-ttu-id="58de5-125">Para o Retail, liberaremos uma biblioteca em breve.</span><span class="sxs-lookup"><span data-stu-id="58de5-125">For Retail, we will be releasing a library in the near future.</span></span>
    - <span data-ttu-id="58de5-126">Não é necessário selecionar uma biblioteca para o Talent - a conexão com a biblioteca correta é estabelecida para você.</span><span class="sxs-lookup"><span data-stu-id="58de5-126">You do not need to select a library for Talent—the connection to the correct library is established for you.</span></span>

3. <span data-ttu-id="58de5-127">Defina a ordem de exibição das bibliotecas do BPM.</span><span class="sxs-lookup"><span data-stu-id="58de5-127">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="58de5-128">Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="58de5-128">This determines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="58de5-129">Após concluir essas etapas, você poderá abrir o painel de **Ajuda** e clicar em **Guias de tarefas**. Agora você verá as guias de tarefas que se aplicam à página que você está utilizando agora no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58de5-129">After you complete these steps, you can open the **Help** pane and click the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations.</span></span> <span data-ttu-id="58de5-130">Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="58de5-130">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="58de5-131">Exibindo guias de tarefa traduzidos</span><span class="sxs-lookup"><span data-stu-id="58de5-131">Showing translated task guides</span></span>

<span data-ttu-id="58de5-132">Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução.</span><span class="sxs-lookup"><span data-stu-id="58de5-132">Translated task guides were first shipped in the May 2016 APQC Unified Library, and the Getting Started library.</span></span> <span data-ttu-id="58de5-133">No Finance and Operations, para ver a ajuda da guia de tarefas localizada, certifique-se de que você está conectado à biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="58de5-133">In Finance and Operations, to see localized task guide help, make sure that you are connected to the May library.</span></span> <span data-ttu-id="58de5-134">O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**.</span><span class="sxs-lookup"><span data-stu-id="58de5-134">The language that a task guide appears in is controlled for each user by the Language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="58de5-135">Embora muitas guias de tarefas tenham sido traduzidas, agora o Finance and Operations não está exibindo os nomes das guias de tarefas traduzidos.</span><span class="sxs-lookup"><span data-stu-id="58de5-135">Even though many task guides have been translated, right now the Finance and Operations client is not showing the translated task guide names.</span></span> <span data-ttu-id="58de5-136">Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio.</span><span class="sxs-lookup"><span data-stu-id="58de5-136">Also, only the task guides that were released in February 2016 are available in translation in the May library.</span></span> <span data-ttu-id="58de5-137">Lançaremos uma biblioteca atualizada com traduções adicionais.</span><span class="sxs-lookup"><span data-stu-id="58de5-137">We will release an updated library with additional translations.</span></span>
>
> - <span data-ttu-id="58de5-138">Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="58de5-138">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="58de5-139">Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="58de5-139">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="creating-custom-help"></a><span data-ttu-id="58de5-140">Criando ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="58de5-140">Creating custom help</span></span>

<span data-ttu-id="58de5-141">Você pode usar guias de tarefa para criar ajuda personalizada ou conectar a um site para o painel da ajuda.</span><span class="sxs-lookup"><span data-stu-id="58de5-141">You can use task guides to create custom help, or connect a website to the Help pane.</span></span>

### <a name="create-custom-help-with-task-guides"></a><span data-ttu-id="58de5-142">Criar Ajuda personalizada com guia de tarefas</span><span class="sxs-lookup"><span data-stu-id="58de5-142">Create custom help with task guides</span></span>

<span data-ttu-id="58de5-143">Você pode criar ajuda personalizada para o Finance and Operations e para o Retail criando gravações de tarefas que refletem a sua implementação, e salvando-as em uma biblioteca de processo comercial de LCS.</span><span class="sxs-lookup"><span data-stu-id="58de5-143">You can create custom help for Finance and Operations, and for Retail by creating task recordings that reflect your implementation, and saving them to an LCS Business Process Library.</span></span> <span data-ttu-id="58de5-144">Você não pode criar guias de tarefas personalizadas para o Talent.</span><span class="sxs-lookup"><span data-stu-id="58de5-144">You cannot create custom task guides for Talent.</span></span>

<span data-ttu-id="58de5-145">Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes.</span><span class="sxs-lookup"><span data-stu-id="58de5-145">For partners, if you promote a library to be a corporate library, and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="58de5-146">Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="58de5-146">You can also make a copy of the APQC Unified global library, and then open your copy, open task recordings from it, modify them, and save the recordings with your changes.</span></span> <span data-ttu-id="58de5-147">Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="58de5-147">For more information, see [How to create a task recording to use as documentation or training](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-site"></a><span data-ttu-id="58de5-148">Conectar um site personalizado</span><span class="sxs-lookup"><span data-stu-id="58de5-148">Connect a custom site</span></span>

<span data-ttu-id="58de5-149">A Microsoft fornece um white paper e um código de amostra que descreve como criar e conectar um site de ajuda personalizado para o painel de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="58de5-149">Microsoft has provided a white paper and sample code that describe how to create and connect a custom help site to the Help pane.</span></span> <span data-ttu-id="58de5-150">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="58de5-150">For more information, see:</span></span>

- [<span data-ttu-id="58de5-151">Crie a ajuda personalizada para Finance and Operations (white paper)</span><span class="sxs-lookup"><span data-stu-id="58de5-151">Create Custom Help for Finance and Operations (white paper)</span></span>](https://go.microsoft.com/fwlink/?linkid=2041185)
- [<span data-ttu-id="58de5-152">Repositório do GitHub de ajuda personalizado</span><span class="sxs-lookup"><span data-stu-id="58de5-152">Custom help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a><span data-ttu-id="58de5-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="58de5-153">Additional resources</span></span>

[<span data-ttu-id="58de5-154">Visão geral da ajuda</span><span class="sxs-lookup"><span data-stu-id="58de5-154">Help overview</span></span>](help-overview.md)

[<span data-ttu-id="58de5-155">Visão geral do Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="58de5-155">Task recorder overview</span></span>](../../dev-itpro/user-interface/task-recorder.md)

[<span data-ttu-id="58de5-156">Como criar um registro de tarefa para usar como documentação ou treinamento</span><span class="sxs-lookup"><span data-stu-id="58de5-156">How to create a task recording to use as documentation or training</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)
