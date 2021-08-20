---
title: Solucionar problemas durante a sincronização inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 0fe319f4c8edd54700b2b32ef80539a8d0ff793aa815cef3813af4c63fd1b0d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736365"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante a sincronização inicial

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificar erros de sincronização inicial em um aplicativo do Finance and Operations

Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**. Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial. Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.

![Erro na guia Detalhes da sincronização inicial.](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Não é possível concluir a sincronização inicial: 400 Solicitação incorreta

**Função necessária para corrigir o problema:** administrador do sistema

A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:

*(\[Solicitação Incorreta\], O servidor remoto retornou um erro: (400) Solicitação Incorreta.), a exportação AX encontrou um erro*

Veja aqui um exemplo da mensagem de erro completa.

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

Se esse erro ocorrer consistentemente e você não puder concluir a sincronização inicial, siga estas etapas para corrigir o problema.

1. Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.
2. Abra o console de gerenciamento da Microsoft.
3. No painel **Serviços**, verifique se o serviço de estrutura de importação/exportação de dados do Microsoft Dynamics 365 está em execução. Reinicie-o se ele tiver sido interrompido, pois a sincronização inicial requer essa ação.

## <a name="initial-synchronization-error-403-forbidden"></a>Erro de sincronização inicial: 403 Proibido

A seguinte mensagem de erro pode ser exibida durante sincronização inicial:

*(\[Proibido\], O servidor remoto retornou um erro: (403) Proibido.), a exportação AX encontrou um erro*

Para corrigir o problema, siga estas etapas.

1. Entrar no aplicativo Finance and Operations.
2. Na página **aplicativo do Azure Active Directory**, exclua o cliente **DtAppID** e, em seguida, adicione-o novamente.

![Cliente DtAppID na lista de aplicativos do Azure AD.](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Falhas de autorreferência ou referência circular durante a sincronização inicial

Você poderá receber mensagens de erro se um dos seus mapeamentos tiver autorreferências ou referências circulares: Os erros são classificados nestas categorias:

- [Erros em Fornecedores V2 para mapeamento de tabela msdyn_vendors](#error-vendor-map)
- [Erros no mapeamento de Clientes V3 para a tabela Contas](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a>Resolver erros em Fornecedores V2 para mapeamento de tabela msdyn_vendors

Você poderá encontrar erros de sincronização inicial para o mapeamento de **Fornecedores V2** para **msdyn\_vendors** se as tabelas tiverem linhas existentes com valores nas colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Esses erros ocorrem porque **InvoiceVendorAccountNumber** é uma coluna de auto-referência e **PrimaryContactPersonId** é uma referência circular no mapeamento do fornecedor.

As mensagens de erro recebidas terão o seguinte formulário.

*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Eis alguns exemplos:

- *Não foi possível resolver a GUID do campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Não foi possível resolver a GUID do campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. A pesquisa não foi encontrada: V24-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*

Se alguma linha na tabela do fornecedor tiver valores nas colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**, siga estas etapas para concluir a sincronização inicial.

1. No aplicativo Finance and Operations, exclua as colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** do mapeamento e depois salve o mapeamento.

    1. Na página de mapeamento de gravação dupla para **Fornecedores V2 (msdyn\_vendors)**, na guia **Mapeamentos de tabela**, no filtro esquerdo, selecione **Finance and Operations apps.Vendors V2**. No filtro direito, selecione **Sales.Vendor**.
    2. Procure **primarycontactperson** para encontrar a coluna de origem **PrimaryContactPersonId**.
    3. Selecione **Ações** e depois **Excluir**.

        ![Excluindo a coluna PrimaryContactPersonId.](media/vend_selfref3.png)

    4. Repita essas etapas para excluir a coluna **InvoiceVendorAccountNumber**.

        ![Excluindo a coluna InvoiceVendorAccountNumber.](media/vend-selfref4.png)

    5. Salve as alterações feitas no mapeamento.

2. Desative o controle de alterações para a tabela **Fornecedor V2**.

    1. No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Tabelas de dados**.
    2. Selecione a tabela **Fornecedores V2**.
    3. No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.

        ![Selecionando a opção Controle de Alterações.](media/selfref_options.png)

    4. Selecione **Desabilitar Controle de Alterações**.

        ![Selecionando Desabilitar Controle de Alterações.](media/selfref_tracking.png)

3. Execute a sincronização inicial para mapeamento do **Fornecedor V2 (msdyn\_vendors)**. A sincronização inicial deve ser executada com êxito, sem erros.
4. Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**. Você deverá sincronizar este mapeamento se desejar sincronizar a coluna de contato principal na tabela fornecedores, pois a sincronização inicial também precisa ser feita para as linhas de contatos.
5. Adicione as colunas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** novamente ao mapeamento **Fornecedores V2 (msdyn\_vendors)** e salve o mapeamento.
6. Execute a sincronização inicial novamente para o mapeamento do **Fornecedor V2 (msdyn\_vendors)**. Como o controle de alterações está desabilitado, todas as linhas serão sincronizadas.
7. Ative o controle de alterações novamente para a tabela **Fornecedor V2**.

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a>Resolver erros no mapeamento de Clientes V3 para a tabela Contas

Você poderá encontrar erros de sincronização inicial para o mapeamento de **Clientes V3** para **Contas** se as tabelas tiverem linhas existentes com valores nas colunas **ContactPersonID** e **InvoiceAccount**. Esses erros ocorrem porque **InvoiceAccount** é uma coluna de autorreferência e **ContactPersonID** é uma referência circular no mapeamento do fornecedor.

As mensagens de erro recebidas terão o seguinte formulário.

*Não foi possível resolver a GUID do campo: \<field\>. A pesquisa não foi encontrada: \<value\>. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*

Eis alguns exemplos:

- *Não foi possível resolver a GUID do campo: primarycontactid.msdyn\_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*
- *Não foi possível resolver a GUID do campo: msdyn\_billingaccount.accountnumber. A pesquisa não foi encontrada: 1206-1. Experimente esta(s) URLs para verificar se os dados de referência existem: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*

Se alguma linha na tabela cliente tiver valores nas colunas **ContactPersonID** e **InvoiceAccount**, siga estas etapas para concluir a sincronização inicial. Você pode usar essa abordagem para qualquer tabela pronta para uso, como **Contas** e **Contatos**.

1. No aplicativo Finance and Operations, exclua as colunas **ContactPersonID** e **InvoiceAccount** do mapeamento **Clientes V3 (contas)** e salve o mapeamento.

    1. Na página de mapeamento de gravação dupla para **Clientes V3 (contas)**, na guia **Mapeamentos de tabela**, no filtro esquerdo, selecione **Finance and Operations app.Customers V3**. No filtro direito, selecione **Dataverse.Account**.
    2. Pesquise **contactperson** para encontrar a coluna de origem **ContactPersonID**.
    3. Selecione **Ações** e depois **Excluir**.

        ![Excluir a coluna ContactPersonID.](media/cust_selfref3.png)

    4. Repita essas etapas para excluir a coluna **InvoiceAccount**.

        ![Excluir a coluna InvoiceAccount.](media/cust_selfref4.png)

    5. Salve as alterações feitas no mapeamento.

2. Desative o controle de alterações para a tabela **Clientes V3**.

    1. No espaço de trabalho **Gerenciamento de dados**, selecione o bloco **Tabelas de dados**.
    2. Selecione a tabela **Fornecedor V3**.
    3. No Painel de Ações, selecione **Opções** e depois selecione **Controle de Alterações**.

        ![Selecionando a opção Controle de Alterações.](media/selfref_options.png)

    4. Selecione **Desabilitar Controle de Alterações**.

        ![Selecionando Desabilitar Controle de Alterações.](media/selfref_tracking.png)

3. Execute a sincronização inicial para o mapeamento de **Clientes V3 (contas)**. A sincronização inicial deve ser executada com êxito, sem erros.
4. Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**.

    > [!NOTE]
    > Há dois mapas com o mesmo nome. Certifique-se de selecionar o mapa que tenha a seguinte descrição na guia **Detalhes**: **Gravação dupla para sincronização entre Contatos FO.CDS do Fornecedor V2 para CDS.Contacts. Exige novo pacote \[Dynamics365SupplyChainExtended\].**

5. Adicione as colunas **InvoiceAccount** e **ContactPersonId** novamente no mapeamento **Clientes V3 (contas)** e depois salve o mapeamento. As colunas **InvoiceAccount** e **ContactPersonId** agora fazem parte do modo de sincronização ao vivo novamente. Na próxima etapa, você executará a sincronização inicial dessas colunas.
6. Execute a sincronização inicial novamente para o mapeamento de **Clientes V3 (contas)**. Como o controle de alterações está desabilitado, os dados de **InvoiceAccount** e **ContactPersonId** serão sincronizados do aplicativo Finance and Operations para o Dataverse.
7. Para sincronizar os dados de **InvoiceAccount** e **ContactPersonId** do Dataverse para o Finance and Operations, você deve usar um projeto de integração de dados.

    1. No Power Apps, crie um projeto de integração de dados entre as tabelas **Sales.Account** e **Finance and Operations apps.Customers V3**. A direção de dados deve ser do Dataverse para o aplicativo do Finance and Operations. Como **InvoiceAccount** é um novo atributo na gravação dupla, talvez você queira ignorar a sincronização inicial desse atributo. Para obter mais informações, consulte [Integrar dados no Dataverse](/power-platform/admin/data-integrator).

        A ilustração a seguir mostra um projeto que atualiza **CustomerAccount** e **ContactPersonId**.

        ![Projeto de integração de dados para atualizar CustomerAccount e ContactPersonId.](media/cust_selfref6.png)

    2. Adicione os critérios da empresa no filtro do Dataverse, para que somente as linhas que correspondem aos critérios do filtro sejam atualizadas no aplicativo do Finance and Operations. Para adicionar um filtro, selecione o botão de filtro. Em seguida, na caixa de diálogo **Editar consulta**, você pode adicionar uma consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**. 

        > [NOTA] Se o botão de filtro não estiver presente, crie um tíquete de suporte para solicitar que a equipe de integração de dados habilite a capacidade de filtro no seu locatário.

        Se você não inserir uma consulta de filtro para **\_msdyn\_company\_value**, todas os linhas serão sincronizados.

        ![Adicionando uma consulta de filtro.](media/cust_selfref7.png)

    A sincronização inicial das linhas está concluída.

8. No aplicativo do Finance and Operations, habilite o controle de alterações novamente para a tabela **Clientes V3**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]