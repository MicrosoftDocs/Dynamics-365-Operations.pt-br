---
title: Criar atributos de lote para um produto
description: Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70141cfd6fd973038b2ac2aa51d1d6d5cc445b4c416d32a30dec120b0929b8da
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762881"
---
# <a name="create-batch-attributes-for-a-product"></a>Criar atributos de lote para um produto

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo. A empresa de dados demonstrativos utilizada para criar este procedimento é a empresa USP2.

1. Acesse Gerenciamento de estoque > Configuração > Lote > Atributos de lote.
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
12. Acesse Gerenciamento de estoque > Configuração > Lote > Grupos de atributos de lote.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]