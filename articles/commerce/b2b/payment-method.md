---
title: Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B
description: Este tópico descreve como configurar a forma de pagamento da conta de cliente no Microsoft Dynamics 365 Commerce. Ele também mostra como os limites de crédito afetam a captura de pagamento por conta nos sites de comércio eletrônico entre empresas (B2B).
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a8fdeb109204557f0e44457e23a60224e662474f
ms.sourcegitcommit: 96e2fb26efd2cd07bbf97518b5c115e17b77a0a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2022
ms.locfileid: "8616823"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurar o método de pagamento da conta do cliente para sites de comércio eletrônico B2B

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar a forma de pagamento da conta de cliente no Microsoft Dynamics 365 Commerce. Ele também mostra como os limites de crédito afetam a captura de pagamento por conta nos sites de comércio eletrônico entre empresas (B2B).

Os varejistas podem aceitar vários tipos de pagamento em troca de produtos e serviços vendidos em um canal de comércio eletrônico. Cada tipo de pagamento que o varejista aceita deve ser configurado no Dynamics 365 Commerce quando o sistema for configurado. A forma de pagamento da conta do cliente (ou "por conta") deve ter suporte em sites de comércio eletrônico B2B. 

## <a name="prerequisites"></a>Pré-requisitos

1. Adicione o método de pagamento da conta do cliente na sede do Commerce.
2. Associe o método de pagamento da conta do cliente ao canal de comércio eletrônico.
3. Verifique se a propriedade **Permitir por conta** está habilitada para o cliente em **Varejo e Comércio \> Clientes \> Todos os clientes \> Padrões de pagamentos** no Commerce Headquarters.

    > [!NOTE]
    > Se todos os clientes tiverem permissão para ativar a forma de pagamento por conta, você poderá definir a propriedade **Permitir por conta** como **Sim** para o cliente padrão do canal associado ao site B2B. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce 

Para habilitar o método de pagamento da conta do cliente no assistente para criação de sites do Commerce, siga estas etapas.

1. Acesse **Configurações do Site \> Extensões**.
1. Defina a propriedade **Habilitar pagamentos de conta do cliente** como **Habilitado para clientes B2B**. 
1. Selecione **Salvar e publicar**.

> [!NOTE]
> As novas configurações de sites terão efeito somente após a atualização do arquivo app.settings.json. Para obter mais informações, consulte [SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B

Para habilitar o método de pagamento da conta do cliente na página de finalização de compra para o site de comércio eletrônico B2B, siga estas etapas.

1. No assistente para criação de sites do Commerce, encontre e edite a página de finalização de compra ou o fragmento que contenha o módulo de finalização de compra para o site de comércio eletrônico B2B.
1. No slot de **Contêiner da seção de finalização de compra**, selecione **Adicionar Módulo** e, depois, adicione um módulo **Pagamento de conta do cliente**.
1. Para posicionar o módulo **Pagamento da conta do cliente**, selecione a elipse (**...**) e, depois, selecione **Mover para cima** ou **Mover para baixo**, conforme necessário.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirme que o método de pagamento da conta do cliente foi ativado e publicado

Para confirmar que o método de pagamento da conta do cliente foi ativado e publicado, siga estas etapas.

1. Entre no site de comércio eletrônico.
1. Adicione um produto ao carrinho.
1. Acesse a página de finalização de compra. Você deve ver o novo método de pagamento da **Conta do Cliente**.

## <a name="work-with-credit-limits"></a>Trabalhar com limites de crédito

Quando os recursos de pagamentos de contas de clientes são ativados no site B2B, as organizações normalmente querem mostrar informações sobre limites de crédito e saldos de limite de crédito durante o processo de captura da ordem. O limite de crédito de um cliente é definido pela propriedade **Limite de crédito** na guia rápida **Crédito e cobranças** do registro de cliente no Commerce Headquarters. No entanto, em cenários B2B, uma ordem de um cliente geralmente deve ser faturada para a conta da organização à qual o cliente pertence. Portanto, você deve definir a propriedade **Conta de faturamento** na guia rápida **Fatura e entrega** do registro do cliente para a ID da conta de cliente da organização. Depois, quando o cliente fizer uma ordem no site B2B, ela será faturada para a organização. O site B2B também usará o limite de crédito da organização em vez do limite de crédito definido no registro do cliente.

O cálculo e o saldo do limite de crédito mostrados no site B2B dependem da configuração da propriedade do **Tipo de limite de crédito** no Commerce Headquarters. A localização dessa propriedade varia, dependendo se o recurso **Gerenciamento de crédito** está habilitado no espaço de trabalho **Gerenciamento de recursos**:

- Se o recurso **Gerenciamento de crédito** estiver habilitado, a propriedade estará na guia rápida **Limites de crédito** em **Créditos e cobranças \> Configuração \>Parâmetros de crédito e cobrança \> Crédito**. 
- Se o recurso **Gerenciamento de crédito**, a propriedade estará em **Avaliação de crédito** em **Contas a receber \> Configuração \> Parâmetros de contas a receber \> Avaliação de crédito**.

Os valores aos quais a propriedade **Tipo de limite de crédito** oferece suporte são **Nenhum**, **Saldo**, **Saldo + guia de remessa ou recebimento de produtos** e **Saldo + Todos**. Para obter mais informações sobre esses valores, consulte [Valores de tipo de limite de crédito](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Recomendamos que você defina a propriedade **Tipo de limite de crédito** como **Saldo + guia de remessa ou guia de produto** para que as ordens de venda abertas não entrem para o cálculo do saldo. Em seguida, se os clientes fizerem ordens futuras, não precisarão se preocupar se essas ordens afetarão o saldo atual.

Outra propriedade que afeta a ordem por conta é a propriedade **Limite de crédito obrigatório**, que está localizada na guia rápida **Crédito e cobranças** do registro do cliente. Ao definir essa propriedade como **Sim** para clientes específicos, você pode forçar o sistema a verificar seu limite de crédito, mesmo se a propriedade **Tipo de limite de crédito** tiver sido definida como **Nenhum**, para especificar que o limite de crédito não deve ser verificado para qualquer cliente.

No momento, um cliente que esteja usando a forma de pagamento por conta não poderá pagar mais que o saldo de crédito restante para uma ordem. Por exemplo, se o saldo de crédito restante de um cliente for US$ 1.000, mas o valor da ordem for de US$1.200, o cliente poderá pagar somente US$ 1.000 usando a forma por conta. Ele deve usar outra forma de pagamento para quitar o saldo. Em uma versão futura, uma configuração do Commerce permitirá que os usuários gastem além do limite de crédito ao criar ordens.

O módulo **Crédito e cobrança** tem novos recursos de gerenciamento de crédito. Para ativar esses recursos, habilite o recurso de **Gerenciamento de crédito** no espaço de trabalho **Gerenciamento de recursos**. Um dos novos recursos permite que as ordens de venda sejam colocadas em espera com base nas regras de bloqueio. O gerente de crédito poderá então liberar ou rejeitar as ordens após uma análise adicional. No entanto, a capacidade de colocar ordens de venda em espera não é aplicável a ordens do Commerce, pois as ordens de venda geralmente têm um pagamento antecipado e o recurso de **gerenciamento de crédito** não oferece suporte total a cenários de pagamento antecipado. 

Independentemente da ativação do recurso de **Gerenciamento de crédito**, se o saldo do cliente ultrapassar o limite de crédito durante a efetivação da ordem, as ordens de venda não ficarão em espera. Em vez disso, o Commerce gerará uma mensagem de aviso ou uma mensagem de erro, dependendo do valor do campo **Mensagem ao exceder o limite de crédito** na guia rápida **Limites de crédito**.

A propriedade **Excluir do gerenciamento de crédito** que impede que as ordens de venda do Commerce entrem em espera está localizada no cabeçalho da ordem de venda (**Varejo e comércio\> Clientes \> Todas as ordens de venda**). Se esta propriedade for definida como **Sim** (o valor padrão) para ordens de venda do Commerce, as ordens serão excluídas do fluxo de trabalho em espera do gerenciamento de crédito. Embora a propriedade seja denominada **Excluir do gerenciamento de crédito**, o limite de crédito definido ainda será usado durante a efetivação da ordem. As ordens só não ficarão em espera.

A capacidade de colocar ordens de venda do Commerce em espera com base nas regras de bloqueio é planejada para versões futuras do Commerce. Até que ela seja suportada, se você precisar forçar ordens de venda do Commerce a percorrer os novos fluxos de gerenciamento de crédito, poderá personalizar os seguintes arquivos XML na solução do Visual Studio. Nos arquivos, modifique a lógica para que o sinalizador **CredManExcludeSalesOrder** seja definido como **Não**. Dessa forma, a propriedade **Excluir do gerenciamento de crédito** será definida como **Não**, por padrão, para ordens de venda do Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Se o sinalizador **CredManExcludeSalesOrder** estiver definido como **Não** e um cliente B2B puder comprar de lojas usando o aplicativo do PDV (ponto de venda), o lançamento das transações cash-and-carry poderá falhar. Por exemplo, há uma regra de bloqueio no tipo de pagamento à vista e o cliente B2B comprou alguns itens na loja usando dinheiro. Nesse caso, a ordem de venda resultante não será faturada com êxito porque ela ficará em espera. Portanto, o lançamento falhará. Por esse motivo, recomendamos que você faça os testes de ponta a ponta após a implementação dessa personalização.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar um site de comércio eletrônico B2B](set-up-b2b-site.md)

[Gerenciar parceiros de negócios B2B usando hierarquias do cliente](partners-customer-hierarchies.md)

[Gerenciar usuários parceiros comerciais em sites de comércio eletrônico B2B](manage-b2b-users.md)

[Definir limites de quantidade de produto para sites de comércio eletrônico B2B](quantity-limits.md)

[SDK e atualizações da biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
