---
title: Criar uma hierarquia de classificação de produto
description: Este procedimento mostra como criar uma nova hierarquia de categoria e atribuir um tipo da hierarquia de código de mercadoria.
author: ShylaThompson
manager: tfehr
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResCategoryHierarchyListPage, EcoResCategoryHierarchyCreate, EcoResCategory, EcoResCategoryHierarchyRole, EcoResProductCategory, EcoResCategorySearchList, EcoResCategoryHierarchyFactbox, EcoResCategoryFriendlyName, EcoResCategoryAddProduct
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 439df63a4f8f0cc1c030554d18f80e9934c88b00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422185"
---
# <a name="create-a-hierarchy-of-product-classification"></a>Criar uma hierarquia de classificação de produto

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma nova hierarquia de categoria e atribuir um tipo da hierarquia de código de mercadoria. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é destinado ao gerente de categoria.


## <a name="create-the-new-category-hierarchy"></a>Criar a nova hierarquia de categoria
1. Vá para **Painel de navegação > Módulos > Gerenciamento de informações sobre produtos > Configuração > Categorias e atributos > Hierarquias de categoria**.
2. Clique em **Novo**.
3. No campo **Nome**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Clique em **Criar**.

## <a name="build-the-hierarchy"></a>Construir a hierarquia
1. Clique no nó de categoria **Novo**.
2. No campo **Nome**, digite um valor.
3. No campo **Código**, digite um valor.
4. No campo **Nome amigável**, digite um valor.
5. Clique no nó de categoria **Novo**.
6. No campo **Nome**, digite um valor.
7. No campo **Código**, digite um valor.
8. No campo **Nome amigável**, digite um valor.
9. Clique no nó de categoria **Novo**.
10. No campo **Nome**, digite um valor.
11. No campo **Código**, digite um valor.
12. No campo **Nome amigável**, digite um valor.
13. Clique no nó de categoria **Novo**.
14. No campo **Nome**, digite um valor.
15. No campo **Código**, digite um valor.
16. No campo **Nome amigável**, digite um valor.
17. Feche a página.

## <a name="classify-the-hierarchy"></a>Classificar a hierarquia
1. Na lista, localize e selecione o PDV desejado.
2. No **Painel de Ação**, clique em **Hierarquia de categoria**.
3. Clique em **Associar tipo de hierarquia**.
4. Clique em **Novo**.
5. No campo **Tipo de hierarquia de categoria**, selecione uma opção. Selecione o **Tipo de hierarquia de categoria de códigos de mercadoria para a classificação de produtos**.  
6. No campo **Hierarquia de categoria**, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o registro desejado.
8. Na lista, clique no link na linha selecionada.
9. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]