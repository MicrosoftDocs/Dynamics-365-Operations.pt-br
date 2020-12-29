---
title: Entender os campos de data e hora
description: Entenda o que esperar ao usar os campos Data e Hora no Microsoft Dynamics 365 Human Resources. Saiba exatamente o que esperar ao interagir com dados de data e hora em um formulário no Human Resources, em uma fonte externa ou no Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 027e46d53fd9704f5483e90409be53c1510e8cd4
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529843"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="e106f-104">Entender os campos de data e hora</span><span class="sxs-lookup"><span data-stu-id="e106f-104">Understand Date and Time fields</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="e106f-105">Os campos **Data e Hora** são um conceito fundamental no Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e106f-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="e106f-106">É importante compreender como trabalhar com dados de **Data e Hora** em formulários do Dynamics 365 Human Resources, no Common Data Service e em fontes externas.</span><span class="sxs-lookup"><span data-stu-id="e106f-106">It's important to understand how to work with **Date and Time** data in Dynamics 365 Human Resources forms, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="e106f-107">Compreendendo a diferença entre os tipos de dados do campo Data e Data e Hora</span><span class="sxs-lookup"><span data-stu-id="e106f-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="e106f-108">Os campos **Data e Hora** contêm informações de fuso horário, enquanto os campos **Data** não.</span><span class="sxs-lookup"><span data-stu-id="e106f-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="e106f-109">Os campos **Data** exibem as mesmas informações em qualquer local.</span><span class="sxs-lookup"><span data-stu-id="e106f-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="e106f-110">Quando você insere uma data no campo **Data**, o Human Resources registra a mesma data no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e106f-110">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="e106f-111">Ao exibir os dados em um campo **Data e Hora**, o Human Resources ajusta a data e hora com base no fuso horário do usuário definido no formulário **Opções do usuário** (**Comum > Configuração > Opções do usuário**).</span><span class="sxs-lookup"><span data-stu-id="e106f-111">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="e106f-112">As informações de data e hora que você insere nesse campo podem não ser as mesmas que são registradas na base de dados.</span><span class="sxs-lookup"><span data-stu-id="e106f-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="e106f-113">[![Formulário Opções do usuário](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="e106f-114">Compreendendo os campos Data e Hora nos formulários</span><span class="sxs-lookup"><span data-stu-id="e106f-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="e106f-115">Ao inserir dados no campo **Data e Hora**, os dados exibidos na tela não serão os mesmos que aqueles armazenados no banco de dados se o fuso horário do usuário não estiver definido como Tempo Universal Coordenado (UTC).</span><span class="sxs-lookup"><span data-stu-id="e106f-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="e106f-116">Os dados dos campos **Data e Hora** sempre são armazenados em UTC.</span><span class="sxs-lookup"><span data-stu-id="e106f-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="e106f-117">[![Formulário Trabalhador](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="e106f-118">Compreenda os campos Data e Hora no banco de dados</span><span class="sxs-lookup"><span data-stu-id="e106f-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="e106f-119">Quando o Human Resources registra um valor de **Data e Hora** no banco de dados, os dados são armazenados em UTC.</span><span class="sxs-lookup"><span data-stu-id="e106f-119">When Human Resources writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="e106f-120">Isso permite que os usuários vejam todos os dados de **Data e Hora** relacionados ao fuso horário definido nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="e106f-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="e106f-121">No exemplo acima, a hora de início é um momento específico, e não uma data.</span><span class="sxs-lookup"><span data-stu-id="e106f-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="e106f-122">Ao alterar o fuso horário do usuário conectado de GMT +12:00 para GMT UTC, o mesmo registro que foi criado exibirá 30/04/2019 12:00:00 em vez de 01/05/2019 de 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="e106f-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="e106f-123">No exemplo abaixo, o início do funcionário 000724 torna-se ativo no mesmo horário independentemente do fuso horário.</span><span class="sxs-lookup"><span data-stu-id="e106f-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="e106f-124">O funcionário estará ativo em 30/04/2019 no fuso horário GMT, que é o equivalente a 01/05/2019 no fuso horário GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="e106f-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="e106f-125">Ambos fazem referência ao mesmo momento e não a uma data específica.</span><span class="sxs-lookup"><span data-stu-id="e106f-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="e106f-126">[![Formulário Trabalhador](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="e106f-127">Dados de Data e Hora no Data Management Framework, Excel, Common Data Service e Power BI</span><span class="sxs-lookup"><span data-stu-id="e106f-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="e106f-128">Os relatórios do Data Management Framework, do suplemento do Excel, do Common Data Service e do Power BI foram desenvolvidos para interagir com os dados diretamente no nível do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e106f-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="e106f-129">Como não há um cliente para ajustar os dados de **Data e Hora** ao fuso horário do usuário, todos os valores de **Data e Hora** estão em UTC, o que pode resultar em algumas suposições incorretas na inserção ou na exibição de dados.</span><span class="sxs-lookup"><span data-stu-id="e106f-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="e106f-130">O banco de dados supõe que os dados de **Data e Hora** enviados pelo DMF, Excel, ou Common Data Service são assumidos estejam em UTC.</span><span class="sxs-lookup"><span data-stu-id="e106f-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="e106f-131">Isso poderá ocasionar certa confusão quando o valor de **Data e hora** enviado não for exibido conforme esperado, pois o fuso horário do usuário que está visualizando os dados não está definido como UTC.</span><span class="sxs-lookup"><span data-stu-id="e106f-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="e106f-132">O mesmo pode ocorrer de maneira reversa mediante a exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="e106f-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="e106f-133">Os dados de **Data e Hora** na entidade exportada do DMF podem ser diferentes daqueles exibidos no cliente do Dynamics.</span><span class="sxs-lookup"><span data-stu-id="e106f-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="e106f-134">Ao usar fontes externas, como o DMF, para exibir ou criar dados, é importante se lembrar de que os valores de **Data e Hora** são considerados em UTC por padrão independentemente do fuso horário do computador do usuário ou das configurações atuais de fuso horário do usuário.</span><span class="sxs-lookup"><span data-stu-id="e106f-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="e106f-135">Exemplos do mesmo registro sendo exibido em diferentes áreas do produto</span><span class="sxs-lookup"><span data-stu-id="e106f-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="e106f-136">**Human Resources com fuso horário do usuário definido como UTC**</span><span class="sxs-lookup"><span data-stu-id="e106f-136">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="e106f-137">[![Formulário Trabalhador](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="e106f-138">**Human Resources com fuso horário do usuário definido como GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="e106f-138">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="e106f-139">[![Formulário Trabalhador](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="e106f-140">**Excel via OData**</span><span class="sxs-lookup"><span data-stu-id="e106f-140">**Excel Via OData**</span></span>

<span data-ttu-id="e106f-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="e106f-142">**Preparação do DMF**</span><span class="sxs-lookup"><span data-stu-id="e106f-142">**DMF Staging**</span></span>

<span data-ttu-id="e106f-143">[![Preparação do DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="e106f-144">**Exportar DMF**</span><span class="sxs-lookup"><span data-stu-id="e106f-144">**DMF Export**</span></span>

<span data-ttu-id="e106f-145">[![Preparação do DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="e106f-146">**Excel via Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="e106f-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="e106f-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="e106f-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="e106f-148">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e106f-148">See also</span></span>

[<span data-ttu-id="e106f-149">Dados de data e hora</span><span class="sxs-lookup"><span data-stu-id="e106f-149">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="e106f-150">Fusos horários de preferência do usuário</span><span class="sxs-lookup"><span data-stu-id="e106f-150">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
