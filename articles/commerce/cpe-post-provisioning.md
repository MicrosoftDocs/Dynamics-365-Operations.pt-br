---
title: Configurar um ambiente de avaliação do Dynamics 365 Commerce
description: Este artigo explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.
author: psimolin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 19d88139e35554bce68bc6203141957b96e439a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892321"
---
# <a name="configure-a-dynamics-365-commerce-evaluation-environment"></a>Configurar um ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artigo explica como configurar um ambiente de avaliação do Microsoft Dynamics 365 Commerce após ter sido provisionado.

Conclua os procedimentos neste artigo somente após o provisionamento do seu ambiente de avaliação do Commerce. Para obter informações sobre como provisionar seu ambiente de avaliação do Commerce, consulte [Provisionar um ambiente de avaliação do Commerce](provisioning-guide.md).

Depois que o ambiente de avaliação do Commerce for provisionado de ponta a ponta, as etapas adicionais de configuração de pós-provisionamento deverão ser concluídas para que você possa começar a avaliar o ambiente. Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.

## <a name="before-you-start"></a>Antes de começar

1. Entre no [Portal de LCS](https://lcs.dynamics.com).
1. Acesse seu projeto.
1. No menu superior, selecione **Ambientes hospedados na nuvem**.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, selecione **Fazer logon no ambiente**. Você será direcionado para o Commerce headquarters.
1. Verifique se a entidade legal **USRT** está selecionada no canto superior direito.
1. Acesse **Parâmetros do Commerce \> Parâmetros de configuração** e verifique se há uma entrada para **ProductSearch.UseAzureSearch** definida como **verdadeira**. Se essa entrada estiver faltando, você pode adicioná-la, definir o valor como **verdadeiro** e selecionar **Banco de Dados do Canal \> Sincronização de dados completa** para a Commerce Scale Unit associada ao seu site de comércio eletrônico.
1. Acesse **Retail e Commerce \> Configuração do headquarters \> Agendador do Commerce \> Inicializar agendador do Commerce** No submenu **Inicializar agendador do Commerce**, certifique-se de que a opção **Excluir configuração existente** esteja definida como **Sim** e, em seguida, selecione **OK**.
1. Para adicionar canais ao Commerce Scale Unit, vá para **Retail e Commerce \> Configuração do headquarters \> Agendador do Commerce \> Banco de dados do canal** e, no painel esquerdo, selecione o Commerce Scale Unit. Na guia rápida **Canal de varejo**, adicione os canais **Loja online do AW**, **Loja online do AW Business** e **loja online estendida Fabrikam**. Opcionalmente, você também pode adicionar lojas de varejo se usar o POS (por exemplo, **Seattle**, **San Francisco** e **San Jose**).

Durante as atividades de pós-provisionamento no Commerce headquarters, garanta que a entidade legal **USRT** esteja sempre selecionada.

## <a name="configure-the-point-of-sale"></a>Configurar o ponto de venda

### <a name="associate-a-worker-with-your-identity"></a>Associar um trabalhador com sua identidade

Para associar um trabalhador à sua identidade, siga estas etapas no Commerce headquarters.

1. Use o menu à esquerda, Acesse **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.
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
1. Repita as etapas de 2 a 7 para o site do **AdventureWorks** (que mapeia para o canal **Loja online do AW**) e o site do **AdventureWorks Business** (que mapeia para o canal **Loja online do AW Business**). Se o campo **Caminho** para o site do Fabrikam estiver vazio, você deverá adicionar caminhos para os dois sites do AdventureWorks (por exemplo, "aw" e "awbusiness").

## <a name="enable-jobs"></a>Habilitar trabalhos

Para habilitar trabalhos no Commerce, siga estas etapas.

1. Entre no ambiente (Matriz).
1. Use o menu à esquerda, Acesse **Varejo e comércio \> Consultas e relatórios \> Trabalhos em lotes**.

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

1. Se o status do trabalho for **Retido**, siga estas etapas:

    1. Selecione o registro.
    1. No Painel de Ação, na guia **Trabalho em lotes**, selecione **Alterar status**.
    1. Selecione **Aguardando** e, depois, **OK**.

Opcionalmente, você também pode definir o intervalo de recorrência como um (1) minuto para os seguintes trabalhos:

* Trabalho Processar notificação por email da ordem de varejo
* Trabalho P-0001
* Sincronizar trabalho de ordens

### <a name="run-full-data-synchronization"></a>Executar sincronização de dados completa

Para executar a sincronização completa dos dados no Commerce, siga estas etapas no Commerce headquarters.

1. Use o menu à esquerda para ir para **Módulos \> Varejo e comércio \> Configuração do headquarters \> Agendador do Commerce \> Banco de dados do canal**.
1. Selecione o canal chamado **scXXXXXXXXX**.
1. No Painel de Ação, selecione **Sincronização de dados completa**.
1. Digite **9999** como a agenda de distribuição.
1. Selecione **OK**.
1. Selecione **OK**.

### <a name="test-credit-card-information-to-do-test-purchases"></a>Testar informações do cartão de crédito para testar compras

Para realizar transações de teste no site, você pode usar as informações do cartão de crédito de teste a seguir:

- **Número do cartão:** 4111-1111-1111-1111
- **Data de vencimento:** 30/10
- **Código do valor de verificação do cartão (CVV):** 737

> [!IMPORTANT]
> Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.

## <a name="next-steps"></a>Próximas etapas

Depois que as etapas de provisionamento e configuração forem concluídas, você poderá começar a usar seu ambiente de avaliação. Use a URL do construtor de sites do Commerce para acessar a experiência de criação. Use a URL do site do Commerce para acessar a experiência de site do cliente de varejo.

Para configurar recursos opcionais para seu ambiente de avaliação do Commerce, consulte [Configurar recursos opcionais para um ambiente de avaliação do Commerce](cpe-optional-features.md).

> [!NOTE]
> Os ambientes de avaliação do Commerce vêm com um locatário do business-to-consumer B2C pré-carregado do Azure Active Directory (Azure AD) para fins de demonstração. Configurar seu próprio locatário do Azure AD B2C não é necessário para os ambientes de avaliação. No entanto, se você estiver configurando o ambiente de avaliação para usar seu próprio locatário do Azure AD B2C, certifique-se de adicionar ``https://login.commerce.dynamics.com/_msdyn365/authresp`` como uma URL de resposta no aplicativo do Azure AD B2C por meio do Portal do Azure.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="site-builder-channel-list-is-empty-when-configuring-site"></a>A lista de canais do construtor de sites está vazia durante a configuração do site

Se o construtor de sites não mostrar nenhum canal de loja online, no headquarters, verifique se os canais foram adicionados ao Commerce Scale Unit, conforme descrito na seção [Antes de começar](#before-you-start) acima. Além disso, execute **Inicializar Agendador do Commerce** com o valor **Excluir configuração existente** definido como **Sim**.  Uma vez que essas etapas são concluídas, na página **Banco de dados do canal**(**Retail e Commerce \> Configuração do headquarters \> Agendador do Commerce \> Banco de dados do canal**), execute o trabalho **9999** no Commerce Scale Unit.

### <a name="color-swatches-are-not-rendering-on-the-category-page-but-are-rendering-on-the-product-details-page-pdp-page"></a>As amostras de cor não são renderizadas na página de categoria, mas na página de detalhes do produto (PDP)

Siga estas etapas para garantir que as amostras de cor e de tamanho estejam definidas como refináveis.

1. No headquarters, acesse **Varejo e Comércio \> Configuração de canal \> Categorias do canal e atributos de produto**.
1. No painel esquerdo, selecione o canal de loja online e, em seguida, selecione **Definir metadados do atributo**.
1. Defina a opção **Mostrar atributo no canal** como **Sim**, defina a opção **Pode ser refinado** como **Sim** e selecione **Salvar**. 
1. Volte à página do canal de loja online e selecione **Publicar atualizações de canal**.
1. Vá para **Retail e Commerce \> Configuração do headquarters \> Agendador do Commerce \> Banco de dados do canal** e execute o trabalho **9999** no Commerce Scale Unit.

### <a name="business-features-dont-appear-to-be-turned-on-for-the-adventureworks-business-site"></a>Os recursos comerciais não parecem estar ativados para o local da empresa do AdventureWorks

No headquarters, verifique se o canal de loja online está configurado com o **Tipo de cliente** definido como **B2B**. Se o **Tipo de cliente** for definido como **B2C**, um novo canal deverá ser criado, pois o canal existente não poderá ser editado. 

Os dados de demonstração fornecidos no Commerce versão 10.0.26 e versões anteriores tinham um bug no qual o canal da **loja online do AW Business** estava configurado incorretamente. A solução é criar um novo canal com as mesmas definições e configurações, exceto para o **Tipo de cliente**, que deve ser definido como **B2B**.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de avaliação do Dynamics 365 Commerce](cpe-overview.md)

[Provisionar um ambiente de avaliação do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce](cpe-optional-features.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Configurar um locatário de B2C no Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
