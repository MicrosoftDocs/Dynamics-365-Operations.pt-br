---
title: Importar dados de modelos de entidade de dados do Excel com várias planilhas
description: Este tópico descreve como importar dados usando modelos de entidade de dados do Excel para o Finance and Operations.
author: Sunil-Garg
manager: AnnBe
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 618b62364353f409f6971ddd9adc7d55297d09cf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688070"
---
# <a name="import-data-from-excel-data-entity-templates-that-have-multiple-worksheets"></a>Importar dados de modelos de entidade de dados do Excel com várias planilhas

[!include [banner](../includes/banner.md)]

O gerenciamento de dados no aplicativo dá suporte a modelos baseados no Microsoft Excel para entidades de dados. Esses modelos podem conter uma ou mais planilhas. Os modelos com várias planilhas frequentemente são usados quando é conveniente gerenciar dados em um único arquivo e os importar para várias entidades de dados. Um exemplo seria locais e depósitos.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Carregar um arquivo e depois mapeá-lo para todas as entidades
Vamos ver um exemplo no qual há um arquivo do Excel com planilhas chamadas **Locais** e **Depósitos**. Para configurar o projeto de importação de dados, você adicionaria a primeira entidade de dados, **Locais** e depois carregaria o arquivo. Você pode selecionar **Locais** como a planilha a ser usada para esta entidade.

Se adicionar a segunda entidade **Depósitos** sem deixar o formulário **Adicionar arquivo**, a pesquisa de planilha permitirá que você selecione a planilha **Depósitos** sem ter que carregar novamente o arquivo. O único motivo para carregar um novo arquivo seria se os dados dos **Depósitos** estivessem em um arquivo diferente.

![Várias planilhas](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>Planilha de correção para o mapeamento de entidade

O mapeamento da planilha para uma entidade de dados no job de importação pode ser corrigido na grade. A coluna **Planilha** na grade mostra as planilhas do arquivo que foi mapeado. Você pode escolher uma planilha diferente do menu suspenso. Se a planilha escolhida já estiver mapeada para uma entidade no projeto de dados, o sistema solicitará que você confirme a alteração. Recomendamos que você corrija os mapeamentos na grade.

![Atualizar mapeamento da planilha](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Remapear para um novo arquivo

Nos casos em que uma nova versão do mesmo arquivo ou um arquivo completamente novo tiver que ser carregado para entidades existentes em um projeto de dados, você deverá usar a experiência **Adicionar arquivo** e adicionar as entidades novamente, como se elas fossem adicionadas pela primeira vez. O sistema confirmará que se você deseja substituir as entidades existentes no projeto de dados antes de continuar. As entidades que não são adicionadas novamente (ou substituídas) continuarão mantendo os mapeamentos anteriores do arquivo anterior.

## <a name="upload-a-file-using-run-project"></a>Carregar um arquivo usando Executar projeto

Você pode carregar um arquivo do Excel ao usar a opção **Executar projeto** para executar um projeto de importação. Tenha cautela ao carregar somente arquivos que têm as mesmas planilhas que os mapeamentos existentes nas entidades de dados no projeto de dados. Se a planilha não for encontrada no arquivo recém-carregado, o sistema exibirá um erro e interromperá a importação. Se o mapeamento para a planilha tiver que ser alterado para uma entidade, então os mapeamentos no projeto de dados devem ser atualizados primeiro dentro do projeto de dados, antes de usar o arquivo na experiência **Executar projeto**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]