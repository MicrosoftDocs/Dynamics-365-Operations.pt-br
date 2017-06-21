---
title: "Aplicativos de PDV e configurações do idioma do usuário"
description: "Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e Cloud POS."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b2cbdb8bc65a3bfa84620a50480c503c3bb07991
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="pos-application-and-user-language-settings"></a>Aplicativos de PDV e configurações do idioma do usuário

[!include[banner](includes/banner.md)]


Este tópico descreve como alterar as configurações de idioma no Retail Modern POS (MPOS) e Cloud POS.

<a name="overview"></a>Visão Geral
========

Retail Modern POS (MPOS) e Cloud POS suportam ambientes onde configurações de idioma e traduções podem variar entre as configurações de loja e de usuário. Por exemplo, a loja pode estar localizada em uma região onde o inglês é mais comum para seus clientes, mas alguns trabalhadores preferem usar o aplicativo com as traduções em francês.

## <a name="data-language"></a>Idioma dos dados
Independentemente das configurações do usuário, MPOS e Cloud POS sempre usarão as configurações de idioma de loja para determinar as traduções usadas para dados. Isso garantirá que todos usuário e clientes terão uma experiência consistente.  Exemplos de dados incluem:

-   Produtos
-   Atributos e valores
-   Nomes de categoria
-   Recibos de transação enviados por email ou impressos
-   Nomes de método de pagamento
-   Mensagens de exibição de linha

O idioma de loja será usado também para a tela de login do PDV principal, pois o usuário não é conhecido antes do login. Se uma tradução não estiver disponível para o idioma da loja, o PDV reverterá o idioma da empresa.

### <a name="configuring-the-stores-language-setting"></a>Definindo a configuração do idioma da loja

A configuração de idioma da loja é definida em **Todas as lojas de varejo** na página **Loja de varejo** em **Configurações &gt; regionais gerais &gt; Idioma. ** Use o menu suspenso para escolher o idioma para cada loja.

## <a name="user-interface-language"></a>Idioma da interface do usuário
As configurações de idioma do PDV determinam as traduções usadas na interface de usuário do aplicativo. Isso inclui os rótulos, menus e listas que não são considerados dados. Uma exceção é o texto exibido em grades de botão do PDV. As grades de botão não oferecem suporte a traduções e, portanto, sempre mostrarão o texto como definido no botão. Para dar suporte aos botões traduzidos, você terá de copiar e manter as grades de botão separadas e atribuí-las aos usuários como apropriado.

### <a name="configuring-the-users-language-setting"></a>Definindo a configuração do idioma do usuário

A configuração de idioma do usuário do PDV é definida em **Todos os funcionários** na página **Trabalhador** em **Varejo &gt; Idioma**.  Não é definido na guia principal Perfil.  Esta configuração não é usada pelo PDV. Se o idioma do usuário não for definido ou for definido como um idioma no qual as traduções não estão disponíveis, o PDV será revertido para o idioma da loja.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **Idioma da interface do usuário** ** **      | **Idioma dos dados (produtos, formatos de recibo, exibição de linha etc.)** |
| **Empresa** | Padrão                    | Padrão                                                           |
| **Loja**   | Substitui a empresa          | Substitui a empresa                                                 |
| **Usuário**    | Substitui a loja ou a empresa | Nunca                                                             |






