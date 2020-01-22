---
title: Configurar um ambiente de visualização de comércio
description: Este tópico explica como configurar um ambiente de visualização do Microsoft Dynamics 365 Commerce após ter sido provisionado.
author: psimolin
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f19d03f3f2f5a9f6f7ba08b682277e4e3b764d10
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906130"
---
# <a name="configure-a-commerce-preview-environment"></a>Configurar um ambiente de visualização de comércio

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico explica como configurar um ambiente de visualização do Microsoft Dynamics 365 Commerce após ter sido provisionado.

## <a name="overview"></a>Visão geral

Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de visualização comercial. Para obter informações sobre como provisionar seu ambiente de visualização do Commerce depois, consulte [Provisionar um ambiente de visualização do Commerce](provisioning-guide.md).

Depois que o ambiente de visualização comercial é provisionado de ponta a ponta, as etapas adicionais de configuração posteriores ao provisionamento devem ser concluídas para que você possa começar a avaliar o ambiente. Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS), Dynamics 365 Commerce e Dynamics 365 Retail.

## <a name="before-you-start"></a>Antes de começar

1. Entre no [Portal de LCS](https://lcs.dynamics.com).
1. Vá para seu projeto.
1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.
1. Selecione **Logon** para abrir um menu e depois selecione **Fazer logon no ambiente**.
1. Verifique se a entidade legal **USRT** está selecionada no canto superior direito.

## <a name="configure-the-point-of-sale-in-lcs"></a>Configurar o ponto de venda no LCS

### <a name="associate-a-worker-with-your-identity"></a>Associar um trabalhador com sua identidade

Para associar um trabalhador à sua identidade no LCS, siga estas etapas.

1. Use o menu à esquerda, vá para **Módulos \> Varejo \> Funcionários \> Trabalhadores**.
1. Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.
1. No Painel de Ação, selecione **Varejo**.
1. Selecione **Associar identidade existente**.
1. No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.
1. Selecione **Pesquisar**.
1. Selecione o registro com seu nome.
1. Selecione **OK**.
1. Selecione **Salvar**.

### <a name="activate-cloud-pos"></a>Ativar PDV em nuvem

Para ativar a nuvem POS no LCS, siga estas etapas.

1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, clique em **Detalhes completos**.
1. Selecione **Logon** para abrir um menu e selecione **Fazer logon no ponto de venda da nuvem** para abrir o ponto de venda (POS).
1. Selecione **Avançar**.
1. Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).
1. Em **Nome da loja**, selecione **São Francisco**.
1. Selecione **Avançar**.
1. Em **Registro e dispositivo**, selecione **SANFRAN-1**.
1. Selecione **Ativar**. Você está desconectado e será levado para a página de entrada do POS.
1. Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.

## <a name="set-up-your-site-in-commerce"></a>Configurar seu site no Commerce

Para iniciar a configuração do seu site de visualização no Commerce, siga estas etapas.

1. Efetue login na ferramenta de gerenciamento de site usando a URL que você fez uma observação ao inicializar o comércio eletrônico durante o provisionamento (consulte [Inicializar comércio eletrônico](provisioning-guide.md#initialize-e-commerce)).
1. Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.
1. Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.
1. Selecione **Loja online estendida Fabrikam** como o canal padrão. (Certifique-se de selecionar a loja online **estendida**.)
1. Selecione **en-us** como o idioma padrão.
1. Deixe o valor do campo **Caminho** como está.
1. Selecione **OK**. A lista de páginas do site é exibida.

## <a name="enable-jobs-in-retail"></a>Habilitar trabalhos no Varejo

Para habilitar trabalhos em Varejo, siga estas etapas.

1. Entre no ambiente (Matriz).
1. Use o menu à esquerda, vá para **Varejo \> Consultas e relatórios \> Trabalhos em lotes**.

    As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:

    * Processar notificação por email da ordem de varejo
    * Disponibilidade do produto
    * P-0001
    * Sincronizar trabalho de ordens

1. Use o Filtro Rápido para procurar o trabalho pelo nome.
1. Se o status do trabalho for **Retido**, siga estas etapas:

    1. Selecione o registro.
    1. No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.
    1. Selecione **Aguardando** e, depois, **OK**.

### <a name="run-full-data-synchronization-in-retail"></a>Executar sincronização completa de dados no varejo

Para executar a sincronização completa dos dados no Varejo, siga estas etapas.

1. Use o menu à esquerda para ir para **Módulos \> Varejo \> configuração da Sede \> agendador do Retail \> Banco de dados do canal**.
1. Na lista à esquerda, o canal **Padrão** é selecionado. Selecione o outro canal disponível. Esse canal é nomeado **scXXXXXXXXX**.
1. No Painel de Ação, selecione **Sincronização de dados completa**.
1. Digite **9999** como a agenda de distribuição.
1. Selecione **OK**.
1. Selecione **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testar informações do cartão de crédito para testar compras

Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:

- **Número do cartão:** 4111-1111-1111-1111
- **Data de vencimento:** 20/10
- **Código do valor de verificação do cartão (CVV):** 737

> [!IMPORTANT]
> Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.

## <a name="next-steps"></a>Próximas etapas

Depois que as etapas de provisionamento e configuração forem concluídas, você estará pronto para avaliar seu ambiente de visualização. Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de criação de páginas. Use a URL da ferramenta de gerenciamento de site do Commerce para ir para a experiência de site do cliente de varejo.

Para configurar recursos opcionais de seu ambiente de visualização do Commerce, consulte [Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de visualização do Commerce](cpe-overview.md)

[Provisionar um ambiente de visualização do Commerce](provisioning-guide.md)

[Configurar recursos opcionais para um ambiente de visualização do Commerce](cpe-optional-features.md)

[Perguntas frequentes do ambiente de visualização do Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Recursos de ajuda do Dynamics 365 Retail](../retail/index.md)
