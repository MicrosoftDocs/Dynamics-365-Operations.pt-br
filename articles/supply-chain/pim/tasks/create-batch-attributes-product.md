---
title: Criar atributos de lote para um produto
description: Este procedimento mostra como criar um atributo de lote, atribuir faixas padrões de valores, e incluir o atributo em um grupo.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d51cecc800a827fe91583b6086fd88b10aedc41
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986920"
---
# <a name="create-batch-attributes-for-a-product"></a>Criar atributos de lote para um produto

[!include [banner](../../includes/banner.md)]

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

