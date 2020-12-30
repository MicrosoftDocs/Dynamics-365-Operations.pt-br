---
title: Migração de tipo de dados de moeda para gravação dupla
description: Este tópico descreve como alterar o número de casas decimais que a gravação dupla permite para moeda.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-04-06
ms.openlocfilehash: 6a0f114bce6bdb7813c93e9441744d67cd043c30
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683715"
---
# <a name="currency-data-type-migration-for-dual-write"></a><span data-ttu-id="6c39e-103">Migração de tipo de dados de moeda para gravação dupla</span><span class="sxs-lookup"><span data-stu-id="6c39e-103">Currency data-type migration for dual-write</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="6c39e-104">Você pode aumentar o número de casas decimais com suporte para os valores de moeda para um máximo de 10.</span><span class="sxs-lookup"><span data-stu-id="6c39e-104">You can increase the number of decimal places that are supported for currency values to a maximum of 10.</span></span> <span data-ttu-id="6c39e-105">O limite padrão é quatro casas decimais.</span><span class="sxs-lookup"><span data-stu-id="6c39e-105">The default limit is four decimal places.</span></span> <span data-ttu-id="6c39e-106">Ao aumentar o número de casas decimais, você ajuda a prevenir a perda de dados usando a gravação dupla para sincronizar dados.</span><span class="sxs-lookup"><span data-stu-id="6c39e-106">By increasing the number of decimal places, you help prevent data loss when you use dual-write to sync data.</span></span> <span data-ttu-id="6c39e-107">O aumento no número de casas decimais é uma alteração de adesão.</span><span class="sxs-lookup"><span data-stu-id="6c39e-107">The increase in the number of decimal places is an opt-in change.</span></span> <span data-ttu-id="6c39e-108">Para implementá-la, é necessário solicitar assistência da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c39e-108">To implement it, you must request assistance from Microsoft.</span></span>

<span data-ttu-id="6c39e-109">O processo de alterar o número de casas decimais tem duas etapas:</span><span class="sxs-lookup"><span data-stu-id="6c39e-109">The process of changing the number of decimal places has two steps:</span></span>

1. <span data-ttu-id="6c39e-110">Solicite a migração da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c39e-110">Request migration from Microsoft.</span></span>
2. <span data-ttu-id="6c39e-111">Altere o número de casas decimais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6c39e-111">Change the number of decimal places in Dataverse.</span></span>

<span data-ttu-id="6c39e-112">O aplicativo Finance and Operations e o Dataverse devem oferecer suporte ao mesmo número de casas decimais nos valores de moeda.</span><span class="sxs-lookup"><span data-stu-id="6c39e-112">The Finance and Operations app and Dataverse must support the same number of decimal places in currency values.</span></span> <span data-ttu-id="6c39e-113">Caso contrário, pode haver perda de dados quando essas informações forem sincronizadas entre aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6c39e-113">Otherwise, data loss can occur when this information is synced between apps.</span></span> <span data-ttu-id="6c39e-114">O processo de migração reconfigura a maneira como os valores de moeda e da taxa de câmbio são armazenados, mas não altera nenhum dado.</span><span class="sxs-lookup"><span data-stu-id="6c39e-114">The migration process reconfigures the way that currency and exchange rate values are stored, but it doesn't change any data.</span></span> <span data-ttu-id="6c39e-115">Após a conclusão da migração, é possível aumentar o número de casas decimais para códigos de moeda e preços, e os dados que os usuários inserem e visualizam poderão ter maior precisão decimal.</span><span class="sxs-lookup"><span data-stu-id="6c39e-115">After the migration is completed, the number of decimal places for currency codes and pricing can be increased, and the data that users enter and view can have more decimal precision.</span></span>

<span data-ttu-id="6c39e-116">A migração é opcional.</span><span class="sxs-lookup"><span data-stu-id="6c39e-116">Migration is optional.</span></span> <span data-ttu-id="6c39e-117">Se você puder se beneficiar com o suporte para mais casas decimais, recomendamos que considere a migração.</span><span class="sxs-lookup"><span data-stu-id="6c39e-117">If you might benefit from support for more decimal places, we recommend that you consider migration.</span></span> <span data-ttu-id="6c39e-118">As organizações que não exigem valores com mais de quatro casas decimais não precisam migrar.</span><span class="sxs-lookup"><span data-stu-id="6c39e-118">Organizations that don't require values that have more than four decimal places don't have to migrate.</span></span>

## <a name="requesting-migration-from-microsoft"></a><span data-ttu-id="6c39e-119">Solicitando a migração da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6c39e-119">Requesting migration from Microsoft</span></span>

<span data-ttu-id="6c39e-120">O armazenamento para campos de moeda existentes no Dataverse não pode oferecer suporte para mais de quatro casas decimais.</span><span class="sxs-lookup"><span data-stu-id="6c39e-120">Storage for existing currency fields in Dataverse can't support more than four decimal places.</span></span> <span data-ttu-id="6c39e-121">Portanto, durante o processo de migração, os valores de moeda são copiados para novos campos internos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6c39e-121">Therefore, during the migration process, currency values are copied to new internal fields in the database.</span></span> <span data-ttu-id="6c39e-122">Esse processo ocorre continuamente até que todos os dados tenham sido migrados.</span><span class="sxs-lookup"><span data-stu-id="6c39e-122">This process occurs continuously until all data has been migrated.</span></span> <span data-ttu-id="6c39e-123">Internamente, no final da migração, os novos tipos de armazenamento substituem os tipos de armazenamento antigos, mas os valores dos dados permanecem inalterados.</span><span class="sxs-lookup"><span data-stu-id="6c39e-123">Internally, at the end of migration, the new storage types replace the old storage types, but the data values are unchanged.</span></span> <span data-ttu-id="6c39e-124">Os campos de moeda podem oferecer suporte para até 10 casas decimais.</span><span class="sxs-lookup"><span data-stu-id="6c39e-124">The currency fields can then support up to 10 decimal places.</span></span> <span data-ttu-id="6c39e-125">Durante o processo de migração, o Dataverse pode continuar sendo usado sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="6c39e-125">During the migration process, Dataverse can continue to be used without interruption.</span></span>

<span data-ttu-id="6c39e-126">Ao mesmo tempo, as taxas de câmbio são modificadas para que ofereçam suporte para até 12 casas decimais em vez do limite atual de 10.</span><span class="sxs-lookup"><span data-stu-id="6c39e-126">At the same time, exchange rates are modified so that they support up to 12 decimal places instead of the current limit of 10.</span></span> <span data-ttu-id="6c39e-127">Essa alteração é necessária para que o número de casas decimais seja o mesmo no aplicativo Finance and Operations e no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="6c39e-127">This change is required so that the number of decimal places is the same in both the Finance and Operations app and Dataverse.</span></span>

<span data-ttu-id="6c39e-128">A migração não altera os dados.</span><span class="sxs-lookup"><span data-stu-id="6c39e-128">Migration doesn't change any data.</span></span> <span data-ttu-id="6c39e-129">Depois que os campos de moeda e taxa de câmbio forem convertidos, os administradores podem configurar o sistema para usar até 10 casas decimais para campos de moeda ao especificar o número de casas decimais para cada moeda da transação e para preços.</span><span class="sxs-lookup"><span data-stu-id="6c39e-129">After the currency and exchange rate fields are converted, admins can configure the system to use up to 10 decimal places for currency fields by specifying the number of decimal places for each transaction currency and for pricing.</span></span>

### <a name="request-a-migration"></a><span data-ttu-id="6c39e-130">Solicitar uma migração</span><span class="sxs-lookup"><span data-stu-id="6c39e-130">Request a migration</span></span>

<span data-ttu-id="6c39e-131">Para disponibilizar esse recurso, envie um email para **CDSExpandDecimal@microsoft.com** e inclua as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6c39e-131">To make this feature available, email **CDSExpandDecimal@microsoft.com**, and include the following information:</span></span>

+ <span data-ttu-id="6c39e-132">**Assunto:** Solicitação para habilitar o suporte decimal expandido para \<organizationID\></span><span class="sxs-lookup"><span data-stu-id="6c39e-132">**Subject:** Request to enable expanded decimal support for \<organizationID\></span></span>
+ <span data-ttu-id="6c39e-133">**Corpo:** Gostaria de habilitar o suporte decimal expandido para a minha organização \<organizationID\>.</span><span class="sxs-lookup"><span data-stu-id="6c39e-133">**Body:** I would like to enable expanded decimal support for my org \<organizationID\>.</span></span>

<span data-ttu-id="6c39e-134">Um representante da Microsoft entrará em contato dentro de dois a três dias úteis para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="6c39e-134">A Microsoft representative will contact you within two to three business days for the next steps.</span></span>

<span data-ttu-id="6c39e-135">Ao solicitar uma migração, esteja ciente dos seguintes detalhes e estabeleça um plano de forma adequada:</span><span class="sxs-lookup"><span data-stu-id="6c39e-135">When you request a migration, you should be aware of the following details and plan for them accordingly:</span></span>

+ <span data-ttu-id="6c39e-136">O tempo necessário para migrar os dados depende da quantidade de dados no sistema.</span><span class="sxs-lookup"><span data-stu-id="6c39e-136">The time that is required to migrate the data depends the amount of data in the system.</span></span> <span data-ttu-id="6c39e-137">A migração de bancos de dados grandes pode demorar vários dias.</span><span class="sxs-lookup"><span data-stu-id="6c39e-137">Migration of large databases can take several days.</span></span>
+ <span data-ttu-id="6c39e-138">O tamanho do banco de dados aumenta temporariamente enquanto a migração está sendo executada, pois é necessário espaço adicional para os índices.</span><span class="sxs-lookup"><span data-stu-id="6c39e-138">The size of the database temporarily increases while the migration is running, because additional space is needed for indexes.</span></span> <span data-ttu-id="6c39e-139">A maior parte do espaço adicional é liberada quando a migração é concluída.</span><span class="sxs-lookup"><span data-stu-id="6c39e-139">Most of the additional space is freed when the migration is completed.</span></span>
+ <span data-ttu-id="6c39e-140">Durante o processo de migração, se ocorrerem erros que impedem a conclusão da migração, o sistema gera alertas para o Suporte da Microsoft, para que a equipe de Suporte possa intervir.</span><span class="sxs-lookup"><span data-stu-id="6c39e-140">During the migration process, if errors occur that prevent the migration from being completed, the system raise alerts to Microsoft Support, so that Support staff can intervene.</span></span> <span data-ttu-id="6c39e-141">No entanto, mesmo se ocorrer erros durante a migração, o Dataverse permanecerá totalmente disponível para uso regular.</span><span class="sxs-lookup"><span data-stu-id="6c39e-141">However, even if errors occur during the migration, Dataverse remains fully available for regular use.</span></span>
+ <span data-ttu-id="6c39e-142">O processo de migração é irreversível.</span><span class="sxs-lookup"><span data-stu-id="6c39e-142">The migration process isn't reversible.</span></span>

## <a name="changing-the-number-of-decimal-places"></a><span data-ttu-id="6c39e-143">Alterar o número de casas decimais</span><span class="sxs-lookup"><span data-stu-id="6c39e-143">Changing the number of decimal places</span></span>

<span data-ttu-id="6c39e-144">Depois que a migração for concluída, o Dataverse pode armazenar números com mais casas decimais.</span><span class="sxs-lookup"><span data-stu-id="6c39e-144">After the migration is completed, Dataverse can store numbers that have more decimal places.</span></span> <span data-ttu-id="6c39e-145">Os administradores podem escolher quantas casas decimais são usadas para códigos de moeda específicos e para preços.</span><span class="sxs-lookup"><span data-stu-id="6c39e-145">Admins can choose how many decimal places are used for specific currency codes and for pricing.</span></span> <span data-ttu-id="6c39e-146">Os usuários do Microsoft Power Apps, Power BI e Power Automate podem exibir e usar números com mais casas decimais.</span><span class="sxs-lookup"><span data-stu-id="6c39e-146">Users of Microsoft Power Apps, Power BI, and Power Automate can then view and use numbers that have more decimal places.</span></span>

<span data-ttu-id="6c39e-147">Para fazer essa alteração, atualize as seguintes configurações no Power Apps:</span><span class="sxs-lookup"><span data-stu-id="6c39e-147">To make this change, you must update the following settings in Power Apps:</span></span>

+ <span data-ttu-id="6c39e-148">**Configurações do Sistema: Precisão da moeda para precificação** – O campo **Defina o número de decimais da moeda que será usada para precificação em todo o sistema** define como a moeda se comportará para a organização quando **Precisão de preço** for selecionado.</span><span class="sxs-lookup"><span data-stu-id="6c39e-148">**System Settings: Currency precision for pricing** – The **Set the currency precision that is used for pricing throughout the system** field defines how the currency will behave for the organization when **Pricing Precision** is selected.</span></span>
+ <span data-ttu-id="6c39e-149">**Gerenciamento de Negócios: Moedas** – O campo **Precisão da Moeda** permite especificar um número personalizado de casas decimais para uma moeda específica.</span><span class="sxs-lookup"><span data-stu-id="6c39e-149">**Business Management: Currencies** – The **Currency Precision** field lets you specify a custom number of decimal places for a specific currency.</span></span> <span data-ttu-id="6c39e-150">Há um fallback para a configuração em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="6c39e-150">There is a fallback to the organization-wide setting.</span></span>

<span data-ttu-id="6c39e-151">Estas são algumas limitações:</span><span class="sxs-lookup"><span data-stu-id="6c39e-151">There are some limitations:</span></span>

+ <span data-ttu-id="6c39e-152">Não é possível configurar o campo de moeda em uma entidade.</span><span class="sxs-lookup"><span data-stu-id="6c39e-152">You can't configure the currency field on an entity.</span></span>
+ <span data-ttu-id="6c39e-153">Você pode especificar mais de quatro casas decimais somente nos níveis **Preço** e **Moeda de Transação**.</span><span class="sxs-lookup"><span data-stu-id="6c39e-153">You can specify more than four decimal places only at the **Pricing** and **Transaction Currency** levels.</span></span>

### <a name="system-settings-currency-precision-for-pricing"></a><span data-ttu-id="6c39e-154">Configurações do Sistema: Precisão da moeda para precificação</span><span class="sxs-lookup"><span data-stu-id="6c39e-154">System Settings: Currency precision for pricing</span></span>

<span data-ttu-id="6c39e-155">Após a conclusão da migração, os administradores podem definir a precisão da moeda.</span><span class="sxs-lookup"><span data-stu-id="6c39e-155">After migration is completed, admins can set the currency precision.</span></span> <span data-ttu-id="6c39e-156">Vá para **Configurações \> Administração** e selecione **Configurações do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="6c39e-156">Go to **Settings \> Administration**, and select **System Settings**.</span></span> <span data-ttu-id="6c39e-157">Em seguida, na guia **Geral**, altere o valor do campo **Defina o número de decimais da moeda que será usada para precificação em todo o sistema**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c39e-157">Then, on the **General** tab, change the value of the **Set the currency precision that is used for pricing throughout the system** field, as shown in the following illustration.</span></span>

![Configurações do sistema para moeda](media/currency-system-settings.png)

### <a name="business-management-currencies"></a><span data-ttu-id="6c39e-159">Gerenciamento de Negócios: Moedas</span><span class="sxs-lookup"><span data-stu-id="6c39e-159">Business Management: Currencies</span></span>

<span data-ttu-id="6c39e-160">Se quiser que a precisão de uma moeda específica seja diferente da precisão da moeda usada para os preços, é possível alterá-la.</span><span class="sxs-lookup"><span data-stu-id="6c39e-160">If you require that the currency precision for a specific currency differ from the currency precision that is used for pricing, you can change it.</span></span> <span data-ttu-id="6c39e-161">Vá para **Configurações \> Gerenciamento de Negócios**, selecione **Moedas** e selecione a moeda a ser alterada.</span><span class="sxs-lookup"><span data-stu-id="6c39e-161">Go to **Settings \> Business Management**, select **Currencies**, and select the currency to change.</span></span> <span data-ttu-id="6c39e-162">Em seguida, defina o campo **Precisão da Moeda** com o número de casas decimais que deseja, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c39e-162">Then set the **Currency Precision** field to the number of decimal places that you want, as shown in the following illustration.</span></span>

![Configurações de moeda para uma localidade específica](media/specific-currency.png)

### <a name="tables-currency-field"></a><span data-ttu-id="6c39e-164">tabelas: campo Moeda</span><span class="sxs-lookup"><span data-stu-id="6c39e-164">tables: Currency field</span></span>

<span data-ttu-id="6c39e-165">O número de casas decimais que podem ser configuradas para campos de moeda específicos é limitado a quatro.</span><span class="sxs-lookup"><span data-stu-id="6c39e-165">The number of decimal places that can be configured for specific currency fields is limited to four.</span></span>
