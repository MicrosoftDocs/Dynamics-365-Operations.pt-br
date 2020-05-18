---
title: Configurar e criar formatos de recibo
description: Este artigo descreve como modificar layouts de formulário para controlar como os recibos, as notas fiscais e outros documentos serão impressos. O Dynamics 365 Commerce inclui um designer do layout de formulário que você pode usar para criar e modificar de modo fácil e gráfico diversos tipos de layouts de formulário.
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ab6b01d6833850af8c04167d94b0a60c7312075c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021646"
---
# <a name="set-up-and-design-receipt-formats"></a><span data-ttu-id="b3302-104">Configurar e criar formatos de recibo</span><span class="sxs-lookup"><span data-stu-id="b3302-104">Set up and design receipt formats</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3302-105">Este artigo descreve como modificar layouts de formulário para controlar como os recibos, as notas fiscais e outros documentos serão impressos.</span><span class="sxs-lookup"><span data-stu-id="b3302-105">This article describes how to modify form layouts to control how receipts, invoices, and other documents are printed.</span></span> <span data-ttu-id="b3302-106">O Dynamics 365 Commerce inclui um designer do layout de formulário que você pode usar para criar e modificar facilmente vários tipos de layout de formulário</span><span class="sxs-lookup"><span data-stu-id="b3302-106">Dynamics 365  Commerce includes a form layout designer that you can use to easily create and modify various kinds of form layouts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3302-107">Você deve configurar layouts de formulário e perfis de recibo para imprimir recibos e outros documentos no Retail Modern POS e no Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="b3302-107">You must set up form layouts and receipt profiles to print receipts and other documents from Retail Modern POS and Cloud POS.</span></span> <span data-ttu-id="b3302-108">Você pode incluir vários layouts de formulário em um perfil de recibo.</span><span class="sxs-lookup"><span data-stu-id="b3302-108">You can include multiple form layouts in a receipt profile.</span></span> <span data-ttu-id="b3302-109">Em seguida, você pode atribuir o perfil de recibo a uma impressora modificando um perfil de hardware.</span><span class="sxs-lookup"><span data-stu-id="b3302-109">You can then assign the receipt profile to a printer by modifying a hardware profile.</span></span>

## <a name="set-up-a-receipt-format"></a><span data-ttu-id="b3302-110">Configurar um formato de recibo</span><span class="sxs-lookup"><span data-stu-id="b3302-110">Set up a receipt format</span></span>

1. <span data-ttu-id="b3302-111">Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Formatos de recibo**.</span><span class="sxs-lookup"><span data-stu-id="b3302-111">Click **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Receipt formats**.</span></span>
2. <span data-ttu-id="b3302-112">Na página **Formato de recibo**, clique em **Novo** para criar um novo layout de formulário ou selecione um layout de formulário existente.</span><span class="sxs-lookup"><span data-stu-id="b3302-112">On the **Receipt format** page, click **New** to create a new form layout, or select an existing form layout.</span></span>
3. <span data-ttu-id="b3302-113">No campo **Formato de recibo**, insira um identificador para o layout de formulário e selecione o tipo de recibo para o qual esse layout será usado.</span><span class="sxs-lookup"><span data-stu-id="b3302-113">In the **Receipt format** field, enter an identifier for the form layout, and then select the type of receipt that this layout is used for.</span></span> <span data-ttu-id="b3302-114">Você também pode inserir uma descrição e um nome curto para o recibo no campo **Título**.</span><span class="sxs-lookup"><span data-stu-id="b3302-114">You can also enter a description and a short name for the receipt in the **Title** field.</span></span>
4. <span data-ttu-id="b3302-115">Na Guia Rápida **Geral**, selecione uma opção para definir o comportamento da impressão:</span><span class="sxs-lookup"><span data-stu-id="b3302-115">On the **General** FastTab, select an option to define the print behavior:</span></span>

    - <span data-ttu-id="b3302-116">**Sempre imprimir** – O recibo é impresso automaticamente, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="b3302-116">**Always print** – The receipt is printed automatically, as appropriate.</span></span>
    - <span data-ttu-id="b3302-117">**Não imprimir** – O recibo não é impresso.</span><span class="sxs-lookup"><span data-stu-id="b3302-117">**Do not print** – The receipt isn't printed.</span></span>
    - <span data-ttu-id="b3302-118">**Avisar usuário** – O usuário será solicitado a imprimir o recibo.</span><span class="sxs-lookup"><span data-stu-id="b3302-118">**Prompt user** – The user is prompted to print the receipt.</span></span>
    - <span data-ttu-id="b3302-119">**Conforme necessário** – Esta opção é usada apenas para os recibos de presentes.</span><span class="sxs-lookup"><span data-stu-id="b3302-119">**As required** – This option is used only for gift receipts.</span></span> <span data-ttu-id="b3302-120">Quando essa opção for selecionada, o usuário poderá imprimir um recibo de presente na página **Alterar** se um recibo de presente for necessário.</span><span class="sxs-lookup"><span data-stu-id="b3302-120">When this option is selected, the user can print a gift receipt from the **Change** page, if a gift receipt is required.</span></span>

## <a name="design-a-receipt-format"></a><span data-ttu-id="b3302-121">Criar um formato de recibo</span><span class="sxs-lookup"><span data-stu-id="b3302-121">Design a receipt format</span></span>

<span data-ttu-id="b3302-122">Use o designer de layout de formulário para criar graficamente o layout do documento do formulário.</span><span class="sxs-lookup"><span data-stu-id="b3302-122">Use the form layout designer to graphically create the layout of the form document.</span></span> <span data-ttu-id="b3302-123">A página **Designer de formato de recibo** tem três seções: **Cabeçalho**, **Linhas** e **Rodapé**.</span><span class="sxs-lookup"><span data-stu-id="b3302-123">The **Receipt format designer** page has three sections: **Header**, **Lines**, and **Footer**.</span></span> <span data-ttu-id="b3302-124">Alguns tipos de layouts de formulário usam elementos das três seções, enquanto outros tipos usam elementos de apenas uma ou duas seções.</span><span class="sxs-lookup"><span data-stu-id="b3302-124">Some types of form layouts use elements from all three sections, whereas other types use elements from only one or two sections.</span></span> <span data-ttu-id="b3302-125">Para exibir os elementos que estão disponíveis em cada seção, clique no botão apropriado no painel de navegação no lado esquerdo da página.</span><span class="sxs-lookup"><span data-stu-id="b3302-125">To view the elements that are available for each section, click the appropriate button in the navigation pane on the left side of the page.</span></span>

1. <span data-ttu-id="b3302-126">Clique em **Retail e Commerce** &gt; **Configuração de canal** &gt; **Configuração do PDV** &gt; **PDV** &gt; **Formatos de recibo**.</span><span class="sxs-lookup"><span data-stu-id="b3302-126">Click **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS** &gt; **Receipt formats**.</span></span>
2. <span data-ttu-id="b3302-127">Na página **Formato de recibo**, selecione um layout de formulário e clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="b3302-127">On the **Receipt format** page, select a form layout, and then click **Designer**.</span></span>
3. <span data-ttu-id="b3302-128">Clique em **Executar** para começar a instalar o host de designer Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3302-128">Click **Run** to start to install the Commerce designer host.</span></span>
4. <span data-ttu-id="b3302-129">Na barra de notificação exibida na parte inferior da janela do Internet Explorer, clique em **Abrir** para começar a instalação do designer de um clique.</span><span class="sxs-lookup"><span data-stu-id="b3302-129">On the Notification bar that appears at the bottom of the Internet Explorer window, click **Open** to start to install the one-click designer.</span></span> <span data-ttu-id="b3302-130">(A barra de notificação poderá aparecer em um outro local em outros browsers.) O indicador de progresso mostra o progresso do processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="b3302-130">(The Notification bar might appear in a different location in other browsers.) The progress indicator shows the progress of the installation process.</span></span>
5. <span data-ttu-id="b3302-131">Ao final da instalação, insira seu nome de usuário e senha do Commerce, e clique em **Entrar** para iniciar o designer.</span><span class="sxs-lookup"><span data-stu-id="b3302-131">After the installation is completed, enter your Commerce user name and password, and then click **Sign in** to start the designer.</span></span>
6. <span data-ttu-id="b3302-132">Depois que suas credenciais forem validadas e o designer for iniciado, você poderá começar a criar o formato de recibo ou modificar um formato existente.</span><span class="sxs-lookup"><span data-stu-id="b3302-132">After your credentials are validated and the designer starts, you can start to design the receipt format or modify an existing format.</span></span>
7. <span data-ttu-id="b3302-133">Para criar os elementos do formulário, selecione a seção **Cabeçalho**, **Linhas** ou **Rodapé** e arraste um elemento dessa seção para o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b3302-133">To create the elements of the form, select the **Header**, **Lines**, or **Footer** section, and then drag an element from that section to the workspace.</span></span> <span data-ttu-id="b3302-134">A maioria dos elementos contém variáveis que são preenchidas automaticamente com dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b3302-134">Most elements contain variables that are automatically populated with data from the database.</span></span> <span data-ttu-id="b3302-135">Outros elementos, como **Texto**, permitem imprimir texto personalizado no recibo.</span><span class="sxs-lookup"><span data-stu-id="b3302-135">Other elements, such as **Text**, let you print custom text on the receipt.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b3302-136">Você pode especificar por quantas linhas cada seção se estende ajustando o número no canto inferior direito dessa seção.</span><span class="sxs-lookup"><span data-stu-id="b3302-136">You can specify how many lines each section spans by adjusting the number in the lower-right corner of that section.</span></span> <span data-ttu-id="b3302-137">Para facilitar a modificação de uma seção, aumente sua altura arrastando a barra de dimensionamento na parte inferior da seção.</span><span class="sxs-lookup"><span data-stu-id="b3302-137">To make it easier to modify a section, increase its height by dragging the sizing bar at the bottom of the section.</span></span> <span data-ttu-id="b3302-138">A altura da seção no espaço de trabalho não afeta o número de linhas no recibo real.</span><span class="sxs-lookup"><span data-stu-id="b3302-138">The height of the section on the workspace doesn't affect the number of lines on the actual receipt.</span></span>

8. <span data-ttu-id="b3302-139">Após arrastar um elemento para o espaço de trabalho, defina as propriedades da parte no painel **Informações do objeto** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="b3302-139">After you drag an element to the workspace, set the properties for the part in the **Object information** pane at the bottom of the page.</span></span> <span data-ttu-id="b3302-140">Especifique uma ou mais das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b3302-140">Enter one or more of the following settings:</span></span>

    - <span data-ttu-id="b3302-141">**Alinhar** – defina o alinhamento do campo à **Esquerda** ou à **Direita**.</span><span class="sxs-lookup"><span data-stu-id="b3302-141">**Align** – Set the alignment of the field to either **Left** or **Right**.</span></span>
    - <span data-ttu-id="b3302-142">**Caractere de preenchimento** – Especifique o caractere de espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="b3302-142">**Fill char** – Specify the white space character.</span></span> <span data-ttu-id="b3302-143">Por padrão, um espaço em branco é usado, mas você pode inserir qualquer caractere.</span><span class="sxs-lookup"><span data-stu-id="b3302-143">By default, an empty space is used, but you can enter any character.</span></span>
    - <span data-ttu-id="b3302-144">**Prefixo** – Insira o valor que aparece no início do campo.</span><span class="sxs-lookup"><span data-stu-id="b3302-144">**Prefix** – Enter the value that appears at the beginning of the field.</span></span> <span data-ttu-id="b3302-145">Essa configuração se aplica apenas à seção **Linhas** do layout.</span><span class="sxs-lookup"><span data-stu-id="b3302-145">This setting applies only to the **Lines** section of the layout.</span></span>
    - <span data-ttu-id="b3302-146">**Caracteres** – Especifique o número máximo de caracteres que o campo poderá conter se o elemento tiver uma variável.</span><span class="sxs-lookup"><span data-stu-id="b3302-146">**Characters** – Specify the maximum number of characters that the field can contain if the element contains a variable.</span></span> <span data-ttu-id="b3302-147">Se o texto no campo for maior do que o número de caracteres que você especificar, o texto será truncado para se ajustar ao campo.</span><span class="sxs-lookup"><span data-stu-id="b3302-147">If the text in the field is longer than the number of character that you specify, the text is truncated to fit the field.</span></span>
    - <span data-ttu-id="b3302-148">**Variável** – Esta caixa de seleção será marcada automaticamente se o elemento contiver uma variável e não puder ser personalizado.</span><span class="sxs-lookup"><span data-stu-id="b3302-148">**Variable** – This check box is selected automatically if the element contains a variable and can't be customized.</span></span>
    - <span data-ttu-id="b3302-149">**Tipo de fonte** – Defina o estilo de fonte como **Normal** ou **Negrito**.</span><span class="sxs-lookup"><span data-stu-id="b3302-149">**Font type** – Set the font style to either **Regular** or **Bold**.</span></span> <span data-ttu-id="b3302-150">As letras em negrito usam duas vezes mais espaço que as letras normais.</span><span class="sxs-lookup"><span data-stu-id="b3302-150">Bold letters use two times as much space as regular letters.</span></span> <span data-ttu-id="b3302-151">Portanto, alguns caracteres podem ser truncados.</span><span class="sxs-lookup"><span data-stu-id="b3302-151">Therefore, some characters might be truncated.</span></span>
    - <span data-ttu-id="b3302-152">**Tamanho de fonte** – Defina o estilo de fonte como **Normal** ou **Grande**.</span><span class="sxs-lookup"><span data-stu-id="b3302-152">**Font size** – Set the font size to either **Regular** or **Large**.</span></span> <span data-ttu-id="b3302-153">As letras grandes são duas vezes maiores do que as letras comuns.</span><span class="sxs-lookup"><span data-stu-id="b3302-153">Large letters are two times higher than regular letters.</span></span> <span data-ttu-id="b3302-154">Portanto, o uso de letras grandes pode levar à sobreposição de texto no recibo.</span><span class="sxs-lookup"><span data-stu-id="b3302-154">Therefore, using large letters may lead to overlapping text in the receipt.</span></span>
    - <span data-ttu-id="b3302-155">**Excluir** – Clique neste botão para remover o componente selecionado do layout do formulário.</span><span class="sxs-lookup"><span data-stu-id="b3302-155">**Delete** – Click this button to remove the selected part from the form layout.</span></span>

## <a name="assign-receipt-profiles"></a><span data-ttu-id="b3302-156">Atribuir perfis de recibo</span><span class="sxs-lookup"><span data-stu-id="b3302-156">Assign receipt profiles</span></span>

<span data-ttu-id="b3302-157">Os perfis de recibo são atribuídos diretamente às impressoras por meio do perfil de hardware.</span><span class="sxs-lookup"><span data-stu-id="b3302-157">Receipt profiles are assigned directly to printers through the hardware profile.</span></span>

1. <span data-ttu-id="b3302-158">Abra o perfil de hardware clicando em **Retail e Commerce** &gt; **Configuração de canal** &gt;**Configuração do PDV** &gt; **Perfis de PDV** &gt; **Perfil de hardware**.</span><span class="sxs-lookup"><span data-stu-id="b3302-158">Open the hardware profile by clicking **Retail and Commerce** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profiles** &gt; **Hardware profile**.</span></span>
2. <span data-ttu-id="b3302-159">Selecione a impressora e, no campo **Perfil de recibo**, atribua o perfil de recibo a ser usado no registro</span><span class="sxs-lookup"><span data-stu-id="b3302-159">Select the printer, and then, in the **Receipt profile** field, assign the receipt profile to use on the register.</span></span>

> [!NOTE]
> <span data-ttu-id="b3302-160">Se duas impressoras forem usadas, uma delas poderá ser usada para imprimir recibos térmicos padrão de 40 colunas.</span><span class="sxs-lookup"><span data-stu-id="b3302-160">If two printers are used, one printer can be used to print standard 40-column thermal receipts.</span></span> <span data-ttu-id="b3302-161">A segunda normalmente é usada para imprimir tipos de recibo de página inteira que requerem mais informações.</span><span class="sxs-lookup"><span data-stu-id="b3302-161">The second printer is typically used to print full-page receipt types that require more information.</span></span> <span data-ttu-id="b3302-162">Esses tipos de recibo incluem recibos de ordens de clientes e faturas de clientes.</span><span class="sxs-lookup"><span data-stu-id="b3302-162">These receipt types include customer order receipts and customer invoices.</span></span>