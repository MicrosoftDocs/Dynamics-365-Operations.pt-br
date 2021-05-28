---
title: Quando redefinir um data mart
description: Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart e as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988983"
---
# <a name="when-to-reset-a-data-mart"></a>Quando redefinir um data mart

A redefinição de um data mart pode ser demorada. Dependendo das circunstâncias, essa ação pode não ser a solução necessária. Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart, bem como as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>Quando preciso fazer uma redefinição de data mart?
Considere as afirmações a seguir antes de redefinir um data mart. Se uma ou mais afirmações forem aplicáveis, é possível que sua organização se beneficie da redefinição do data mart.

- O banco de dados do aplicativo foi restaurado?
- Você reportou incidente de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas?
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>Quando não é adequado redefinir um data mart?
Há algumas circunstâncias em que não é recomendável redefinir um data mart. Veja a seguir. 

- Você está enfrentando problemas de desempenho associados a uma sincronização de dados. 
- Se você tiver um padrão de redefinição recorrente devido a qualquer um dos seguintes motivos: 
  - **Dados ausentes** 
  - **Estado de integração travado** 
  - **Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente a redefinição do data mart. Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhoria.
 
## <a name="what-is-a-data-mart-reset"></a>O que é uma redefinição de data mart?
- Uma redefinição só será iniciada quando as tarefas existentes forem concluídas. Isso garante que dados antigos não sejam inseridos. Nesse momento, talvez você veja uma mensagem como: "Não foi possível processar a redefinição do data mart por causa de uma tarefa ativa. Tente novamente mais tarde.”
- A redefinição desabilitará as tarefas de integração e excluirá todos os dados do data mart. A integração é habilitada novamente.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Se redefinir o data mart, perderei os relatórios já criados? 
Não, os relatórios são armazenados em tabelas de SQL que não são afetadas por uma redefinição do data mart. Se você estiver preocupado em perder os relatórios que criou, poderá fazer backup daqueles que não deseja perder. Para fazer backups, abra o Report Designer e acesse **Empresa > Empresas > Blocos de construção > Exportar**.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>É necessário que todos os usuários saiam do sistema para redefinir o data mart?
Não, os usuários podem continuar trabalhando no sistema durante a redefinição do data mart. No entanto, eles não poderão acessar os relatórios criados com o Financial Reporter até que a redefinição seja concluída. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
