---
title: "Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário"
description: "Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e Cloud POS."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: faf8cdcee70b55842072298b51789f6cd7a577af
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Configurações do aplicativo de ponto de venda (PDV) e de idioma do usuário

[!include [banner](includes/banner.md)]

Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e Cloud POS.

## <a name="overview"></a>Visão Geral

Retail Modern POS (MPOS) e Cloud POS suportam ambientes onde configurações de idioma e traduções podem variar entre as configurações de loja e de usuário. Por exemplo, a loja pode estar localizada em uma região onde o inglês é mais comum para seus clientes, mas alguns trabalhadores preferem usar o aplicativo com as traduções em francês.

## <a name="data-language"></a>Idioma dos dados

Independentemente das configurações do usuário, o MPOS e PDV na Nuvem sempre usarão as configurações de idioma da loja para determinar as traduções usadas para dados. Isso garantirá que todos usuário e clientes terão uma experiência consistente. Exemplos de dados incluem:

- Produtos
- Atributos e valores
- Nomes de categoria
- Recibos de transação enviados por email ou impressos
- Nomes de método de pagamento
- Mensagens de exibição de linha

O idioma da loja também será usado para a tela principal de login do PDV, pois o usuário não é conhecido antes do login. Se uma tradução não estiver disponível para o idioma da loja, o PDV reverterá para o idioma da empresa.

### <a name="configuring-the-stores-language-setting"></a>Definindo a configuração do idioma da loja

A configuração do idioma da loja é definida em **Todas as lojas de varejo** na página **Loja de Varejo** em **Geral &gt; Configurações Regionais &gt; Idioma**. Use o menu suspenso para escolher o idioma para cada loja.

## <a name="user-interface-language"></a>Idioma da interface do usuário

As configurações de idioma do PDV determinam as traduções usadas na interface de usuário do aplicativo. Isso inclui os rótulos, menus e listas que não são considerados dados. Uma exceção é o texto exibido em grades de botão do PDV. As grades de botão não oferecem suporte a traduções e, portanto, sempre mostrarão o texto como definido no botão. Para dar suporte aos botões traduzidos, você terá de copiar e manter as grades de botão separadas e atribuí-las aos usuários como apropriado.

### <a name="configuring-the-users-language-setting"></a>Definindo a configuração do idioma do usuário

A configuração de idioma do usuário do PDV é definida em **Todos os trabalhadores** na página **Trabalhador** em **Varejo &gt; Idioma**. Ela não é definida na guia principal Perfil. Essa configuração não é usada pelo PDV. Se o idioma do usuário não for definido ou for definido como um idioma no qual as traduções não estejam disponíveis, o PDV será revertido para o idioma da loja.

|             | Idioma da interface do usuário                  | Idioma dos dados (produtos, formatos de recibo, exibição de linha etc.) |
|-------------|----------------------------|---------------------------------------------------------------|
| **Empresa** | Padrão                    | Padrão                                                       |
| **Loja**   | Substitui a empresa          | Substitui a empresa                                             |
| **Usuário**    | Substitui a loja ou a empresa | Nunca                                                         |

