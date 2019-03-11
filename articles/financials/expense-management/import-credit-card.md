---
title: Importar e manter transações de cartão de crédito
description: Este tópico explica como importar e manter as transações de cartão de crédito relacionadas a despesa. Essas transações podem ser configuradas de forma que sejam importadas automaticamente em uma agenda recorrente ou podem ser importadas manualmente, conforme necessário.
author: KimANelson
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvPbsMainDataLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 9674cf495b7fdd40d8672580b9d10e9ebe626bb0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "322642"
---
# <a name="import-and-maintain-credit-card-transactions"></a>Importar e manter transações de cartão de crédito

[!include [banner](../includes/banner.md)]

As transações de cartão de crédito relacionadas à despesa podem ser configuradas de forma que possam ser importadas automaticamente em uma agenda recorrente. Como alternativa, as transações podem ser importadas manualmente, conforme necessário. As transações de cartão de crédito são importadas por meio da entidade de dados das transações de cartão de crédito.

Para obter mais informações sobre as entidades de dados, consulte [Entidades de dados](../../dev-itpro/data-entities/data-entities.md).

## <a name="import-credit-card-transactions"></a>Importar transações de cartão de crédito

1. Na página **Transações de cartão de crédito** , selecione **Transações de importação**. Se estiver abrindo o gerenciamento de dados pela primeira vez, o sistema deve atualizar a lista de entidades de dados antes de continuar.
2. No campo **Nome**, insira uma descrição exclusiva da tarefa de importação.
3. No campo **Formato de dados de origem**, selecione o formato do arquivo que contém as transações do cartão de crédito para importação.
4. Selecione **Carregar** e, em seguida, localize e selecione o arquivo a ser importado.
5. Depois que o arquivo for carregado, valide o mapeamento do arquivo da transação de cartão de crédito e as colunas da entidade de dados das transações de cartão de crédito, selecionando o link **Exibir mapa** no bloco. Se houver erros de mapeamento ou se você tiver que alterar o mapeamento, faça as alterações de mapeamento da guia **Visualização de mapeamento** ou na guia **Detalhes de mapeamento**.
6. Para automatizar as transações de cartão de crédito, selecione **Criar trabalho de dados recorrente**. Você poderá então definir a recorrência que define a frequência na qual as transações de cartão de crédito devem ser importadas. Quando terminar, selecione **OK**.
7. Para importar o arquivo selecionado agora, selecione **Importar**.
8. Se houver erros durante a importação, é possível exibir o log de execução ou dados de preparo para ver os erros que você deve corrigir para garantir uma importação bem-sucedida.

> [!NOTE]
> Se tiver que importar mais de um formato de arquivo, é necessário criar trabalhos de importação separados para cada tipo de formato.

## <a name="reassign-the-credit-card-transactions-for-terminated-employees"></a>Reatribuir as transações de cartão de crédito de funcionários demitidos.

Depois que um registro de funcionário foi finalizado, a conta Serviços de domínio Active Directory (AD DS) do funcionário é desativada. Porém, pode haver transações de cartão de crédito ativa que ainda devem ser despendidas e reembolsadas. Na página **Crédito e transações**, é possível reatribuir o funcionário de qualquer transação de cartão de crédito na qual o funcionário associado foi demitido.

Selecione uma ou mais transações de cartão de crédito e depois selecione **Reatribuir transações**. Você pode selecionar outro funcionário para atribuir as transações do cartão de crédito. Depois que as transações do cartão de crédito forem reatribuídas, elas poderão ser selecionadas de um relatório de despesas e pagas pelo processo comum para reembolso do relatório de despesas.
