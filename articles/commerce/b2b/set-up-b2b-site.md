---
title: Configurar um site de comércio eletrônico entre empresas
description: Este artigo descreve como configurar um site de comércio eletrônico B2B no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 162a8d4b51f10f409b77e1ced4c63c1a69a3b1f2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281115"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Configurar um site de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Sites de comércio eletrônico B2B (entre empresas) fornecem alguns recursos importantes que otimizam o fluxo de trabalho para um usuário de B2B. Este artigo descreve como configurar um site de comércio eletrônico B2B no Microsoft Dynamics 365 Commerce. Ele descreve os módulos e as configurações de site que devem ser configurados para habilitar cenários específicos de B2B.

## <a name="prerequisites"></a>Pré-requisitos

- Para configurar um site de comércio eletrônico B2B, você deve habilitar e configurar recursos específicos no Commerce headquarters, conforme descrito neste artigo.
- As experiências principais, como a descoberta de produtos, as páginas de detalhes dos produtos, o carrinho e a finalização de compra são ativadas pelos mesmos módulos usados para sites de comércio de empresas para clientes (B2C). Os criadores do site devem estar familiarizados com todos os módulos compatíveis do Dynamics 365 Commerce. Para obter mais informações, consulte [Visão geral da biblioteca de módulos](../starter-kit-overview.md).
- Este artigo pressupõe que os criadores do site entendem as noções básicas do construtor de sites, modelos, fragmentos e páginas do Commerce, de forma que possam habilitar os recursos B2B para sites de comércio eletrônico.

## <a name="site-level-settings"></a>Configurações no nível do site

É possível acessar as configurações no nível do site no construtor de sites, em **Configurações do site \> Extensões**. As duas configurações no nível do site a seguir aplicam-se a cenários B2B:

- **Habilitar pagamentos da conta de cliente** – Essa propriedade permite que os usuários paguem pelas ordens usando contas de cliente. Os valores disponíveis são **Habilitado para clientes B2B**, **Habilitado para clientes B2C**, **Habilitado para todos os clientes** e **Desabilitado para todos os clientes**. Se o site B2B oferecer suporte a contas de cliente, você deverá selecionar **Habilitado para clientes B2B**.
- **Habilitar limites de quantidade da ordem** – Essa propriedade permite definir limites no número de itens que podem ser pedidos para cada produto ou categoria. Os valores disponíveis são **Habilitado para clientes B2B**, **Habilitado para clientes B2C**, **Habilitado para todos os clientes** e **Desabilitado para todos os clientes**.

> [!NOTE]
> Ao atualizar para a versão mais recente da biblioteca de módulos, você deve seguir etapas adicionais para garantir que as configurações de site descritas anteriormente estejam disponíveis no seu ambiente. Para obter mais informações, consulte [Atualizar o arquivo app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Criar páginas de inscrição de parceiro de negócios

Para se tornar um parceiro de negócios, os usuários devem primeiro enviar uma solicitação de parceiro de negócios. Um link para a página de solicitação de parceiro de negócios ficará disponível na página inicial B2B, para que os usuários possam iniciar o processo. Depois que os usuários enviarem uma solicitação de parceiro de negócios, eles receberão a confirmação de que a solicitação foi enviada. 

### <a name="create-a-business-partner-request-page"></a>Criar uma página de solicitação de parceiro de negócios

O módulo de **Inscrição de parceiro** em uma página de solicitação de parceiro de negócios é usado que os usuários iniciem solicitações para se tornar parceiros de negócios. Este módulo permite coletar as informações de usuário necessárias para o processo de inscrição. Além disso, o módulo de **Endereço de conta de negócios** é usado para obter o endereço do usuário.

Para configurar a página de solicitação de parceiro de negócios no construtor de sites, siga estas etapas.

1. Crie um modelo denominado **Inscrição**. Este modelo deve incluir os seguintes módulos:

    - Inscrição de parceiro
    - Estrutura
    - Cabeçalho
    - Rodapé
    - Bloco de Conteúdo
    - Bloco de texto
    - Coleção de produtos

1. Use o modelo de **Inscrição** para criar uma página chamada **Solicitação de parceiro de negócios**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial e digite **Início** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Inscrição de parceiro** abaixo do módulo de **Trilha de navegação**. No painel de propriedades do módulo, em **Título**, digite **Tornar-se um parceiro de negócios**.
1. No slot **Inscrição de parceiro**, adicione um módulo de **Endereço de conta de negócios**.
1. No slot **Contêiner**, adicione um módulo de **Bloco de texto** abaixo do módulo de **Inscrição de parceiro**. Aqui, você pode definir alguns termos e condições para o processo de inscrição.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.

### <a name="create-a-business-partner-request-confirmation-page"></a>Criar uma página de confirmação da solicitação de parceiro de negócios

Depois que uma solicitação de parceiro de negócios é enviada, uma página de confirmação deve ser mostrada para que o usuário confirme o envio. 

Para configurar a página de confirmação da solicitação no construtor de sites, siga estas etapas.

1. Use o modelo de **Inscrição** que você criou anteriormente para criar uma página chamada **Confirmação da solicitação de parceiro**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo de **Bloco de conteúdo**. No painel de propriedades do módulo, em **Título**, digite **Solicitação enviada**. No campo **Rich Text**, digite **Sua solicitação foi enviada**. Em **Links**, configure um link para a página inicial e digite **Continuar comprando** como o texto do link.
1. Adicione outro módulo de **Contêiner** e adicione um módulo de **Coleção de produtos** a ele.
1. Configure o módulo de **Coleção de produtos** com a lista de recomendações ou categorias que deseja apresentar na página.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.

Para adicionar um link à página de confirmação da solicitação no construtor de sites, siga estas etapas.

1. Acesse a página de **Solicitação de parceiro de negócios** que você criou anteriormente e selecione **Editar**. 
1. Selecione o slot do módulo de **Inscrição de parceiro**. No painel de propriedades, em **Vincular à página de confirmação de inscrição**, configure o link para a página de solicitação de parceiro de negócios criada anteriormente. 
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Adicionar link de solicitação de parceiro de negócios à página inicial

Depois de as páginas de solicitação de inscrição e confirmação de parceiro de negócios serem criadas, você deve tornar a página de inscrição acessível por meio de um link na página inicial. Você pode concluir essa tarefa adicionando o link a qualquer módulo de **Bloco de conteúdo** na página inicial.

Para adicionar um link de solicitação de parceiro de negócios na página inicial do construtor de sites, siga estas etapas.

1. Acesse a página inicial do seu site e selecione **Editar**.
1. Selecione um slot do módulo de **Bloco de conteúdo**. No painel de propriedades do módulo, em **Links**, configure um link para a página de solicitação de parceiro de negócios que você criou anteriormente e digite **Inscrever-se como parceiro de negócios** ou um texto semelhante como o texto do link. Adicione uma imagem conforme apropriado.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="account-management-landing-page"></a>Página de aterrissagem de gerenciamento de contas

A página inicial de gerenciamento de contas inclui todas as informações de gerenciamento de contas necessárias para os sites de comércio eletrônico B2B e B2C. Somente os usuários conectados podem visualizar esta página.

Para criar e configurar uma página inicial de gerenciamento de contas B2B no construtor de sites, siga estas etapas.

1. Crie um modelo denominado **Gerenciamento de conta**. Este modelo deve incluir os seguintes módulos:

    - Cabeçalho
    - Rodapé
    - Estrutura
    - Bloco de boas-vindas da conta
    - Bloco genérico da conta
    - Bloco de endereço da conta
    - Bloco de lista de desejos da conta
    - Bloco de endereço da conta
    - Bloco de fidelidade da conta
    - Bloco de saldo do cliente da conta
    - Bloco de modelos de ordem da conta
    - Usuários da organização
    - Lista de organizações de negócios
    - Saldo da conta do cliente
    - Linhas do modelo de ordem
    - Lista de modelos de ordem
    - Bloco da fatura da conta
    - Lista de faturas
    - Detalhes da fatura

1. Use o modelo de **Gerenciamento de contas** para criar uma página chamada **Minha conta**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. 
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial e digite **Início** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Bloco de boas-vindas**. No painel de propriedades do módulo, em **Título**, digite **Bem-vindo**.
1. No slot **Principal**, adicione outro módulo de **Contêiner** (**Contêiner 2**). No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. Defina o valor **Filhos mostrados** como **Dois**. 
1. No slot do **Contêiner 2**, adicione um módulo de **Bloco genérico da conta**. No painel de propriedades do módulo, em **Título**, digite **Meu perfil**. Em **Links**, configure um link para a página **Meu perfil**. 
1. No slot do **Contêiner 2**, adicione outro módulo de **Bloco genérico da conta**. No painel de propriedades do módulo, em **Título**, digite **Histórico de ordens**. Em **Links**, configure um link para a página de histórico de ordens.
1. No slot **Principal**, adicione outro módulo de **Contêiner** (**Contêiner 3**). No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. Defina o valor **Filhos mostrados** como **Dois**. 
1. No slot do **Contêiner 3**, adicione um módulo de **Bloco de endereço da conta**. No painel de propriedades do módulo, em **Título**, digite **Meu endereço**. Em **Links**, configure um link para a página **Meu endereço**. 
1. No slot do **Contêiner 3**, adicione um módulo de **Bloco de lista de desejos da conta**. No painel de propriedades do módulo, em **Título**, digite **Minha lista de desejos**. Em **Links**, configure um link para a página **Minha lista de desejos**.
1. No slot **Principal**, adicione outro módulo de **Contêiner** (**Contêiner 4**). No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. Defina o valor **Filhos mostrados** como **Dois**. 
1. No slot do **Contêiner 4**, adicione um módulo de **Usuários da organização**. No painel de propriedades do módulo, em **Título**, digite **Usuários da organização**. 
1. No slot do **Contêiner 4**, adicione um módulo de **Bloco de saldo do cliente da conta**. No painel de propriedades do módulo, em **Título**, digite **Crédito da conta**. 
1. No slot **Principal**, adicione outro módulo de **Contêiner** (**Contêiner 5**). No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. Defina o valor **Filhos mostrados** como **Dois**. 
1. No módulo do **Contêiner 5**, adicione um módulo de **Bloco de modelos de ordem da conta**. No painel de propriedades do módulo, em **Título**, digite **Modelos de ordem**. 
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

> [!NOTE] 
> Algumas das seções que você adicionou na etapa 13 a 18 não aparecerão na tela "você vê como vai aparecer" (WYSIWIG) no construtor de sites, pois elas exigem uma conta B2B conectada.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Criar e configurar páginas e módulos de saldo do cliente 

As contas de cliente podem ser usadas para pagar ordens. O saldo disponível em uma conta de cliente pode ser exibido na página de gerenciamento de conta de um usuário.

### <a name="create-a-customer-balance-page"></a>Criar uma página de saldo do cliente 

Antes que os usuários B2B conectados possam visualizar o saldo do cliente, você deve criar uma página de saldo do cliente. 

Para criar uma página de saldo do cliente no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Saldo do cliente**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione outro módulo de **Contêiner** (**Contêiner 3**). No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**. Defina o valor **Filhos mostrados** como **Dois**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link.
1. No slot do **Contêiner**, adicione um módulo de **Saldo da conta do cliente**. No painel de propriedades do módulo, em **Título**, digite **Saldo da conta**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.
1. Acesse a página inicial de gerenciamento de conta (**Minha conta**) que você criou anteriormente.
1. No painel Propriedades do módulo de **Bloco de saldo do cliente da conta**, adicione um link à página de saldo do cliente. 
1. Salve e publique a página.

A página de saldo do cliente foi criada e os usuários podem acessá-la na página inicial de gerenciamento de conta.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Configurar uma página de finalização de compra para que o saldo do cliente possa ser usado como uma forma de pagamento

O módulo de **Pagamento de conta de cliente** é necessário para que o saldo do cliente possa ser habilitado como uma forma de pagamento. Esse módulo deve ser adicionado à página de finalização de compra como uma forma de pagamento. Para obter informações sobre como configurar uma página de finalização de compra e os módulos necessários para finalizar compras, incluindo todos os detalhes de pagamento, consulte [Módulo de finalização de compra](../add-checkout-module.md).

Depois de configurar uma página de finalização de compra, você deve adicionar o módulo de **Pagamento de conta do cliente** à seção de pagamento, salve e publicar a página. Os usuários B2B poderão fazer se conectar ao site de comércio eletrônico e aplicar seu saldo de cliente disponível às ordens durante a finalização de compra.

Além disso, em **Construtor de sites \> Extensões**, você deve verificar se a propriedade **Habilitar pagamentos de conta do cliente** está definida como **Habilitado para clientes B2B**.

## <a name="create-order-template-pages"></a>Criar páginas de modelo de ordem

Duas páginas de modelo de ordem podem ser configuradas para um site de comércio eletrônico B2B: uma página de lista de modelos de ordem e uma página de linhas de modelo de ordem.

Uma página de lista de modelos de ordem mostra uma lista de todos os modelos de ordem disponíveis. Ela é configurada com o módulo de **Lista de modelos de ordem**. A página de lista de modelos de ordem permite criar ou excluir um modelo e adicionar os itens de um modelo ao carrinho.

Uma página de linhas de modelo de ordem mostra os detalhes do modelo de ordem selecionado em uma página de lista de modelos de ordem. Ela é configurada com o módulo de **Linhas de modelos de ordem**. Quando um usuário seleciona o nome de um modelo em uma página de lista de modelos de ordem, a página de linhas de modelo de ordem aparece e mostra os detalhes do modelo. O usuário poderá visualizar e editar os itens no modelo.

### <a name="create-an-order-templates-list-page"></a>Criar uma página de lista de modelos de ordem

Para criar uma página de modelos de ordem no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Modelos de ordem**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Lista de modelos de ordem**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.
1. Acesse a página inicial de gerenciamento de conta (**Minha conta**) que você criou anteriormente.
1. No painel de propriedades do módulo de **Bloco de modelos de ordem de conta**, em **Links**, configure um link para a página de lista de modelos de ordem que você acabou de criar.
1. Salve e publique a página.

A página de lista de modelos de ordem foi criada e os usuários podem acessá-la na página inicial de gerenciamento de conta.

### <a name="create-an-order-template-lines-page"></a>Criar uma página de linhas de modelo de ordem

Para criar uma página de linhas de modelo de ordem no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Linhas de modelo de ordem**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Linhas de modelo de ordem**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.

## <a name="onboard-business-partner-users"></a>Usuários do parceiro de negócios integrado

A página de usuários da organização permite que o administrador de uma organização de negócios parceira integre os usuários adicionais dessa organização ao site de comércio eletrônico B2B. Ela é configurada com o módulo de **Lista de organizações de negócios**. Na página de usuários da organização, um administrador pode adicionar ou remover usuários, definir saldos de conta e solicitar demonstrativos para um usuário.

Para criar uma página de usuários da organização no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Usuários da organização**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Lista de organizações de negócios**. No painel de propriedades do módulo, em **Título**, digite **Usuários da organização**.
1. No painel de propriedades do módulo de **Lista de organizações de negócios**, habilite as Propriedades **Classificação em tabela** e **Paginação em tabela**. Defina a contagem de paginação como **5**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.
1. Acesse a página inicial de gerenciamento de conta (**Minha conta**) que você criou anteriormente.
1. No painel de propriedades do módulo de **Bloco de usuários da organização**, em **Links**, configure um link para a página de usuários da organização que você acabou de criar. 
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="create-invoice-pages"></a>Criar páginas de fatura

Uma página de lista de faturas mostra uma lista de todas as faturas disponíveis. Ela é configurada com o módulo **InvoicesList**. Na página de lista de faturas, os usuários podem pagar ou solicitar faturas. 

Uma página de detalhes da fatura mostra os detalhes da fatura selecionada em uma página de lista de faturas. Ela é configurada com o módulo de **Detalhes da fatura**. Quando um usuário seleciona um ID de fatura em uma página de lista de faturas, a página de detalhes da fatura aparece e mostra os detalhes da dela.

### <a name="create-an-invoices-list-page"></a>Criar uma página de lista de faturas

Para criar uma página de lista de faturas no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Lista de faturas**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link.
1. No slot **Contêiner**, adicione um módulo **InvoicesList**. No painel de propriedades do módulo, em **Título**, digite **Faturas**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.
1. Acesse a página inicial de gerenciamento de conta (**Minha conta**) que você criou anteriormente.
1. No painel de propriedades do módulo de **Bloco de faturas da conta**, em **Links**, configure um link para a página de lista de faturas que você acabou de criar. 
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

### <a name="create-an-invoice-details-page"></a>Criar uma página de detalhes da fatura

Para criar uma página de detalhes da fatura no construtor de sites, siga estas etapas.

1. Use o modelo de **Gerenciamento de conta** criado anteriormente para criar uma página chamada **Detalhes da fatura**.
1. No slot **Cabeçalho**, adicione o fragmento de cabeçalho que é pré-configurado com o cabeçalho do site.
1. No slot **Rodapé**, adicione o fragmento de rodapé que é pré-configurado com o rodapé do site.
1. No slot **Principal**, adicione um módulo de **Contêiner**. No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.
1. No slot **Contêiner**, adicione um módulo **Trilha de navegação**. No painel de propriedades do módulo, em **Links**, configure um link para a página inicial de gerenciamento de conta e digite **Minha conta** como o texto do link. Em seguida, configure um link para a página de lista de faturas e insira **Listas de faturas** como o texto do link.
1. No slot **Contêiner**, adicione um módulo de **Detalhes da fatura**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.
1. Publique o URL para a página.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Adicionar um módulo de adição rápida à página de carrinho

O módulo de adição rápida oferece uma maneira de adicionar rapidamente vários itens ao carrinho usando IDs de item (também conhecidas como IDs de unidade de manutenção de estoque \[SKU\]). O módulo de adição rápida é adicionado à página de carrinho de um site.

Para adicionar um módulo de adição rápida a uma página de carrinho no construtor de sites do Commerce, siga estas etapas.

1. Acesse **Modelos** e selecione o modelo da página de carrinho do seu site.
1. Selecione **Editar**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Adição rápida** e depois **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione a página de carrinho do seu site.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades do módulo **Contêiner**, em **Largura**, selecione **Preencher Contêiner**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Adição rápida** e depois **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

> [!NOTE] 
> O módulo de adição rápida está disponível a partir do Commerce versão 10.0.17. Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="add-a-bulk-purchase-module-to-a-product-details-page"></a>Adicionar um módulo de compra em massa a uma página de detalhes do produto

O módulo de compra em massa em uma página de detalhes do produto (PDP) oferece uma experiência com base em matriz, que permite ao comprador adicionar rapidamente variantes de um produto ao carrinho. Quando um usuário do site precisa encomendar variantes do mesmo produto, essa experiência elimina a necessidade de selecionar a combinação de dimensões do produto, definir a quantidade, adicionar a variante ao carrinho e repetir o processo para outras combinações.

Para adicionar o módulo de compra em massa a uma PDP no construtor de sites do Commerce, siga estas etapas.

1. Acesse **Modelos** e selecione o modelo da PDP do seu site.
1. Selecione **Editar**.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Compra em massa** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione a PDP do seu site.
1. No slot **Principal** do módulo **Página Padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No painel de propriedades do módulo **Contêiner**, em **Largura**, selecione **Preencher contêiner**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Compra em massa** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

> [!NOTE] 
> O módulo de compra em massa está disponível a partir da versão 10.0.24 do Commerce. Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](../starter-kit-overview.md)

[SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Visão geral da página Criação](../authoring-home-overview.md)

[Visão geral de modelos e layouts](../templates-layouts-overview.md)

[Trabalhar com fragmentos](../work-with-fragments.md)

[Adicionar uma nova página do site](../add-new-page.md)

[Módulo de finalização da compra](../add-checkout-module.md)

[Módulo de bloco de conteúdo](../add-hero-module.md)

[Módulos de coleta de produtos](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
