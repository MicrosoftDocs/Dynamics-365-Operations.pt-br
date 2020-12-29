---
title: Atribuição de imposto e substituições
description: Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais de comércio.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74a7eed04648c63c0b19d5de26d2bdbef59aec7d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422233"
---
# <a name="sales-tax-assignment-and-overrides"></a> Substituições e atribuições de impostos

[!include [banner](../../includes/banner.md)]

Este procedimento demonstra como atribuir grupos dos impostos sobre venda aos canais de comércio. Também mostra o processo de criação de uma substituição de impostos e atribuição da mesma ao grupo de substituição de impostos existente. Este procedimento usa a empresa USRT nos dados de demonstração.

1. Vá para Retail e Commerce > Canais > Lojas > Todas as lojas.
2. Na lista, clique no link do ID do Canal para "Houston".
3. Clique em Editar.
    * O campo "Grupo de impostos sobre vendas" contém a lista de grupos de imposto para a empresa atual. O grupo atualmente atribuído é um grupo genérico dos impostos sobre venda de "Texas". Também há grupos de impostos para "Washington" e "Washington, King County". Os grupos de impostos podem incluir impostos aplicáveis a várias municipalidades.  
    * O campo "Substituição de imposto" é onde os grupos de imposto de substituição podem ser mapeados ao canal. Os grupos da substituição dos impostos sobre venda podem ser usados para agrupar junto impostos sobre venda que cancelam esse trabalho para lojas múltiplas. Em vez de atribuir manualmente substituição de impostos sobre venda um por um, o grupo pode ser criado e atribuído diretamente aos canais para ganhar o tempo.  
4. Clique em Salvar.
5. Feche a página.
6. Vá para Retail e Commerce > Configuração de canal > Impostos > Substituições de impostos.
7. Clique em Novo.
8. No campo Substituições de impostos, forneça um nome para sua nova substituição.
9. No campo Descrição, insira uma descrição da substituição.
10. Ajuste o status para "Habilitar".
11. Expandir ou recolher a seção Substituições.
12. No campo Tipo, selecione uma opção.
    * Os grupos dos impostos sobre venda do artigo podem ser usados para cancelar impostos para os artigos específicos que pertencem ao grupo. Por exemplo, os alimentos são taxados tipicamente diferentemente dos bens duráveis, e teriam provavelmente seu próprio grupo dos impostos sobre venda. Os grupos dos impostos sobre venda são grupos de impostos que são aplicáveis a um canal particular. Por exemplo, se um canal vende o varejo e um interempresarial, os grupos diferentes dos impostos sobre venda dos artigos podem ser usados. Todos os impostos aplicáveis seriam traçados ao grupo dos impostos sobre venda.  
    * Agora você pode selecionar "De" e "Para" impostos ou "Do grupo de impostos" e "Para grupo de impostos" para criar sua substituição de impostos. O campo "De" indica o imposto ou o grupo do imposto a ser substituído. Substituição pelo grupo dos impostos sobre venda do artigo fornece opções diferentes do que cancelar pelo grupo dos impostos sobre venda. A substituição dos impostos sobre venda pode estabelecer-se para cancelar impostos em transações inteiras ou em linhas particulares na transação.  
13. Clique em Salvar.
14. Feche a página.
15. Vá para Retail e Commerce > Configuração de canal > Impostos > Grupos de substituições de impostos.
    * Nesta etapa você atribuiu a ultrapassagem recém-criada dos impostos sobre venda ao grupo da ultrapassagem dos impostos sobre venda atribuído ao canal de Houston.  
16. Clique em Editar.
17. Expanda ou recolha a seção Configuração.
18. Clique em Adicionar.
19. No campo Substituir imposto, clique no botão suspenso para abrir a pesquisa.
20. Selecione a substituição previamente criada dos impostos sobre venda da lista.
21. Na lista, clique no link na linha selecionada.
22. Clique em Salvar.

