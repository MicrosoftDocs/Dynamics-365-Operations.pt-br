---
title: Rounds de manutenção
description: Este tópico explica os rounds de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a0ac4820d2efa37387382c2890e3ddc7dbc0878b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875501"
---
# <a name="maintenance-rounds"></a><span data-ttu-id="de806-103">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="de806-103">Maintenance rounds</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="de806-104">No **Gerenciamento de Ativos**, você pode criar rounds de manutenção para vários ativos nos quais você precisa executar uma tarefa semelhante em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="de806-104">In **Asset Management**, you can create maintenance rounds for various assets, on which you need to carry out a similar task at regular intervals.</span></span> <span data-ttu-id="de806-105">Por exemplo, trabalhos de lubrificação ou trabalhos de inspeção de segurança que precisam ser realizados em várias máquinas dentro dos mesmos intervalos.</span><span class="sxs-lookup"><span data-stu-id="de806-105">For example, lubrication jobs or safety inspection jobs that need to be carried out on a number of machines within the same intervals.</span></span> <span data-ttu-id="de806-106">A primeira etapa é criar um round de manutenção, incluindo os ativos que exigem o mesmo trabalho do formulário de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-106">First step is to create a maintenance round, including assets that require the same form of maintenance job.</span></span> <span data-ttu-id="de806-107">Em seguida, você agenda os rounds de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-107">Next, you schedule the maintenance rounds.</span></span> <span data-ttu-id="de806-108">Quando tiver concluído o agendamento de rounds de manutenção, você verá todos os registros do trabalho referentes ao round em **Todos agendamentos de manutenção** e nas **Linhas de agendamento de manutenção abertas**.</span><span class="sxs-lookup"><span data-stu-id="de806-108">When you have completed the maintenance rounds schedule, you can see all the job records relating to the round in the **All maintenance schedule** and **Open maintenance schedule lines**.</span></span>

>[!NOTE]
><span data-ttu-id="de806-109">Os rounds de manutenção também podem ser configurados em locais funcionais a serem concluídos nos ativos instalados no local funcional no momento da criação da ordem de serviço com base no round.</span><span class="sxs-lookup"><span data-stu-id="de806-109">Maintenance rounds can also be set up on functional locations to be completed on the assets installed on the functional location at the time of creation of the round-based work order.</span></span> <span data-ttu-id="de806-110">Consulte [Criar locais funcionais](../functional-locations/create-functional-locations.md) para obter mais informações sobre a configuração de rounds de manutenção nos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="de806-110">Refer to [Create functional locations](../functional-locations/create-functional-locations.md) for more information on the setup of maintenance rounds on functional locations.</span></span>

## <a name="set-up-a-maintenance-round"></a><span data-ttu-id="de806-111">Configurar um round de manutenção</span><span class="sxs-lookup"><span data-stu-id="de806-111">Set up a maintenance round</span></span>

1. <span data-ttu-id="de806-112">Clique em **Gerenciamento de ativos** > **Configuração** > **Manutenção preventiva** > **Rounds de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-112">Click **Asset management** > **Setup** > **Preventive maintenance** > **Maintenance rounds**.</span></span>

2. <span data-ttu-id="de806-113">Clique em **Novo** para criar um novo round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-113">Click **New** to create a new maintenance round.</span></span>

3. <span data-ttu-id="de806-114">Insira uma ID no campo **Round de manutenção** e um nome para o round de manutenção no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="de806-114">Insert and ID in the **Maintenance round** field, and a name for the maintenance round in the **Name** field.</span></span>

4. <span data-ttu-id="de806-115">Selecione uma data de início para o round no campo **Data de início**.</span><span class="sxs-lookup"><span data-stu-id="de806-115">Select a start date for the round in the **Start date** field.</span></span>

5. <span data-ttu-id="de806-116">Nos campos **Concluir em dias** e **Concluir em horas** você pode inserir a data de término esperada em dias ou horas.</span><span class="sxs-lookup"><span data-stu-id="de806-116">In the **Finish within days** and **Finish within hours** fields, you can insert expected end date in days or hours.</span></span> <span data-ttu-id="de806-117">A data de término esperada é calculada em relação à data de início, calculada quando linhas de agendamento de manutenção forem criadas.</span><span class="sxs-lookup"><span data-stu-id="de806-117">The expected end date is calculated relative to the start date, which is calculated when maintenance schedule lines are created.</span></span> <span data-ttu-id="de806-118">Por exemplo, você pode inserir "7" no campo **Concluir em dias** para indicar que o trabalho relacionado deve ser concluído dentro de uma semana da data de início.</span><span class="sxs-lookup"><span data-stu-id="de806-118">For example, you can insert "7" in the **Finish within days** field to indicate that the related job should be completed within a week from the start date.</span></span>

6. <span data-ttu-id="de806-119">Selecione "Sim" no botão de alternância **Criação automática** se as ordens de serviço tiverem que ser criadas automaticamente das linhas de agendamento de manutenção que são criados deste round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-119">Select "Yes" on the **Auto create** toggle button if work orders should automatically be created from maintenance schedule lines that are created from this maintenance round.</span></span>

7. <span data-ttu-id="de806-120">No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço a ser usado em ordens de serviço criadas deste round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-120">In the **Work order type** field, select the work order type to be used on work orders created from this maintenance round.</span></span>

8. <span data-ttu-id="de806-121">No campo **Nível de serviço**, selecione o nível de serviço da ordem de serviço a ser usado nas ordens de serviço criados deste round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-121">In the **Service level** field, select the work order service level to be used on work orders created from this maintenance round.</span></span>

9. <span data-ttu-id="de806-122">Na Guia Rápida **Linhas do ativo**, clique em **Adicionar** para adicionar um ativo ao round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-122">On the **Asset lines** FastTab, click **Add** to add an asset to the maintenance round.</span></span>

10. <span data-ttu-id="de806-123">Um número da linha é automaticamente inserido no campo **Número da linha** para indicar a sequência de ativos no round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-123">A line number is automatically inserted in the **Line number** field to indicate the sequence of the assets in maintenance round.</span></span>

11. <span data-ttu-id="de806-124">Selecione o ativo no campo **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="de806-124">Select the asset in the **Asset** field.</span></span>

12. <span data-ttu-id="de806-125">Selecione o tipo de trabalho de manutenção do ativo no campo **Tipo de trabalho de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-125">Select the maintenance job type for the asset in the **Maintenance job type** field.</span></span>

13. <span data-ttu-id="de806-126">Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício** relacionados ao tipo de trabalho de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-126">If required, select **Maintenance job typ variant** and **Trade** related to the maintenance job type.</span></span>

14. <span data-ttu-id="de806-127">Selecione a recorrência (dia, semana, etc) no campo **Tipo de período**.</span><span class="sxs-lookup"><span data-stu-id="de806-127">Select the recurrence (day, week, etc.) in the **Period type** field.</span></span>

15. <span data-ttu-id="de806-128">No campo **Frequência do período**, insira o número de recorrências para o round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-128">In the **Period frequency** field, insert the number of recurrences for the maintenance round.</span></span> <span data-ttu-id="de806-129">Exemplo: se você selecionar "Dia" no campo **Tipo de período** e você inserir o número "7" neste campo, as novas linhas do round de manutenção são criadas durante o agendamento de manutenção preventiva uma vez por semana.</span><span class="sxs-lookup"><span data-stu-id="de806-129">Example: If you have selected "Day" in the **Period type** field, and you insert the number "7" in this field, new maintenance round lines are created during preventive maintenance scheduling once a week.</span></span>

16. <span data-ttu-id="de806-130">Selecione uma data de início do ativo a ser incluído no round de manutenção no campo **Data de início**.</span><span class="sxs-lookup"><span data-stu-id="de806-130">Select a start date for the asset to be included in the maintenance round in the **Start date** field.</span></span> <span data-ttu-id="de806-131">Esta data pode ser diferente da data de início definida no round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-131">This date may differ from the start date set on the maintenance round.</span></span>

17. <span data-ttu-id="de806-132">Repita as etapas de 9 a 16 para adicionar mais ativos ao round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-132">Repeat steps 9-16 to add more assets to the maintenance round.</span></span>

18. <span data-ttu-id="de806-133">Na Guia Rápida **Linhas do local funcional** clique em **Adicionar** para adicionar um local funcional ao round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-133">On the **Functional location lines** FastTab, click **Add** to add a functional location to the maintenance round.</span></span> <span data-ttu-id="de806-134">Consulte a descrição dos campos relacionados acima.</span><span class="sxs-lookup"><span data-stu-id="de806-134">Refer to the description of the related fields above.</span></span> <span data-ttu-id="de806-135">Os mesmos campos estão disponíveis para criar uma linha do ativo, mas você também pode selecionar **Fabricante** e **Modelo** para um local funcional, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="de806-135">The same fields are available as for creating an asset line, but you can also select **Manufacturer** and **Model** for a functional location, if required.</span></span> <span data-ttu-id="de806-136">Se você selecionar apenas um local funcional em uma linha, mas não fizer seleções em **Tipo de ativo**, **Fabricante**, **Modelo**, **Tipo de trabalho de manutenção**, **Grade do tipo de trabalho de manutenção** e **Ofício**, todos os ativos relacionados a esse local funcional no momento do agendamento de manutenção serão incluídos no round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-136">If you only select a functional location on a line, but make no selections in **Asset type**, **Manufacturer**, **Model**, **Maintenance job type**, **Maintenance job type variant** and **Trade**, all assets related to that functional location at the time of maintenance scheduling will be included in the maintenance round.</span></span>

19. <span data-ttu-id="de806-137">Na Guia Rápida **Grupos**, clique em **Adicionar** para selecionar um grupo de ordem de serviço a ser incluído no round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-137">On the **Pools** FastTab, click **Add** to select a work order pool to be included in the maintenance round.</span></span> <span data-ttu-id="de806-138">Vários grupos de ordens de serviço podem ser conectados a um round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-138">Several work order pools can be connected to one maintenance round.</span></span>

20. <span data-ttu-id="de806-139">Salve sua configuração.</span><span class="sxs-lookup"><span data-stu-id="de806-139">Save your setup.</span></span>

>[!NOTE]
><span data-ttu-id="de806-140">Os campos **Ativos** e **Linhas** localizados no grupo **Detalhes** na Guia Rápida **Cabeçalho** mostram o número total de ativos e linhas relacionados ao round de manutenção selecionado.</span><span class="sxs-lookup"><span data-stu-id="de806-140">The **Assets** and **Lines** fields located in the **Details** group on the **Header** FastTab show the total number of assets and lines related to the selected maintenance round.</span></span>

![Figura 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a><span data-ttu-id="de806-142">Agendar rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="de806-142">Schedule maintenance rounds</span></span>

<span data-ttu-id="de806-143">Ao configurar um round de manutenção, você executa um trabalho de agendamento para agendar todos os trabalhos relacionados ao round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-143">When you have set up a maintenance round, you run a schedule job to schedule all the jobs related to the maintenance round.</span></span>

1. <span data-ttu-id="de806-144">Clique no botão **Gerenciamento de ativos** > **Periódico** > **Manutenção preventiva** > **Agendar rounds de manutenção** ou **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção** > selecione linha de agendamento de manutenção na lista > **Rounds de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-144">Click **Asset management** > **Periodic** > **Preventive maintenance** > **Schedule maintenance rounds**, or **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** > select maintenance schedule line in the list > **Maintenance rounds** button.</span></span>

2. <span data-ttu-id="de806-145">No campo **Período**, selecione o tipo de período a ser usado para o trabalho de agendamento.</span><span class="sxs-lookup"><span data-stu-id="de806-145">In the **Period** field, select the period type to be used for the scheduling job.</span></span>

3. <span data-ttu-id="de806-146">No campo **Frequência de período**, insira o número de períodos a ser incluído no trabalho de agendamento.</span><span class="sxs-lookup"><span data-stu-id="de806-146">In the **Period frequency** field, insert the number of periods to be included in the scheduling job.</span></span> <span data-ttu-id="de806-147">O início do agendamento é a data atual.</span><span class="sxs-lookup"><span data-stu-id="de806-147">The start of the scheduling is the current date.</span></span>

4. <span data-ttu-id="de806-148">Selecione "Sim" no botão de alternância **Criação automática**, se uma ordem de serviço tiver que ser criada automaticamente na base de um round de manutenção.</span><span class="sxs-lookup"><span data-stu-id="de806-148">Select "Yes" on the **Auto create** toggle button if a work order should automatically be created on the basis of a maintenance round.</span></span>

>[!NOTE]
><span data-ttu-id="de806-149">Se este botão de alternância for definido como "Sim" e o botão de alternância **Criação automática** também for definido como "Sim" no round de manutenção no formulário **Rounds de manutenção**, as ordens de serviço serão criadas com base nas linhas do round de manutenção e as linhas de agendamento de manutenção com o status "Ordem de serviço criada" também são criadas.</span><span class="sxs-lookup"><span data-stu-id="de806-149">If this toggle button is set to "Yes", and the **Auto create** toggle button is also set to "Yes" on the maintenance round in **Maintenance rounds** form, work orders are created based on the maintenance round lines, and maintenance schedule lines with status "Work order created" are also created.</span></span> <span data-ttu-id="de806-150">Se apenas um dos botões de alternância **Criação automática** for definido como "Sim", nesta lista suspensa ou nos **Rounds de manutenção**, somente serão criadas linhas de agendamento de manutenção com status "Criado".</span><span class="sxs-lookup"><span data-stu-id="de806-150">If only one of the **Auto create** toggle buttons is set to "Yes", in this drop-down or in **Maintenance rounds**, only maintenance schedule lines are created with status "Created".</span></span> <span data-ttu-id="de806-151">Nesse caso, nenhuma ordem de serviço é criada.</span><span class="sxs-lookup"><span data-stu-id="de806-151">In that case, no work orders are created.</span></span>

5. <span data-ttu-id="de806-152">Se necessário, é possível selecionar rounds específicos ou outra data de início para o trabalho da agenda.</span><span class="sxs-lookup"><span data-stu-id="de806-152">If required, you can select specific rounds or another start date for the schedule job.</span></span> <span data-ttu-id="de806-153">Clique em **Filtro** e adicione os rounds a serem incluídos.</span><span class="sxs-lookup"><span data-stu-id="de806-153">Click **Filter**, and add the rounds to be included.</span></span>

6. <span data-ttu-id="de806-154">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de806-154">Click **OK**.</span></span>

7. <span data-ttu-id="de806-155">Agora você pode ver os trabalhos dos rounds de manutenção no **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-155">You are now able to see the maintenance rounds jobs in **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines**.</span></span> <span data-ttu-id="de806-156">Se os rounds programados forem conectados a um grupo de ordem de serviço, você também poderá ver as linhas de agendamento de manutenção em **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-156">If the scheduled rounds are connected to a work order pool, you also see maintenance schedule lines in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="de806-157">As linhas de agendamento de manutenção criadas a partir de um round têm o tipo de referência "Rounds de manutenção".</span><span class="sxs-lookup"><span data-stu-id="de806-157">Maintenance schedule lines created from a round have the reference type "Maintenance rounds".</span></span>

![Figura 2](media/14-preventive-maintenance.png)

![Figura 3](media/15-preventive-maintenance.png)

- <span data-ttu-id="de806-160">Quando as ordens de trabalho são criadas manualmente nos ativos que serão cobertos por uma garantia do fornecedor, uma caixa de diálogo será exibida para que o usuário fique ciente da garantia.</span><span class="sxs-lookup"><span data-stu-id="de806-160">When work orders are manually created on assets that are covered by a vendor warranty, a dialog box is shown to make the user aware of the warranty.</span></span> <span data-ttu-id="de806-161">A criação da ordem de serviço pode ser cancelada.</span><span class="sxs-lookup"><span data-stu-id="de806-161">The creation of the work order can then be canceled.</span></span> <span data-ttu-id="de806-162">A verificação de uma relação da garantia é omitida para as ordens de serviço que são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="de806-162">The check for a warranty relation is omitted for work orders that are automatically created.</span></span>  
- <span data-ttu-id="de806-163">Você pode configurar um trabalho em lotes na Guia Rápida **Executar em segundo plano** para agendar rounds em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="de806-163">You can set up a batch job on the **Run in the background** FastTab to schedule rounds at regular intervals.</span></span>  
- <span data-ttu-id="de806-164">Se um round for incluído em vários grupos da ordem de serviço (consulte [Grupos da ordem de serviço](../work-orders/work-order-pools.md)), um registro será mostrado para cada grupo em **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="de806-164">If a round is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="de806-165">Isso é feito para otimizar as opções de filtragem para grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="de806-165">This is done to optimize the filtering options for work order pools.</span></span>

