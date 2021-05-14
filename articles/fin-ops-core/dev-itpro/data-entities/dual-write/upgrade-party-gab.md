---
title: Atualizar para o modelo de catálogo de endereços global e de participantes
description: Este tópico descreve como atualizar dados de gravação dupla para o modelo de catálogo de endereços global e do participante.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 32128d48bfac195530d70b60e67cfd4921fc001e
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941074"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a>Atualizar para o modelo de catálogo de endereços global e de participantes

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

O [modelo do Azure Data Factory](https://aka.ms/dual-write-gab-adf) ajuda você a atualizar os dados existentes das tabelas **Conta**, **Contato** e **Fornecedor** em uma gravação dupla para o modelo de catálogo de endereços global e do participante. O modelo reconcilia os dados dos aplicativos do Finance and Operations e dos aplicativos de participação do cliente. No final do processo, os campos **Participante** e **Contato** para os registros de **Participante** serão criados e associados aos registros de **Conta**, **Contato** e **Fornecedor** nos aplicativos do participação do cliente. Um arquivo .csv (`FONewParty.csv`) é gerado para criar novos registros de **Participante** no aplicativo Finance and Operations. Este tópico fornece as instruções para usar o modelo do Data Factory e atualizar seus dados.

Se não tiver nenhuma personalização, você poderá usar o modelo no estado em que se encontra. Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo usando as instruções a seguir.

> [!Note]
> O modelo ajuda a atualizar somente os dados do **Participante**. Em uma versão futura, os endereços postais e eletrônicos serão incluídos.

## <a name="prerequisites"></a>Pré-requisitos

Estes pré-requisitos são obrigatórios:

+ [Assinatura do Azure](https://portal.azure.com/)
+ [Acesso ao modelo](https://aka.ms/dual-write-gab-adf)
+ Você ser um cliente de gravação dupla existente.

## <a name="prepare-for-the-upgrade"></a>Preparar-se para o upgrade

+ **Totalmente sincronizado**: ambos os ambientes estão em um estado totalmente sincronizado para **Conta (Cliente)**, **Contato** e **Fornecedor**.
+ **Chaves de integração**: as tabelas **Conta (Cliente)**, **Contato** e **Fornecedor** nos aplicativos de participação do cliente estão usando as chaves de integração prontas para uso que são enviadas. Se personalizou as chaves de integração, você deve personalizar o modelo.
+ **Número do participante**: todos os registros de **Conta (Cliente)**, **Contato** e **Fornecedor** que serão atualizados têm um número de **Participante**. Registros sem um número de **Participante** serão ignorados. Se desejar fazer upgrade desses registros, adicione um número de **Participante** a eles antes de iniciar o processo de upgrade.
+ **Interrupção do sistema**: durante o processo de upgrade, você terá de manter os ambientes do Finance and Operations e de participação do cliente offline.
+ **Instantâneo**: tire instantâneos dos aplicativos Finance and Operations e de participação do cliente. Use os instantâneos para restaurar o estado anterior, se necessário.

## <a name="deployment"></a>Implantação

1. Baixe o modelo de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).

2. Entre no [Microsoft Azure](https://portal.azure.com/).

3. Crie um [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).

4. Crie uma [conta de armazenamento](/azure/storage/common/storage-account-create?tabs=azure-portal) no grupo de recursos que você criou.

5. Crie uma [data factory](/azure/data-factory/quickstart-create-data-factory-portal) no grupo de recursos que você criou acima.

6. Abra a data Factory e selecione o bloco **Autoria e Monitoramento**.

7. Na guia **Gerenciar**, selecione **Modelo de ARM**.

8. Selecione **Importar modelo ARM** para importar o modelo de **Participante**.

9. Importe o modelo para a data factory. Insira os valores a seguir para **Detalhes do projeto** e **Detalhes da instância**.

    Campo | Alíquota
    ---|---
    Assinatura | Assinatura do Azure
    Grupo de recursos | Forneça o mesmo recurso no qual a conta de armazenamento foi criada.
    Região | Especifique a região.
    Nome da fábrica | Especifique o nome da fábrica.
    Chave principal_da entidade de serviço vinculada ao FO | Especifique a chave do aplicativo.
    Cadeia de conexão_Armazenamento de Blobs do Azure | Cadeia de conexão do Armazenamento de Blobs do Azure.
    Service_password vinculada ao Dynamics CRM | A senha da conta de usuário especificada como nome de usuário.
    Service_properties_type Properties_url vinculada ao FO  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    Service_properties_type Properties_tenant vinculado ao FO | Especifique as informações do locatário (nome do domínio ou ID do locatário) em que seu aplicativo reside.
    Service_properties_type Properties_aad Resource Id vinculado ao FO | `https://sampledynamics.sandboxoperationsdynamics.com`
    ID Principal do Service_properties_type Properties_service vinculada ao FO | Especifique a ID do cliente do aplicativo.
    Service_properties_type Properties_username vinculado ao Dynamics CRM | O nome de usuário para conectar-se ao Dynamics.

    Para obter mais informações, consulte [Promover manualmente um modelo do Resource Manager para cada ambiente](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Propriedades do serviço vinculado](/azure/data-factory/connector-dynamics-ax#linked-service-properties) e [Copiar dados usando o Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. Após a implantação, valide os conjuntos de dados, de fluxo de dados e o serviço vinculado da data factory.

   ![Conjuntos de dados, fluxo de dados e serviço vinculado](media/data-factory-validate.png)

11. Navegue até **Gerenciar**. Em **Conexões**, selecione **Serviço vinculado**. Selecione **DynamicsCrmLinkedService**. No formulário **Editar serviço vinculado (Dynamics CRM)**, insira os seguintes valores:

    Campo | Alíquota
    ---|---
    Organização | DynamicsCrmLinkedService
    descrição | Serviços vinculados para conectar com a instância do CRM para obter dados de entidades
    Conectar via tempo de execução de integração | AutoResolvelntegrationRuntime
    Tipo de implantação | Online
    URI de serviço | `https://<organization-name>.crm[x].dynamics.com`
    Tipo de autenticação | Office365
    Nome de usuário |
    Senha ou Azure Key Vault | Senha
    Senha |

## <a name="run-the-template"></a>Executar o modelo

1. Interrompa a seguinte gravação dupla de **Conta**, **Contato** e **Fornecedor** usando o aplicativo do Finance and Operations.

    + Clientes V3 (contas)
    + Clientes V3 (contatos)
    + Contatos V2 do CDS (contatos)
    + Contatos V2 do CDS (contatos)
    + Fornecedores V2 (msdyn_vendor)

2. Certifique-se de que os mapas sejam removidos da tabela `msdy_dualwriteruntimeconfig` no Dataverse.

3. Instale [Soluções de gravação dupla de catálogo de endereços global e de participante](https://aka.ms/dual-write-gab) pelo AppSource.

4. No aplicativo Finance and Operations, se as tabelas a seguir contiverem dados, execute a **Sincronização Inicial** para elas.

    + Saudações
    + Tipos de caracteres pessoais
    + Fechamento complementar
    + Títulos da pessoa de contato
    + Funções de tomada de decisão
    + Níveis de fidelidade

5. No aplicativo de participação do cliente, desabilite as seguintes etapas do plug-in.

    + Atualização da conta
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta
    + Atualização do contato
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato
    + Atualização de msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party
    + Atualização de msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor

6. No aplicativo de participação do cliente, desabilite os seguintes fluxos de trabalho:

    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores do tipo pessoa na Tabela Contatos
    + Criar Fornecedores do tipo Pessoa na Tabela Fornecedores
    + Atualizar Fornecedores na Tabela Contas
    + Atualizar Fornecedores na Tabela Fornecedores
    + Atualizar Fornecedores do tipo Pessoa na Tabela Contatos
    + Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores

7. Na data Factory, execute o modelo selecionando **Disparar Agora**, conforme mostrado na imagem a seguir. Esse processo pode levar algumas horas para ser concluído com base no volume de dados.

    ![Disparar execução](media/data-factory-trigger.png)

    > [!NOTE]
    > Se tiver personalizações para **Conta**, **Contato** e **Fornecedor**, você deverá modificar o modelo.

8. Importe os novos registros de **Participante** no aplicativo Finance and Operations.

    + Baixe o arquivo `FONewParty.csv` do Armazenamento de Blobs do Azure. O caminho é `partybootstrapping/output/FONewParty.csv`.
    + Converta o arquivo `FONewParty.csv` em um arquivo do Excel e importe-o para o aplicativo Finance and Operations.  Se a importação de CSV funcionar para você, você poderá importar o arquivo CSV diretamente. A importação pode levar algumas horas para ser executada, dependendo do volume de dados. Para obter mais informações, consulte [Visão geral de trabalhos de importação e exportação de dados](../data-import-export-job.md).

    ![Importar os registros de participante do Dataverse](media/data-factory-import-party.png)

9. Nos aplicativos de participação do cliente, habilite as seguintes etapas do plug-in:

    + Atualização da conta
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: atualização da conta
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: atualização da conta
    + Atualização do contato
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: atualização do contato
         + Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: atualização do contato
    + Atualização de msdyn_party
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: atualização de msdyn_party
    + Atualização de msdyn_vendor
         + Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: atualização de msdyn_vendor

10. Nos aplicativos de participação do cliente, ative os seguintes fluxos de trabalho se eles foram desativados nas etapas anteriores:

    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores na Tabela Contas
    + Criar Fornecedores do tipo pessoa na Tabela Contatos
    + Criar Fornecedores do tipo Pessoa na Tabela Fornecedores
    + Atualizar Fornecedores na Tabela Contas
    + Atualizar Fornecedores na Tabela Fornecedores
    + Atualizar Fornecedores do tipo Pessoa na Tabela Contatos
    + Atualizar Fornecedores do tipo Pessoa na Tabela Fornecedores

11. Execute os mapas relacionados ao **Participante**, conforme instruído em [Catálogo de endereços global e de participantes](party-gab.md).

## <a name="troubleshooting"></a>Solução de problemas

1. Se houve falha no processo, execute novamente a data factory começando pela atividade com falha.
2. Alguns arquivos são gerados pela data Factory que podem ser usados para a finalidade de validação dos dados.
3. A data Factory é executada com base em arquivos CSV que são delimitados por vírgula. Se houver um valor de campo com uma vírgula, isso poderá interferir nos resultados. Você deve remover as vírgulas.
4. A guia **Monitoramento** fornece informações sobre todas as etapas e os dados processados. Selecione uma etapa específica para depurá-la.

    ![Guia Monitoramento](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a>Saiba mais sobre o modelo

Você pode encontrar comentários sobre o modelo no arquivo [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).