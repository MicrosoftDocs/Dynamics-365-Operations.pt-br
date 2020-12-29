---
title: Configurar um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.
author: psimolin
manager: annbe
ms.date: 07/16/2020
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
ms.openlocfilehash: 6a1ae960f0f530104af7bdea9a8fcb78b01571f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410082"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Configurar um ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.

## <a name="overview"></a>Visão Geral

Conclua os procedimentos neste tópico somente após o provisionamento do seu ambiente de avaliação do Commerce. Para obter informações sobre como provisionar seu ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).

Depois que o ambiente de avaliação do Commerce for provisionado de ponta a ponta, as etapas adicionais de configuração de pós-provisionamento deverão ser concluídas para que você possa começar a avaliar o ambiente. Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.

## <a name="before-you-start"></a>Antes de começar

1. Entre no [Portal de LCS](https://lcs.dynamics.com).
1. Vá para seu projeto.
1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, selecione **Fazer logon no ambiente**. Você será direcionado para a sede do Commerce.
1. Verifique se a entidade legal **USRT** está selecionada no canto superior direito.

Durante as atividades de pós-provisionamento na sede do Commerce, garanta que a entidade legal **USRT** esteja sempre selecionada.

## <a name="configure-the-point-of-sale"></a>Configurar o ponto de venda

### <a name="associate-a-worker-with-your-identity"></a>Associar um trabalhador com sua identidade

Para associar um trabalhador à sua identidade, siga estas etapas na sede do Commerce.

1. Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.
1. Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**.
1. No Painel de Ação, selecione **Commerce**.
1. Selecione **Associar identidade existente**.
1. No campo **Email** à direita de **Pesquisar usando email**, insira seu endereço de email.
1. Selecione **Pesquisar**.
1. Selecione o registro com seu nome.
1. Selecione **OK**.
1. Selecione **Salvar**.

### <a name="activate-cloud-pos"></a>Ativar PDV em nuvem

Para ativar o PDV em Nuvem, siga estas etapas no LCS.

1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, selecione **Fazer logon no Ponto de Venda em Nuvem**.
1. Selecione **Avançar** para abrir a caixa de diálogo **Antes de começar**.
1. Deixe o campo **URL do Servidor** como está. Selecione **Avançar**.
1. Entre usando sua conta do Microsoft Azure Active Directory (Azure AD).
1. Em **Nome da loja**, selecione **São Francisco** e, em seguida, selecione **Avançar**.
1. Em **Registro e dispositivo**, selecione **SANFRAN-1**.
1. Selecione **Ativar**. Você está desconectado e será levado para a página de entrada do POS.
1. Agora você pode fazer logon na experiência do Cloud POS usando o ID do operador **000713** e a senha **123**.

## <a name="set-up-your-site-in-commerce"></a>Configurar seu site no Commerce

Para iniciar a configuração do seu site de avaliação no Commerce, siga estas etapas.

1. Entre no construtor de sites usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Selecione o site **Fabrikam** para abrir a caixa de diálogo de configuração do site.
1. Selecione o domínio que você inseriu ao inicializar o comércio eletrônico.
1. Selecione **Loja online estendida Fabrikam** como o canal padrão. (Certifique-se de selecionar a loja online **estendida**.)
1. Selecione **en-us** como o idioma padrão.
1. Deixe o valor do campo **Caminho** como está.
1. Selecione **OK**. A lista de páginas do site é exibida.

## <a name="enable-jobs"></a>Habilitar trabalhos

Para habilitar trabalhos no Commerce, siga estas etapas.

1. Entre no ambiente (Matriz).
1. Use o menu à esquerda, vá para **Varejo e comércio \> Consultas e relatórios \> Trabalhos em lotes**.

    As etapas restantes deste procedimento devem ser concluídas para cada um dos seguintes trabalhos:

    * Processar notificação por email da ordem de varejo
    * Disponibilidade do produto
    * P-0001
    * Sincronizar trabalho de ordens

1. Use o Filtro Rápido para procurar o trabalho pelo nome.
1. Se o status do trabalho for **Em execução**, siga estas etapas:

    1. Selecione o registro.
    1. No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.
    1. Selecione **Cancelar** e, em seguida, selecione **OK**.

Opcionalmente, você também pode definir o intervalo de recorrência como um (1) minuto para os seguintes trabalhos:

* Trabalho Processar notificação por email da ordem de varejo
* Trabalho P-0001
* Sincronizar trabalho de ordens

### <a name="run-full-data-synchronization"></a>Executar sincronização de dados completa

Para executar a sincronização completa dos dados no Commerce, siga estas etapas na sede do Commerce.

1. Use o menu à esquerda para ir para **Módulos \> Varejo e comércio \> Configuração da sede \> Agendador do Commerce \> Banco de dados do canal**.
1. Selecione o canal chamado **scXXXXXXXXX**.
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

Depois que as etapas de provisionamento e configuração forem concluídas, você poderá começar a usar seu ambiente de avaliação. Use a URL do construtor de sites do Commerce para acessar a experiência de criação. Use a URL do site do Commerce para acessar a experiência de site do cliente de varejo.

Para configurar recursos opcionais para seu ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de avaliação do Dynamics 365 Commerce](cpe-overview.md)

[Provisionar um ambiente de avaliação do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce](cpe-optional-features.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)
