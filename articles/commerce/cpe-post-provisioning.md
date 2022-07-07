---
title: Configurar um ambiente de área restrita do Dynamics 365 Commerce
description: Este artigo explica como configurar um ambiente de área restrita do Microsoft Dynamics 365 Commerce depois que ele for provisionado.
author: psimolin
ms.date: 06/14/2022
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
ms.openlocfilehash: 259a580981003f135e234f66e9e93ceb18605412
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013100"
---
# <a name="configure-a-dynamics-365-commerce-sandbox-environment"></a>Configurar um ambiente de área restrita do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artigo explica como configurar um ambiente de área restrita do Microsoft Dynamics 365 Commerce depois que ele for provisionado.

Conclua os procedimentos neste artigo somente após o provisionamento do seu ambiente de área restrita do Commerce. Para obter informações sobre como provisionar seu ambiente de área restrita do Commerce, consulte [Provisionar um ambiente de área restrita do Commerce](provisioning-guide.md).

Depois que o ambiente de área restrita do Commerce for totalmente provisionado, as etapas adicionais de configuração posteriores ao provisionamento devem ser concluídas para que você possa começar a usar o ambiente. Para concluir essas etapas, você deve usar Microsoft Dynamics Lifecycle Services (LCS) e Dynamics 365 Commerce.

## <a name="before-you-start"></a>Antes de começar

1. Entre no [Portal de LCS](https://lcs.dynamics.com).
1. Acesse seu projeto.
1. Selecione seu ambiente na lista.
1. Nas informações sobre o ambiente à direita, selecione **Fazer logon no ambiente**. Você será direcionado para o Commerce headquarters.
1. Verifique se a entidade legal **USRT** está selecionada no canto superior direito. Esta entidade legal foi pré-configurada nos dados de demonstração.
1. Acesse **Parâmetros do Commerce \> Parâmetros de configuração** e verifique se há uma entrada para **ProductSearch.UseAzureSearch** definida como **verdadeira**. Se esta entrada estiver ausente, adicione-a e defina o valor como **verdadeiro**.
1. Acesse **Retail e Commerce \> Configuração do headquarters \> Agendador do Commerce \> Inicializar agendador do Commerce** No submenu **Inicializar agendador do Commerce**, certifique-se de que a opção **Excluir configuração existente** esteja definida como **Sim** e, em seguida, selecione **OK**.
1. Para que os canais de armazenamento e comércio eletrônico funcionem corretamente, eles devem ser adicionados à Commerce Scale Unit. Acesse **Varejo e Comércio \> Configuração da sede \> Agendador do Commerce \> Banco de dados do canal** e, no painel esquerdo, selecione a Commerce Scale Unit. Na Guia Rápida **Canal de varejo**, adicione os canais **Loja online da AW**, **Loja online da AW para empresas** e **loja online estendida da Fabrikam** se planeja usar esses canais de comércio eletrônico. Opcionalmente, você também pode adicionar lojas de varejo se for usar o PDV (ponto de venda) (por exemplo, **Seattle**, **San Francisco** e/ou **San Jose**).
1. Para garantir que todas as alterações sejam sincronizadas com o banco de dados do canal, selecione **Banco de Dados do Canal \> Sincronização de dados completa** para a Commerce Scale Unit.

Durante as atividades de pós-provisionamento no Commerce headquarters, garanta que a entidade legal **USRT** esteja sempre selecionada.

## <a name="configure-the-point-of-sale"></a>Configurar o ponto de venda

### <a name="associate-a-worker-with-your-identity"></a>Associar um trabalhador com sua identidade

Para associar um trabalhador à sua identidade, siga estas etapas no Commerce headquarters.

1. Use o menu à esquerda, Acesse **Módulos \> Varejo e comércio \> Funcionários \> Trabalhadores**.
1. Na lista, encontre e selecione o registro a seguir: **000713 - Andrew Collette**. Este exemplo de usuário está associado ao armazenamento de San Francisco que será usado na próxima seção.
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

## <a name="set-up-your-e-commerce-sites"></a>Configurar seus sites de comércio eletrônico

Há três sites de demonstração de comércio eletrônico disponíveis: Fabrikam, Adventure Works e Adventure Works para empresas. Siga as etapas abaixo para configurar cada site de demonstração.

1. Entre no construtor de sites usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Selecione o site (**Fabrikam**, **Adventure Works** ou **Adventure Works para empresas**) para abrir a caixa de diálogo configuração do site.
1. Selecione o domínio que você inseriu ao inicializar o Commerce.
1. Na matriz, selecione o canal de loja online pré-configurado (**Loja online estendida da Fabrikam**, **Loja online da AW** ou **Loja online da AW para empresas**) que corresponda ao canal padrão.
1. Selecione **en-us** como o idioma padrão.
1. Configure os campos de caminho. Isso pode ser deixado em branco para um único site, mas deverá ser configurado se você usar o mesmo nome de domínio para vários sites. Por exemplo, se o nome de domínio for `https://www.constoso.com`, você poderá usar um caminho em branco para a Fabrikam (`https://contoso.com`) e, em seguida, usar "aw" para Adventure Works (`https://contoso.com/aw`) e "awbusiness" para o site para empresas da Adventure Works (`https://contoso.com/awbusiness`).
1. Selecione **OK**. A lista de páginas do site é exibida.
1. Opcionalmente, repita as etapas 2 a 7 para configurar os outros sites de demonstração, se necessário.

## <a name="enable-jobs"></a>Habilitar trabalhos

Para habilitar trabalhos no Commerce, siga estas etapas.

1. Entre no seu ambiente da sede.
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

Depois que as etapas de provisionamento e configuração forem concluídas, você poderá começar a usar seu ambiente de área restrita. Use a URL do construtor de sites do Commerce para acessar a experiência de criação. Use a URL do site do Commerce para acessar a experiência de site do cliente de varejo.

Para configurar recursos opcionais de seu ambiente de área restrita do Commerce, consulte [Configurar recursos opcionais para um ambiente de área restrita do Commerce](cpe-optional-features.md).

Para habilitar usuários de comércio eletrônico a entrar no site de comércio eletrônico, é necessária configuração adicional para habilitar a autenticação do site por meio do business-to-consumer (B2C) do Azure Active Directory. Para obter instruções, consulte [Configurar um locatário B2C no Commerce](set-up-b2c-tenant.md).

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

[Provisionar um ambiente de área restrita do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar recursos opcionais para um ambiente de área restrita do  Dynamics 365 Commerce](cpe-optional-features.md)

[Configurar BOPIS em um ambiente de área restrita do Dynamics 365 Commerce](cpe-bopis.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Configurar um locatário de B2C no Commerce](set-up-B2C-tenant.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
