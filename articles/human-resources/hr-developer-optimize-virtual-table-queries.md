---
title: Otimizar consultas de tabela virtual do Dataverse
description: Otimizar e solucionar problemas de desempenho de consultas a tabelas virtuais do Dataverse
author: andreabichsel
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-04-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66fb9f2b50079b5eb4eb16da17b8a473d687d354
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054899"
---
# <a name="optimize-dataverse-virtual-table-queries"></a><span data-ttu-id="5cb7d-103">Otimizar consultas de tabela virtual do Dataverse</span><span class="sxs-lookup"><span data-stu-id="5cb7d-103">Optimize Dataverse virtual table queries</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a><span data-ttu-id="5cb7d-104">Problema</span><span class="sxs-lookup"><span data-stu-id="5cb7d-104">Issue</span></span>

### <a name="overview"></a><span data-ttu-id="5cb7d-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="5cb7d-105">Overview</span></span>

<span data-ttu-id="5cb7d-106">Ao usar tabelas virtuais do Dataverse para desenvolver integrações e outras conexões de dados com o Dynamics 365 Human Resources, você pode ter problemas de desempenho com consultas nas tabelas virtuais.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-106">When using Dataverse virtual tables to develop integrations and other data connections with Dynamics 365 Human Resources, you can experience performance issues with queries against the virtual tables.</span></span> <span data-ttu-id="5cb7d-107">A execução de consulta lenta pode ocorrer em vários clientes ou interfaces.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-107">The slow query execution can occur across various clients or interfaces.</span></span> <span data-ttu-id="5cb7d-108">Por exemplo, o problema pode ocorrer nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="5cb7d-108">For example, you may experience the issue in the following circumstances:</span></span>

- <span data-ttu-id="5cb7d-109">Ao consultar uma tabela virtual por meio da API Web do Dataverse</span><span class="sxs-lookup"><span data-stu-id="5cb7d-109">When querying a virtual table through the Dataverse Web API</span></span>
- <span data-ttu-id="5cb7d-110">Ao criar um Power App em uma tabela virtual</span><span class="sxs-lookup"><span data-stu-id="5cb7d-110">When creating a Power App against a virtual table</span></span>
- <span data-ttu-id="5cb7d-111">Ao criar um relatório do Power BI em uma tabela virtual</span><span class="sxs-lookup"><span data-stu-id="5cb7d-111">When building a Power BI report on a virtual table</span></span>

<span data-ttu-id="5cb7d-112">Todas essas interfaces têm o potencial de destacar o problema de desempenho.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-112">All these interfaces have the potential to surface the performance issue.</span></span>

<span data-ttu-id="5cb7d-113">Uma causa do baixo desempenho com tabelas virtuais do Dataverse para o Human Resources são as colunas de chave estrangeira da tabela virtual relacionada a [propriedades de navegação](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) da tabela.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-113">One cause of slow performance with Dataverse virtual tables for Human Resources is the foreign key columns of the virtual table related to the table's [navigation properties](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties).</span></span> <span data-ttu-id="5cb7d-114">Quando as propriedades de navegação são criadas para uma tabela virtual, uma coluna de chave estrangeira é adicionada automaticamente à tabela para representar o valor da chave da coluna de chave da tabela virtual relacionada.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-114">When navigation properties are created for a virtual table, a foreign key column is automatically added to the table to represent the value of the key for the related virtual table's key column.</span></span> <span data-ttu-id="5cb7d-115">Por exemplo, a coluna **_mshr_fk_person_id_value** é adicionada à entidade **mshr_hcmworkerbaseentity** com a propriedade de chave estrangeira da entidade **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-115">For example, the **_mshr_fk_person_id_value** column is added to the **mshr_hcmworkerbaseentity** entity with the foreign key property from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="5cb7d-116">Devido à forma como os valores dessas colunas de chave estrangeira são mantidos em uma tabela, a busca de valores pode ter um impacto negativo no desempenho de uma consulta na tabela virtual.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-116">Because of how the values for these foreign key columns are maintained in a table, fetching the values can have a negative impact on the performance of a query against the virtual table.</span></span>

### <a name="potential-symptoms"></a><span data-ttu-id="5cb7d-117">Sintomas potenciais</span><span class="sxs-lookup"><span data-stu-id="5cb7d-117">Potential symptoms</span></span>

<span data-ttu-id="5cb7d-118">Um exemplo em que você pode ver esse impacto está nas consultas sobre a entidade Trabalhador (**mshr_hcmworkerentity**) ou Trabalhador base (**mshr_hcmworkerbaseentity**).</span><span class="sxs-lookup"><span data-stu-id="5cb7d-118">An example where you may see this impact is in queries against the Worker (**mshr_hcmworkerentity**) or Base worker (**mshr_hcmworkerbaseentity**) entity.</span></span> <span data-ttu-id="5cb7d-119">Você pode ver o próprio manifesto de problema de desempenho de diferentes maneiras:</span><span class="sxs-lookup"><span data-stu-id="5cb7d-119">You may see the performance issue manifest itself in a few different ways:</span></span>

- <span data-ttu-id="5cb7d-120">**Execução lenta de consulta**: a consulta na tabela virtual pode retornar os resultados esperados, mas levar um tempo além do esperado para concluir a execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-120">**Slow query execution**: The query against the virtual table may return the expected results, but take longer than expected to complete execution of the query.</span></span>
- <span data-ttu-id="5cb7d-121">**Tempo limite da consulta**: a consulta pode expirar e retornar o seguinte erro: "Foi obtido um token para chamar o Finance and Operations, mas o Finance and Operations retornou um erro do tipo InternalServerError".</span><span class="sxs-lookup"><span data-stu-id="5cb7d-121">**Query timeout**: The query may time out and return the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type InternalServerError."</span></span>
- <span data-ttu-id="5cb7d-122">**Erro inesperado**: a consulta pode retornar um tipo de erro 400 com a seguinte mensagem: "Ocorreu um erro inesperado".</span><span class="sxs-lookup"><span data-stu-id="5cb7d-122">**Unexpected error**: The query may return an error type 400 with the following message: "An unexpected error occurred."</span></span>

  ![Tipo de erro 400 em HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType400.png)

- <span data-ttu-id="5cb7d-124">**Limitação**: a consulta pode usar excessivamente recursos do servidor e ficar sujeita à limitação.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-124">**Throttling**: The query may overuse server resources, and become subject to throttling.</span></span> <span data-ttu-id="5cb7d-125">Nesse caso, a consulta retorna o seguinte erro: "Foi obtido um token para chamar o Finance and Operations, mas o Finance and Operations retornou um erro do tipo 429".</span><span class="sxs-lookup"><span data-stu-id="5cb7d-125">In this case, the query returns the following error: "A token was obtained to call Finance and Operations, but Finance and Operations returned an error of type 429."</span></span> <span data-ttu-id="5cb7d-126">Para obter mais informações sobre a limitação no Human Resources, consulte [Perguntas frequentes sobre limitação](./hr-admin-integration-throttling-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5cb7d-126">For more information in throttling in Human Resources, see [Throttling FAQ](./hr-admin-integration-throttling-faq.md).</span></span>

  ![Tipo de erro 429 em HcmWorkerBaseEntity](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a><span data-ttu-id="5cb7d-128">Resolução</span><span class="sxs-lookup"><span data-stu-id="5cb7d-128">Resolution</span></span>

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a><span data-ttu-id="5cb7d-129">Limitar o número de colunas incluídas na consulta de dados</span><span class="sxs-lookup"><span data-stu-id="5cb7d-129">Limit the number of columns included in your data query</span></span>

<span data-ttu-id="5cb7d-130">Com tabelas virtuais, um dos métodos com o maior potencial para melhorar o desempenho da consulta é limitar o número de colunas selecionadas na consulta.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-130">With virtual tables, one of the methods with the greatest potential to improve query performance is to limit the number of columns selected in the query.</span></span> <span data-ttu-id="5cb7d-131">A orientação geral para otimizar o desempenho da consulta é limitar as colunas retornadas na consulta somente às propriedades necessárias.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-131">The general guidance for optimizing query performance is to limit the columns returned in your query to only those properties that you need.</span></span> <span data-ttu-id="5cb7d-132">Isso é verdadeiro especialmente nas colunas de chave estrangeira em tabelas virtuais.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-132">This is particularly true with the foreign key columns on virtual tables.</span></span> <span data-ttu-id="5cb7d-133">Se você não precisar dos valores nas colunas de chave estrangeira para integração ou relatório, estruture a consulta para selecionar apenas as colunas necessárias, excluindo as colunas de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-133">If you don't need the values in the foreign key columns for your integration or report, then structure the query to select only the columns you need, excluding the foreign key columns.</span></span>

#### <a name="selecting-columns-in-an-odata-query"></a><span data-ttu-id="5cb7d-134">Selecionar colunas em uma consulta OData</span><span class="sxs-lookup"><span data-stu-id="5cb7d-134">Selecting columns in an OData query</span></span>

<span data-ttu-id="5cb7d-135">Ao consultar uma tabela virtual por meio da API Web do Dataverse, você pode limitar o número de colunas incluídas na consulta usando a opção de consulta de sistema **$select** e definir as colunas para as quais você precisa do retorno de resultados.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-135">When querying a virtual table through the Dataverse Web API, you can limit the number of columns included in the query by using the **$select** system query option, and define the columns for which you need results returned.</span></span> <span data-ttu-id="5cb7d-136">Para maximizar o desempenho, exclua colunas de chave estrangeira (com o prefixo **_mshr_FK_**) da consulta.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-136">To maximize performance, exclude foreign key columns (those with the **_mshr_FK_** prefix) from the query.</span></span>

<span data-ttu-id="5cb7d-137">Por exemplo, a consulta a seguir sobre a entidade **mshr_hcmworkerbaseentity** incluirá somente as colunas incluídas na cláusula de opção de consulta **$select**, excluindo os valores de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-137">For example, the following query against the **mshr_hcmworkerbaseentity** entity will include only the columns included in the **$select** query option clause, excluding foreign key values.</span></span> <span data-ttu-id="5cb7d-138">Isso traz melhorias significativas no desempenho em uma consulta que inclui todas as colunas da tabela.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-138">This provides significant improvements in performance over a query that includes all table columns.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="5cb7d-139">A recomendação para limitar o número de colunas selecionadas também se aplica ao utilizar a opção de consulta **$expand** para expandir a consulta a tabelas virtuais relacionadas por meio de propriedades de navegação.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-139">The recommendation to limit the number of columns selected also applies when using the **$expand** query option to expand the query to related virtual tables through navigation properties.</span></span> <span data-ttu-id="5cb7d-140">Por exemplo, a consulta a seguir inclui colunas da entidade **mshr_hcmworkerbaseentity** com colunas expandidas da entidade **mshr_dirpersonentity**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-140">For example, the following query includes columns from the **mshr_hcmworkerbaseentity** entity with expanded columns from the **mshr_dirpersonentity** entity.</span></span> <span data-ttu-id="5cb7d-141">Observe que a opção de consulta **$select** também está incluída na cláusula de opção de consulta **$expand**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-141">Note that the **$select** query option is also included in the **$expand** query option clause.</span></span>

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

<span data-ttu-id="5cb7d-142">Ao usar esse método de recuperação de dados com a opção de consulta **$select** na cláusula de opção de consulta **$expand**, você em geral verá maiores melhorias de desempenho quando a propriedade de navegação entre as entidades for uma relacionamentos muitos para um.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-142">When using this method of retrieving data with the **$select** query option in the **$expand** query option clause, you will typically see greater performance improvements when the navigation property between the entities is a many-to-one relationship.</span></span> <span data-ttu-id="5cb7d-143">Talvez você não veja a mesma redução no tempo de execução da consulta ao expandir um relacionamento um para muitos.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-143">You may not see the same decrease in query execution time when expanding a one-to-many relationship.</span></span> <span data-ttu-id="5cb7d-144">Para obter mais informações sobre a definição de relacionamentos de tabelas virtuais do Dataverse, consulte [Relacionamentos de tabela](/powerapps/maker/data-platform/create-edit-entity-relationships).</span><span class="sxs-lookup"><span data-stu-id="5cb7d-144">For more information on relationship definition for Dataverse virtual tables, see [Table relationships](/powerapps/maker/data-platform/create-edit-entity-relationships).</span></span>

<span data-ttu-id="5cb7d-145">Para obter mais informações sobre como usar as opções de consulta do sistema **$select** e **$expand** na API Web do Dataverse, consulte [Recuperar registros de entidades relacionadas com uma consulta](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span><span class="sxs-lookup"><span data-stu-id="5cb7d-145">For more information on using the **$select** and **$expand** system query options in the Dataverse Web API, see [Retrieve related entity records with a query](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).</span></span>

#### <a name="selecting-columns-in-power-bi"></a><span data-ttu-id="5cb7d-146">Selecionar colunas no Power BI</span><span class="sxs-lookup"><span data-stu-id="5cb7d-146">Selecting columns in Power BI</span></span>

<span data-ttu-id="5cb7d-147">Se você tiver uma das indicações mencionadas anteriormente de baixo desempenho ao criar um relatório do Power BI em uma tabela virtual do Dataverse, poderá melhorar o desempenho excluindo colunas de chave estrangeira das colunas selecionadas da tabela para o relatório.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-147">If you experience any of the aforementioned indications of slow performance when building a Power BI report against a Dataverse virtual table, you can improve the performance by excluding foreign key columns from the columns selected from the table for the report.</span></span> <span data-ttu-id="5cb7d-148">Por exemplo, se você estiver usando o Power BI Desktop para criar um relatório na entidade **mshr_hcmworkerbaseentity**, poderá usar as etapas a seguir para selecionar as colunas que deseja incluir na consulta de relatório.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-148">For example, if you are using Power BI Desktop to create a report against the **mshr_hcmworkerbaseentity** entity, you can use the following steps to select the columns you want included in the report query.</span></span>

1. <span data-ttu-id="5cb7d-149">No Power BI Desktop, selecione **Mais...** na lista suspensa **Obter dados** na faixa de opções de ação.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-149">In Power BI Desktop, select **More...** from the **Get data** drop-down list on the action ribbon.</span></span>
2. <span data-ttu-id="5cb7d-150">Na janela **Obter Dados**, insira **Common Data Service** na caixa de pesquisa, selecione o conector **Common Data Service** e selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-150">In the **Get Data** window, enter **Common Data Service** in the search box, select the **Common Data Service** connector, and select **Connect**.</span></span>
3. <span data-ttu-id="5cb7d-151">No campo **URL do Servidor** da janela Common Data Service, insira o URI da organização para o ambiente do Dataverse e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-151">In the **Server Url** field of the Common Data Service window, enter the organization URI for your Dataverse environment, and select **OK**.</span></span>
  
   ![Insira o URI do ambiente do Dataverse](./media/PowerBIDataverseURLSetup.png)
  
4. <span data-ttu-id="5cb7d-153">Na janela Navegador, expanda o nó **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-153">In the Navigator window, expand the **Entities** node.</span></span>
5. <span data-ttu-id="5cb7d-154">Na caixa de pesquisa, insira **mshr_hcmworkerbaseentity** e selecione a entidade.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-154">In the search box, enter **mshr_hcmworkerbaseentity**, and select the entity.</span></span>
6. <span data-ttu-id="5cb7d-155">Selecione **Transformar Dados**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-155">Select **Transform Data**.</span></span>
7. <span data-ttu-id="5cb7d-156">Na janela do Editor do Power Query, selecione **Editor Avançado**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-156">In the Power Query Editor window, select **Advanced Editor**.</span></span>
8. <span data-ttu-id="5cb7d-157">Na janela **Editor Avançado**, atualize a consulta para ter a aparência a seguir, adicionando ou removendo colunas da matriz, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-157">In the **Advanced Editor** window, update the query to look like the below, adding or removing any columns to the array as needed.</span></span>

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Atualize a consulta no Editor Avançado para o Editor do Power Query](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. <span data-ttu-id="5cb7d-159">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-159">Select **Done**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5cb7d-160">Se você recebeu anteriormente um erro do tipo 429 da consulta antes da atualização, talvez precise aguardar o período de novas tentativas antes de atualizar a consulta para que ela seja concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-160">If you previously received an error of type 429 from the query prior to updating, you may need to wait for the retry period prior to refreshing the query for it to complete successully.</span></span>

10. <span data-ttu-id="5cb7d-161">Clique em **Fechar e Aplicar** na faixa de opções de ação do Editor do Power Query.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-161">Click **Close & Apply** on the Power Query Editor action ribbon.</span></span>

<span data-ttu-id="5cb7d-162">Você poderá começar a criar o relatório do Power BI nas colunas selecionadas a partir da tabela virtual.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-162">You're then able to begin building your Power BI report against the columns selected from the virtual table.</span></span>

#### <a name="selecting-columns-in-power-apps"></a><span data-ttu-id="5cb7d-163">Selecionar colunas no Power Apps</span><span class="sxs-lookup"><span data-stu-id="5cb7d-163">Selecting columns in Power Apps</span></span>

<span data-ttu-id="5cb7d-164">Semelhante às consultas de API Web do Dataverse e ao Power BI, você pode melhorar o desempenho da consulta do Power Apps com base em tabelas virtuais do Dataverse, excluindo colunas de tabelas relacionadas do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-164">Similar to Dataverse Web API queries and Power BI, you can improve query performance for Power Apps based on Dataverse virtual tables by excluding columns of related tables from your app.</span></span> <span data-ttu-id="5cb7d-165">Se alguma coluna de uma tabela relacionada tiver sido incluída em uma página, a URL de solicitação construída para buscar os dados incluirá propriedades de chave estrangeira da tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-165">If any columns from a related table have been included on a page, then the request URL constructed to fetch the data will include foreign key properties of the related table.</span></span> <span data-ttu-id="5cb7d-166">Como nos exemplos anteriores de [Seleção de colunas em uma consulta OData](#selecting-columns-in-power-apps), isso reduz o desempenho levando a pesquisas de dados adicionais.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-166">This, as in the examples of [Selecting columns in an OData Query](#selecting-columns-in-power-apps) above, reduces performance by causing additional data lookups.</span></span>

<span data-ttu-id="5cb7d-167">Para solucionar isso, você pode validar que nenhum campo de dados de tabelas relacionadas foi incluído em formulários de dados do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-167">To work around this, you can validate that no data fields from related tables have been included on any data form of your Power App.</span></span>

1. <span data-ttu-id="5cb7d-168">No painel de exibição de árvore, selecione o formulário de dados para a tela.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-168">In the Tree view pane, select the data form for the screen.</span></span>
2. <span data-ttu-id="5cb7d-169">No painel **Propriedades**, selecione **Editar** na propriedade **Campos**.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-169">In the **Properties** pane, select **Edit** on the **Fields** property.</span></span>
3. <span data-ttu-id="5cb7d-170">No painel **Dados**, verifique se nenhum dos campos selecionados são campos da tabela virtual da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-170">In the **Data** pane, verify that none of the selected fields are fields of the virtual table of the data source.</span></span>

<span data-ttu-id="5cb7d-171">Por exemplo, se um dos campos de dados incluídos em uma página no aplicativo referenciar outra tabela, como **ThisItem.Worker.Name**, em que **Trabalhador** é a tabela relacionada, haverá potencial de redução no desempenho na busca dos dados.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-171">For example, if one of the data fields included on a page in the app references another table, such as **ThisItem.Worker.Name**, where **Worker** is the related table, there is a potential for reduced performance in fetching the data.</span></span>

<span data-ttu-id="5cb7d-172">Você pode usar o [Monitor do Power Apps](/powerapps/maker/monitor-overview) para garantir que somente as colunas necessárias sejam incluídas na consulta para obter os dados do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-172">You can use the [Power Apps Monitor](/powerapps/maker/monitor-overview) to ensure that only the columns you need are being included in the query to get the data for the Power App.</span></span> <span data-ttu-id="5cb7d-173">Você pode exibir a URL construída para a operação getRows para garantir que as colunas selecionadas para o seu aplicativo sejam ideais para a recuperação dos dados.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-173">You can view the URL constructed for the getRows operation to ensure the columns you have selected for your app will be optimal for retrieving the data.</span></span>

![Use o Monitor do Power Apps para analisar a operação getData](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a><span data-ttu-id="5cb7d-175">Filtrar a consulta de dados</span><span class="sxs-lookup"><span data-stu-id="5cb7d-175">Filtering the data query</span></span>

<span data-ttu-id="5cb7d-176">Outro método para melhorar o desempenho da execução da consulta é limitar o número de registros retornados nos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-176">Another method for improving query execution performance is to limit the number of records returned in the query results.</span></span> <span data-ttu-id="5cb7d-177">É possível fazer isso filtrando os resultados para garantir que você só receba os registros necessários.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-177">You can do this by filtering the results to ensure that you are only receiving the records you need.</span></span>

<span data-ttu-id="5cb7d-178">Consulte [Resultados do filtro](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) para obter mais informações sobre a filtragem de dados de consulta.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-178">See [Filter results](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) for more information on filtering query data.</span></span>

### <a name="limiting-the-page-size-of-the-query"></a><span data-ttu-id="5cb7d-179">Limitar o tamanho da página da consulta</span><span class="sxs-lookup"><span data-stu-id="5cb7d-179">Limiting the page size of the query</span></span>

<span data-ttu-id="5cb7d-180">Se você estiver trabalhando com grandes conjuntos de dados, poderá dividir os resultados da consulta em várias páginas adicionando o cabeçalho de preferência `odata.maxpagesize` a consultas de dados.</span><span class="sxs-lookup"><span data-stu-id="5cb7d-180">If you're working with large data sets, you can divide query results into multiple pages by adding the `odata.maxpagesize` preference header to data queries.</span></span>

<span data-ttu-id="5cb7d-181">Para obter mais informações sobre paginação, consulte [Especifique o número de entidades a serem retornadas em uma página](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span><span class="sxs-lookup"><span data-stu-id="5cb7d-181">For more information on paging, see [Specify the number of entities to return in a page](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).</span></span>

## <a name="see-also"></a><span data-ttu-id="5cb7d-182">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5cb7d-182">See also</span></span>

- [<span data-ttu-id="5cb7d-183">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="5cb7d-183">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)
- [<span data-ttu-id="5cb7d-184">Perguntas frequentes sobre tabelas virtuais do Human Resources</span><span class="sxs-lookup"><span data-stu-id="5cb7d-184">Human Resources virtual tables FAQ</span></span>](hr-admin-virtual-entity-faq.md)
- [<span data-ttu-id="5cb7d-185">Perguntas frequentes sobre limitação</span><span class="sxs-lookup"><span data-stu-id="5cb7d-185">Throttling FAQ</span></span>](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]