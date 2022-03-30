---
title: Atualizar para o modelo de catálogo de endereços global e de participantes
description: Este tópico descreve como atualizar dados de gravação dupla para o modelo de catálogo de endereços global e do participante.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 95d272d9076f1ab25230e4efa98e321bdd618062
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407785"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Atualizar para o modelo de catálogo de endereços global e de participantes

[!include [banner](../../includes/banner.md)]



Os [modelos do Microsoft Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema) ajudam você a atualizar os dados existentes das tabelas **Conta**, **Contato** e **Fornecedor** em uma gravação dupla para o modelo de catálogo de endereços global e do participante.

Os três modelos de Data Factory a seguir são fornecidos. Eles ajudam a reconciliar os dados dos aplicativos Finanças e operações e Customer Engagement.

- **[Modelo de participante](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/arm_template.json) (atualizar dados para esquema Participante-GAB de gravação dupla/arm_template.json)** – esse modelo ajuda a atualizar dados de **Participante** e de **Contato** associados a dados de **Conta**, **Contato** e **Fornecedor**.
- **[Modelo de endereço postal do participante](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Postal%20Address%20-%20GAB/arm_template.json) (atualizar dados para participante de esquema Participante-GAB de gravação dupla/atualizar para endereço postal do participante-GAB/arm_template.json)** – esse modelo ajuda a atualizar os endereços postais associados aos dados de **Conta**, **Contato** e **Fornecedor**.
- **[Modelo de endereço eletrônico do participante](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/Upgrade%20to%20Party%20Electronic%20Address%20-%20GAB/arm_template.json) (atualizar dados para participante de esquema Participante-GAB de gravação dupla/atualizar para endereço eletrônico do participante-GAB/arm_template.json)** – esse modelo ajuda a atualizar os endereços eletrônicos associados aos dados de **Conta**, **Contato** e **Fornecedor**.

No final do processo, são gerados os arquivos de valores separados por vírgula (.csv) a seguir.

| Nome do arquivo | Finalidade |
|---|---|
| FONewParty.csv | Este arquivo ajuda a criar novos registros de **Participante** no aplicativo Finanças e operações. |
| ImportFONewPostalAddressLocation.csv | Esse arquivo ajuda a criar registros de **Localização de endereço postal** no aplicativo Finanças e operações. |
| ImportFONewPartyPostalAddress.csv | Esse arquivo ajuda a criar registros de **Endereço postal do participante** no aplicativo Finanças e operações. |
| ImportFONewPostalAddress.csv | Esse arquivo ajuda a criar novos registros de **Endereço postal** no aplicativo Finanças e operações. |
| ImportFONewElectronicAddress.csv | Esse arquivo ajuda a criar novos registros de **Endereço eletrônico** no aplicativo Finanças e operações. |

Este tópico explica como usar os modelos do Data Factory e atualizar seus dados. Se não tiver nenhuma personalização, você poderá usar os modelos no estado em que se encontram. No entanto, se tiver personalizações para dados de **Conta**, **Contato** e **Fornecedor**, você deverá modificar os modelos conforme descrito no tópico.

> [!IMPORTANT]
> Há instruções especiais para executar os modelos de Endereço postal do participante e de Endereço eletrônico do participante. Você deve executar o modelo de Participante primeiro, em seguida, o modelo de Endereço postal do participante e, por fim, o modelo de Endereço eletrônico do participante. Cada modelo foi criado para ser importado em um data factory separado.

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos devem ser atendidos antes que você possa atualizar para o modelo de catálogo de endereços global e de participante:

+ Você deve ter uma [assinatura do Azure](https://portal.azure.com/).
+ Você deve ter acesso [aos modelos](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
+ Você deve ser um cliente de gravação dupla existente.

## <a name="prepare-for-the-upgrade"></a>Preparar-se para o upgrade

Uma atualização requer a seguinte preparação:

+ **Sincronização completa:** os ambientes do Finance and Operations e do Customer Engagement devem estar em um estado totalmente sincronizado das tabelas **Conta (Cliente)**, **Contato** e **Fornecedor**.
+ **Chaves de integração**: as tabelas **Conta (Cliente)**, **Contato** e **Fornecedor** nos aplicativos do Customer Engagement devem estar usando as chaves de integração prontas para uso que são enviadas. Se personalizou as chaves de integração, você deve personalizar o modelo.
+ **Número de participante:** todos os registros de **Conta (Cliente)**, **Contato** e **Fornecedor** que serão atualizados devem ter um número de participante. Os registros sem um número de participante serão ignorados. Se você desejar atualizar esses registros, adicione um número de participante a eles antes de iniciar o processo de upgrade.
+ **Interrupção do sistema**: durante o processo de atualização, será necessário manter os ambientes do Finance and Operations e do Customer Engagement offline.
+ **Instantâneo**: tire instantâneos dos aplicativos Finanças e operações e Customer Engagement. Você pode usar os instantâneos para restaurar o estado anterior, se necessário.

## <a name="deployment"></a>Implantação

1. Baixe os modelos em [Dynamics-365-FastTrack-Implementation-Assets](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema).
2. Entre no [portal do Azure](https://portal.azure.com/).
3. Crie um [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).
4. Crie uma [conta de armazenamento](/azure/storage/common/storage-account-create?tabs=azure-portal) no grupo de recursos que você criou.
5. Crie uma [data factory](/azure/data-factory/quickstart-create-data-factory-portal) no grupo de recursos que você criou.
6. Abra a data factory e selecione o bloco **Autoria e Monitoramento**.
7. Na guia **Gerenciar**, selecione **Modelo de ARM**.
8. Selecione **Importar modelo do ARM** para importar o modelo de **Participante**.
9. Importe o modelo para a data factory. Insira os valores a seguir para **Detalhes do projeto** e **Detalhes da instância**.

    | Campo | Valor |
    |---|---|
    | Assinatura | A assinatura do Azure |
    | Grupo de recursos | Forneça o mesmo recurso no qual a conta de armazenamento foi criada. |
    | Região | A região |
    | Nome da fábrica | O nome da fábrica |
    | Chave principal_da entidade de serviço vinculada ao FO | A chave do aplicativo |
    | Cadeia de conexão_Armazenamento de Blobs do Azure | A cadeia de conexão do Armazenamento de Blobs do Azure |
    | Service_password vinculada ao Dynamics CRM | A senha da conta de usuário que você especificar como o nome de usuário |
    | Service_properties_type Properties_url vinculada ao FO | `https://sampledynamics.sandbox-operationsdynamics.com/data` |
    | Service_properties_type Properties_tenant vinculado ao FO | Informações (nome do domínio ou ID do locatário) do locatário no qual seu aplicativo reside |
    | Service_properties_type Properties_aad Resource Id vinculado ao FO | `https://sampledynamics.sandboxoperationsdynamics.com` |
    | ID Principal do Service_properties_type Properties_service vinculada ao FO | A ID do cliente do aplicativo |
    | Service_properties_type Properties_username vinculado ao Dynamics CRM | O nome de usuário que é usado para conectar-se ao Dynamics 365 |

    Para obter mais informações, consulte os seguintes tópicos:

    - [Promover manualmente um modelo do Resource Manager para cada ambiente](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [Propriedades de serviço vinculadas](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [Copiar dados usando o Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Após a implantação, valide os conjuntos de dados, de fluxo de dados e o serviço vinculado da data factory.

    ![Conjuntos de dados, fluxo de dados e serviço vinculado.](media/data-factory-validate.png)

11. Acesse **Gerenciar**. Em **Conexões**, selecione **Serviço vinculado**. Selecione **DynamicsCrmLinkedService**. Na caixa de diálogo **Editar serviço vinculado (Dynamics CRM)**, insira os seguintes valores:

    | Campo | Valor |
    |---|---|
    | Nome | DynamicsCrmLinkedService |
    | descrição | Serviços vinculados para conectar com a instância do CRM para obter dados de entidades |
    | Conectar via tempo de execução de integração | AutoResolvelntegrationRuntime |
    | Tipo de implantação | Online |
    | URI de serviço | `https://<organization-name>.crm[x].dynamics.com` |
    | Tipo de autenticação | Office365 |
    | Nome de usuário | |
    | Senha ou Azure Key Vault | Senha |
    | Senha | |

## <a name="prepare-to-run-the-data-factory-templates"></a>Preparar a execução dos modelos do Data Factory

Esta seção descreve a configuração necessária antes de executar os modelos do Data Factory de Endereço postal do participante e de Endereço eletrônico do participante.

### <a name="setup-to-run-the-party-postal-address-template"></a>Configuração para executar o modelo de Endereço postal do participante

1. Faça login nos aplicativos do Customer Engagement e acesse **Configurações** \> **Configurações de Personalização**. Na guia **Geral**, defina a configuração de fuso horário para a conta de administrador do sistema. O fuso horário deve estar no Tempo Universal Coordenado (UTC) para atualizar as datas "válido desde" e "válido até" dos endereços postais dos aplicativos Finanças e operações.

    ![Configuração de fuso horário para a conta de administrador do sistema.](media/ADF-1.png)

2. No Data Factory, na guia **Gerenciar**, em **Parâmetros Globais**, crie o seguinte parâmetro global:

    | Número | Nome | Tipo | Valor |
    |---|---|---|---|
    | 1 | PostalAddressIdPrefix | cadeia de caracteres | Esse parâmetro anexa um número de série a endereços postais criados recém-criados como um prefixo. Certifique-se de fornecer uma cadeia de caracteres que não entre em conflito com endereços postais nos aplicativos Finanças e operações e nos aplicativos do Customer Engagement. Por exemplo, use **ADF-PAD-**. |

    ![Parâmetro global PostalAddressIdPrefix criado na guia Gerenciar.](media/ADF-2.png)

3. Quando terminar, selecione **Publicar tudo**.

    ![Botão Publicar tudo.](media/ADF-3.png)

### <a name="setup-to-run-the-party-electronic-address-template"></a>Configuração para executar o modelo de Endereço eletrônico do participante

1. No Data Factory, na guia **Gerenciar**, em **Parâmetros Globais**, crie os seguintes parâmetros globais:

    | Número | Nome | Tipo | Valor |
    |---|---|---|---|
    | 1 | IsFOSource | bool | Esse parâmetro determina quais endereços principais do sistema serão substituídos no caso de conflitos. Se o valor for **verdadeiro**, os endereços principais nos aplicativos Finanças e operações substituirão os endereços principais nos aplicativos do Customer Engagement. Se o valor for **falso**, os endereços principais nos aplicativos Customer Engagement substituirão os endereços principais nos aplicativos Finanças e operações. |
    | 2 | ElectronicAddressIdPrefix | cadeia de caracteres | Esse parâmetro anexa um número de série a endereços eletrônicos criados recém-criados como um prefixo. Certifique-se de fornecer uma cadeia de caracteres que não entre em conflito com endereços eletrônicos nos aplicativos Finanças e operações e nos aplicativos do Customer Engagement. Por exemplo, use **ADF-EAD-**. |

    ![Parâmetros globais IsFOSource e ElectronicAddressIdPrefix criados na guia Gerenciar.](media/ADF-4.png)

2. Quando terminar, selecione **Publicar tudo**.

## <a name="run-the-templates"></a>Executar os modelos

1. Interrompa os mapas de gravação dupla de **Participante**, **Conta**, **Contato** e **Fornecedor** que usam o aplicativo do Finanças e Operações:

    + Participantes do CDS (msdyn_parties) 
    + Clientes V3 (contas)
    + Clientes V3 (contatos)
    + Contatos V2 do CDS (contatos)
    + Contatos V2 do CDS (contatos)
    + Fornecedores V2 (msdyn_vendor)
    + Contatos V2 (msdyn_contactforparties)
    + Locais de endereço postal de parceiros do CDS (msdyn_partypostaladdresses)
    + Histórico de endereço postal V2 do CDS (msdyn_postaladdresses)
    + Locais de endereço postal de parceiros do CDS (msdyn_postaladdresscollections)
    + Contatos do participante V3 (msdyn_partyelectronicaddresses)

2. Certifique-se de que os mapas sejam removidos da tabela **msdy_dualwriteruntimeconfig** no Dataverse.
3. Instale [Soluções de gravação dupla de catálogo de endereços global e de participante](https://aka.ms/dual-write-gab) pelo AppSource.
4. No aplicativo Finanças e operações, execute a **Sincronização inicial** para as tabelas a seguir, se elas tiverem dados:

    + Saudações
    + Tipos de caracteres pessoais
    + Fechamento complementar
    + Títulos da pessoa de contato
    + Funções de tomada de decisão
    + Níveis de fidelidade

5. No aplicativo do Customer Engagement, desabilite as seguintes etapas do plug-in:

    + Atualização de Conta

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta

    + Atualização do contato

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato

    + Atualização de msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party

    + Atualização de msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor

    + Customeraddress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: criar de customeraddress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreatePartyAddress: atualizar de customeraddress

        + Excluir

            + Microsoft.Dynamics.GABExtended.Plugins.DeleteCustomerAddress: excluir de customeraddress

    + msdyn_partypostaladdress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: criar de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: criar de msdyn_partypostaladdress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: atualizar de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: atualizar de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: criar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: criar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: criar de msdyn_postaladdress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: atualizar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: atualizar de msdyn_postaladdress

    + msdyn_partyelectronicaddress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: criar de msdyn_partyelectronicaddress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: criar de msdyn_partyelectronicaddress

        + Excluir

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: excluir de msdyn_partyelectronicaddress

6. No aplicativo do Customer Engagement, desabilite os seguintes fluxos de trabalho:

    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores do tipo pessoa na Tabela Contatos
    + Criar Fornecedores do tipo Pessoa na Tabela Fornecedores
    + Atualizar Fornecedores na Tabela Contas
    + Atualizar Fornecedores na Tabela Fornecedores
    + Atualizar Fornecedores do tipo Pessoa na Tabela Contatos
    + Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores

7. Na data Factory, execute o modelo selecionando **Disparar agora**, conforme mostrado na ilustração a seguir. Esse processo pode levar algumas horas para ser concluído, dependendo do volume de dados.

    ![Executando o modelo.](media/data-factory-trigger.png)

    > [!NOTE]
    > Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo.

8. Importe os novos registros de **Participante** para o aplicativo do Finanças e operações.

    1. Baixe o arquivo **FONewParty.csv** do Armazenamento de Blobs do Azure. O caminho é **partybootstrapping/output/FONewParty.csv**.
    2. Converta o arquivo **FONewParty.csv** em um arquivo do Excel e importe-o para o aplicativo Finanças e operações. Como alternativa, se a importação de CSV funcionar para você, você poderá importar o arquivo .csv diretamente. Essa etapa pode levar algumas horas para ser concluída, dependendo do volume de dados. Para obter mais informações, consulte [Visão geral de trabalhos de importação e exportação de dados](../data-import-export-job.md).

    ![Importando os registros de Participante do Dataverse.](media/data-factory-import-party.png)

9. Na data factory, execute os modelos de Endereço postal do participante e de Endereço eletrônico do participante, um após o outro.

    + O modelo de Endereço postal do participante cria e atualiza todos os registros de endereço postal no aplicativo do Customer Engagement e os associa com os registros de **Conta**, **Contato** e **Fornecedor** correspondentes. Ele também gera três arquivos. csv: ImportFONewPostalAddressLocation.csv, ImportFONewPartyPostalAddress.csv e ImportFONewPostalAddress.csv.
    + O modelo de Endereço eletrônico do participante cria e atualiza todos os endereços eletrônicos no aplicativo do Customer Engagement e os associa com os registros de **Conta**, **Contato** e **Fornecedor** correspondentes. Ele também gera um arquivo. csv: ImportFONewElectronicAddress.csv.

    ![Executando os modelos de Endereço postal do participante e de Endereço eletrônico do participante.](media/ADF-7.png)

10. Para atualizar o aplicativo Finanças e operações com esses dados, você deve converter os arquivos .csv em uma pasta de trabalho do Excel e [importá-los para o aplicativo](/data-entities/data-import-export-job). Como alternativa, se a importação de CSV funcionar para você, você poderá importar os arquivos .csv diretamente. Essa etapa pode levar algumas horas para ser concluída, dependendo do volume.

    ![Importação com êxito.](media/ADF-8.png)

11. No aplicativos do Customer Engagement, habilite as seguintes etapas do plug-in:

    + Atualização de Conta

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta

    + Atualização do contato

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato
        + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato

    + Atualização de msdyn_party

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party

    + Atualização de msdyn_vendor

        + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor

    + msdyn_partypostaladdress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: criar de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: criar de msdyn_partypostaladdress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.CreateCustomerAddress: atualizar de msdyn_partypostaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PartyPostalAddress: atualizar de msdyn_partypostaladdress

    + msdyn_postaladdress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddress: criar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressPostCreate: criar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: criar de msdyn_postaladdress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PostalAddressUpdate: atualizar de msdyn_postaladdress
            + Microsoft.Dynamics.GABExtended.Plugins.UpdateCustomerAddress: atualizar de msdyn_postaladdress
 
    + msdyn_partyelectronicaddress

        + Criar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: criar de msdyn_partyelectronicaddress

        + Atualizar

            + Microsoft.Dynamics.GABExtended.Plugins.PartyElectronicAddressSync: criar de msdyn_partyelectronicaddress

        + Excluir

            + Microsoft.Dynamics.GABExtended.Plugins.DeletePartyElectronicAddressSync: excluir de msdyn_partyelectronicaddress

12. Nos aplicativos do Customer Engagement, ative os seguintes fluxos de trabalho se eles foram desativados anteriormente:

    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores do tipo pessoa na Tabela Contatos
    + Criar Fornecedores do tipo Pessoa na Tabela Fornecedores
    + Atualizar Fornecedores na Tabela Contas
    + Atualizar Fornecedores na Tabela Fornecedores
    + Atualizar Fornecedores do tipo Pessoa na Tabela Contatos
    + Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores

13. Execute os mapas relacionados ao registro de **Participante**, conforme descrito em [Catálogo de endereços global e de participantes](party-gab.md).

## <a name="explanation-of-the-data-factory-templates"></a>Explicação dos modelos do Data Factory

Esta seção fornece orientações sobre as etapas em cada modelo do Data Factory.

### <a name="steps-in-the-party-template"></a>Etapas no modelo de Participante

1. As etapas 1 a 6 identificam as empresas habilitadas para a gravação dupla e criam uma cláusula de filtro para elas.
2. As etapas de 7-1 a 7-9 recuperam dados do aplicativo do Finanças e operações e do aplicativo Customer Engagement, e transferem os dados para atualização.
3. As etapas de 8 a 9 comparam o número do participante dos registros de **Conta**, **Contato** e **Fornecedor** entre o aplicativo Finanças e operações e o aplicativo do Customer Engagement. Os registros sem um número de participante são ignorados.
4. A etapa 10 gera dois arquivos .csv para os registros de participante que devem ser criados no aplicativo do Customer Engagement e no aplicativo Finanças e operações.

    - **FOCDSParty.csv** – esse arquivo contém todos os registros de participante de ambos os sistemas, independentemente de a empresa estar habilitada para gravação dupla.
    - **FONewParty.csv** – esse arquivo contém um subconjunto dos registros de participante do qual o Dataverse está ciente (por exemplo, contas do tipo **Cliente potencial**).

5. A etapa 11 cria os participantes no aplicativo do Customer Engagement.
6. A etapa 12 recupera os identificadores globais exclusivos (GUIDs) dos participantes do aplicativo do Customer Engagement e os prepara para que possam ser associados com os registros de **Conta**, **Contato** e **Fornecedor** nas etapas subsequentes.
7. A etapa 13 associa os registros de **Conta**, **Contato** e **Fornecedor** com os GUIDs do participante.
8. As etapas de 14-1 a 14-3 atualizam os registros de **Conta**, **Contato** e **Fornecedor** no aplicativo do Customer Engagement com os GUIDs do participante.
9. As etapas de 15-1 a 15-3 preparam os registros de **Contato do participante** para os registros de **Conta**, **Contato** e **Fornecedor**.
10. As etapas de 16-1 a 16-7 recuperam dados de referência, como saudações e tipos de caracteres pessoais, e os associam aos registros de **Contato do participante**.
11. A etapa 17 mescla os registros de **Contato do participante** para os registros de **Conta**, **Contato** e **Fornecedor**.
12. A etapa 18 importa os registros de **Contato do participante** para o aplicativo do Customer Engagement.

### <a name="steps-in-the-party-postal-address-template"></a>Etapas no modelo de Endereço postal do participante

1. As etapas de 1-1 a 1-10 recuperam dados do aplicativo do Finanças e operações e do aplicativo Customer Engagement, e transferem os dados para atualização.
2. A etapa 2 desnormaliza os dados do endereço postal no aplicativo Finanças e operações unindo o endereço postal e o endereço postal do participante.
3. A etapa 3 elimina duplicatas e mescla os dados de endereço de conta, contato e fornecedor do aplicativo do Customer Engagement.
4. A etapa 4 cria arquivos .csv para o aplicativo Finanças e operações criar dados de endereço com base nos endereços de conta, contato e fornecedor.
5. A etapa 5-1 cria arquivos .csv para o aplicativo do Customer Engagement todos os dados de endereço, com base no aplicativo Finanças e operações e no aplicativo do Customer Engagement.
6. A etapa 5-2 converte os arquivos .csv no formato de importação Finanças e operações para a importação manual.

    - ImportFONewPostalAddressLocation.csv
    - ImportFONewPartyPostalAddress.csv
    - ImportFONewPostalAddress.csv

7. A etapa 6 importa os dados da coleção de endereços postais para o aplicativo do Customer Engagement.
8. A etapa 7 recupera os dados da coleção de endereços postais do aplicativo do Customer Engagement.
9. A etapa 8 cria dados de endereço de cliente e associa uma ID de coleção de endereço postal.
10. As etapas de 9-1 a 9-2 associam as IDs de coleção participante e de endereço postal com os endereços postais e os endereços postais de participante.
11. As etapas de 10-1 a 10-3 importam os endereços de clientes, os endereços postais e endereços postais de participante para o aplicativo do Customer Engagement.

### <a name="steps-in-the-party-electronic-address-template"></a>Etapas no modelo de Endereço eletrônico do participante

1. As etapas de 1-1 a 1-5 recuperam dados do aplicativo do Finanças e operações e do aplicativo Customer Engagement, e transferem os dados para atualização.
2. A etapa 2 consolida os endereços eletrônicos no aplicativo do Customer Engagement das entidades Conta, Contato e Fornecedor.
3. A etapa 3 mescla os dados do endereço eletrônico principal do aplicativo do Customer Engagement e do aplicativo Finanças e operações.
4. A etapa 4 cria os arquivos .csv.

    - Crie dados de endereço eletrônico para o aplicativo Finanças e operações com base nos endereços de conta, contato e fornecedor.
    - Crie dados de endereço eletrônico para o aplicativo do Customer Engagement, com base nos endereços de endereço eletrônico, conta, contato e fornecedor no aplicativo Finanças e operações.

5. A etapa 5-1 importa os endereços eletrônicos para o aplicativo do Customer Engagement.
6. A etapa 5-2 cria os arquivos .csv para atualizar endereços principais de contas e contatos no aplicativo do Customer Engagement.
7. As etapas de 6-1 a 6-2 importam as contas e os endereços principais do contato para o aplicativo do Customer Engagement.

## <a name="troubleshooting"></a>Solução de problemas

1. Se houver falha no processo, execute novamente a data factory. Inicie a partir da atividade com falha.
2. Alguns arquivos que são gerados pela data factory podem ser usados para a validação dos dados.
3. A data factory é executada com base em arquivos .csv. Portanto, se uma vírgula for incluída em algum valor de campo, isso poderá interferir nos resultados. Você deve remover todas as vírgulas dos valores de campo.
4. A guia **Monitoramento** fornece informações sobre todas as etapas e dados que foram processados. Selecione uma etapa específica para depurá-la.

    ![Guia Monitoramento.](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Saiba mais sobre o modelo

Para obter mais informações sobre o modelo, consulte [Comentários para o leiame do modelo do Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).
