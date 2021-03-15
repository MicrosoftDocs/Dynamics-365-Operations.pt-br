---
title: Quando redefinir um data mart
description: Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart e as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.
author: jinniew
manager: AnnBe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1c1524c7a1a3fbe71c51b23571996d87641cdf7e
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093203"
---
# <a name="when-to-reset-a-data-mart"></a>Quando redefinir um data mart

A redefinição de um data mart pode ser demorada. Dependendo das circunstâncias, essa ação pode não ser a solução necessária. Este tópico lista as circunstâncias que podem ser aprimoradas pela redefinição de um data mart, bem como as circunstâncias nas quais a redefinição do data mart provavelmente não ajudará.  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a>Quando é necessário fazer uma redefinição de data mart?
Considere as afirmações a seguir antes de redefinir um data mart. Se uma ou mais afirmações forem aplicáveis, é possível que sua organização se beneficie da redefinição do data mart.

- O banco de dados do aplicativo foi restaurado, mas o banco de dados do data mart não foi.
- Você vê dados incorretos para um período contábil, que não são o resultado de um problema com o design de relatórios.
- Você vê dados incorretos para um período contábil e os registros são listados em Tentativas de integração na página **Status de integração** no Designer de Relatórios (inicie o Designer de Relatórios e selecione **Ferramentas > Status de integração**).
- Você abriu um incidente de suporte e foi orientado por um engenheiro de suporte a redefinir o data mart como parte de uma etapa de solução de problemas.
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a>Quando não é adequado redefinir um data mart?
Há algumas circunstâncias em que não é recomendável redefinir um data mart. Veja a seguir. 

- Sempre que o motivo não estiver listado neste tópico.
- Se você estiver enfrentando problemas de desempenho associados a uma sincronização de dados. Neste caso, a redefinição do data mart provavelmente não ajudará.
- Se você tiver um padrão de redefinição recorrente devido a qualquer um dos seguintes motivos: 
  - **Dados ausentes** – Primeiro, elimine problemas de design de relatórios e problemas de tempo de sincronização de dados, por exemplo, ao observar que o mapa de fatos não é executado desde que os dados ausentes foram lançados.
  - **Estado de integração travado** – Se a integração estiver lenta ou parecer travada, a redefinição do data mart provavelmente não resolverá o problema.
  - **Tentativas de redefinição malsucedidas** – Se um número de tentativas de concluir uma redefinição tiver sido feito e não tiver tido êxito devido a dados ausentes, é recomendável abrir um incidente de suporte e trabalhar com um engenheiro de suporte para analisar sua situação antes de tentar redefinir o data mart novamente.
  - **Registros obsoletos** – Os registros obsoletos por si só não justificam necessariamente a redefinição do data mart. Se você tiver um grande conjunto de dados, o processo de redefinição levará algum tempo para ser executado, mas é improvável que isso resulte em melhoria.
 
## <a name="what-a-data-mart-reset-does-not-do"></a>O que uma redefinição de data mart não faz  
- Uma redefinição só será iniciada quando as tarefas existentes forem concluídas. Isso garante que dados antigos não sejam inseridos. Nesse momento, talvez você veja uma mensagem como: "Não foi possível processar a redefinição do data mart por causa de uma tarefa ativa. Tente novamente mais tarde.”
- A redefinição desabilitará as tarefas de integração e excluirá todos os dados do data mart. A integração é habilitada novamente.

> [!NOTE]
> Os pontos a seguir especificam duas coisas que a redefinição de um data mart *não* fará. <br>
> - As redefinições não limpam designs de relatórios. <br>
> - As redefinições não limpam dados da empresa ou dados do usuário a menos que sejam selecionados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]