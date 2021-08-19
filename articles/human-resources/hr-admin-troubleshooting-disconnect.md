---
title: O cliente desconecta
description: Este artigo explica o que fazer se o cliente for desconectado do ambiente e não souber por que.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3ee3bb4547cb9d77b7559ce4ba54b478f63cb045caefefec0583b3f9b03cf53b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770471"
---
# <a name="client-disconnects"></a>O cliente desconecta

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Detalhes do ambiente** 

Esse problema pode ocorrer em todos os ambientes.
 
**Sintoma** 

O cliente é desconectado do ambiente e não sabe por que. O cliente recebe uma das mensagens de erro:

- Perdemos sua conexão. Clique em Fechar para continuar trabalhando.
- Parece que você perdeu a conectividade de rede. Clique em Repetir para tentar novamente.

**Sinalizador vermelho**

Esse problema ocorre com frequência quando usuários estão no estágio de implementação, são informações de comparação entre produção e ambientes de teste, e esquecem que estão movendo entre sessões. Se os usuários estiverem neste estágio, eles provavelmente passarão por esse problema.

**Emissão** 

**Tipos de navegador:** Google Chrome, Internet Explorer e Microsoft Edge

O Microsoft Dynamics 365 Human Resources desconecta os usuários quando duas sessões diferentes são abertas ao mesmo tempo para o mesmo usuário e o mesmo tipo de navegador. (Por exemplo, usuário A está exibindo tanto o ambiente 1 quanto o 2 no Chrome.) Não importa se os usuários abram janelas de navegador diferentes ou guias diferentes. Se as mesmas credenciais de usuário são usadas para entrar tanto no ambiente 1 quanto no ambiente 2 ao mesmo tempo e no mesmo tipo de navegador, Human Resources desconecta uma das sessões.

**Solução**

Verifique se somente um ambiente está aberto em vez de um navegador de tipo determinado. Os usuários podem abrir mais sessões no mesmo ambiente (ou seja, várias guias no navegador.)

Os usuários que desejam pular entre dois ambientes ao mesmo tempo devem abrir cada ambiente em um tipo de navegador diferente. (Por exemplo, o usuário A pode exibir o ambiente 1 no Chrome e o ambiente 2 no Microsoft Edge.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]