---
title: Reclassificar ativos fixos
description: Este artigo explica o processo de reclassificação de ativos. Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.
author: moaamer
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 89c046b131afd1728b26465816eee98ee1898e49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861377"
---
# <a name="reclassify-fixed-assets"></a>Reclassificar ativos fixos

[!include [banner](../../includes/banner.md)]

Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo. 

Quando um ativo fixo é reclassificado:

- Todos os livros do ativo fixo existente são criados para o novo ativo fixo. Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo. O status dos livros para o ativo fixo original é Fechado. 

- Os novos registros do novo ativo fixo contêm a data da reclassificação no campo **Data de aquisição**. A data indicada no campo **Data de execução da depreciação** é copiada das informações originais de ativo. Caso a depreciação já tenha sido iniciada, o campo **Data da última depreciação exibirá** a data da reclassificação. 

- As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.

- Quando um ativo que tem uma transação de transferência for reclassificado, o sistema exibirá uma mensagem na **Central de ações** para indicar que uma transação de transferência não foi concluída durante o processo de reclassificação. É necessário concluir uma transação de transferência para mover as transações de reclassificação existentes para as dimensões financeiras apropriadas. 

   Durante o processo de reclassificação, o sistema executa as ações a seguir para reclassificar o saldo do ativo original para o novo ativo. 
   
   - O processo de reclassificação copia os dados do registro de ativos fixos original para o novo registro de ativos fixos.

   - A transação de reclassificação usa informações da aquisição original lançada que inclui as informações de dimensão financeira incluídas na transação de aquisição.  
   
   - Ao mesmo tempo, o processo de reclassificação reverte a transação original de aquisição e transferência de ativos. 

O diagrama e o procedimento a seguir fornecem um exemplo do processo de reclassificação. 

[![Diagrama mostrando o processo de reclassificação.](../media/reclassification-process-01.png)](../media/reclassification-process-01.png)

Siga essa etapas para reclassificar um ativo fixo:

1. Acesse **Ativos fixos > Tarefas periódicas > Reclassificação**.
2. No campo **Grupo de ativos fixos**, selecione o grupo a ser reclassificado.
3. No campo **Número do ativo fixo**, selecione o ativo fixo a ser reclassificado.
4. No campo **Novo grupo de ativos fixos**, selecione um grupo para o qual deseja transferir o ativo fixo.
    * Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo **Número do novo ativo fixo** será atualizado com o número da nova sequência numérica do grupo de ativos fixos. Caso contrário, o campo **Número do novo ativo fixo** será atualizado com o número da sequência numérica que está configurada na página **Parâmetros do ativo fixo**. Se uma sequência numérica não estiver configurada na página **Parâmetros do ativo fixo**, insira um número no campo **Número do novo ativo fixo**.  
5. No campo **Data de reclassificação**, insira uma data.
6. No campo **Série de comprovante**, insira ou selecione um valor.
7. Selecione **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
