---
title: Criar e associar uma estação de hardware
description: Este procedimento orienta como criar uma nova estação de hardware.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80df4fa663d208e28f5c9b031b6610d29286171c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "330554"
---
# <a name="create-and-associate-a-hardware-station"></a>Criar e associar uma estação de hardware

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta como criar uma nova estação de hardware. Um novo perfil de hardware será criado e usado para adicionar novas estações de hardware a uma loja predefinida (canal). Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Fundamentos do comércio > Canais > .. > .. > .. > Perfis das estações de hardware.
2. Clique em Novo.
3. No campo ID da estação de hardware, digite 'TestHWProfile'.
4. No campo Nome, digite um valor.
5. No campo Número da porta, insira um número.
6. No campo Perfil de hardware, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo Nome do pacote, clique no botão suspenso para abrir a pesquisa.
10. Na lista, clique no link na linha selecionada.
    * Este é o pacote padrão vindo com um novo ambiente. O número de versão pode variar.  
11. Clique em Salvar.
12. Feche a página.
13. Vá para Varejo e comércio > Canais > Todas as lojas de varejo.
14. Na lista, selecione a linha 17.
    * Se você estiver usando a empresa de dados de demonstração USRT, esta é a loja Houston.  
15. Na lista, clique no link na linha selecionada.
16. Ative/desative a expansão da seção Estações de hardware.
17. Clique em Adicionar.
18. Na lista, marque a linha selecionada.
19. No campo ID do perfil, clique no botão suspenso para abrir a pesquisa.
20. Na lista, localize e selecione o PDV desejado.
    * Este deve ser o novo perfil da estação de hardware criado nas etapas anteriores.  
21. Na lista, clique no link na linha selecionada.
22. No campo Nome do host, digite um valor.
23. No campo ID do terminal de TEF, digite um valor.
24. Clique em Salvar.

