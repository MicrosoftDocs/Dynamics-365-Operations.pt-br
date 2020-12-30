---
title: Configurar a experiência de ajuda para aplicativos do Finance and Operations
description: Este tópico fornece informações sobre os componentes do sistema de ajuda para alguns aplicativos do Microsoft Dynamics 365. Ele também explica como conectar esses aplicativos e fornece um resumo do processo para criar ajuda personalizada.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0495bbc008ed1760b98c2c1ace63fc4a8b1ab5cc
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694412"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a><span data-ttu-id="a0a06-104">Configurar a experiência de ajuda para aplicativos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a0a06-104">Configure the Help experience for Finance and Operations apps</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0a06-105">Neste tópico, você encontrará uma visão geral dos componentes do sistema de ajuda para aplicativos do Finance and Operations, como Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a0a06-105">In this topic, you will find an overview of the components of the Help system for Finance and Operations apps, such as Microsoft Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce, and Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a0a06-106">O tópico também explica como conectar esses componentes e fornece um resumo do processo para criar ajuda personalizada.</span><span class="sxs-lookup"><span data-stu-id="a0a06-106">The topic also explains how to connect these components and provides a summary of the process for creating custom Help.</span></span>

## <a name="help-architecture"></a><span data-ttu-id="a0a06-107">Arquitetura de ajuda</span><span class="sxs-lookup"><span data-stu-id="a0a06-107">Help architecture</span></span>

<span data-ttu-id="a0a06-108">Os aplicativos do Finance and Operations incluem visões gerais conceituais e outros tópicos publicados no site [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="a0a06-108">Finance and Operations apps include conceptual overviews and other topics that are published to the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span> <span data-ttu-id="a0a06-109">Esse conteúdo pode ser acessado no painel **Ajuda** do produto.</span><span class="sxs-lookup"><span data-stu-id="a0a06-109">This content can then be accessed from the in-product **Help** pane.</span></span> <span data-ttu-id="a0a06-110">A ilustração a seguir mostra as partes do sistema de Ajuda.</span><span class="sxs-lookup"><span data-stu-id="a0a06-110">The following illustration shows the parts of the Help system.</span></span>

<span data-ttu-id="a0a06-111">[![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="a0a06-111">[![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)</span></span>

<span data-ttu-id="a0a06-112">O sistema de ajuda do produto recebe os artigos de docs.microsoft.com e de outros sites conectados.</span><span class="sxs-lookup"><span data-stu-id="a0a06-112">The in-product Help system pulls articles from docs.microsoft.com and other connected websites.</span></span> <span data-ttu-id="a0a06-113">Ele também reúne guias de tarefas que são armazenadas no BPM (Modelador de processo de negócios) no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="a0a06-113">It also pulls in task guides that are stored in Business process modeler (BPM) in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="adding-task-guides"></a><span data-ttu-id="a0a06-114">Adição de guias de tarefas</span><span class="sxs-lookup"><span data-stu-id="a0a06-114">Adding task guides</span></span>

> [!NOTE]
> <span data-ttu-id="a0a06-115">No momento, a guia **Guias de tarefas** não está disponível no Human Resources nem no Commerce.</span><span class="sxs-lookup"><span data-stu-id="a0a06-115">The **Task guides** tab isn't currently available in Human Resources or Commerce.</span></span> <!--We are currently working to enable this functionality in a future release.--> <span data-ttu-id="a0a06-116">Mas, as guias de tarefas da experiência de Introdução ao Human Resources permanecem disponíveis para a funcionalidade básica.</span><span class="sxs-lookup"><span data-stu-id="a0a06-116">However, the task guides in the Getting Started experience in Human Resources remain available to cover basic functionality.</span></span> <span data-ttu-id="a0a06-117">No Human Resources e no Commerce, a ajuda de procedimentos está disponível no site [https://docs.microsoft.com/dynamics365](/dynamics365/).</span><span class="sxs-lookup"><span data-stu-id="a0a06-117">For both Human Resources and Commerce, procedural Help is available on the [https://docs.microsoft.com/dynamics365](/dynamics365/) site.</span></span>

<span data-ttu-id="a0a06-118">Na página **Parâmetros do sistema**, os administradores de sistema podem configurar o acesso às bibliotecas relevantes do guia de tarefas para uma implementação.</span><span class="sxs-lookup"><span data-stu-id="a0a06-118">On the **System parameters** page, system admins can configure access to the relevant task guide libraries for an implementation.</span></span>

> [!NOTE]
> - <span data-ttu-id="a0a06-119">Para configurar a Ajuda, você precisa entrar usando uma conta no mesmo locatário que o locatário em que o aplicativo é implantado.</span><span class="sxs-lookup"><span data-stu-id="a0a06-119">To configure Help, you must sign in by using an account in the same tenant as the tenant where the app is deployed.</span></span>
> - <span data-ttu-id="a0a06-120">Uma biblioteca de LCS não pode ser conectada de uma instância do aplicativo que esteja em execução em uma unidade de disco rígido virtual local (VHD).</span><span class="sxs-lookup"><span data-stu-id="a0a06-120">An LCS library can't be connected from an instance of the app that is running on a local virtual hard drive (VHD).</span></span>

<span data-ttu-id="a0a06-121">[![Formulário Parâmetros do Sistema com configurações da Ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span><span class="sxs-lookup"><span data-stu-id="a0a06-121">[![System Parameters form with Help settings](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)</span></span>

<span data-ttu-id="a0a06-122">Para configurar guias de tarefas para uma solução, siga estas etapas na página **Parâmetros do sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-122">To configure task guides for a solution, follow these steps on the **System parameters** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a0a06-123">A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="a0a06-123">The first time that you open the **Help** tab, you must connect to Lifecycle Services.</span></span> <span data-ttu-id="a0a06-124">Selecione o link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e selecione **OK** para acessar a página **Parâmetros do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-124">Be sure to select the link in the middle of the form, wait for the connection, close the dialog box, and then select **OK** to get to the **System Parameters** page.</span></span>
>
> <span data-ttu-id="a0a06-125">[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)</span><span class="sxs-lookup"><span data-stu-id="a0a06-125">[![Connect to LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)</span></span>

1. <span data-ttu-id="a0a06-126">Selecione o projeto do Lifecycle Services para se conectar.</span><span class="sxs-lookup"><span data-stu-id="a0a06-126">Select the Lifecycle Services project to connect to.</span></span>
2. <span data-ttu-id="a0a06-127">Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.</span><span class="sxs-lookup"><span data-stu-id="a0a06-127">Select the BPM libraries (within the selected project) to retrieve task recordings from.</span></span>
3. <span data-ttu-id="a0a06-128">Defina a ordem de exibição das bibliotecas do BPM.</span><span class="sxs-lookup"><span data-stu-id="a0a06-128">Set the display order of the BPM libraries.</span></span> <span data-ttu-id="a0a06-129">A ordem de exibição define a ordem em que as gravações de tarefas das bibliotecas aparecerão no painel de **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-129">The display order defines the order in which task recordings from the libraries will appear in the **Help** pane.</span></span>

<span data-ttu-id="a0a06-130">Após concluir essas etapas, você poderá abrir o painel de **Ajuda** e selecionar a guia **Guias de tarefas**. Veja as guias de tarefas que se aplicam à página em que você está agora nos aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a0a06-130">After you complete these steps, you can open the **Help** pane and select the **Task guides** tab. You'll now see the task guides that apply to the page that you're currently on in Finance and Operations apps.</span></span> <span data-ttu-id="a0a06-131">Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a0a06-131">If no task guides are found, you can enter keywords to refine your search.</span></span>

### <a name="showing-translated-task-guides"></a><span data-ttu-id="a0a06-132">Exibindo guias de tarefa traduzidos</span><span class="sxs-lookup"><span data-stu-id="a0a06-132">Showing translated task guides</span></span>

<span data-ttu-id="a0a06-133">Guias de tarefas traduzidas foram liberadas primeiro na Biblioteca Unificada de APQC de maio de 2016 e na biblioteca Introdução.</span><span class="sxs-lookup"><span data-stu-id="a0a06-133">Translated task guides were first released in the May 2016 APQC Unified Library and in the Getting Started library.</span></span> <span data-ttu-id="a0a06-134">Para exibir a ajuda da guia de tarefas localizadas, verifique se a solução do Dynamics 365 está conectada à biblioteca de maio de 2016.</span><span class="sxs-lookup"><span data-stu-id="a0a06-134">To view localized task guide Help, make sure that your Dynamics 365 solution is connected to the May 2016 library.</span></span> <span data-ttu-id="a0a06-135">Para mudar o idioma em que uma guia de tarefas aparece, usuários podem alterar as configurações de idioma em **Opções** &gt; **Preferências**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-135">Users can change the language that a task guide appears in by changing the language settings under **Options** &gt; **Preferences**.</span></span>

> [!NOTE]
> <span data-ttu-id="a0a06-136">Embora muitas guias de tarefas tenham sido traduzidas, no momento o cliente não mostra os nomes de guias de tarefas traduzidos.</span><span class="sxs-lookup"><span data-stu-id="a0a06-136">Although many task guides have been translated, the client doesn't currently show the translated task guide names.</span></span> <span data-ttu-id="a0a06-137">Além disso, na biblioteca de maio de 2016, foram disponibilizadas traduções apenas para guias de tarefas que foram liberadas em fevereiro de 2016.</span><span class="sxs-lookup"><span data-stu-id="a0a06-137">Additionally, in the May 2016 library, translations are available only for the task guides that were released in February 2016.</span></span> <span data-ttu-id="a0a06-138">A Microsoft lançará uma biblioteca atualizada que inclui traduções adicionais.</span><span class="sxs-lookup"><span data-stu-id="a0a06-138">Microsoft will release an updated library that includes additional translations.</span></span>
>
> - <span data-ttu-id="a0a06-139">Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="a0a06-139">If a task guide has been translated, when you open that task guide all the text of the task guide will appear in your selected language.</span></span>
> - <span data-ttu-id="a0a06-140">Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.</span><span class="sxs-lookup"><span data-stu-id="a0a06-140">If a task guide has not yet been translated, when you open it, only some of the text (the text of the controls) will appear in your selected language.</span></span>

## <a name="adding-custom-help"></a><span data-ttu-id="a0a06-141">Adição de ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="a0a06-141">Adding custom Help</span></span>

<span data-ttu-id="a0a06-142">Você pode usar guias de tarefa para criar ajuda personalizada ou conectar um site de ajuda personalizada ao painel de **Ajuda**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-142">You can use task guides to create custom Help, or you can connect a custom Help website to the **Help** pane.</span></span>

### <a name="create-custom-help-by-using-task-guides"></a><span data-ttu-id="a0a06-143">Crie ajuda personalizada com guias de tarefas</span><span class="sxs-lookup"><span data-stu-id="a0a06-143">Create custom Help by using task guides</span></span>

<span data-ttu-id="a0a06-144">Você pode criar ajuda personalizada para aplicativos com suporte criando registros de tarefas que reflitam sua implementação e salvando-os em uma biblioteca de processos comerciais no LCS.</span><span class="sxs-lookup"><span data-stu-id="a0a06-144">You can create custom Help for the supported apps by creating task recordings that reflect your implementation and then saving them to a Business process library in LCS.</span></span> <span data-ttu-id="a0a06-145">Não é possível criar guias de tarefas personalizadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a0a06-145">You can't create custom task guides for Human Resources.</span></span>

<span data-ttu-id="a0a06-146">Se você for um parceiro e promover uma biblioteca para uma biblioteca corporativa e incluí-la em uma solução, ela ficará disponível para os clientes.</span><span class="sxs-lookup"><span data-stu-id="a0a06-146">If you're a partner, and you promote a library to a corporate library and include it in a solution, it will be available to your customers.</span></span> <span data-ttu-id="a0a06-147">Você também pode fazer uma cópia da biblioteca unificada de APQC, abrir as gravações de tarefas na cópia, editá-las e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a0a06-147">You can also make a copy of the APQC Unified Library, and then open the task recordings in the copy, edit them, and save your changes.</span></span> <span data-ttu-id="a0a06-148">Para obter mais informações, consulte [Recursos do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="a0a06-148">For more information, see [Task recorder resources](../../dev-itpro/user-interface/task-recorder.md).</span></span>

### <a name="connect-a-custom-help-site"></a><span data-ttu-id="a0a06-149">Conecte um site de ajuda personalizado</span><span class="sxs-lookup"><span data-stu-id="a0a06-149">Connect a custom Help site</span></span>

<span data-ttu-id="a0a06-150">Os aplicativos do Finance and Operations raramente são usados no formulário pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="a0a06-150">Finance and Operations apps are rarely used in their out-of-box form.</span></span> <span data-ttu-id="a0a06-151">Em vez disso, a solução é personalizada e estendida para atender às necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="a0a06-151">Instead, the solution is customized and extended to fit the organization's needs.</span></span> <span data-ttu-id="a0a06-152">Também é possível personalizar e estender a experiência da ajuda.</span><span class="sxs-lookup"><span data-stu-id="a0a06-152">You can also customize and extend the Help experience.</span></span> <span data-ttu-id="a0a06-153">Por exemplo, você pode adicionar ajuda personalizada ao painel de **ajuda** do produto.</span><span class="sxs-lookup"><span data-stu-id="a0a06-153">For example, you can add custom Help to the in-product **Help** pane.</span></span>

<span data-ttu-id="a0a06-154">A Microsoft forneceu um kit de ferramentas para ajudar você a implantar e conectar a ajuda personalizada ao painel de **ajuda**.</span><span class="sxs-lookup"><span data-stu-id="a0a06-154">Microsoft has provided a toolkit to help you deploy and connect custom Help to the **Help** pane.</span></span> <span data-ttu-id="a0a06-155">Para obter informações sobre como você pode configurar uma solução de ajuda personalizada que está conectada ao painel de **ajuda**, consulte [Visão geral da ajuda personalizada](../../dev-itpro/help/custom-help-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a0a06-155">For information about how you can set up a custom Help solution that is connected to the **Help** pane, see [Custom Help overview](../../dev-itpro/help/custom-help-overview.md).</span></span>

<span data-ttu-id="a0a06-156">Se você desejar colaborar com a Microsoft em ferramentas e processos para personalizar a ajuda, preencha o formulário em [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span><span class="sxs-lookup"><span data-stu-id="a0a06-156">If you want to collaborate with Microsoft on tools and processes for customizing Help, fill in the form at [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).</span></span>

## <a name="see-also"></a><span data-ttu-id="a0a06-157">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a0a06-157">See also</span></span>

[<span data-ttu-id="a0a06-158">Sistema de ajuda</span><span class="sxs-lookup"><span data-stu-id="a0a06-158">Help system</span></span>](help-overview.md)  
[<span data-ttu-id="a0a06-159">Visão geral da ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="a0a06-159">Custom Help overview</span></span>](../../dev-itpro/help/custom-help-overview.md)  
[<span data-ttu-id="a0a06-160">Recursos do Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="a0a06-160">Task recorder resources</span></span>](../../dev-itpro/user-interface/task-recorder.md)  
[<span data-ttu-id="a0a06-161">Criar documentação ou treinamento com o Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="a0a06-161">Create documentation or training with Task Recorder</span></span>](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[<span data-ttu-id="a0a06-162">Repositório do GitHub de ajuda personalizada</span><span class="sxs-lookup"><span data-stu-id="a0a06-162">Custom Help GitHub repository</span></span>](https://github.com/microsoft/dynamics356f-o-custom-help)  
