--- 
title: Configurar encargos suplementares do hub e mestres suplementares
description: Este procedimento mostra como criar um mestre suplementar para um hub e usar esse mestre para criar um encargo suplementar do hub.
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6381416640ffacf0a9d96d7da96bc33612ca7137
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Configurar encargos suplementares do hub e mestres suplementares

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um mestre suplementar para um hub e usar esse mestre para criar um encargo suplementar do hub. O procedimento usa o conjunto de dados USMF. Essa configuração será feita tipicamente por um coordenador de transporte.


## <a name="set-up-a-hub-master"></a>Configurar um mestre de hub
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Mestres suplementares.
2. Clique em Novo.
3. No campo Mestre suplementar, digite um valor.
4. No campo Nome, digite um valor.
5. No campo Tipo de acessório, selecione 'Hub'.
6. Clique em Salvar.
7. Feche a página.

## <a name="set-up-a-hub-accessorial-charge"></a>Configurar um encargo suplementar do hub
1. Vá para Gerenciamento de transporte > Configurar > Classificação > Encargos suplementares do hub.
2. Clique em Novo.
3. No campo ID suplementar do hub, digite um valor.
4. No campo Hub, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o PDV desejado.
6. No campo Posição do hub, selecione uma opção.
    * Você pode criar o encargo como uma retirada ou uma entrega. Dependendo da sua escolha, o encargo será aplicado ao segmento de transporte correspondente na sua rota.  
7. No campo Mestre suplementar, clique no botão suspenso para abrir a pesquisa.
8. Na lista, clique no link na linha selecionada.
    * Selecione o mestre que você acabou de criar.  
9. Clique em Salvar.
10. Feche a página.


