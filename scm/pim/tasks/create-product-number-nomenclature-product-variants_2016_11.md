--- 
title: "Criar um número de produtos para grades de produto configuradas"
description: "Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável."
author: BibiSp
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 8a9bf8241a0dc66f34715513d2d201569b810582
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-product-number-for-configured-product-variants"></a>Criar um número de produtos para grades de produto configuradas

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável. O procedimento também demonstra como você pode criar uma nomenclatura de configuração para um componente de modelo de configuração de produto. A empresa de dados demo usada para criar este procedimento é USMF. A nova nomenclatura de número de produto é atribuída ao produto mestre D0004. A tarefa geralmente seria realizada por um designer de produto.


## <a name="create-a-product-number-nomenclature"></a>Criar uma nomenclatura de número de produto
1. Clique em Definição de modelo de variante de produto.
2. Clique em Nomenclatura de produto.
3. Clique em Novo.
4. No campo Nome, digite um valor.
5. No campo Descrição, digite um valor.
6. Clique em Adicionar.
7. Clique em Número do produto mestre.
8. Clique em Adicionar.
9. Clique em Constante de texto.
10. Na lista, marque a linha selecionada.
11. No campo Texto, digite um valor.
12. Clique em Adicionar.
13. Clique em Configuração.
14. Feche a página.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Atribuir a nomenclatura de número de produto a um produto mestre
1. Clique em Produtos mestres.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Número do produto com um valor de "D".
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Selecione Sim no campo Usar nomenclatura.
6. No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.
7. Feche a página.
8. Feche a página.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Criar nomenclatura para um componente de modelo de configuração de produto
1. Clique em Modelos de configuração do produto.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique em Editar.
5. Selecione Sim no campo Usar nomenclatura de configuração.
6. Clique em Adicionar.
7. Clique em Valor do atributo.
8. Na lista, marque a linha selecionada.
9. No campo Atributo, insira ou selecione um valor.
10. Clique em Adicionar.
11. Clique em Constante de texto.
12. Na lista, marque a linha selecionada.
13. No campo Texto, digite um valor.
14. Clique em Adicionar.
15. Clique em Valor do atributo.
16. Na lista, marque a linha selecionada.
17. No campo Atributo, insira ou selecione um valor.
18. Clique em Adicionar.
19. Clique em Constante de texto.
20. Na lista, marque a linha selecionada.
21. No campo Texto, digite um valor.
22. Clique em Adicionar.
23. Clique em Valor do atributo.
24. Na lista, marque a linha selecionada.
25. No campo Atributo, insira ou selecione um valor.
26. Clique em Adicionar.
27. Clique em Constante de texto.
28. Na lista, marque a linha selecionada.
29. No campo Texto, digite um valor.
30. Clique em Adicionar.
31. Clique em Valor do atributo.
32. Na lista, marque a linha selecionada.
33. No campo Atributo, insira ou selecione um valor.
34. Clique em Adicionar.
35. Clique em Constante de texto.
36. Na lista, marque a linha selecionada.
37. No campo Texto, digite um valor.
38. Clique em Adicionar.
39. Clique em Valor de sequência numérica.
40. Na lista, marque a linha selecionada.
41. No campo Sequência numérica, digite ou selecione um valor.
42. Feche a página.
43. Feche a página.
44. Feche a página.


