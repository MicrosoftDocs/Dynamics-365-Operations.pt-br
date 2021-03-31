---
title: Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico explica como configurar recursos opcionais para um ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: def99a34404357e28501de5ccf11c6130d53f34f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213809"
---
# <a name="configure-optional-features-for-a-dynamics-365-commerce-evaluation-environment"></a>Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico explica como configurar recursos opcionais para um ambiente de avaliação do Microsoft Dynamics 365 Commerce.

## <a name="prerequisites"></a>Pré-requisitos

Se quiser avaliar os recursos transacionais de email, os seguintes pré-requisitos deverão ser atendidos:

- Há um servidor de email disponível (servidor Simple Mail Transfer Protocol \[SMTP\]) que pode ser usado da assinatura do Microsoft Azure onde você provisionou o ambiente de avaliação.
- Você tem o nome de domínio totalmente qualificado (FQDN)/endereço IP do servidor, o número da porta SMTP e os detalhes de autenticação disponíveis.

## <a name="configure-the-image-back-end"></a>Configurar o back-end de imagem

### <a name="find-your-media-base-url"></a>Encontrar sua URL base da mídia

> [!NOTE]
> Antes de concluir este procedimento, você deve concluir as etapas em [Configurar seu site no Commerce](cpe-post-provisioning.md#set-up-your-site-in-commerce).

1. Entre no construtor de sites do Commerce usando a URL que você anotou ao inicializar o e-Commerce durante o provisionamento (consulte [Inicializar o e-Commerce](provisioning-guide.md#initialize-e-commerce)).
1. Abra o site **Fabrikam**.
1. No menu à esquerda, selecione **Biblioteca de Mídia**.
1. Selecione qualquer ativo único da imagem.
1. No Inspetor de propriedades à direita, localize a propriedade de **URL pública**. O valor é uma URL. Este é um exemplo:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/MA1nQC`.

1. Substitua o último identificador no URL (**MA1nQC** no exemplo anterior) pela seguinte string **search?fileName=**. Esta é a aparência da URL de exemplo após esta alteração ser feita:

    `https://images-us-sb.cms.commerce.dynamics.com/cms/api/fabrikam/imageFileData/search?fileName=`

    Esta URL é sua URL base da mídia. Anote-o.

### <a name="update-the-media-base-url"></a>Atualize a URL base da mídia

1. Entre na sede do Commerce.
1. Use o menu à esquerda, vá para **Módulos \> Varejo e comércio \> Configuração do Canal \> Perfis do canal**.
1. Selecione **Editar**.
1. Em **Propriedades do perfil**, substitua o valor da propriedade da **URL Base do Servidor de Mídia** com a URL Base de Mídia que você criou anteriormente.
1. Selecione o canal chamado **scXXXXXXXXX**.
1. Em **Propriedades de perfil**, selecione **Adicionar**.
1. Para a propriedade adicionada, selecione **URL Base do Servidor de Mídia** como a chave de propriedade. Como o valor da propriedade, insira a URL base da mídia criada anteriormente.
1. Selecione **Salvar**.

## <a name="configure-and-test-the-email-server"></a>Configurar e testar o servidor de email

> [!NOTE]
> Observe que o servidor SMTP ou o serviço de email digitado aqui deve estar acessível na assinatura do Azure que você está usando para o ambiente.

1. Entre na sede do Commerce.
1. Use o menu à esquerda para acessar **Módulos \> Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros de email**.
1. Na guia **Configurações de SMTP**, no campo **Servidor de email de saída**, insira o FQDN ou o endereço IP do servidor SMTP ou serviço de email.
1. No campo **Número da porta SMTP**, insira o número da porta. (Se você não estiver usando Secure Sockets Layer \[SSL\], o número da porta padrão é **25**.)
1. Se a autenticação for necessária, insira os valores nos campos **Nome de usuário** e **Senha**.
1. Selecione **Salvar**.
1. Selecione **Atualizar**.
1. Na guia **Email de teste**, no campo **Provedor de email**, selecione **SMTP**.
1. No campo **Enviar a**, insira o endereço de email para o qual você quer que o email de teste seja enviado.
1. Selecione **Enviar email de teste**.

## <a name="configure-email-templates"></a>Configurar modelos de email

Para cada evento transacional para o qual você deseja enviar emails, você deve atualizar o modelo de email com um endereço de email do remetente válido.

1. Entre na sede do Commerce.
1. Use o menu à esquerda para acessar **Módulos \> Retail e Commerce \> Configuração da sede \> Parâmetros \> Modelos de email da organização**.
1. Selecione **Mostrar lista**.
1. Para cada modelo na lista, siga estas etapas:

    1. No campo **Email do remetente**, insira o email do remetente.
    1. Opcional: no campo **Nome do remetente**, insira o nome que deve ser usado como o nome do remetente.

1. Selecione **Salvar**.

## <a name="customize-email-templates"></a>Personalizar modelos de email

Você pode desejar personalizar os modelos de email para que eles usem imagens diferentes. Ou, talvez queira atualizar os links nos modelos para que eles levem você ao seu ambiente de avaliação. Esse procedimento explica como baixar os modelos padrão, personalizá-los e atualizar os modelos no sistema.

1. Em um navegador da Web, baixe o [arquivo zip de modelos de email padrão para a Avaliação do Microsoft Dynamics 365 Commerce](https://download.microsoft.com/download/d/7/b/d7b6c4d4-fe09-4922-9551-46bbb29d202d/Commerce.Preview.Default.Email.Templates.zip) no seu computador local. Esse arquivo contém os seguintes documentos HTML:

    - Módulo de confirmação da ordem
    - Emitir modelo de vale-presente
    - Novo modelo de ordem
    - Empacotar modelo de ordem
    - Separar modelo de ordem

1. Personalizar os modelos usando um texto ou editor HTML. Consulte a lista de [tokens compatíveis](#supported-tokens-in-the-email-template) posteriormente neste tópico.
1. Entre no Commerce.
1. Use o menu à esquerda para acessar **Módulos \> Administração da organização \> Configurar \> Modelos de email da organização**.
1. Expanda a lista à esquerda para consultar todos os modelos.
1. Para cada modelo que você deseja personalizar, siga estas etapas:

    1. Selecione o modelo na lista.
    1. Em **Conteúdo da mensagem de email**, selecione a versão do idioma apropriado na lista. (O idioma padrão é **en-us**.)
    1. Em **Conteúdo da mensagem de email**, selecione **Editar**. O painel **Carregar modelo de email** é exibido.
    1. Selecione **Procurar** e localize o arquivo HTML que tem o conteúdo personalizado.
    1. Selecione **Carregar**. O modelo será carregado no sistema e a visualização será mostrada.
    1. Selecione **OK**.
    1. Opcional: personalize a propriedade **Assunto** do modelo.
    1. Selecione **Salvar**.

### <a name="supported-tokens-in-the-email-template"></a>Tokens suportados no modelo de email

Quando o email é processado, esses tokens são substituídos com valores reais que se aplicam ao cliente e ao pedido do cliente.

#### <a name="sales-order"></a>Ordem de venda

Os seguintes tokens se aplicam à ordem de venda geral.

| Nome do token | Token |
|-------------------|-------|
| Número da ordem      | %salesid% |
| Nome do cliente   | %customername% |
| Endereço de entrega  | %deliveryaddress% |
| Endereço para cobrança   | %customeraddress% |
| Data da ordem        | %shipdate% |
| Modo de entrega     | %modeofdelivery% |
| Desconto          | %discount% |
| Impostos         | %tax% |
| Total da ordem       | %total% |

#### <a name="sales-line"></a>Linha de venda 

Os seguintes tokens são substituídos com valores para cada produto no pedido.

> [!NOTE]
> Coloque o token **Lista de produtos - iniciar** no início do bloqueio de HTML que é repetido para cada produto, e insere o token **Lista de produto - fim** no final do bloqueio.

| Nome do token      | Token |
|------------------------|-------|
| Lista de produtos - início   | \<!--%tablebegin.salesline% --\> |
| Lista de produtos - fim     | \<!--%tableend.salesline%--\> |
| Nome do produto           | %lineproductname% |
| descrição            | %lineproductdescription% |
| Quantidade               | %linequantity% |
| Preço unitário da linha        | %lineprice% (verificar) |
| total do item de linha        | %linenetamount% |
| desconto de linha          | %linediscount% |
| Data da remessa              | %lineshipdate% |
| Método de aquisição     | %linedeliverymode% |
| endereço de entrega       | %linedeliveryaddress% |
| Unidade de venda da linha | %lineunit% |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do ambiente de avaliação do Dynamics 365 Commerce](cpe-overview.md)

[Provisionar um ambiente de avaliação do Dynamics 365 Commerce](provisioning-guide.md)

[Configurar um ambiente de avaliação do Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce](cpe-bopis.md)

[Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portal do Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Site do Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]