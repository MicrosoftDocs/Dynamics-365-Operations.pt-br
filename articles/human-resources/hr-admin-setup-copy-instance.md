---
title: Copiar uma instância
description: ''
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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008044"
---
# <a name="copy-an-instance"></a><span data-ttu-id="ab7a8-102">Copiar uma instância</span><span class="sxs-lookup"><span data-stu-id="ab7a8-102">Copy an instance</span></span>

<span data-ttu-id="ab7a8-103">É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-103">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="ab7a8-104">Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-104">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="ab7a8-105">Para copiar uma instância, é necessário garantir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ab7a8-105">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="ab7a8-106">A instância de Human Resources que deseja substituir deve ser um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-106">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="ab7a8-107">Os ambientes dos quais você está copiando e devem estar na mesma região.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-107">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="ab7a8-108">Não é possível copiar entre regiões.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-108">You can't copy across regions.</span></span>

- <span data-ttu-id="ab7a8-109">Você deve ser um administrador no ambiente de destino para que possa fazer login nele depois de copiar a instância.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-109">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="ab7a8-110">Ao copiar o banco de dados de Human Resources, você não copia os elementos (aplicativos ou dados) contidos em um ambiente do Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-110">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="ab7a8-111">Para obter informações sobre como copiar elementos em um ambiente do PowerApps, consulte [Copiar um ambiente](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="ab7a8-111">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="ab7a8-112">A ambiente do PowerApps que deseja substituir deve ser um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-112">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="ab7a8-113">Você deve ser um administrador de locatário global para alterar um ambiente de produção do PowerApps para um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-113">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="ab7a8-114">Para obter mais informações sobre como alterar um ambiente do PowerApps, consulte [Alternar uma instância](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="ab7a8-114">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="ab7a8-115">Efeitos da cópia de um banco de dados do Human Resources</span><span class="sxs-lookup"><span data-stu-id="ab7a8-115">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="ab7a8-116">Os seguintes eventos ocorrem ao copiar um banco de dados do Human Resources:</span><span class="sxs-lookup"><span data-stu-id="ab7a8-116">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="ab7a8-117">O processo de cópia apaga o banco de dados existente no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-117">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="ab7a8-118">Depois que o processo de cópia for concluído, não será possível recuperar o banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-118">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="ab7a8-119">O ambiente de destino não estará disponível até que o processo de cópia seja concluído.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-119">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="ab7a8-120">Os documentos do armazenamento em Microsoft Azure Blob não são copiados de um ambiente para outro.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-120">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="ab7a8-121">Portanto, quaisquer documentos e modelos anexados não serão copiados e permanecerão no ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-121">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="ab7a8-122">Todos usuários, exceto o usuário Administrador e outras contas de usuário de serviço internas estarão indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-122">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="ab7a8-123">Portanto, o usuário administrador pode excluir ou ofuscar dados antes que outros usuários tenham permissão de volta para o sistema.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-123">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="ab7a8-124">O usuário administrador deve fazer as alterações de configuração necessárias, como reconectar empresas de integração a serviços ou URLs específicos.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-124">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="ab7a8-125">Copiar o banco de dados do Human Resources</span><span class="sxs-lookup"><span data-stu-id="ab7a8-125">Copy the Human Resources database</span></span>

<span data-ttu-id="ab7a8-126">Para concluir essa tarefa, primeiro copie uma instância e efetue login na central de administração do Microsoft Power Platform para copiar seu ambiente do PowerApps.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-126">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="ab7a8-127">Quando você copia uma instância, o banco de dados é apagado na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-127">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="ab7a8-128">A instância de destino não está disponível durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-128">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="ab7a8-129">Faça login nas LCS e selecione o projeto LCS que contém a instância que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-129">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="ab7a8-130">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-130">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="ab7a8-131">Selecione a instância a ser copiada e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-131">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="ab7a8-132">No painel de tarefas **Copiar uma instância**, selecione a instância a ser substituída e, em seguida, selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-132">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="ab7a8-133">Aguarde o valor do campo **Copiar status** ser atualizado para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-133">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="ab7a8-134">Selecione a instância a ser substituída</span><span class="sxs-lookup"><span data-stu-id="ab7a8-134">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="ab7a8-135">Selecione **Power Platform**, e entre na central de administração do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-135">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="ab7a8-136">Selecione Power Platform</span><span class="sxs-lookup"><span data-stu-id="ab7a8-136">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="ab7a8-137">Selecione o ambiente do PowerApps a ser copiada e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-137">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="ab7a8-138">Quando o processo de cópia for concluído, efetue login na instância de destino e habilite a integração do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-138">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="ab7a8-139">Para saber mais informações e instruções, consulte [Configurar a integração do Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="ab7a8-139">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="ab7a8-140">Elementos de dados e status</span><span class="sxs-lookup"><span data-stu-id="ab7a8-140">Data elements and statuses</span></span>

<span data-ttu-id="ab7a8-141">Os seguintes elementos de dados não são copiados quando você copia uma instância de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="ab7a8-141">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="ab7a8-142">Endereços de email na tabela **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-142">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="ab7a8-143">O histórico do trabalho em lotes nas tabelas **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-143">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="ab7a8-144">A senha SMTP (Simple Mail Transfer Protocol) na tabela **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-144">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="ab7a8-145">O servidor de retransmissão SMTP na tabela **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-145">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="ab7a8-146">Configurações de gerenciamento de impressão nas tabelas **PrintMgmtSettings** e **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-146">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="ab7a8-147">Registros específicos de ambiente nas tabelas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup** tables</span><span class="sxs-lookup"><span data-stu-id="ab7a8-147">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="ab7a8-148">Os anexos de documento na tabela DocuValue.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-148">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="ab7a8-149">Esses anexos incluem todos modelos do Microsoft Office substituídos no ambiente de origem</span><span class="sxs-lookup"><span data-stu-id="ab7a8-149">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="ab7a8-150">A sequência de conexão na tabela **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="ab7a8-150">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="ab7a8-151">Alguns desses elementos não são copiados porque são específicos do ambiente.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-151">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="ab7a8-152">Exemplos incluem registros **BatchServerConfig** e **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-152">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="ab7a8-153">Outros elementos não são copiados devido ao volume de tíquetes de suporte.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-153">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="ab7a8-154">Por exemplo, os emails duplicados podem ser enviados porque o SMTP ainda está habilitado no ambiente de teste de aceitação do usuário (Sandbox), as mensagens de integração inválidas podem ser enviadas porque os trabalhos em lotes ainda estão habilitados e os usuários podem estar habilitados para que os administradores possam realizar ações de limpeza após a renovação.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-154">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="ab7a8-155">Além disso, os seguintes status são alterados ao copiar uma instância:</span><span class="sxs-lookup"><span data-stu-id="ab7a8-155">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="ab7a8-156">Todos os usuários, exceto o administrador, estão definidos como **Desabilitados**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-156">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="ab7a8-157">Todos os trabalhos em lotes, exceto para alguns trabalhos do sistema, são definidos como **Retenção**.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-157">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="ab7a8-158">Administrador do ambiente</span><span class="sxs-lookup"><span data-stu-id="ab7a8-158">Environment admin</span></span>

<span data-ttu-id="ab7a8-159">Todos os usuários no ambiente de área de proteção de destino, incluindo os administradores, são substituídos pelos usuários do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-159">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="ab7a8-160">Antes de copiar uma instância, verifique se você é um administrador no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-160">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="ab7a8-161">Se não estiver, não será possível fazer logon no ambiente de área de proteção de destino após a conclusão da cópia.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-161">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="ab7a8-162">Todos os usuários que não são administradores no ambiente de área de proteção de destino são desabilitados para evitar a entrada indesejada no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-162">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="ab7a8-163">Os administradores podem habilitar novamente os usuários, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ab7a8-163">Administrators can reenable users if needed.</span></span>
