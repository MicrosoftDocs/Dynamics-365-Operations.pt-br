---
title: Configurar BOPIS em um ambiente de área restrita do Dynamics 365 Commerce
description: Este artigo explica como configurar e fazer compras online, retirar na loja (BOPIS) em um ambiente de área restrita do Microsoft Dynamics 365 Commerce depois que ele for provisionado.
author: BrianShook
ms.date: 06/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-04-20
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 16cea7beb6ca05b5e96a9713b1217b414e27d56e
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013153"
---
# <a name="configure-bopis-in-a-dynamics-365-commerce-sandbox-environment"></a>Configurar BOPIS em um ambiente de área restrita do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artigo explica como configurar e fazer compras online, retirar na loja (BOPIS) em um ambiente de área restrita do Microsoft Dynamics 365 Commerce depois que o ambiente for provisionado.

## <a name="prerequisite"></a>Pré-requisito

Conclua os procedimentos neste artigo somente após o provisionamento e a configuração do seu ambiente de área restrita do Commerce. Para obter informações sobre como provisionar e configurar seu ambiente, consulte [Provisionar um ambiente de área restrita do Dynamics 365 Commerce](provisioning-guide.md) e [Configurar um ambiente de área restrita do Dynamics 365 Commerce](./cpe-post-provisioning.md).

Depois que o ambiente do Commerce tiver sido provisionado e configurado de ponta a ponta, é possível usar esse artigo para habilitar cenários de BOPIS.

## <a name="configure-the-pos"></a>Configurar o PDV

### <a name="configure-modern-pos"></a>Configurar o PDV Moderno

Os cenários de BOPIS que envolvem um pagamento em cartão de crédito exigem uma estação de hardware. A estação de hardware é criada nos programas de PDV Moderno para clientes do Windows e Android. Se você estiver usando o PDV em Nuvem ou o PDV Moderno para iOS, o cliente do ponto de venda (PDV) deve ser emparelhado com uma estação de hardware compartilhada. Este artigo explica como configurar BOPIS para clientes do Windows e Android. Para mais informações sobre como configurar uma estação de hardware compartilhada, consulte [Configurar e instalar a estação de hardware do Retail](./retail-hardware-station-configuration-installation.md).

1. Acesse **Varejo e comércio \> Configuração de canal \> Configuração do PDV \> Caixas registradoras**.
2. Selecione registrar **SANFRAN-5** e, depois, **Editar**.
3. Altere o valor do campo **Perfil do hardware** de **HW002** para **HW001** e selecione **Salvar**.
4. Para sincronizar as alterações, Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
5. Selecione a agenda de distribuição **1090** e selecione **Executar agora** no Painel de Ações.
6. Selecione **Sim** e depois **OK** para iniciar a sincronização de dados. 

### <a name="install-modern-pos"></a>Instalar o PDV Moderno

1. Acesse **Varejo e comércio \> Configuração de canal \> Configuração do PDV \> Dispositivos**.
2. Selecione o dispositivo **SANFRANCIS-5**.
3. No Painel de Ações, selecione **Download** e depois selecione **Arquivo de configuração**.
4. Selecione **Download** e depois **Retail Modern POS**. 
5. Quando o download do arquivo **ModernPOSSetup.exe** for concluído, selecione **Abrir arquivo**.

    ![Abrir arquivo.](./dev-itpro/media/PAYMENTS/openfile.png)

6. Selecione **Avançar** para continuar o processo de instalação. Quando a instalação for concluída, selecione **Fechar**.

### <a name="activate-modern-pos"></a>Ativar o PDV Moderno

1. Na área de trabalho do Windows, selecione o botão **Iniciar** e insira **Retail Modern POS**.
2. Selecione o aplicativo **Retail Modern POS** para iniciar a ativação.
3. Selecione **Avançar**. Os campos **URL do servidor**, **ID do dispositivo** e **Número do registro** devem ser predefinidos usando as informações do arquivo de configuração baixado no procedimento anterior.
4. Selecione **Ativar**.
5. Uma caixa de diálogo de autenticação é exibida. Selecione a conta que usa o endereço de email que foi associado previamente ao trabalhador **000713 - Andrew Collette**.

    > [!NOTE]
    > Se você ainda não associou um trabalhador à sua identidade, a ativação não terá êxito. Nesse caso, siga as etapas na seção "Associar um trabalhador à sua identidade" no artigo [Configurar um ambiente de área restrita do Dynamics 365 Commerce](cpe-post-provisioning.md#associate-a-worker-with-your-identity).
    
6. Quando for solicitado permitir que a sua organização gerencie o dispositivo, selecione **Somente este aplicativo**.
7. Quando a ativação for concluída, selecione **Introdução**.

### <a name="enable-bopis-in-modern-pos"></a>Habilitar BOPIS no PDV Moderno

1. Faça logon no PDV Moderno usando **000713** como ID do operador e **123** como a senha.
2. Enquanto o vídeo do passo a passo introdutório estiver sendo exibido, marque as duas caixas de seleção no canto inferior esquerdo da caixa de diálogo e depois feche-a.
3. Caso não seja solicitado que você feche o turno, role para a direita na página **Inicial**, selecione **Fechar turno** e faça logon novamente no PDV.
4. Após fazer o logon, quando solicitado, selecione **Executar uma operação sem gaveta**.
5. Na página **Inicial**, role para a direita e selecione a operação **Selecionar estação de hardware**.
6. Selecione **Gerenciar**, defina a opção **Usar estação de hardware** como **Ativado** e selecione **OK**.
7. Saia do POS e entre novamente.
8. Depois de fazer logon, selecione **Abrir novo turno** e selecione **Gaveta**.

## <a name="complete-a-bopis-scenario"></a>Concluir um cenário BOPIS

### <a name="create-a-storefront-order-for-in-store-pickup"></a>Crie uma ordem da vitrine para retirada na loja

1. Acesse a URL especificada na etapa [Inicializar o e-Commerce](./provisioning-guide.md#initialize-e-commerce) durante a configuração do ambiente.
2. Selecione um item e, depois, **Adicionar ao carrinho**.
3. Na página da sacola de compras, selecione **Retirar este item** na linha da ordem que acabou de adicionar.
4. Na caixa de diálogo **Selecionar uma loja**, insira **São Francisco** e, depois, selecione o botão **Pesquisar**.
5. Na lista de resultados, encontre a loja em São Francisco e selecione **Retirar aqui**.
6. Na página da sacola de compras, selecione **Finalizar Compra como Convidado**. 

    > [!NOTE]
    > Para continuar com a finalização da compra, é necessário aceitar o aviso de cookies. Este aviso aparece como um banner no topo da página da finalização da compra.

7. Para a forma de pagamento no cartão de crédito, insira os seguintes detalhes:

    - **Nome do titular do cartão:** Insira qualquer nome.
    - **Número do cartão:** Insira **4111-1111-1111-1111**.
    - **Data de vencimento:** Insira **20/10**.
    - **Código do valor de verificação do cartão (CVV)**: Insira **737**.

    > [!IMPORTANT]
    > Nunca, em qualquer circunstância, tente usar as informações reais do cartão de crédito no local do teste.

8. Continue a finalização da compra inserindo os detalhes do endereço de cobrança e selecione **Salvar e continuar**.
9. Quando a ordem estiver pronta para ser realizada, selecione **Finalizar compra**.

### <a name="synchronize-online-orders-to-the-back-office"></a>Sincronizar ordens online para o back-office

Para obter informações sobre como sincronizar ordens online, consulte [Lançamento de vendas e pagamentos online](./tasks/posting-online-sales-payments.md).

### <a name="pick-up-an-order-in-the-store"></a>Retirar um pedido na loja

1. Entrar no PDV.
2. Na tela **Inicial**, selecione **Atendimento da ordem**
3. Na lista de itens para retirada, selecione a linha da ordem que foi lançada online.
4. Quando a linha da ordem for selecionada, selecione **Retirar**.

    O item da linha é adicionado à tela da transação e **US$ 0,00** é exibido como o saldo devido.

5. Selecione o saldo devido de **US$0,00** ou selecione qualquer forma de pagamento para concluir a transação.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="online-orders-that-are-retrieved-in-the-pos-have-a-non-zero-balance-due"></a>As ordens online que são recuperadas no PDV têm um saldo devido diferente de zero

Quando uma ordem for recuperada para uma retirada na loja, se o saldo devido não for zero (0), certifique-se de que o PDV Moderno está sendo usado e de que a estação de hardware está ativa. Se o PDV em Nuvem ou o PDV Moderno para iOS estiver sendo usado, certifique-se de que uma estação de hardware compartilhada está ativa. É necessário ter alguma forma de estação de hardware ativa para recuperar pagamentos que foram feitos online.

### <a name="general-issues-with-payment-capture"></a>Problemas gerais com a captura de pagamento

Para todos os problemas gerais, é necessário sempre consultar o PDV Moderno ou os logs de evento da Estação de Hardware dos Serviços de Informações da Internet (IIS) como a primeira etapa. Você pode encontrar esses logs nos seguintes nós no log de eventos do Windows:

- Logs de Aplicativos e Serviços \> Microsoft \> Dynamics \> Commerce-ModernPOS
- Logs de Aplicativos e Serviços \> Microsoft \> Dynamics \> Commerce-Estação de Hardware

## <a name="additional-resources"></a>Recursos adicionais

[Provisionar um ambiente de área restrita do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar recursos opcionais para um ambiente de área restrita do  Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)

[Conector de pagamento Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3)

[Salvando meios de pagamento online com o conector Adyen](./dev-itpro/adyen-connector-listpi.md)

[Visão geral de pagamentos de omnicanal](./omni-channel-payments.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
