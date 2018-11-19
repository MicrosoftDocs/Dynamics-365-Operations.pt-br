---
title: "Novidades ou alterações no Dynamics 365 for Talent Core HR (31 de outubro de 2018)"
description: "Este tópico descreve os recursos novos ou alterados na versão atual do Core HR do Microsoft Dynamics 365 for Talent."
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c5acd09e25ecd5fefa637342f83d0ee0f1891402
ms.contentlocale: pt-br
ms.lasthandoff: 11/01/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a><span data-ttu-id="25c75-103">Novidades ou alterações no Dynamics 365 for Talent Core HR (31 de outubro de 2018)</span><span class="sxs-lookup"><span data-stu-id="25c75-103">What's new or changed in Dynamics 365 for Talent Core HR (October 31, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="25c75-104">**Compilação 8.1.2031**</span><span class="sxs-lookup"><span data-stu-id="25c75-104">**Build 8.1.2031**</span></span>

<span data-ttu-id="25c75-105">Este tópico descreve os recursos novos ou alterados no Core HR.</span><span class="sxs-lookup"><span data-stu-id="25c75-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="create-links-from-talent-to-finance-and-operations"></a><span data-ttu-id="25c75-106">Cria links do Talent ao Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="25c75-106">Create links from Talent to Finance and Operations</span></span>
<span data-ttu-id="25c75-107">Essa nova funcionalidade de navegação permite que você vincule o Talent ao Finance and Operations, oferecendo a você navegação direta nas páginas de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-107">This new navigation functionality allows you to link from Talent to Finance and Operations, giving you direct navigation into Finance and Operations pages.</span></span> <span data-ttu-id="25c75-108">Quando links são configurados, você pode especificar o nome e o grupo do link, onde o link deve aparecer no Talent, e a página de destino a ser aberta dentro de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-108">When links are configured, you can specify the name and group of the link, where the link should surface in Talent, and the target page to be opened within Finance and Operations.</span></span>

#### <a name="coming-soon"></a><span data-ttu-id="25c75-109">Em breve</span><span class="sxs-lookup"><span data-stu-id="25c75-109">Coming soon</span></span>
<span data-ttu-id="25c75-110">O contexto de campo será adicionado no futuro para permitir a navegação direta aos registros correspondentes no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-110">Field context will be added in the future to allow for direct navigation to corresponding records in Finance and Operations.</span></span> <span data-ttu-id="25c75-111">Por exemplo, você pode usar **Link para campo** para fornecer o contexto para navegar diretamente a um funcionário ou a uma posição específica no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-111">For example, you can use **Link to field** to provide the context to navigate directly to a specific employee or position in Finance and Operations.</span></span>

### <a name="configure-target-systems"></a><span data-ttu-id="25c75-112">Configurar sistemas de destino</span><span class="sxs-lookup"><span data-stu-id="25c75-112">Configure target systems</span></span>

<span data-ttu-id="25c75-113">No Talent, administradores do sistema podem definir links que serão exibidos por meio do espaço de trabalho do Sistema de administração.</span><span class="sxs-lookup"><span data-stu-id="25c75-113">In Talent, system administrators can define links that will be surfaced through the System Administration workspace.</span></span> <span data-ttu-id="25c75-114">Parte da configuração são os ambientes do Finance and Operations onde gostaria de navegar para como "destino" do link.</span><span class="sxs-lookup"><span data-stu-id="25c75-114">Part of the configuration is the Finance and Operations environments that you would like to navigate to as the "target" of the link.</span></span> <span data-ttu-id="25c75-115">Você faz isso dando ao sistema de destino um nome e fornecendo a URL de ambiente do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-115">You do this by giving the target system a name and providing the URL of the Finance and Operations environment.</span></span> <span data-ttu-id="25c75-116">Aqui está um exemplo de uma URL de Finance and Operations que você fornece: https://devax00124aos.cloud.test.dynamics.com/.</span><span class="sxs-lookup"><span data-stu-id="25c75-116">Here is an example of a Finance and Operations URL that you would provide: https://devax00124aos.cloud.test.dynamics.com/.</span></span> <span data-ttu-id="25c75-117">Após configurar sistemas de destino, você pode definir os links.</span><span class="sxs-lookup"><span data-stu-id="25c75-117">After you have configured your target systems,  you can define your links.</span></span>

### <a name="configure-links"></a><span data-ttu-id="25c75-118">Configurar links</span><span class="sxs-lookup"><span data-stu-id="25c75-118">Configure links</span></span>

<span data-ttu-id="25c75-119">Cada link criado terá as seguintes informações definidas.</span><span class="sxs-lookup"><span data-stu-id="25c75-119">Each link that is created will have the following information defined.</span></span>

- <span data-ttu-id="25c75-120">Link - nome do link, usado somente para a identificação.</span><span class="sxs-lookup"><span data-stu-id="25c75-120">Link - Name of the link, used for identification only.</span></span>

- <span data-ttu-id="25c75-121">Habilitar esse link - Defina para **Sim** para exibir o link para os usuários do Talent.</span><span class="sxs-lookup"><span data-stu-id="25c75-121">Enable this Link - Set to **Yes** if you want to display the link to users of Talent.</span></span>

- <span data-ttu-id="25c75-122">Nome para exibição - Defina o nome que parecerá como um link para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-122">Display name - Define the name that will appear as a link to Finance and Operations.</span></span> <span data-ttu-id="25c75-123">Esses dados não são traduzidos no momento.</span><span class="sxs-lookup"><span data-stu-id="25c75-123">This data is currently is not translated.</span></span>

- <span data-ttu-id="25c75-124">Link de superfície no formulário - Escolha qual página gostaria de exibir o link.</span><span class="sxs-lookup"><span data-stu-id="25c75-124">Surface link on form - Choose which page you would like to display the link on.</span></span>

- <span data-ttu-id="25c75-125">Grupo - Grupos não são necessários, mas se quiser organizar seus links usando grupos, selecione um grupo existente ou crie um novo usando o campo **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="25c75-125">Group - Groups are not required, but if you want to organize your links using groups, select an existing group or create a new one using the **Group** field.</span></span>

- <span data-ttu-id="25c75-126">Sistema de destino - Selecione o sistema de destino criado usando a opção **Configurar o sistema de destino**.</span><span class="sxs-lookup"><span data-stu-id="25c75-126">Target system - Select the target system that was created using the **Configure target system** option.</span></span> <span data-ttu-id="25c75-127">Este será o ambiente de Finance and Operations que será usado para navegar pelo link.</span><span class="sxs-lookup"><span data-stu-id="25c75-127">This will be the Finance and Operations environment that will be used when navigating by using the link.</span></span>

- <span data-ttu-id="25c75-128">Use a empresa atual de usuário - Selecione **Sim** caso você queira usar o contexto da empresa atual do usuário para navegar para Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-128">Use user's current Company - Select **Yes** if you would like to use the User's current company context when navigating to Finance and Operations.</span></span> <span data-ttu-id="25c75-129">Se **Não** for selecionado, você poderá selecionar a empresa que deverá ser usada.</span><span class="sxs-lookup"><span data-stu-id="25c75-129">If **No** is selected, then you can select the company that should be used.</span></span>

- <span data-ttu-id="25c75-130">Item de menu de destino - Digite o item de menu de Finance and Operations que o link deve usar ao navegar.</span><span class="sxs-lookup"><span data-stu-id="25c75-130">Target menu item - Enter the menu item from Finance and Operation that the link should use when navigating.</span></span> <span data-ttu-id="25c75-131">Itens de menu onde você pode navegar diretamente estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25c75-131">Menu items that you can directly navigate to are available.</span></span> <span data-ttu-id="25c75-132">Para localizar o item de menu, abra Finance and Operations e a página que é o destino da navegação.</span><span class="sxs-lookup"><span data-stu-id="25c75-132">To find the menu item required, open Finance and Operations and open the page that is the target of the navigation.</span></span> <span data-ttu-id="25c75-133">Copie o item de menu da URL.</span><span class="sxs-lookup"><span data-stu-id="25c75-133">Copy the menu item from the URL.</span></span> <span data-ttu-id="25c75-134">Por exemplo, se desejar que o link execute a lista de funcionários em Finance and Operations, insira o valor que surge após "&mi" na URL.</span><span class="sxs-lookup"><span data-stu-id="25c75-134">For example, if you want the link to take you to the employee list in Finance and Operations, enter the value that appears after the "&mi" in the URL.</span></span> <span data-ttu-id="25c75-135">https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees.</span><span class="sxs-lookup"><span data-stu-id="25c75-135">https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees.</span></span> <span data-ttu-id="25c75-136">O item de menu para navegar para a página de listagem de funcionário neste exemplo é: HcmWorkerListPage_Employees.</span><span class="sxs-lookup"><span data-stu-id="25c75-136">The menu item to navigate to the employee list page in this example is: HcmWorkerListPage_Employees.</span></span>

- <span data-ttu-id="25c75-137">Link para fonte de dados - selecione a fonte de dados com o qual o link está fazendo referência.</span><span class="sxs-lookup"><span data-stu-id="25c75-137">Link to data source - Select the source of data that the link is referencing.</span></span> <span data-ttu-id="25c75-138">As origens mais comuns como **Trabalhador** e **Posição** estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="25c75-138">The most common sources like **Worker** and **Position** are available.</span></span>

- <span data-ttu-id="25c75-139">Link para campo (Em breve) Este campo permitirá a navegação direta de um único registro em talento a um único registro em Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-139">Link to field - (Coming soon) This field selection will allow for direct navigation from a single record in Talent to a single record in Finance and Operations.</span></span>

### <a name="access-to-links"></a><span data-ttu-id="25c75-140">Acesso a links</span><span class="sxs-lookup"><span data-stu-id="25c75-140">Access to links</span></span>

<span data-ttu-id="25c75-141">Os administradores de sistema verão links recém-criados em páginas definidas se a opção **Habilitar esse link** estiver definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="25c75-141">System administrators will see the newly created links on the defined pages even if the **Enable this link** option is set to **No**.</span></span> <span data-ttu-id="25c75-142">Isso pode ser usado antes testando links para aparecerem para outros funcionários.</span><span class="sxs-lookup"><span data-stu-id="25c75-142">This can be used for testing links prior to surfacing them to other employees.</span></span> <span data-ttu-id="25c75-143">Todas funções restantes considerarão links configurados somente depois que a opção **Habilitar esse link** estiver definida como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="25c75-143">All other roles will only see the configured links after the **Enable this link** option is set to **Yes**.</span></span> <span data-ttu-id="25c75-144">Os funcionários que têm acesso a páginas dos links terão acesso aos links.</span><span class="sxs-lookup"><span data-stu-id="25c75-144">Employees who have access to the pages in which the links are surfaced will have access to the links.</span></span>

<span data-ttu-id="25c75-145">Os usuários também podem ter direitos de segurança em Finance and Operations definidos para acessar as páginas em Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="25c75-145">Users can also have security rights within Finance and Operations defined to access the pages in Finance and Operations.</span></span> <span data-ttu-id="25c75-146">Se não tiverem, uma caixa de diálogo de segurança será exibida usando o link.</span><span class="sxs-lookup"><span data-stu-id="25c75-146">If they don't, a security dialog box will be displayed when using the link.</span></span>


## <a name="other-changesfixes"></a><span data-ttu-id="25c75-147">Outras alterações/correções</span><span class="sxs-lookup"><span data-stu-id="25c75-147">Other changes/fixes</span></span>

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a><span data-ttu-id="25c75-148">Posições com uma data inicial futura não podem ser atribuídas a um novo funcionário</span><span class="sxs-lookup"><span data-stu-id="25c75-148">Positions with a future start date cannot be assigned to a new employee</span></span>

<span data-ttu-id="25c75-149">As alterações foram feitas para permitir atribuições de funcionário a posições datadas futuras.</span><span class="sxs-lookup"><span data-stu-id="25c75-149">Changes have been made to allow employee assignments to future-dated positions.</span></span> <span data-ttu-id="25c75-150">Posições que têm datas iniciais no futuro podem ser selecionadas e a atribuição de funcionário será feita ao salvar ou ao concluir o fluxo de trabalho (se o fluxo de trabalho for habilitado).</span><span class="sxs-lookup"><span data-stu-id="25c75-150">Positions that have start dates in the future can be selected and the employee assignment will be made upon save or completion of the workflow (if the workflow is enabled).</span></span>

### <a name="new-employee-cannot-be-assigned-existing-position"></a><span data-ttu-id="25c75-151">O novo funcionário não pode ser atribuído à posição existente</span><span class="sxs-lookup"><span data-stu-id="25c75-151">New employee cannot be assigned existing position</span></span>

<span data-ttu-id="25c75-152">As alterações foram feitas para que a nova atribuição de funcionários possa ser atribuída a cargos existentes.</span><span class="sxs-lookup"><span data-stu-id="25c75-152">Changes have been made so new employee assignment can now be assigned to existing positions.</span></span>

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a><span data-ttu-id="25c75-153">A data de tempo de trabalho/local de escritório desaparece quando a data de início do emprego está no passado e o registro está salvo.</span><span class="sxs-lookup"><span data-stu-id="25c75-153">Seniority date/Office location disappears when the employment start date is in the past and the record is saved</span></span>

<span data-ttu-id="25c75-154">As alterações foram feitas para corrigir a visibilidade de **Data de tempo de trabalho** e **Localização do escritório** quando salvar para funcionários passados.</span><span class="sxs-lookup"><span data-stu-id="25c75-154">Changes have been made to correct the visibilty of the **Senority date** and **Office location** when saving changes for past employees.</span></span>

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a><span data-ttu-id="25c75-155">Não pode inserir dados para empregos futuros datados na página de trabalho</span><span class="sxs-lookup"><span data-stu-id="25c75-155">Can't enter data for future-dated employments on the worker page</span></span>

<span data-ttu-id="25c75-156">Os dados de emprego para empregos de datas futuras foram desativados na página principal do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="25c75-156">Employment data for future-dated employments has been disabled on the main worker page.</span></span> <span data-ttu-id="25c75-157">Os dados de emprego podem ser inseridos em páginas do **Gerente da data**.</span><span class="sxs-lookup"><span data-stu-id="25c75-157">Employment data can be entered through the **Date Manager** pages.</span></span> <span data-ttu-id="25c75-158">Alterações adicionais serão feitas em versões futuras para habilitar inserção de dados de emprego diretamente durante o processo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="25c75-158">Additional changes will be made in future releases to enable entering employment data directly during the workflow process.</span></span>

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a><span data-ttu-id="25c75-159">Adicionar ValidFrom e ValidTo to HcmPersonalContactPersonEntity</span><span class="sxs-lookup"><span data-stu-id="25c75-159">Add ValidFrom and ValidTo to HcmPersonalContactPersonEntity</span></span>

<span data-ttu-id="25c75-160">A entidade de Data Management Framework (DMF) HcmPersonalContactPersonEntity foi atualizada para incluir datas de "válido de" e "válido até" para habilitar certos cenários de integração de benefício.</span><span class="sxs-lookup"><span data-stu-id="25c75-160">The Data Management Framework (DMF) entity HcmPersonalContactPersonEntity has been updated to include "valid from" and "valid to" dates to enable certain benefit integration scenarios.</span></span> 

## <a name="known-issue"></a><span data-ttu-id="25c75-161">Problema conhecido</span><span class="sxs-lookup"><span data-stu-id="25c75-161">Known issue</span></span>
- <span data-ttu-id="25c75-162">**Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos.</span><span class="sxs-lookup"><span data-stu-id="25c75-162">**Issue**: When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out.</span></span> 
- <span data-ttu-id="25c75-163">**Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas.</span><span class="sxs-lookup"><span data-stu-id="25c75-163">**Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="25c75-164">Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="25c75-164">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="25c75-165">(Esse problema será corrigido na próxima atualização de plataforma.)</span><span class="sxs-lookup"><span data-stu-id="25c75-165">(This issue will be fixed in the next platform update.)</span></span>

