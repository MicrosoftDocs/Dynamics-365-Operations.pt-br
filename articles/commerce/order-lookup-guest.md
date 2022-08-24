---
title: Habilitar pesquisa de ordem para finalização de compra do convidado
description: Este artigo descreve como habilitar a pesquisa de ordem para finalização de compra do convidado no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4f381f1ec0ea08f18db3cac474e8990906364504
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286882"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Habilitar pesquisa de ordem para finalização de compra do convidado

[!include [banner](includes/banner.md)]

Este artigo descreve como habilitar a pesquisa de ordem para finalização de compra do convidado no Microsoft Dynamics 365 Commerce.

O recurso de pesquisa de ordem para finalização de compra do convidado permite que os clientes que façam compras como os usuários convidados pesquisam suas ordens. O recurso de pesquisa de ordem é útil quando os clientes desejam executar ações, como verificar o status de cumprimento de produtos em uma ordem, verificar o endereço para o qual uma ordem foi enviada, repetir a ordem de um produto ou confirmar a loja da qual uma ordem será retirada.

Os clientes que fazem ordens como usuários registrados podem ver os detalhes da ordem quando estão conectados, mas os clientes que usam a finalização de compra do convidado para fazer ordens não podem. No entanto, quando o recurso pesquisa de ordem para finalização de compra do convidado está habilitado, ele fornece um formulário que os clientes podem usar para pesquisar ordens que foram feitas como convidados. Neste formulário, os clientes inserem a ID de confirmação da ordem e (opcionalmente) o endereço de email especificado na finalização de compra.

Além disso, um link ou botão que leva o cliente diretamente para a página detalhes da ordem em sua ordem pode ser incluído em qualquer email transacional relacionado à ordem. Este link ou botão funciona para ordens que são feitas por usuários registrados e por usuários convidados.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Ativar os recursos necessários no Commerce headquarters

Para habilitar a pesquisa de ordem para finalização de compra do convidado, você deve habilitar os seguintes recursos em **Espaços de trabalho \> Gerenciamento de recursos** no Commerce headquarters.

| Recurso | Finalidade |
|---------|---------|
| Recurso de opção de detalhes da ordem de pesquisa de usuário anônimo do Retail | Este recurso expõe a interface do usuário em parâmetros do Commerce que permite habilitar a API de pesquisa de ordem para usuários não autenticados e configurar como os dados pessoais são exibidos. |
| Habilitar a geração de uma ID de referência de canal mais resistente | Este recurso gera uma ID de referência de canal de 12 caracteres mais segura (ID de confirmação de ordem) que pode ser passada na cadeia de caracteres de consulta quando uma ordem é pesquisada. |
| Gerar um formato consistente de ID de referência de canal entre os canais | Este recurso gera uma ID de referência de canal seguro para ordens feitas por meio de um site de comércio eletrônico, ponto de venda de varejo (POS) ou call center. Antes de ativar este recurso, o recurso **Habilitar geração de uma ID de referência de canal mais resistente** deve estar ativado. |

Depois de ativar o recurso **Detalhes da ordem de pesquisa de usuário anônimo de varejo**, você deve habilitar a API que oferece suporte à pesquisa de ordem não autenticada no Commerce headquarters. Acesse **Retail e Commerce \> Configuração do headquarters \> Parâmetros \> Ordens do cliente**. Na página **Ordens do cliente**, na Guia Rápida **Pesquisa de ordem**, defina a opção **Habilitar pesquisa da ordem não autenticada** como **Sim**, conforme mostrado na ilustração a seguir.

## <a name="manage-the-display-of-personal-data"></a>Gerenciar a exibição de dados pessoais

A Guia Rápida **Pesquisa de ordem** na página **Ordens do cliente** no Commerce headquarters inclui um campo **Incluir dados pessoais na pesquisa de ordem do convidado**, que permite controlar se as informações pessoais são mostradas aos clientes. Essas informações pessoais incluem o endereço de remessa do cliente e os quatro últimos dígitos do número do cartão de crédito do cliente. Por padrão, as informações pessoais não são mostradas aos clientes quando a pesquisa de ordem não autenticada está habilitada. A tabela a seguir descreve as opções disponíveis:

| Opção | Resultado |
|--------|--------|
| Nunca | O valor padrão. Nenhuma informação pessoal é mostrada em pesquisas de ordem. Quando os usuários registrados conectados pesquisarem uma ordem criada enquanto estiverem conectados, eles poderão ver suas informações pessoais. |
| Somente ordens de convidado | As informações pessoais são mostradas em pesquisas de ordem para ordens que os clientes criaram como convidados. Se uma ordem foi criada por um usuário registrado, esse usuário deverá entrar para ver suas informações pessoais. |
| Todas as ordens | Informações pessoais são mostradas em todas as pesquisas de ordem. |

> [!NOTE]
> Estas opções determinam quando dados pessoais, como o endereço do cliente e os quatro últimos dígitos do número do cartão de crédito do cliente, são mostrados para usuários convidados anônimos. Para ajudar a proteger a privacidade de clientes registrados, é recomendável selecionar a opção **Somente ordens de convidado**. No entanto, a opção mais segura é **Nunca**.

Depois de alterar o valor do campo **Incluir dados pessoais na pesquisa de ordem do convidado**, execute o trabalho 1070 (**Configuração do canal**) no Commerce headquarters, acessando **Varejo e comércio \> TI de varejo e comércio \> Agenda de distribuição**.

## <a name="configure-the-order-lookup-module"></a>Configurar o módulo de pesquisa de ordem

O módulo de pesquisa de ordem na biblioteca de módulos do Commerce é usado para renderizar o formulário que os usuários convidados usam para pesquisar ordens. O módulo de pesquisa de ordem pode ser incluído no slot de corpo de qualquer página que não exija entrada do cliente. Para obter informações sobre como configurar o módulo, consulte [Módulo de pesquisa de ordem](order-lookup-module.md).

## <a name="configure-the-order-details-page"></a>Configurar a página de detalhes da ordem

Antes que os usuários convidados possam ver os detalhes da ordem, a página de detalhes da ordem no site de comércio eletrônico deve ser configurada para que não exija credenciais. Para desativar a solicitação de credenciais na página de detalhes da ordem, abra a página no construtor de sites do Commerce, selecione o slot **Página padrão (obrigatório)** no modo de exibição de árvore e desmarque a caixa de seleção **Requer entrada?** na parte inferior do painel de propriedades à direita.

## <a name="add-a-link-to-order-details-in-transactional-emails"></a>Adicionar um link para os detalhes da ordem nos emails transacionais

Em emails relacionados a ordens, você pode fornecer um link ou um botão que leva os clientes à página de detalhes da ordem. Para adicionar esse link ou botão, crie um hiperlink HTML que leve à página de detalhes da ordem no seu site de comércio eletrônico e transmita o ID de confirmação da ordem e o endereço de email do cliente como parâmetros da URL, conforme o exemplo a seguir.

`<a href="https://[domain]/[orderdetailspage]?confirmationId=%orderconfirmationid%&propertyName=email&propertyValue=%customeremailaddress%" target="_blank">View my order status</a>`

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de pesquisa de ordem](order-lookup-module.md)

[Configurar perfil de notificação por email](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
