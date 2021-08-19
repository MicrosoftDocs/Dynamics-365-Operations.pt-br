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
ms.openlocfilehash: 40fc4c06c563415cd5b1a13c145b778276274fd97279dc9f56ff5e3f8954dc76
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732000"
---
# <a name="optimize-dataverse-virtual-table-queries"></a>Otimizar consultas de tabela virtual do Dataverse

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="issue"></a>Problema

### <a name="overview"></a>Visão Geral

Ao usar tabelas virtuais do Dataverse para desenvolver integrações e outras conexões de dados com o Dynamics 365 Human Resources, você pode ter problemas de desempenho com consultas nas tabelas virtuais. A execução de consulta lenta pode ocorrer em vários clientes ou interfaces. Por exemplo, o problema pode ocorrer nas seguintes circunstâncias:

- Ao consultar uma tabela virtual por meio da API Web do Dataverse
- Ao criar um Power App em uma tabela virtual
- Ao criar um relatório do Power BI em uma tabela virtual

Todas essas interfaces têm o potencial de destacar o problema de desempenho.

Uma causa do baixo desempenho com tabelas virtuais do Dataverse para o Human Resources são as colunas de chave estrangeira da tabela virtual relacionada a [propriedades de navegação](/powerapps/developer/data-platform/webapi/web-api-types-operations#navigation-properties) da tabela. Quando as propriedades de navegação são criadas para uma tabela virtual, uma coluna de chave estrangeira é adicionada automaticamente à tabela para representar o valor da chave da coluna de chave da tabela virtual relacionada. Por exemplo, a coluna **_mshr_fk_person_id_value** é adicionada à entidade **mshr_hcmworkerbaseentity** com a propriedade de chave estrangeira da entidade **mshr_dirpersonentity**. Devido à forma como os valores dessas colunas de chave estrangeira são mantidos em uma tabela, a busca de valores pode ter um impacto negativo no desempenho de uma consulta na tabela virtual.

### <a name="potential-symptoms"></a>Sintomas potenciais

Um exemplo em que você pode ver esse impacto está nas consultas sobre a entidade Trabalhador (**mshr_hcmworkerentity**) ou Trabalhador base (**mshr_hcmworkerbaseentity**). Você pode ver o próprio manifesto de problema de desempenho de diferentes maneiras:

- **Execução lenta de consulta**: a consulta na tabela virtual pode retornar os resultados esperados, mas levar um tempo além do esperado para concluir a execução da consulta.
- **Tempo limite da consulta**: a consulta pode expirar e retornar o seguinte erro: "Foi obtido um token para chamar o Finance and Operations, mas o Finance and Operations retornou um erro do tipo InternalServerError".
- **Erro inesperado**: a consulta pode retornar um tipo de erro 400 com a seguinte mensagem: "Ocorreu um erro inesperado".

  ![Tipo de erro 400 em HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType400.png)

- **Limitação**: a consulta pode usar excessivamente recursos do servidor e ficar sujeita à limitação. Nesse caso, a consulta retorna o seguinte erro: "Foi obtido um token para chamar o Finance and Operations, mas o Finance and Operations retornou um erro do tipo 429". Para obter mais informações sobre a limitação no Human Resources, consulte [Perguntas frequentes sobre limitação](./hr-admin-integration-throttling-faq.md).

  ![Tipo de erro 429 em HcmWorkerBaseEntity.](./media/HcmWorkerBaseEntityErrorType429.png)

## <a name="resolution"></a>Resolução

### <a name="limit-the-number-of-columns-included-in-your-data-query"></a>Limitar o número de colunas incluídas na consulta de dados

Com tabelas virtuais, um dos métodos com o maior potencial para melhorar o desempenho da consulta é limitar o número de colunas selecionadas na consulta. A orientação geral para otimizar o desempenho da consulta é limitar as colunas retornadas na consulta somente às propriedades necessárias. Isso é verdadeiro especialmente nas colunas de chave estrangeira em tabelas virtuais. Se você não precisar dos valores nas colunas de chave estrangeira para integração ou relatório, estruture a consulta para selecionar apenas as colunas necessárias, excluindo as colunas de chave estrangeira.

#### <a name="selecting-columns-in-an-odata-query"></a>Selecionar colunas em uma consulta OData

Ao consultar uma tabela virtual por meio da API Web do Dataverse, você pode limitar o número de colunas incluídas na consulta usando a opção de consulta de sistema **$select** e definir as colunas para as quais você precisa do retorno de resultados. Para maximizar o desempenho, exclua colunas de chave estrangeira (com o prefixo **_mshr_FK_**) da consulta.

Por exemplo, a consulta a seguir sobre a entidade **mshr_hcmworkerbaseentity** incluirá somente as colunas incluídas na cláusula de opção de consulta **$select**, excluindo os valores de chave estrangeira. Isso traz melhorias significativas no desempenho em uma consulta que inclui todas as colunas da tabela.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas, mshr_professionaltitle, mshr_nativelanguageid, mshr_disabledverificationdate, mshr_personalsuffix, mshr_lastnameprefix, mshr_personbirthcity, mshr_personaltitle, mshr_phoneticlastname, mshr_namesequencedisplayas, mshr_personbirthcountryregion, mshr_isdisabled, mshr_birthdate, mshr_professionalsuffix, mshr_isfulltimestudent, mshr_education, mshr_namealias, mshr_phoneticmiddlename, mshr_personnelnumber, mshr_hcmworkerbaseentityid, mshr_motherbirthcountryregion, mshr_fatherbirthcountryregion, mshr_lastname, mshr_languageid, mshr_partytype, mshr_ethnicoriginid, mshr_citizenshipcountryregion HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

A recomendação para limitar o número de colunas selecionadas também se aplica ao utilizar a opção de consulta **$expand** para expandir a consulta a tabelas virtuais relacionadas por meio de propriedades de navegação. Por exemplo, a consulta a seguir inclui colunas da entidade **mshr_hcmworkerbaseentity** com colunas expandidas da entidade **mshr_dirpersonentity**. Observe que a opção de consulta **$select** também está incluída na cláusula de opção de consulta **$expand**.

```http
GET [Organization URI]/api/data/v9.1/mshr_hcmworkerbaseentities?$select=mshr_name, mshr_firstname, mshr_gender, mshr_partynumber, mshr_phoneticfirstname, mshr_deceaseddate, mshr_nationalitycountryregion, mshr_allowrehire, mshr_electroniclocationid, mshr_middlename, mshr_knownas&$expand=mshr_FK_Person_id($select=mshr_addressstreet, mshr_addresscity, mshr_addressstate, mshr_addresszipcode) HTTP/1.1
Accept: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0
```

Ao usar esse método de recuperação de dados com a opção de consulta **$select** na cláusula de opção de consulta **$expand**, você em geral verá maiores melhorias de desempenho quando a propriedade de navegação entre as entidades for uma relacionamentos muitos para um. Talvez você não veja a mesma redução no tempo de execução da consulta ao expandir um relacionamento um para muitos. Para obter mais informações sobre a definição de relacionamentos de tabelas virtuais do Dataverse, consulte [Relacionamentos de tabela](/powerapps/maker/data-platform/create-edit-entity-relationships).

Para obter mais informações sobre como usar as opções de consulta do sistema **$select** e **$expand** na API Web do Dataverse, consulte [Recuperar registros de entidades relacionadas com uma consulta](/powerapps/developer/data-platform/webapi/retrieve-related-entities-query).

#### <a name="selecting-columns-in-power-bi"></a>Selecionar colunas no Power BI

Se você tiver uma das indicações mencionadas anteriormente de baixo desempenho ao criar um relatório do Power BI em uma tabela virtual do Dataverse, poderá melhorar o desempenho excluindo colunas de chave estrangeira das colunas selecionadas da tabela para o relatório. Por exemplo, se você estiver usando o Power BI Desktop para criar um relatório na entidade **mshr_hcmworkerbaseentity**, poderá usar as etapas a seguir para selecionar as colunas que deseja incluir na consulta de relatório.

1. No Power BI Desktop, selecione **Mais...** na lista suspensa **Obter dados** na faixa de opções de ação.
2. Na janela **Obter Dados**, insira **Common Data Service** na caixa de pesquisa, selecione o conector **Common Data Service** e selecione **Conectar**.
3. No campo **URL do Servidor** da janela Common Data Service, insira o URI da organização para o ambiente do Dataverse e selecione **OK**.
  
   ![Insira o URI do ambiente do Dataverse.](./media/PowerBIDataverseURLSetup.png)
  
4. Na janela Navegador, expanda o nó **Entidades**.
5. Na caixa de pesquisa, insira **mshr_hcmworkerbaseentity** e selecione a entidade.
6. Selecione **Transformar Dados**.
7. Na janela do Editor do Power Query, selecione **Editor Avançado**.
8. Na janela **Editor Avançado**, atualize a consulta para ter a aparência a seguir, adicionando ou removendo colunas da matriz, conforme necessário.

   ```
   let
     Source = Cds.Entities("[Your Organization URI]", [ReorderColumns=null, UseFormattedValue=null]),
     entities = Source{[Group="entities"]}[Data],
     mshr_hcmworkerbaseentities = entities{[EntitySetName="mshr_hcmworkerbaseentities"]}[Data],
     selectedWorkerBaseEntityColumns=Table.SelectColumns(mshr_hcmworkerbaseentities,{"mshr_name","mshr_partynumber", "mshr_professionaltitle","mshr_birthdate"})
   in
     selectedWorkerBaseEntityColumns
   ```
   ![Atualize a consulta no Editor Avançado para o Editor do Power Query.](./media/HcmWorkerBaseEntityPowerQueryEditor.png)

9. Selecione **Concluído**.

   > [!NOTE]
   > Se você recebeu anteriormente um erro do tipo 429 da consulta antes da atualização, talvez precise aguardar o período de novas tentativas antes de atualizar a consulta para que ela seja concluída com êxito.

10. Clique em **Fechar e Aplicar** na faixa de opções de ação do Editor do Power Query.

Você poderá começar a criar o relatório do Power BI nas colunas selecionadas a partir da tabela virtual.

#### <a name="selecting-columns-in-power-apps"></a>Selecionar colunas no Power Apps

Semelhante às consultas de API Web do Dataverse e ao Power BI, você pode melhorar o desempenho da consulta do Power Apps com base em tabelas virtuais do Dataverse, excluindo colunas de tabelas relacionadas do seu aplicativo. Se alguma coluna de uma tabela relacionada tiver sido incluída em uma página, a URL de solicitação construída para buscar os dados incluirá propriedades de chave estrangeira da tabela relacionada. Como nos exemplos anteriores de [Seleção de colunas em uma consulta OData](#selecting-columns-in-power-apps), isso reduz o desempenho levando a pesquisas de dados adicionais.

Para solucionar isso, você pode validar que nenhum campo de dados de tabelas relacionadas foi incluído em formulários de dados do Power Apps.

1. No painel de exibição de árvore, selecione o formulário de dados para a tela.
2. No painel **Propriedades**, selecione **Editar** na propriedade **Campos**.
3. No painel **Dados**, verifique se nenhum dos campos selecionados são campos da tabela virtual da fonte de dados.

Por exemplo, se um dos campos de dados incluídos em uma página no aplicativo referenciar outra tabela, como **ThisItem.Worker.Name**, em que **Trabalhador** é a tabela relacionada, haverá potencial de redução no desempenho na busca dos dados.

Você pode usar o [Monitor do Power Apps](/powerapps/maker/monitor-overview) para garantir que somente as colunas necessárias sejam incluídas na consulta para obter os dados do Power Apps. Você pode exibir a URL construída para a operação getRows para garantir que as colunas selecionadas para o seu aplicativo sejam ideais para a recuperação dos dados.

![Use o Monitor do Power Apps para analisar a operação getData.](./media/HcmWorkerBaseEntityPowerAppsMonitor.png)

### <a name="filtering-the-data-query"></a>Filtrar a consulta de dados

Outro método para melhorar o desempenho da execução da consulta é limitar o número de registros retornados nos resultados da consulta. É possível fazer isso filtrando os resultados para garantir que você só receba os registros necessários.

Consulte [Resultados do filtro](/powerapps/developer/data-platform/webapi/query-data-web-api#filter-results) para obter mais informações sobre a filtragem de dados de consulta.

### <a name="limiting-the-page-size-of-the-query"></a>Limitar o tamanho da página da consulta

Se você estiver trabalhando com grandes conjuntos de dados, poderá dividir os resultados da consulta em várias páginas adicionando o cabeçalho de preferência `odata.maxpagesize` a consultas de dados.

Para obter mais informações sobre paginação, consulte [Especifique o número de entidades a serem retornadas em uma página](/powerapps/developer/data-platform/webapi/query-data-web-api#specify-the-number-of-entities-to-return-in-a-page).

## <a name="see-also"></a>Consulte também

- [Configurar tabelas virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
- [Perguntas frequentes sobre tabelas virtuais do Human Resources](hr-admin-virtual-entity-faq.md)
- [Perguntas frequentes sobre limitação](./hr-admin-integration-throttling-faq.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]