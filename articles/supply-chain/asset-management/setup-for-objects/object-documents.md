---
title: Documentos do ativo
description: Este tópico explica documentos de ativo no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b830d835d99122a8c0572481f4c229c37d97d0c
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653242"
---
# <a name="asset-documents"></a>Documentos do ativo

[!include [banner](../../includes/banner.md)]

 

Este tópico explica documentos de ativo no Asset Management.

No Asset Management, você pode configurar documentos para que eles sejam automaticamente relacionados a tipos de trabalho, fabricantes de ativo, tipos de ativo ou ativos, por exemplo. Essa funcionalidade será útil quando versões atualizadas de documento forem liberadas. Nesse caso, você só precisará colocar o documento atualizado no local padrão utilizado para seus documentos do Supply Chain Management e anexá-lo ao registro de documentos do ativo criado. O documento atualizado pode ser acessado dos itens de menu **Todos os ativos**, **Ativos ativos**, **Meus ativos ativos**, **Todas as ordens de trabalho** e **Trabalhos de ordem de serviço ativos**. O processo de anexação de documentos a um registro de documentos de ativo usa o sistema padrão de manuseio de documentos.

**Exemplo 1:** um documento relacionado a um tipo de trabalho deve descrever um procedimento desse tipo de trabalho.

**Exemplo 2:** um documento relacionado a uma combinação de um tipo de ativo, fabricante e modelo pode ser o manual padrão para o modelo de fabricante do ativo selecionado.

## <a name="create-asset-document-relation"></a>Criar relação de documento de ativo

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Documentos de ativo**.
2. Selecione **Novo** para criar um registro de documento de ativo.
3. Dependendo do grau de especificidade desejado para a relação do documento, faça seleções relevantes em um ou mais dos seguintes campos: **Tipo de ativo**, **Fabricante**, **Modelo**, **Ativo**, **Categoria do tipo de trabalho**, **Tipo de trabalho**, **Variação do tipo de trabalho** e **Necessidade de trabalho**. As opções disponíveis nos campos **Variação do tipo de trabalho** e **Necessidade de trabalho** dependem da seleção no campo **Tipo de trabalho**.

    > [!NOTE]
    > Quando o sistema pesquisar documentos que tenham de estar relacionados a um ativo ou uma ordem de serviço, o Asset Management examinará todos os registros de documento de ativo para verificar se há uma possível correspondência. Ele sempre verifica a combinação mais específica primeiro. Ou seja, o Asset Management primeiro verifica a existência uma correspondência para o campo **Necessidade de trabalho**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Variação de tipo de trabalho**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Tipo de trabalho** e assim em diante. Como você pode perceber no layout da página **Documentos de ativo**, esse comportamento significa que, para encontrar a combinação mais específica, o Asset Management verifica cada registro da direita para a esquerda em busca de uma correspondência. Vários documentos podem estar relacionados a um ativo ou uma ordem de serviço. Você pode editar o nível de serviço em uma solicitação de manutenção ou ordem de serviço como necessário.

4. Selecione **Anexos**. A página **Manuseio de documentos** padrão será exibida.
5. Configure os documentos ou as anotações que devem ser anexados ao registro do documento de ativo. Depois que você anexar documentos, o campo **Anexos** mostrará o número de documentos relacionados ao registro.
