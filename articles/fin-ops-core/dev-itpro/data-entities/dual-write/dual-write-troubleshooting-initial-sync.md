---
title: Solucionar problemas durante a sincronização inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410072"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a>Solucionar problemas durante a sincronização inicial

[!include [banner](../../includes/banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem acontecer durante a sincronização inicial.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a>Verificar erros de sincronização inicial em um aplicativo do Finance and Operations

Depois de habilitar os modelos de mapeamento, o status dos mapas deve estar em **Execução**. Se o status **Não estiver em execução**, ocorrerão erros durante a sincronização inicial. Para exibir os erros, selecione a guia **Detalhes de sincronização inicial** na página **Gravação dupla**.

![Guia detalhes da sincronização inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a>Não é possível concluir a sincronização inicial: 400 Solicitação incorreta

**Função necessária para corrigir o problema:** administrador do sistema

A seguinte mensagem de erro pode ser exibida ao tentar executar o mapeamento e a sincronização inicial:

*O servidor remoto retornou um erro: (400) Solicitação incorreta.), a exportação AX encontrou um erro*

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

![Lista de aplicativos do Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a>Falhas de autorreferência ou referência circular durante a sincronização inicial

Você poderá receber mensagens de erro se um dos seus mapeamentos tiver autorreferências ou referências circulares: Os erros são classificados nestas categorias:

- [Fornecedores V2 para mapeamento de entidade msdyn_vendors](#error-vendor-map)
- [Clientes V3 para mapeamento de entidade Contas](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a>Resolver um erro em fornecedores v2 para mapeamento de entidade msdyn_vendors

Você poderá executar os seguintes erros de sincronização iniciais nos **Fornecedores V2** para mapeamento de **msdyn_vendors** se as entidades tiverem registros existentes com valores nos campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**. Isso ocorre porque **InvoiceVendorAccountNumber** é um campo de auto-referência e **PrimaryContactPersonId** é uma referência circular no mapeamento do fornecedor.

*Não foi possível resolver a GUID do campo: <field>. A pesquisa não foi encontrada: <value>. Experimente este(s) URLs para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

Veja alguns exemplos:

- *Não foi possível resolver o GUID do campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Não foi possível resolver o GUID do campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. A pesquisa não foi encontrada: V24-1. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*

Se você tiver registros com valores nesses campos na entidade fornecedor, siga as etapas na seção a seguir para concluir a sincronização inicial com êxito.

1. No aplicativo Finance and Operations, exclua os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** do mapeamento e salve as alterações.

    1. Navegue até a página de mapeamento de gravação dupla para **Fornecedores V2 (msdyn_vendors)** e selecione a guia **Mapeamentos de entidade**. No filtro esquerdo, selecione **Finance and Operations apps.Vendors V2**. No filtro direito, selecione **Sales.Vendor**.

    2. Procure **primarycontactperson** para encontrar o campo de origem **PrimaryContactPersonId**.
    
    3. Clique no botão **Ações** e selecione **Excluir**.
    
        ![Autorreferência ou referência circular 3](media/vend_selfref3.png)
    
    4. Repita para excluir o campo **InvoiceVendorAccountNumber**.
    
        ![Autorreferência ou referência circular 4](media/vend-selfref4.png)
    
    5. Salve as alterações de mapeamento.

2. Desabilite o controle de alterações para a entidade **Fornecedor V2**.

    1. Navegue até **Gerenciamento de dados \> Entidades de Dados**.
    
    2. Selecione a entidade **Fornecedores V2**.
    
    3. Clique em **Opções** na barra de menus e em **Controle de alterações**.
    
        ![Autorreferência ou referência circular 5](media/selfref_options.png)
    
    4. Clique em **Desabilitar Controle de Alterações**.
    
        ![Autorreferência ou referência circular 6](media/selfref_tracking.png)

3. Execute o mapeamento de sincronização inicial do **Fornecedor V2 (msdyn_vendors)**. A sincronização inicial deve ser executada com êxito sem erros.

4. Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**. Você deverá sincronizar este mapeamento se desejar sincronizar o campo de contato principal na entidade fornecedores, já que os registros de contatos também precisam ser sincronizados.

5. Adicione os campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** novamente ao mapeamento **Fornecedores V2 (msdyn_vendors)** e salve o mapeamento.

6. Execute novamente a sincronização inicial para mapeamento do **Fornecedor V2 (msdyn_vendors)**. Todos os registros serão sincronizados, pois o controle de alterações está desabilitado.

7. Habilite o controle de alterações para a entidade **Fornecedor V2**.

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a>Resolver um erro no mapeamento de Clientes V3 para a entidade Contas

Você poderá executar os seguintes erros de sincronização inicial no mapeamento de **Clientes V3** para **Contas** se as entidades tiverem registros existentes com valores nos campos **ContactPersonID** e **InvoiceAccount**. Isso ocorre porque **InvoiceAccount** é um campo de autorreferência e **ContactPersonID** é uma referência circular no mapeamento do fornecedor.

*Não foi possível resolver a GUID do campo: <field>. A pesquisa não foi encontrada: <value>. Experimente este(s) URLs para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*

- *Não foi possível resolver o GUID do campo: primarycontactid.msdyn_contactpersonid. A pesquisa não foi encontrada: 000056. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*
- *Não foi possível resolver o GUID do campo: msdyn_billingaccount.accountnumber. A pesquisa não foi encontrada: 1206-1. Experimente este(s) URL(s) para verificar se os dados de referência existem: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*

Se você tiver registros com valores nesses campos na entidade cliente, siga as etapas na seção a seguir para concluir a sincronização inicial com êxito. Você pode usar essa abordagem para qualquer entidade pronta para uso, como Contas e Contatos.

1. No aplicativo Finance and Operations, exclua os campos **ContactPersonID** e **InvoiceAccount** do mapeamento **Clientes V3 (contas)** e salve o mapeamento.

    1. Navegue até a página de mapeamento de gravação dupla para **Clientes V3 (contas)**, selecione a guia **Mapeamentos de entidade**. No filtro esquerdo, selecione **Finance and Operations app.Customers V3**. No filtro direito, selecione **Common Data Service.Account**.

    2. Procure **contactperson** para encontrar o campo de origem **ContactPersonID**.
    
    3. Clique no botão **Ações** e selecione **Excluir**.
    
        ![Autorreferência ou referência circular 3](media/cust_selfref3.png)
    
    4. Repita para excluir o campo **InvoiceAccount**.
    
        ![Autorreferência ou referência circular](media/cust_selfref4.png)
    
    5. Salve as alterações de mapeamento.

2. Desabilite o controle de alterações para a entidade **Clientes V3**.

    1. Navegue até **Gerenciamento de dados \> Entidades de Dados**.
    
    2. Selecione a entidade **Clientes V3**.
    
    3. Clique em **Opções** na barra de menus e em **Controle de alterações**.
    
        ![Autorreferência ou referência circular 5](media/selfref_options.png)
    
    4. Clique em **Desabilitar Controle de Alterações**.
    
        ![Autorreferência ou referência circular 6](media/selfref_tracking.png)

3. Execute a sincronização inicial para o mapeamento de **Clientes V3 (contas)**. A sincronização inicial deve ser executada com êxito sem erros.

4. Execute a sincronização inicial para o mapeamento de **Contatos de CDS V2 (contatos)**. Há 2 mapas com o mesmo nome. Selecione aquele com o modelo de descrição **Gravação dupla para sincronização entre Contatos FO.CDS do Fornecedor V2 para CDS.Contacts. Exige novo pacote \[Dynamics365SupplyChainExtended\].** Na guia **Detalhes** do mapa.

5. Adicione os campos **InvoiceAccount** e **ContactPersonId** novamente no mapeamento **Clientes V3 (contas)** e salve o mapeamento. Agora, os campos **InvoiceAccount** e **ContactPersonId** fazem parte novamente do modo de sincronização ao vivo. Na próxima etapa, você concluirá a sincronização inicial desses campos.

6. Execute a sincronização inicial novamente para o mapeamento de **Clientes V3 (contas)**. Como o controle de alterações está desabilitado, a execução da sincronização sincronizará os dados de **InvoiceAccount** e **ContactPersonId** do aplicativo Finance and Operations para o Common Data Service.

7. Para sincronizar os dados para **InvoiceAccount** e **ContactPersonId** do Common Data Service para o Finance and Operations, você usa um projeto de integração de dados.

    1. No Power Apps, crie um projeto de integração de dados entre as entidades **Sales.Account** e **Finance and Operations apps.Customers V3**. A direção de dados deve ser do Common Data Service para o aplicativo do Finance and Operations.  Como **InvoiceAccount** é um novo atributo na gravação dupla, talvez você deseje ignorar a sincronização inicial desse atributo. Para obter mais informações, consulte [Integrar dados no Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).

        A imagem a seguir mostra um projeto que atualiza **CustomerAccount** e **ContactPersonId**.

        ![Autorreferência ou referência circular](media/cust_selfref6.png)

    2. Adicione os critérios da empresa no filtro do Common Data Service, pois somente os registros que correspondem aos critérios do filtro serão atualizados no aplicativo do Finance and Operations. Para adicionar um filtro, clique no ícone de filtro. Na caixa de diálogo **Editar consulta**, você pode adicionar uma consulta de filtro como **_msdyn_company_value eq '\<guid\>'**. Se o ícone de filtro não estiver presente, crie um tíquete de suporte para solicitar que a equipe de integração de dados habilite a capacidade de filtro no seu locatário. Se você não inserir uma consulta de filtro para **msdyn_company_value**, todos os registros serão sincronizados.

        ![Autorreferência ou referência circular](media/cust_selfref7.png)

        Isso conclui a sincronização inicial dos registros.

8. Habilite o controle de alterações para a entidade **Clientes V3** no aplicativo do Finance and Operations.

