---
title: Cliente Talent se desconecta
description: Este tópico explica o que fazer se o cliente estiver desconectado de seu ambiente e não sabe o porquê.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6d174a8acac3863fb6d9f9431c6bc777cb717470
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008166"
---
# <a name="talent-client-disconnects"></a>Cliente Talent se desconecta

[!include [banner](includes/banner.md)]

**Detalhes do ambiente** 

Esse problema pode ocorrer em todos os ambientes.
 
**Sintoma** 

O cliente estiver desconectado de seu ambiente e não sabe o porquê. O cliente recebe uma das mensagens de erro:

- Perdemos sua conexão. Clique em Fechar para continuar trabalhando.
- Parece que você perdeu a conectividade de rede. Clique em Repetir para tentar novamente.

**Sinalizador vermelho**

Esse problema ocorre com frequência quando usuários estão no estágio de implementação, são informações de comparação entre produção e ambientes de teste, e esquecem que estão movendo entre sessões. Se os usuários estiverem neste estágio, eles provavelmente passarão por esse problema.

**Emissão** 

**Tipos de navegador:** Google Chrome, Internet Explorer e Microsoft Edge

O Microsoft Dynamics 365 Talent desconecta os usuários quando duas sessões diferentes são abertas ao mesmo tempo para o mesmo usuário e o mesmo tipo de navegador. (Por exemplo, usuário A está exibindo tanto o ambiente 1 quanto o 2 no Chrome.) Não importa se os usuários abram janelas de navegador diferentes ou guias diferentes. Se as mesmas credenciais de usuário são usadas para entrar tanto no ambiente 1 quanto no ambiente 2 ao mesmo tempo e no mesmo tipo de navegador, Talent desconecta uma das sessões.

**Solução**

Verifique se somente um ambiente está aberto em vez de um navegador de tipo determinado. Os usuários podem abrir mais sessões no mesmo ambiente (ou seja, várias guias no navegador.)

Os usuários que desejam pular entre dois ambientes ao mesmo tempo devem abrir cada ambiente em um tipo de navegador diferente. (Por exemplo, o usuário A pode exibir o ambiente 1 no Chrome e o ambiente 2 no Microsoft Edge.)
