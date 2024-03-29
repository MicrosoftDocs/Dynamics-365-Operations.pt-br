---
title: Configuração do Finance Insights
description: Este artigo explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis no Finance Insights.
author: ShivamPandey-msft
ms.date: 09/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 07edea234839a477802e5cd875620509c8f92d69
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2022
ms.locfileid: "9644105"
---
# <a name="configuration-for-finance-insights"></a>Configuração do Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O Finance Insights combina a funcionalidade do Microsoft Dynamics 365 Finance com o Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização. Este artigo explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis no Finance Insights. Para concluir com êxito os procedimentos deste artigo, você deve ter acesso de Administrador do Sistema e Personalizador do Sistema no [centro de administração do Power Portal](https://admin.powerplatform.microsoft.com/), acesso de Administrador do Sistema do Dynamics 365 Finance e acesso para criar ambientes no Microsoft Dynamics Lifecycle Services (LCS).

> [!NOTE]
> Os seguintes procedimentos para configurar o Finance Insights são válidos para a versão 10.0.21 e versões posteriores do Dynamics 365 Finance.

## <a name="deploy-dynamics-365-finance"></a>Implantar o Dynamics 365 Finance

Para implantar os ambientes, siga estas etapas.

1. No LCS, crie ou atualize um ambiente do Dynamics 365 Finance. O ambiente requer a versão 10.0.21 ou posterior do aplicativo.

    > [!NOTE]
    > O ambiente deve ser de alta disponibilidade (HA). (Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](/fin-ops-core/fin-ops/imp-lifecycle/environment-planning).

2. Se você estiver configurando o Finance Insights em um ambiente de área restrita, talvez você precise copiar os dados de produção nesse ambiente para que as previsões funcionem. O modelo de previsão usa vários anos de dados para criar previsões. Os dados de demonstração da Contoso não contêm dados históricos suficientes para treinar o modelo de previsão corretamente. 

## <a name="configure-your-azure-ad-tenant"></a>Configurar o locatário do Azure AD

O Azure Active Directory (Azure AD) deve ser configurado de forma que possa ser usado com o Dataverse e os aplicativos da Microsoft Power Platform. Esta configuração exige que a função **Proprietário do Projeto** ou **Gerente do Ambiente** esteja atribuída ao usuário conectado no campo **Função de segurança do projeto** no LCS.

Verifique se a seguinte configuração foi concluída:

- Você tem acesso de **Administrador do sistema** e de **Personalizador do Sistema** no centro de administração do Power Portal.
- A licença do Dynamics 365 Finance ou equivalente é aplicada ao usuário que está instalando o suplemento Finance Insights.
- Os seguintes aplicativos do Azure AD estão registrados no Azure AD.

    |  Aplicativo                             | ID do Aplicativo                               |
    |------------------------------------------|--------------------------------------|
    | CDS de Microsserviços de ERP do Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |

    Para verificar se o aplicativo está registrado no Azure AD, verifique a lista **Todas as solicitações de emprego**. Para obter mais detalhes, consulte [Visualizar aplicativos empresariais](/azure/active-directory/manage-apps/view-applications-portal).
  
    Se o aplicativo não estiver registrado no Azure AD, entre em contato com o suporte.
  
## <a name="configure-dataverse"></a>Configurar o Dataverse

Para configurar o Dataverse para Finance Insights, siga estas etapas:

- No LCS, abra a página do ambiente e verifique se a seção **Integração do Power Platform** já está configurado.

    - Se o Dataverse já tiver sido configurado, o nome do ambiente do Dataverse que está vinculado ao ambiente do Finance deve aparecer na lista.
    - Se o Dataverse ainda não tiver sido configurado, selecione **Configurar**. A configuração do ambiente do Dataverse pode levar até uma hora. Quando a configuração for concluída com êxito, o nome do ambiente do Dataverse que está vinculado ao ambiente do Finance deve aparecer na lista.
    - Se essa integração tiver sido configurada com um ambiente da Microsoft Power Platform existente, entre em contato com o administrador para verificar se o ambiente vinculado não está no estado desabilitado.

        Para obter mais informações, consulte [Habilitando a integração com a Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md). 

        Para acessar o site admin da Microsoft Power Platform, vá para <https://admin.powerplatform.microsoft.com/environments>.

## <a name="configure-the-finance-insights-add-in"></a>Configurar o suplemento do Finance Insights

Se você instalou o suplemento do Finance insights anteriormente, desinstale-o antes de concluir o seguinte procedimento.

> [!NOTE]
> Se você já tiver instalado o suplemento do data lake no LCS, o Finance insights o usará para salvar dados que são necessários para previsões. Se você ainda não instalou o suplemento do data lake nas LCS, o suplemento do Finance insights criará um data lake gerenciado para você.

Para instalar o suplemento do Finance Insights, siga estas etapas.

1. Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.
2. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.
3. Selecione o suplemento do **Finance Insights**.
4. Concorde com os termos e as condições e selecione **Instalar**.

O suplemento pode demorar vários minutos para ser instalado.

## <a name="one-last-thing"></a>Uma última coisa...

Depois que o suplemento for instalado com êxito, pode demorar até uma hora para que você possa habilitar os recursos do Finance insights no espaço de trabalho **Gerenciamento de recursos** no Dynamics 365 Finance. Se você não quiser esperar isso, poderá executar manualmente o processo **Verificação do status de provisionamento do Insights**. 

1. No Dynamics 365 Finance, vá para **Administração do sistema \> Configuração \> Automação do processo**.
2. Na guia **Processos em segundo plano**, localize **Verificação de status de provisionamento do Insight** e selecione **Editar**.
3. Defina o campo **Próxima execução** como 30 minutos antes da hora atual.

   Essa alteração deve forçar o processo **Verificação do status de provisionamento do Insights** para ser executado imediatamente.

   Depois que o processo **Verificação do status de provisionamento do Insights** for executado com êxito, você pode habilitar os recursos do Finance insights no espaço de trabalho **Gerenciamento de recursos**.

> [!NOTE]
> Se o processo **Verificação do status de provisionamento do Insights** não for executado, vá para **Administração do sistema** > **Consultas** > **Trabalhos em lotes**. No campo **Sistema de sondagem de automação do processo**, altere o valor para **Aguardando** para iniciar o processo. 
> 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
