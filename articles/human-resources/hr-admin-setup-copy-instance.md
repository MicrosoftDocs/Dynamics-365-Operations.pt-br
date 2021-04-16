---
title: Copiar uma instância
description: É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6cb8050980b9b54480d09a59379430cd229ff141
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801086"
---
# <a name="copy-an-instance"></a><span data-ttu-id="27648-103">Copiar uma instância</span><span class="sxs-lookup"><span data-stu-id="27648-103">Copy an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="27648-104">É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="27648-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="27648-105">Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado.</span><span class="sxs-lookup"><span data-stu-id="27648-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="27648-106">Para copiar uma instância, lembre-se destas dicas:</span><span class="sxs-lookup"><span data-stu-id="27648-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="27648-107">A instância de Human Resources que deseja substituir deve ser um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="27648-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="27648-108">Os ambientes dos quais você está copiando e para onde serão copiados devem estar na mesma região.</span><span class="sxs-lookup"><span data-stu-id="27648-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="27648-109">Não é possível copiar entre regiões.</span><span class="sxs-lookup"><span data-stu-id="27648-109">You can't copy across regions.</span></span>

- <span data-ttu-id="27648-110">Você deve ser um administrador no ambiente de destino para que possa fazer login nele depois de copiar a instância.</span><span class="sxs-lookup"><span data-stu-id="27648-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="27648-111">Ao copiar o banco de dados de Human Resources, você não copia os elementos (aplicativos ou dados) contidos em um ambiente do Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="27648-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="27648-112">Para obter informações sobre como copiar elementos em um ambiente do Power Apps, consulte [Copiar um ambiente](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="27648-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="27648-113">A ambiente do Power Apps que deseja substituir deve ser um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="27648-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="27648-114">Você deve ser um administrador de locatário global para alterar um ambiente de produção do Power Apps para um ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="27648-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="27648-115">Para obter mais informações sobre como alterar um ambiente do Power Apps, consulte [Alternar uma instância](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="27648-115">For more information about changing a Power Apps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="27648-116">Se você copiar uma instância no ambiente de área restrita e quiser integrar seu ambiente de área restrita com o Dataverse, reaplique campos personalizados a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27648-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span> <span data-ttu-id="27648-117">Consulte [Aplicar campos personalizados ao Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="27648-117">See [Apply custom fields to Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="27648-118">Efeitos da cópia de um banco de dados do Human Resources</span><span class="sxs-lookup"><span data-stu-id="27648-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="27648-119">Os seguintes eventos ocorrem ao copiar um banco de dados do Human Resources:</span><span class="sxs-lookup"><span data-stu-id="27648-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="27648-120">O processo de cópia apaga o banco de dados existente no ambiente de destino.</span><span class="sxs-lookup"><span data-stu-id="27648-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="27648-121">Depois que o processo de cópia for concluído, não será possível recuperar o banco de dados existente.</span><span class="sxs-lookup"><span data-stu-id="27648-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="27648-122">O ambiente de destino não estará disponível até que o processo de cópia seja concluído.</span><span class="sxs-lookup"><span data-stu-id="27648-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="27648-123">Os documentos do armazenamento em Microsoft Azure Blob não são copiados de um ambiente para outro.</span><span class="sxs-lookup"><span data-stu-id="27648-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="27648-124">Como consequência, quaisquer documentos e modelos anexados não serão copiados e permanecerão no ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="27648-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="27648-125">Todos usuários, exceto o usuário Administrador e outras contas de usuário de serviço internas estarão indisponíveis.</span><span class="sxs-lookup"><span data-stu-id="27648-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="27648-126">O usuário administrador pode excluir ou ofuscar dados antes que outros usuários tenham permissão de volta para o sistema.</span><span class="sxs-lookup"><span data-stu-id="27648-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="27648-127">O usuário administrador deve fazer as alterações de configuração necessárias, como reconectar empresas de integração a serviços ou URLs específicos.</span><span class="sxs-lookup"><span data-stu-id="27648-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="27648-128">Copiar o banco de dados do Human Resources</span><span class="sxs-lookup"><span data-stu-id="27648-128">Copy the Human Resources database</span></span>

<span data-ttu-id="27648-129">Para concluir essa tarefa, primeiro copie uma instância e efetue login na central de administração do Microsoft Power Platform para copiar seu ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="27648-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="27648-130">Quando você copia uma instância, o banco de dados é apagado na instância de destino.</span><span class="sxs-lookup"><span data-stu-id="27648-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="27648-131">A instância de destino não está disponível durante esse processo.</span><span class="sxs-lookup"><span data-stu-id="27648-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="27648-132">Faça login nas LCS e selecione o projeto LCS que contém a instância que você deseja copiar.</span><span class="sxs-lookup"><span data-stu-id="27648-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="27648-133">Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="27648-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="27648-134">Selecione a instância a ser copiada e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="27648-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="27648-135">No painel de tarefas **Copiar uma instância**, selecione a instância a ser substituída e, em seguida, selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="27648-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="27648-136">Aguarde o valor do campo **Copiar status** ser atualizado para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="27648-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="27648-137">Selecione a instância a ser substituída</span><span class="sxs-lookup"><span data-stu-id="27648-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="27648-138">Selecione **Power Platform**, e entre na central de administração do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="27648-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="27648-139">Selecione Power Platform</span><span class="sxs-lookup"><span data-stu-id="27648-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="27648-140">Selecione o ambiente do Power Apps a ser copiada e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="27648-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="27648-141">Quando o processo de cópia for concluído, efetue login na instância de destino e habilite a integração do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27648-141">When the copy process is completed, sign in to the target instance, and enable Dataverse integration.</span></span> <span data-ttu-id="27648-142">Para saber mais informações e instruções, consulte [Configurar a integração do Dataverse](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="27648-142">For more information and instructions, see [Configure Dataverse integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="27648-143">Elementos de dados e status</span><span class="sxs-lookup"><span data-stu-id="27648-143">Data elements and statuses</span></span>

<span data-ttu-id="27648-144">Os seguintes elementos de dados não são copiados quando você copia uma instância de Human Resources:</span><span class="sxs-lookup"><span data-stu-id="27648-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="27648-145">Endereços de email na tabela **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="27648-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="27648-146">O histórico do trabalho em lotes nas tabelas **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="27648-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="27648-147">A senha SMTP (Simple Mail Transfer Protocol) na tabela **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="27648-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="27648-148">O servidor de retransmissão SMTP na tabela **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="27648-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="27648-149">Configurações de gerenciamento de impressão nas tabelas **PrintMgmtSettings** e **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="27648-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="27648-150">Registros específicos de ambiente nas tabelas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup** tables</span><span class="sxs-lookup"><span data-stu-id="27648-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="27648-151">Os anexos de documento na tabela DocuValue.</span><span class="sxs-lookup"><span data-stu-id="27648-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="27648-152">Esses anexos incluem todos modelos do Microsoft Office substituídos no ambiente de origem</span><span class="sxs-lookup"><span data-stu-id="27648-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="27648-153">A sequência de conexão na tabela **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="27648-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="27648-154">Alguns desses elementos não são copiados porque são específicos do ambiente.</span><span class="sxs-lookup"><span data-stu-id="27648-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="27648-155">Exemplos incluem registros **BatchServerConfig** e **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="27648-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="27648-156">Outros elementos não são copiados devido ao volume de tíquetes de suporte.</span><span class="sxs-lookup"><span data-stu-id="27648-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="27648-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="27648-157">For example:</span></span>

- <span data-ttu-id="27648-158">Os emails duplicados podem ser enviados porque o SMTP ainda está habilitado no ambiente de teste de aceitação do usuário (área restrita).</span><span class="sxs-lookup"><span data-stu-id="27648-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="27648-159">Mensagens de integração inválidas podem ser enviadas porque os trabalhos em lotes ainda estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="27648-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="27648-160">Os usuários podem ser habilitados para que os administradores possam executar ações de limpeza após a atualização.</span><span class="sxs-lookup"><span data-stu-id="27648-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="27648-161">Além disso, os seguintes status são alterados ao copiar uma instância:</span><span class="sxs-lookup"><span data-stu-id="27648-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="27648-162">Todos os usuários, exceto o administrador, estão definidos como **Desabilitados**.</span><span class="sxs-lookup"><span data-stu-id="27648-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="27648-163">Todos os trabalhos em lotes, exceto para alguns trabalhos do sistema, são definidos como **Retenção**.</span><span class="sxs-lookup"><span data-stu-id="27648-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="27648-164">Administrador do ambiente</span><span class="sxs-lookup"><span data-stu-id="27648-164">Environment admin</span></span>

<span data-ttu-id="27648-165">Todos os usuários no ambiente de área de proteção de destino, incluindo os administradores, são substituídos pelos usuários do ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="27648-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="27648-166">Antes de copiar uma instância, verifique se você é um administrador no ambiente de origem.</span><span class="sxs-lookup"><span data-stu-id="27648-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="27648-167">Se não for, não será possível entrar no ambiente de área restrita de destino após a conclusão da cópia.</span><span class="sxs-lookup"><span data-stu-id="27648-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="27648-168">Todos os usuários que não são administradores no ambiente de área de proteção de destino são desabilitados para evitar a entrada indesejada no ambiente de área restrita.</span><span class="sxs-lookup"><span data-stu-id="27648-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="27648-169">Os administradores podem habilitar novamente os usuários, se necessário.</span><span class="sxs-lookup"><span data-stu-id="27648-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-dataverse"></a><span data-ttu-id="27648-170">Aplicar campos personalizados ao Dataverse</span><span class="sxs-lookup"><span data-stu-id="27648-170">Apply custom fields to Dataverse</span></span>

<span data-ttu-id="27648-171">Se você copiar uma instância no ambiente de área restrita e quiser integrar seu ambiente de área restrita com o Dataverse, reaplique campos personalizados a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="27648-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span>

<span data-ttu-id="27648-172">Para cada campo personalizado que é exposto em tabelas do Dataverse, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="27648-172">For each custom field that's exposed on Dataverse tables, do the following steps:</span></span>

1. <span data-ttu-id="27648-173">Vá para o campo personalizado e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="27648-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="27648-174">Desmarque o campo **Habilitado** para cada entidade cdm_\* na qual o campo personalizado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="27648-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="27648-175">Selecione **Aplicar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="27648-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="27648-176">Selecione **Editar** novamente.</span><span class="sxs-lookup"><span data-stu-id="27648-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="27648-177">Marque o campo **Habilitado** para cada entidade cdm_\* na qual o campo personalizado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="27648-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="27648-178">Selecione **Aplicar Alterações** novamente.</span><span class="sxs-lookup"><span data-stu-id="27648-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="27648-179">O processo de cancelar a seleção, aplicar alterações, selecionar novamente e reaplicar alterações solicita que o esquema seja atualizado no Dataverse para incluir os campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="27648-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Dataverse to include the custom fields.</span></span>

<span data-ttu-id="27648-180">Para obter mais informações sobre como criar campos personalizados, consulte [Criar e trabalhar com campos personalizados](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span><span class="sxs-lookup"><span data-stu-id="27648-180">For more information about custom fields, see [Create and work with custom fields](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/user-defined-fields).</span></span>

## <a name="see-also"></a><span data-ttu-id="27648-181">Consulte também</span><span class="sxs-lookup"><span data-stu-id="27648-181">See also</span></span>

[<span data-ttu-id="27648-182">Provisionar o Human Resources</span><span class="sxs-lookup"><span data-stu-id="27648-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="27648-183">Remover uma instância</span><span class="sxs-lookup"><span data-stu-id="27648-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="27648-184">Atualizar processo</span><span class="sxs-lookup"><span data-stu-id="27648-184">Update process</span></span>](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]