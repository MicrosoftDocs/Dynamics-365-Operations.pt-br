--- 
title: Criar atributos de lote para um produto
description: "Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7fac2753109261a414188a384eb0e8424dbbab2e
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-batch-attributes-for-a-product"></a>Criar atributos de lote para um produto

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo. A empresa de dados demonstrativos utilizada para criar este procedimento é a empresa USP2.

1. Vá para Gerenciamento de estoque > Configuração > Lote > Atributos de lote.
2. Clique em Novo.
3. No campo Atributo, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Tipo de atributo, selecione 'Fração'.
    * Este procedimento usa o tipo Fração para habilitar valores decimais. Você pode selecionar outros tipos de atributo. Se você selecionar o tipo Enumeração, você deve inserir valores na lista de enumeração para que possa inserir um valor no campo Destino.  
6. No campo Mínimo, insira um número.
7. No campo Máximo, insira um número.
8. No campo Incremento, insira um número.
9. No campo Destino, digite um valor.
10. Clique em Salvar.
11. Feche a página.
12. Vá para Gerenciamento de estoque > Configuração > Lote > Grupos de atributos de lote.
13. Clique em Novo.
14. No campo Grupo de atributos, digite um valor.
15. No campo Descrição, digite um valor.
16. Clique em Salvar.
17. Clique em Atributos de grupo.
18. Clique em Novo.
19. No campo Atributo, clique no botão suspenso para abrir a pesquisa.
20. Na lista, localize e selecione o PDV desejado.
21. Na lista, clique no link na linha selecionada.
    * Um atributo pode ser incluído em qualquer um dos grupos.  
22. Clique em Salvar.
23. Feche a página.


