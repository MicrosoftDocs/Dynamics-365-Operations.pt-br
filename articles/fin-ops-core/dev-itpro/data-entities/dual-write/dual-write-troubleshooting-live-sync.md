---
title: Solucionar problemas de sincronização ao vivo
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.
author: RamaKrishnamoorthy
ms.date: 08/19/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 73a226d10c951179fd9f3bc2aed4a70efcc7f020
ms.sourcegitcommit: 98061a5d096ff4b9078d1849e2ce6dd7116408d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466235"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Solucionar problemas de sincronização ao vivo

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Microsoft Dataverse. Especificamente, ele fornece informações que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário do Azure Active Directory (Azure AD). Cada seção explica se uma função ou credenciais específicas são necessárias.

## <a name="live-synchronization-shows-an-error-when-you-create-a-row"></a>A sincronização dinâmica mostra um erro ao criar uma linha

Você pode receber a seguinte mensagem de erro ao criar uma linha em um aplicativo Finance and Operations:

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"O usuário não é um membro da organização.\\"}}\], O servidor remoto retornou um erro: (403) Proibido."}}".*

Para corrigir o problema, siga as etapas dos [pré-requisitos e requisitos do sistema](requirements-and-prerequisites.md). Para concluir essas etapas, os usuários do aplicativo de gravação dupla que foram criados no Dataverse precisam ter a função de administrador do sistema. A equipe de propriedade padrão também deve ter a função de administrador do sistema.

## <a name="live-synchronization-shows-an-error-when-you-try-to-save-table-data"></a>A sincronização dinâmica mostra um erro quando você tenta salvar os dados da tabela

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber a seguinte mensagem de erro ao tentar salvar os dados da tabela em um aplicativo do Finance and Operations:

*Não é possível salvar as alterações no banco de dados. A unidade de trabalho não pode confirmar a transação. Não é possível gravar dados no uoms da entidade. As gravações no UnitOfMeasureEntity falharam com a mensagem de erro. Não é possível sincronizar com a entidade uoms.*

Para corrigir o problema, verifique se os dados de referência de pré-requisito existem no aplicativo do Finance and Operations e no Dataverse. Por exemplo, se o registro de um cliente pertencer a um grupo de clientes específico, verifique se o registro do grupo de clientes existe no Dataverse.

Se houver dados nos dois lugares e você tiver confirmado que o problema não é relacionado a dados, siga estas etapas.

1. Abra a entidade **DualWriteProjectConfigurationEntity** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no suplemento do Excel no Finance and Operations e adicione **DualWriteProjectConfigurationEntity** a uma planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
2. Selecione e exclua os registros com problemas no mapa e projeto de gravação dupla. Haverá dois registros para todos os mapeamentos de gravação dupla.
3. Publique as alterações usando o suplemento do Excel. Esta etapa é importante porque exclui os registros da entidade e das tabelas subjacentes.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Manipular erros de privilégio de leitura ou gravação ao criar dados em um aplicativo Finance and Operations

Você pode receber uma mensagem de erro "Solicitação Incorreta" ao criar dados em um aplicativo do Finance and Operations.

![Exemplo da mensagem inválida de erro de solicitação.](media/error_record_id_source.png)

Para corrigir o problema, você precisa habilitar o privilégio ausente atribuindo o direito de acesso correto à equipe da unidade de negócios do Dynamics 365 Sales ou do Dynamics 365 Customer Service mapeada.

1. No aplicativo Finance and Operations, localize a unidade de negócios mapeada no conjunto de conexões de integração de dados.

    ![Mapeamento da organização.](media/mapped_business_unit.png)

2. No aplicativo de interação com o cliente, faça login no ambiente, acesse **Configurações \> Segurança** e encontre a equipe da unidade de negócios mapeada.

    ![Equipe da unidade de negócios mapeada.](media/setting_security_page.png)

3. Abra a página da equipe para edição e, em seguida, selecione **Gerenciar funções**.

    ![Gerenciar botão de funções.](media/manage_team_roles.png)

4. Na caixa de diálogo **Gerenciar funções da equipe**, atribua a função que tem o privilégio de leitura/gravação para as tabelas relevantes e selecione **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Corrigir problemas de sincronização em um ambiente que tem um ambiente Dataverse alterado recentemente

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber a seguinte mensagem de erro ao criar dados em um aplicativo Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable para gerar carga de trabalho para a entidade CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Criação de carga de trabalho falhada com erro de URI inválido: O URI está vazio."}\],"isErrorCountUpdated":true}*

Veja uma mensagem de erro no aplicativo de interação com o cliente:

> Ocorreu um erro inesperado no código do ISV. (ErrorType = ClientError) Exceção inesperada do plug-in (Executar): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: falha ao processar conta da entidade – Houve falha em uma tentativa de conexão porque a parte conectada não respondeu adequadamente após um período de tempo ou houve falha na conexão estabelecida porque o host não respondeu.

Este erro ocorre se o ambiente do Dataverse for redefinido incorretamente quando você tenta criar dados no aplicativo do Finance and Operations.

> [!IMPORTANT]
> Se você tiver vinculado novamente os ambientes, deverá interromper todos os mapas de entidade antes de continuar com as etapas de mitigação.

Para corrigir o problema, conclua as etapas no Dataverse e no aplicativo do Finance and Operations.

1. Siga estas etapas no aplicativo do Finance and Operations.

    1. Abra a entidade **DualWriteProjectConfigurationEntity** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no suplemento do Excel no Finance and Operations e adicione **DualWriteProjectConfigurationEntity** a uma planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
    2. Selecione e exclua os registros com problemas no mapa e projeto de gravação dupla. Haverá dois registros para todos os mapeamentos de gravação dupla.
    3. Publique as alterações usando o suplemento do Excel. Esta etapa é importante porque exclui os registros da entidade e das tabelas subjacentes.
    4. Para ajudar a evitar erros ao vincular novamente os ambientes do Finance and Operations ou Dataverse, verifique se as configurações de gravação dupla permanecem.

2. Execute estas etapas no Dataverse:

    1. Faça login no ambiente do Dataverse (por exemplo, `https://*****.crm.dynamics.com/`).
    2. Vá para **Configurações Avançadas** \> **Localização Avançada**.
    3. Selecione **Configuração de tempo de execução de gravação dupla**.
    4. Selecione a coluna a ser exibida.
    5. Selecione **Resultados** para exibir as configurações.
    6. Exclua todas as instâncias.

3. Siga estas etapas no aplicativo do Finance and Operations.

    1. Abra a entidade **DualWriteProjectConfigurationEntity** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no suplemento do Excel no Finance and Operations e adicione **DualWriteProjectConfigurationEntity** a uma planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
    2. Selecione e exclua os registros com problemas no mapa e projeto de gravação dupla. Haverá dois registros para todos os mapeamentos de gravação dupla.
    3. Publique as alterações usando o suplemento do Excel. Esta etapa é importante porque exclui os registros da entidade e das tabelas subjacentes.
    4. Para ajudar a evitar erros ao vincular novamente os ambientes do Finance and Operations ou Dataverse, verifique se as configurações de gravação dupla permanecem.

## <a name="live-synchronization-error-after-you-do-a-full-database-copy"></a>Erro de sincronização dinâmica depois de fazer uma cópia completa do banco de dados

A seguinte mensagem de erro poderá ser exibida após você executar uma cópia de todo o banco de dados de um sistema para outro e depois tentar executar uma operação de banco de dados:

*A Organização SecureConfig (???) não corresponde à Organização de CRM real (???).*

A mensagem de erro é mostrada no plug-in de tempo de execução de gravação dupla para garantir que a configuração de gravação dupla configurada em um sistema não possa ser usada em outro sistema.

Para corrigir o problema, exclua todos os registros na tabela **msdyn_dualwriteruntimeconfig** depois de restaurar o banco de dados. Para obter mais informações, consulte [Desvincular e vincular novamente ambientes de gravação dupla](relink-environments.md).

## <a name="live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps"></a>Problemas de sincronização dinâmica causados por sintaxe incorreta de filtro de consulta nos mapas de gravação dupla

Embora a expressão de consulta para um filtro de mapa de gravação dupla esteja sintaticamente correta, talvez ela não funcione conforme o esperado. A expressão de filtro está em uma entidade, não em uma fonte de dados individual de um objeto de consulta. Portanto, a consulta SQL gerada não retorna os resultados esperados.

Veja aqui um exemplo.

```dos
Query entity = PROJECTENTITY
Query expression = (ParentProject == "")
```

Talvez você espere que os projetos sem pai sejam filtrados. No entanto, o filtro não funciona porque ele é traduzido para uma consulta semelhante ao exemplo a seguir.

```sql
SELECT T1.RECID,T1.MODIFIEDDATETIME,T1.RECVERSION,T1.RECID,T1.DIMENSION,
T1.LOCATION,T1.PROJECTCONTROLLER,T1.PROJECTID,T1.PROJECTMANAGER,T1.REFERENCE,
T1.SALESMANAGER,T1.SCHEDULED,T1.RECVERSION#8,T1.RECVERSION#7,
T1.RECVERSION#6,T1.RECVERSION#5,T1.RECVERSION#4,T1.RECVERSION#3,
T1.RECVERSION#2,T1.RECID#8,T1.RECID#7,T1.RECID#6,T1.RECID#5,
T1.RECID#4,T1.RECID#3,T1.RECID#2,T1.PARTITION FROM PROJECTENTITY T1 
WHERE(((((((((((PARTITION=5637144576) AND (DATAAREAID=N'usmf')) AND 
((PARTITION#2=5637144576) OR (PARTITION#2 IS NULL))) AND 
((PARTITION#3=5637144576) OR (PARTITION#3 IS NULL))) AND 
((PARTITION#4=5637144576) OR (PARTITION#4 IS NULL))) AND 
((PARTITION#5=5637144576) OR (PARTITION#5 IS NULL))) AND 
((PARTITION#6=5637144576) OR (PARTITION#6 IS NULL))) AND 
((PARTITION#7=5637144576) OR (PARTITION#7 IS NULL))) AND 
((PARTITION#8=5637144576) OR (PARTITION#8 IS NULL))) AND 
((DATAAREAID#8=N'usmf') OR (DATAAREAID#8 IS NULL))) AND 
(PARENTPROJECT='')) 
ORDER BY T1.PROJECTID
```

O resultado real é que o campo `parentProject` é avaliado como `null`. No entanto, `null` não é o mesmo que a cadeia de caracteres vazia. Por causa dessa incompatibilidade, o filtro de consulta não retorna resultados válidos.

Para corrigir o problema, siga estas etapas.

1. Adicione uma coluna computada que possa ser adicionada a um modelo de extensão e que tenha respaldo da lógica que converte `null` para a cadeia de caracteres vazia.

    ```dos
    SysComputedColumn::if(SysComputedColumn::isNullExpression(ParentProject), SysComputedColumn::returnLiteral(""), fieldName);
    ```

2. Use o filtro na nova coluna computada em vez da coluna padrão.

Para avaliar o filtro em um ambiente de desenvolvimento, use o código X++ a seguir para validar os resultados. Execute esse código como um programa independente. Você pode usá-lo para avaliar diferentes tipos de filtro que são aplicáveis a uma entidade antes de usar esses filtros em mapas de gravação dupla. A consulta pode ser executada no banco de dados para avaliar discrepâncias.

```xpp
var entityName = "PROJECTENTITY";
var filterExpression = '(ParentProject == "")';
Query query = new Query();
query.literals(NoYes::Yes); 
QueryBuildDataSource qbd = query.addDataSource(tablename2id(entityName));
qbd.addRange(fieldname2id(qbd.table(),identifierStr(RecVersion))).value(filterExpression);
qbd.addSelectionField(fieldname2id(qbd.table(),identifierStr(RecId)));
QueryRun qRun = new QueryRun(query);
// This provides the actual sql statement to execute
var actualSqlStatement = query.getSQLStatement();
while(qRun.next())
{
    var rec = qRun.get(tableName2Id(entityName));
}
```

## <a name="data-from-finance-and-operations-apps-isnt-synced-to-dataverse"></a>Os dados dos aplicativos do Finance and Operations não são sincronizados com o Dataverse

Durante a sincronização dinâmica, talvez você encontre um problema em que somente parte dos dados são sincronizados dos aplicativos do Finance and Operations com o Dataverse, ou nenhum dado é sincronizado.

> [!NOTE]
> Você precisa corrigir esse problema durante o desenvolvimento.

Antes de começar a corrigir o problema, revise os seguintes pré-requisitos:

+ Verifique se as alterações personalizadas foram gravadas em um único escopo de transação.
+ Os eventos de negócios e a estrutura de gravação dupla não tratam as operações `doinsert()`, `doUpdate()` e `recordset()`, ou os registros em que `skipBusinessEvents(true)` está marcado. Se seu código estiver dentro dessas funções, a gravação dupla não será disparada.
+ Os eventos de negócios precisam ser registrados para a fonte de dados mapeada. Algumas fontes de dados podem usar uma junção externa e ser marcadas como somente leitura nos aplicativos do Finance and Operations. Essas fontes de dados não são rastreadas.
+ As alterações só serão disparadas se as modificações estiverem nos campos mapeados. As modificações no campo não mapeado não disparam a gravação dupla.
+ Verifique se as avaliações de filtro fornecem um resultado válido.

### <a name="troubleshooting-steps"></a>Etapas de solução de problemas

1. Revise os mapeamentos de campos na página de administração de gravação dupla. Se um campo não for mapeado dos aplicativos do Finance and Operations para o Dataverse, ele não será rastreado. Por exemplo, na ilustração a seguir, o campo **Descrição** é rastreado do Dataverse, mas não dos aplicativos do Finance and Operations. Nenhuma alteração feita nesse campo dentro dos aplicativos do Finance and Operations será rastreada.

    ![Campo rastreado.](media/live-sync-troubleshooting-1.png)

2. Determine se a fonte de dados é rastreada na definição de eventos de negócios. Por exemplo, na ilustração a seguir, nenhum campo da tabela **DefaultDimensionDAVs** e das tabelas subjacentes terá as alterações rastreadas. As fontes de dados que usam uma junção externa e que são marcadas como somente leitura não são rastreadas.

    ![Campo não rastreado.](media/live-sync-troubleshooting-2.png)

3. Determine se os campos de tabela mapeados serão exibidos na tabela **BUSINESSEVENTSDEFINITION**, conforme mostrado na ilustração a seguir. Se você não localizar o campo que está procurando no resultado da consulta, ele não será disparado por uma gravação dupla.

    ![Campo rastreado na tabela.](media/live-sync-troubleshooting-3.png)

### <a name="sample-scenario"></a>Cenário de exemplo

Nos aplicativos do Finance and Operations, há uma atualização para o endereço de um registro de contato, mas a alteração de endereço não é sincronizada com o Dataverse. Esse cenário ocorre porque nenhum registro na tabela **BusinessEventsDefinition** tem a combinação da tabela e da entidade afetados. Especificamente, a tabela **LogisticsPostalAddress** não é a fonte de dados direta da entidade **smmContactpersonCDSV2Entity**. A entidade **smmContactpersonCDSV2Entity** tem **smmContactPersonV2Entity** como a fonte de dados, e **smmContactPersonV2Entity**, por sua vez, tem **LogisticsPostalAddressBaseEntity** como a fonte de dados. A tabela **LogisticsPostalAddress** é a fonte de dados para **LogisticsPostalAddressBaseEntity**.

Uma situação semelhante pode ocorrer em alguns casos não-padrão, como aqueles em que a tabela sendo modificada nos aplicativos do Finance and Operations não está obviamente vinculada à entidade que a contém. Por exemplo, os dados de endereço principal são computados na entidade **smmContactPersonCDSV2Entity**. A estrutura de gravação dupla tenta determinar como uma alteração em uma tabela subjacente é mapeada de volta para entidades. Normalmente, essa abordagem é suficiente. No entanto, em alguns casos, o vínculo é tão complexo que precisa ser específico. Você deve verificar se a **RecId** da tabela relacionada está disponível diretamente na entidade. Em seguida, adicione um método estático para monitorar alterações na tabela.

Para ver um exemplo, revise o método **smmContactPersonCDSV2Entity::getEntityDataSourceToFieldMapping()**. **CustCustomerV3entity** e **VendVendorV2Entity** foram modificadas para tratar dessa situação.

Para corrigir o problema, siga estas etapas.

1. Adicione um campo **PrimaryPostalAddressRecId** à entidade **smmContactPersonV2Entity**. Torne-o interno.

    ![Campo adicionado à entidade smmContactPersonV2Entity.](media/Troubleshoot_live_sync_issue_1.png)

2. Adicione o mesmo campo à entidade **smmContactPersonCDSV2Entity**.

    ![Campo adicionado à entidade smmContactPersonCDSV2Entity.](media/Troubleshoot_live_sync_issue_2.png)

3. Adicione o seguinte método à classe **smmContactPersonCDSV2Entity**.

    ```xpp
    public static container getEntityDataSourceToFieldMapping(container mapping)
    {
        mapping += [[tablestr(smmContactPersonCDSV2Entity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)]];
        return mapping;
    }
    ```

4. Sincronize o banco de dados e crie o aplicativo.
5. Interrompa todos os mapas de gravação dupla que são criados na entidade **smmContactPersonCDSV2Entity**.
6. Inicie o mapa. Você verá a nova tabela (**LogisticsPostalAddress** neste exemplo) que começou a rastrear usando a coluna **RefTableName** para a linha em que o valor **refentityname** é igual a **smmContactPersonCDSV2Entity** na tabela **BusinessEventsDefinition**.

## <a name="error-when-you-create-a-record-where-multiple-records-are-sent-from-a-finance-and-operations-app-to-dataverse-in-the-same-batch"></a>Erro ao criar um registro no qual vários registros são enviados de um aplicativo do Finance and Operations para o Dataverse no mesmo lote

Para qualquer transação, um aplicativo do Finance and Operations cria dados em um lote e os envia como um lote para Dataverse. Se dois registros são criados como parte da mesma transação e eles fazem referência entre si, você poderá receber uma mensagem de erro semelhante ao seguinte exemplo no aplicativo do Finance and Operations:

*Não é possível gravar dados na entidade aaa_fundingsources. Não é possível procurar ebecsfs_contracts com valores {PC00...}. Não é possível procurar aaa_fundingsources com valores {PC00...}. Falha nas gravações do aaa_fundingsources com a mensagem de erro de exceção: o servidor remoto retornou um erro: (400) solicitação incorreta.*

Para corrigir o problema, crie relações de entidades no aplicativo do Finance and Operations para indicar que as duas entidades estão relacionadas entre si e que os registros relacionados são manuseados na mesma transação.

## <a name="enable-verbose-logging-of-error-messages"></a>Habilitar o log detalhado de mensagens de erro

Em um aplicativo do Finance and Operations, é possível encontrar erros relacionados ao ambiente do Dataverse. Talvez a mensagem de erro não contenha o texto completo da mensagem ou outros dados relevantes. Para obter mais informações, habilite o log detalhado definindo o sinalizador **IsDebugMode** presente na entidade **DualWriteProjectConfigurationEntity** em todas as configurações de projeto nos aplicativos do Finance and Operations.

1. Abra a entidade **DualWriteProjectConfigurationEntity** usando um suplemento do Excel. Para usar o suplemento, habilite o modo de design no suplemento do Excel no Finance and Operations e adicione **DualWriteProjectConfigurationEntity** a uma planilha. Para obter mais informações, consulte [Exibir e atualizar dados da entidade com o Excel](../../office-integration/use-excel-add-in.md).
2. Defina o sinalizador **IsDebugMode** como **Sim** no projeto.
3. Execute o cenário.
4. Os logs detalhados estão disponíveis na tabela **DualWriteErrorLog**. Para pesquisar dados usando o navegador de tabela, use a seguinte URL: `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`.
5. Para capturar mais logs no modo de depuração, instale a atualização em [KB 4595434 (correção para valores em branco que estão sendo propagados em sincronização dinâmica de gravação dupla)](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=c29ce15a80e6b3b4c01a722d9bdae1d7e71aa3662a044cfd0b765f736cfa98e9).

## <a name="error-when-you-add-an-address-for-a-customer-or-contact"></a>Erro ao adicionar um endereço para um cliente ou contato

Talvez você receba a seguinte mensagem de erro ao tentar adicionar um endereço para um cliente ou contato nos aplicativos do Finance and Operations ou no Dataverse:

*Não é possível gravar dados na entidade msdyn_partypostaladdresses. Falha nas gravações em DirPartyPostalAddressLocationCDSEntity com a mensagem de erro Falha na solicitação com código de status Solicitação Incorreta e código de erro de CDS: mensagem de resposta0x80040265: Ocorreu um erro no plugin. Já existe um registro com a ID de local de valores de atributo. A chave ID da localização da chave da entidade requer que esse conjunto de atributos contenha valores exclusivos. Selecione valores exclusivos e tente novamente.*

Para corrigir o problema, instale o pacote de orquestração de gravação dupla versão (2.2.2.60). Assim, as chaves na tabela **Endereço** são definidas como mostra a tabela a seguir.

| Propriedade | Alíquota |
|---|---|
| Nome para Exibição | **Chave de local** |
| Organização | **msdyn_locationkey** |
| Campos | **msdyn_locationid**, **parentid** |
| Status | **Com Atividade** |
| Trabalho do sistema | Em Branco |

## <a name="error-when-you-add-a-customer-in-dataverse"></a>Erro ao adicionar um cliente no Dataverse

Você pode receber a seguinte mensagem de erro ao tentar adicionar um cliente no Dataverse:

*"RecordError0":"Falha na gravação para Clientes v3 da entidade exceção desconhecida – Registro do participante não encontrado para o tipo de participante 'Organização'"}.*

Quando um cliente é criado no Dataverse, um novo número de participante é gerado. A mensagem de erro é mostrada quando o registro do cliente, junto com o participante, é sincronizado com os aplicativos do Finance and Operations, mas já existe um registro de cliente que tem um número de participante diferente.

Para corrigir o problema, localize o cliente por meio da pesquisa do participante. Se o cliente não existir, crie um registro para ele. Se o cliente existir, use o participante existente para criar o novo registro de cliente.

## <a name="error-when-you-create-a-new-customer-vendor-or-contact-in-dataverse"></a>Erro ao criar um novo cliente, fornecedor ou contato no Dataverse

Talvez você receba a seguinte mensagem de erro ao tentar criar um novo cliente, fornecedor ou contato no Dataverse:

*Não é possível atualizar o tipo de participante de "DirOrganization" para "DirPerson". Em vez disso, exclua o participante existente e, em seguida, o insira com o novo tipo.*

No Dataverse, há uma sequência numérica na tabela **msdyn_party**. Quando uma conta é criada no Dataverse, um novo participante é criado (por exemplo, **Party-001** do tipo **Organização**). Esses dados são enviados para o aplicativo do Finance and Operations. Se o ambiente do Dataverse for redefinido ou o ambiente do Finance and Operations estiver vinculado a um ambiente diferente do Dataverse e um novo registro de contato for criado no Dataverse, será criado um novo valor de participante que comece com **Party-001**. Desta vez, o registro de participante criado será **Party-001** do tipo **Pessoa**. Quando esses dados são sincronizados, os aplicativos do Finance and Operations mostram a mensagem de erro anterior, pois o registro de participante **Party-001** do tipo **Organização** já existe.

Para corrigir o problema, altere a sequência numérica automática do campo **msdyn_partynumber** da tabela **msdyn_party** no Dataverse para uma sequência numérica automática diferente.

## <a name="performance-issue-with-customer-or-contact-mappings"></a>Problema de desempenho com mapeamentos de cliente ou de contato

Talvez seja possível melhorar a margem de desempenho da sincronização dinâmica para clientes e contatos personalizando o método **getEntityDataSourceToFieldMapping** (na entidade **CustCustomerV3Entity**) e o método **getEntityDataSourceToFieldMapping** (na entidade **smmContactPersonCDSV2Entity**). Essas personalizações reduzem o número de registros na tabela **BusinessEventsDefinition**. Essa redução no número de registros, por sua vez, reduz o número de eventos que são gerados.

O método **getEntityDataSourceToFieldMapping** na entidade **CustCustomerV3Entity** verifica se uma atualização do endereço eletrônico ou endereço postal do cliente dispara eventos de negócios para que os dados atualizados sejam enviados para o Dataverse. Se você não usar todos os campos e não precisar das informações em gravação dupla, comente as linhas apropriadas no método. Cada campo e tabela rastreados que são adicionados nesse método adiciona um registro na tabela **BusinessEventsDefinition** para a combinação da tabela e da entidade rastreadas.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, AddressRecordId)],
        [identifierstr(DirPartyBaseEntity), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactURLRecordId)],
        [identifierstr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactPhoneRecordId)],
        [identifierstr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactEmailRecordId)],
        [identifierstr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(CustCustomerV3Entity, PrimaryContactFaxRecordId)],
        [identifierstr(DirPartyBaseEntity4), tablenum(DirPartyLocation), fieldstr(CustCustomerV3Entity, DirPartyLocationRecordId)],
        [identifierstr(DirPartyBaseEntity5), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, InvoiceAddressRecordId)],
        [identifierstr(DirPartyBaseEntity6), tablenum(LogisticsPostalAddress), fieldstr(CustCustomerV3Entity, DeliveryAddressRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(DirPartyTable), fieldstr(CustCustomerV3Entity, PartyRecordId)]];
    return mapping;
}
```

Da mesma forma, o método **getEntityDataSourceToFieldMapping** na entidade **smmContactPersonCDSV2Entity** verifica se qualquer atualização do endereço eletrônico ou endereço postal do contato dispara eventos de negócios para que os dados atualizados sejam enviados para o Dataverse. No método, você pode comentar as linhas para os campos que não usa.

```xpp
public static container getEntityDataSourceToFieldMapping(container mapping)
{
    mapping += [
        [tablestr(DirPartyBaseEntity), tablenum(LogisticsPostalAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryPostalAddressRecId)],
        [identifierStr(DirPartyBaseEntity), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PrimaryAddressLocation)],
        [identifierStr(DirPartyBaseEntity1), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactEmailRecordId)],
        [identifierStr(DirPartyBaseEntity2), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFaxRecordId)],
        [identifierStr(DirPartyBaseEntity3), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactPhoneRecordId)],
        [identifierStr(DirPartyBaseEntity4), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactFacebookRecordId)],
        [identifierStr(DirPartyBaseEntity5), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTwitterRecordId)],
        [identifierStr(DirPartyBaseEntity6), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactURLRecordId)],
        [identifierStr(DirPartyBaseEntity7), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactLinkedInRecordId)],
        [identifierStr(DirPartyBaseEntity8), tablenum(LogisticsElectronicAddress), fieldstr(smmContactPersonCDSV2Entity, PrimaryContactTelexRecordId)],
        [identifierStr(DirPartyBaseEntity9), tablenum(DirPartyTable), fieldstr(smmContactPersonCDSV2Entity, PartyRecordId)]];
    return mapping;
}
```

Depois de atualizar os métodos, siga estas etapas.

1. Sincronize o banco de dados e crie o aplicativo.
2. Interrompa todos os mapas de gravação dupla nas entidades **smmContactPersonCDSV2Entity** e **CustCustomerV3Entity**.
3. Inicie os mapas. Você deve ver menos registros nas entidades **smmContactPersonCDSV2Entity** e **CustCustomerV3Entity** e na tabela **BusinessEventsDefinition**, e o desempenho pode ser marginalmente melhorado.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
