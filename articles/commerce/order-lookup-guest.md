---
title: Habilitar pesquisa de ordem para finalização de compra do convidado
description: Este tópico descreve como habilitar a pesquisa de ordem para finalização de compra do convidado no Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 0368f567898210f122047a9f298bcb28b7540de1
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7472566"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Habilitar pesquisa de ordem para finalização de compra do convidado

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico descreve como habilitar a pesquisa de ordem para finalização de compra do convidado no Microsoft Dynamics 365 Commerce.

O recurso de pesquisa de ordem para finalização de compra do convidado permite que os clientes que façam compras como os usuários convidados pesquisam suas ordens. O recurso de pesquisa de ordem é útil quando os clientes desejam executar ações, como verificar o status de cumprimento de produtos em uma ordem, verificar o endereço para o qual uma ordem foi enviada, repetir a ordem de um produto ou confirmar a loja da qual uma ordem será retirada.

Os clientes que fazem ordens como usuários registrados podem ver os detalhes da ordem quando estão conectados, mas os clientes que usam a finalização de compra do convidado para fazer ordens não podem. No entanto, quando o recurso pesquisa de ordem para finalização de compra do convidado está habilitado, ele fornece um formulário que os clientes podem usar para pesquisar ordens que foram feitas como convidados. Neste formulário, os clientes inserem a ID de confirmação da ordem e (opcionalmente) o endereço de email especificado na finalização de compra.

Além disso, um link ou botão que leva o cliente diretamente para a página detalhes da ordem em sua ordem pode ser incluído em qualquer email transacional relacionado à ordem. Este link ou botão funciona para ordens que são feitas por usuários registrados e por usuários convidados.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Ativar os recursos necessários na matriz do Commerce

Para habilitar a pesquisa de ordem para finalização de compra do convidado, você deve habilitar os seguintes recursos em **Espaços de trabalho \> Gerenciamento de recursos** na matriz do Commerce.

| Recurso | Finalidade |
|---------|---------|
| Recurso de opção de detalhes da ordem de pesquisa de usuário anônimo do Retail | Este recurso expõe a interface do usuário em parâmetros do Commerce que permite habilitar a API de pesquisa de ordem para usuários não autenticados e configurar como os dados pessoais são exibidos. |
| Habilitar a geração de uma ID de referência de canal mais resistente | Este recurso gera uma ID de referência de canal de 12 caracteres mais segura (ID de confirmação de ordem) que pode ser passada na cadeia de caracteres de consulta quando uma ordem é pesquisada. |
| Gerar um formato consistente de ID de referência de canal entre os canais | Este recurso gera uma ID de referência de canal seguro para ordens feitas por meio de um site de comércio eletrônico, ponto de venda de varejo (POS) ou call center. Antes de ativar este recurso, o recurso **Habilitar geração de uma ID de referência de canal mais resistente** deve estar ativado. |

Depois de ativar o recurso **Detalhes da ordem de pesquisa de usuário anônimo de varejo**, você deve habilitar a API que oferece suporte à pesquisa de ordem não autenticada na matriz do Commerce. Acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Ordens do cliente**. Na página **Ordens do cliente**, na Guia Rápida **Pesquisa de ordem**, defina a opção **Habilitar pesquisa da ordem não autenticada** como **Sim**, conforme mostrado na ilustração a seguir.

## <a name="manage-the-display-of-personal-data"></a>Gerenciar a exibição de dados pessoais

A Guia Rápida **Pesquisa de ordem** na página **Ordens do cliente** na matriz do Commerce inclui um campo **Incluir dados pessoais na pesquisa de ordem do convidado**, que permite controlar se as informações pessoais são mostradas aos clientes. Essas informações pessoais incluem o endereço de remessa do cliente e os quatro últimos dígitos do número do cartão de crédito do cliente. Por padrão, as informações pessoais não são mostradas aos clientes quando a pesquisa de ordem não autenticada está habilitada. A tabela a seguir descreve as opções disponíveis:

| Opção | Resultado |
|--------|--------|
| Nunca | O valor padrão. Nenhuma informação pessoal é mostrada em pesquisas de ordem. Quando os usuários registrados conectados pesquisarem uma ordem criada enquanto estiverem conectados, eles poderão ver suas informações pessoais. |
| Somente ordens de convidado | As informações pessoais são mostradas em pesquisas de ordem para ordens que os clientes criaram como convidados. Se uma ordem foi criada por um usuário registrado, esse usuário deverá entrar para ver suas informações pessoais. |
| Todas as ordens | Informações pessoais são mostradas em todas as pesquisas de ordem. |

> [!NOTE]
> Estas opções determinam quando dados pessoais, como o endereço do cliente e os quatro últimos dígitos do número do cartão de crédito do cliente, são mostrados para usuários convidados anônimos. Para ajudar a proteger a privacidade de clientes registrados, é recomendável selecionar a opção **Somente ordens de convidado**. No entanto, a opção mais segura é **Nunca**.

Depois de alterar o valor do campo **Incluir dados pessoais na pesquisa de ordem do convidado**, você deve executar o trabalho 1070 (**Configuração de canal**) na matriz Commerce, acessando **Retail e Commerce \> TI de Retail e Commerce \> Agenda de distribuição**.

## <a name="configure-the-order-lookup-module"></a>Configurar o módulo de pesquisa de ordem

O módulo de pesquisa de ordem na biblioteca de módulos do Commerce é usado para renderizar o formulário que os usuários convidados usam para pesquisar ordens. O módulo de pesquisa de ordem pode ser incluído no slot de corpo de qualquer página que não exija entrada do cliente. Para obter informações sobre como configurar o módulo, consulte [Módulo de pesquisa de ordem](order-lookup-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de pesquisa de ordem](order-lookup-module.md)

[Configurar perfil de notificação por email](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
