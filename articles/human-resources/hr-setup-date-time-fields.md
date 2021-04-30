---
title: Entender os campos de data e hora
description: Entenda o que esperar ao usar os campos Data e Hora no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a8bc27bb4560b4a15aef483ff465c4b943bf02b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889875"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="d30d2-103">Entender os campos de data e hora</span><span class="sxs-lookup"><span data-stu-id="d30d2-103">Understand Date and Time fields</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d30d2-104">Os campos **Data e Hora** são um conceito fundamental no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d30d2-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d30d2-105">É importante compreender como trabalhar com dados de **Data e Hora** em formulários, no Dataverse e em fontes externas.</span><span class="sxs-lookup"><span data-stu-id="d30d2-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="d30d2-106">Compreendendo a diferença entre os tipos de dados do campo Data e Data e Hora</span><span class="sxs-lookup"><span data-stu-id="d30d2-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="d30d2-107">Os campos **Data e Hora** contêm informações de fuso horário, enquanto os campos **Data** não.</span><span class="sxs-lookup"><span data-stu-id="d30d2-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="d30d2-108">Os campos **Data** exibem as mesmas informações em qualquer local.</span><span class="sxs-lookup"><span data-stu-id="d30d2-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="d30d2-109">Quando você insere uma data no campo **Data**, o Human Resources registra a mesma data no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d30d2-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="d30d2-110">Ao exibir os dados em um campo **Data e Hora**, o Human Resources ajusta a data e hora com base no fuso horário do usuário definido no formulário **Opções do usuário** (**Comum > Configuração > Opções do usuário**).</span><span class="sxs-lookup"><span data-stu-id="d30d2-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="d30d2-111">As informações de data e hora que você insere nesse campo podem não ser as mesmas que são registradas na base de dados.</span><span class="sxs-lookup"><span data-stu-id="d30d2-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="d30d2-112">[![Formulário Opções do usuário](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="d30d2-113">Compreendendo os campos Data e Hora nos formulários</span><span class="sxs-lookup"><span data-stu-id="d30d2-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="d30d2-114">Os dados de **Data e Hora** exibidos na tela não serão os mesmos que os dados armazenados no banco de dados se o fuso horário do usuário não estiver definido como Tempo Universal Coordenado (UTC).</span><span class="sxs-lookup"><span data-stu-id="d30d2-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="d30d2-115">Os dados dos campos **Data e Hora** sempre são armazenados em UTC.</span><span class="sxs-lookup"><span data-stu-id="d30d2-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="d30d2-116">[![UTC de formulário Trabalhador](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="d30d2-117">Compreenda os campos Data e Hora no banco de dados</span><span class="sxs-lookup"><span data-stu-id="d30d2-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="d30d2-118">Quando o Human Resources registra um valor de **Data e Hora** no banco de dados, os dados são armazenados em UTC.</span><span class="sxs-lookup"><span data-stu-id="d30d2-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="d30d2-119">Isso permite que os usuários vejam todos os dados de **Data e Hora** relacionados ao fuso horário definido nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="d30d2-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="d30d2-120">No exemplo acima, a hora de início é um momento específico, e não uma data.</span><span class="sxs-lookup"><span data-stu-id="d30d2-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="d30d2-121">Ao alterar o fuso horário do usuário conectado de GMT +12:00 para GMT UTC, o mesmo registro mostra 30/04/2019 12:00:00 em vez de 01/05/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="d30d2-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="d30d2-122">No exemplo abaixo, o início do funcionário 000724 torna-se ativo no mesmo horário independentemente do fuso horário.</span><span class="sxs-lookup"><span data-stu-id="d30d2-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="d30d2-123">O funcionário estará ativo em 30/04/2019 no fuso horário GMT, que é o equivalente a 01/05/2019 no fuso horário GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="d30d2-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="d30d2-124">Ambos fazem referência ao mesmo momento e não a uma data específica.</span><span class="sxs-lookup"><span data-stu-id="d30d2-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="d30d2-125">[![GMT de formulário Trabalhador](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="d30d2-126">Dados de Data e Hora no Data Management Framework, Excel, Dataverse e Power BI</span><span class="sxs-lookup"><span data-stu-id="d30d2-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="d30d2-127">Os relatórios do Data Management Framework, do suplemento do Excel, do Dataverse e do Power BI foram desenvolvidos para interagir com os dados diretamente no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d30d2-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="d30d2-128">Como não há um cliente para ajustar dados de **Data e Hora** ao fuso horário do usuário, todos os valores de **Data e Hora** estão em UTC, o que pode resultar em algumas suposições incorretas ao inserir ou exibir dados.</span><span class="sxs-lookup"><span data-stu-id="d30d2-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="d30d2-129">O banco de dados supõe que dados de **Data e Hora** enviados via DMF, Excel, ou Dataverse estejam em UTC.</span><span class="sxs-lookup"><span data-stu-id="d30d2-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="d30d2-130">Isso poderá ocasionar certa confusão quando o valor de **Data e hora** enviado não for exibido conforme esperado, pois o fuso horário do usuário que está visualizando os dados não está definido como UTC.</span><span class="sxs-lookup"><span data-stu-id="d30d2-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="d30d2-131">O mesmo pode ocorrer de maneira reversa mediante a exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="d30d2-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="d30d2-132">Os dados de **Data e Hora** na entidade exportada do DMF podem ser diferentes dos exibidos no cliente do Dynamics.</span><span class="sxs-lookup"><span data-stu-id="d30d2-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="d30d2-133">Ao usar fontes externas, como o DMF, para exibir ou criar dados, é importante se lembrar de que os valores de **Data e Hora** são considerados em UTC por padrão, seja qual for o fuso horário do computador do usuário ou as configurações atuais de fuso horário do usuário.</span><span class="sxs-lookup"><span data-stu-id="d30d2-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="d30d2-134">Exemplos do mesmo registro sendo exibido em diferentes áreas do produto</span><span class="sxs-lookup"><span data-stu-id="d30d2-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="d30d2-135">**Human Resources com fuso horário do usuário definido como UTC**</span><span class="sxs-lookup"><span data-stu-id="d30d2-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="d30d2-136">[![Formulário de trabalhador definido como UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="d30d2-137">**Human Resources com fuso horário do usuário definido como GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="d30d2-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="d30d2-138">[![Formulário de trabalhador definido como GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="d30d2-139">**Excel via OData**</span><span class="sxs-lookup"><span data-stu-id="d30d2-139">**Excel Via OData**</span></span>

<span data-ttu-id="d30d2-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="d30d2-141">**Preparação do DMF**</span><span class="sxs-lookup"><span data-stu-id="d30d2-141">**DMF Staging**</span></span>

<span data-ttu-id="d30d2-142">[![Preparação do DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="d30d2-143">**Exportar DMF**</span><span class="sxs-lookup"><span data-stu-id="d30d2-143">**DMF Export**</span></span>

<span data-ttu-id="d30d2-144">[![Exportação de DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="d30d2-145">**Excel via Dataverse**</span><span class="sxs-lookup"><span data-stu-id="d30d2-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="d30d2-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="d30d2-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="d30d2-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d30d2-147">See also</span></span>

[<span data-ttu-id="d30d2-148">Dados de data e hora</span><span class="sxs-lookup"><span data-stu-id="d30d2-148">Date and time data</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="d30d2-149">Fusos horários de preferência do usuário</span><span class="sxs-lookup"><span data-stu-id="d30d2-149">User preferred time zones</span></span>](/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]