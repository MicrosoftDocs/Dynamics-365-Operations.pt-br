---
title: "Registro para execução de fabricação"
description: "Este tópico descreve termos e conceitos importantes que você precisará compreender para configurar e usar a execução de fabricação."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 81332eed9cf3745442007f98d36bc56e7095d9f8
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="registration-for-manufacturing-execution"></a>Registro para execução de fabricação

[!include[banner](../includes/banner.md)]


Este tópico descreve termos e conceitos importantes que você precisará compreender para configurar e usar a execução de fabricação. 

A execução de fabricação é destinada principalmente para ser usada por empresas de manufatura. Os trabalhadores podem registrar o tempo e o consumo de itens em trabalhos de produção usando a página **Registro de trabalho**. Todos os registros foram aprovados e transferidos posteriormente para os módulos relevantes. A aprovação e a transferência contínuas de registros permitem que os gerentes rastreiem com facilidade os custos reais em ordens de produção.

## <a name="manufacturing-execution-and-registration-terminology"></a>Terminologia de execução e de registro de fabricação
A tabela a seguir contém os termos que pertencem à execução de fabricação e às tarefas relacionadas ao registro.

| Termo                          | descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Execução de fabricação       | Uma função usada para registrar o tempo, o consumo de material, os custos de trabalhos de produção, os projetos e as atividades indiretas. O registro é concluído no cliente de registro da execução de fabricação.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Lista de trabalhos                      | Na página **Registro de trabalho**, é mostrada aos trabalhadores a lista de trabalhos que eles devem executar em um recurso específico, como uma máquina. Um trabalhador pode registrar o tempo e o consumo de itens em cada trabalho ou tarefa na lista de trabalhos.                                                                                                                                                                                                                                                                                                                                                                           |
| Agrupamento de trabalhos                  | Se um trabalhador iniciar mais de um trabalho ao mesmo tempo na página **Registro do trabalho**, isso é chamado de agrupamento de trabalhos. O tempo empregado em trabalhos agrupados pode ser alocado para trabalhos específicos de diversas maneiras, usando chaves de alocação.                                                                                                                                                                                                                                                                                                                                                         |
| Registros de coordenador/assistente | Um trabalhador pode ser registrado como um assistente para um recurso e pode criar uma pequena equipe em que vários trabalhadores trabalham nos mesmos trabalhos de produção. Os recursos aos quais os trabalhadores são conectados à medida que os assistentes são chamados de coordenadores. Somente o recurso coordenador deve fazer registros. Todos os assistentes obtêm automaticamente os mesmos registros. Por exemplo, se uma máquina agir como o coordenador, os trabalhadores que tiverem se registrado como assistentes para a máquina poderão fazer registros na página **Registro do trabalho**, e a máquina e os trabalhadores conectados como assistentes receberão os mesmos registros. |
| Atividade indireta             | Uma atividade ou tarefa que não esteja diretamente relacionada a um trabalho de produção ou a um projeto, como uma reunião de departamento, um trabalho de limpeza ou um trabalho de manutenção no chão de fábrica. Os trabalhadores podem fazer a registros em atividades indiretas da mesma maneira que podem fazer registros em trabalhos de produção e projetos.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Registros na execução de fabricação
Os trabalhadores podem fazer vários tipos de registros na execução de fabricação para o trabalho executado em trabalhos de produção. Dependendo da configuração do sistema, talvez os trabalhadores também consigam fazer registros em atividades de projeto e em tarefas não produtivas, como ausências, interrupções e atividades indiretas. Estes são os tipos de registro:

-   **Registro de entrada/saída** (disponível com Horário e presença) – os trabalhadores registram a entrada no trabalho e registram a saída quando voltam para casa.
-   **Registrar em trabalhos de produção** – os trabalhadores podem fazer registros, como iniciar o trabalho e relatar comentários sobre um trabalho em trabalhos de produção que aparecem em sua lista de trabalho. Os trabalhadores podem iniciar vários trabalhos ao mesmo tempo. Isso é conhecido como agrupamento de trabalhos.
-   **Registro no estoque** – os trabalhadores podem fazer registros em materiais usados no chão de fábrica, mas que não estejam diretamente relacionados a trabalhos de produção. Os exemplos incluem graxa, lubrificantes ou outros materiais usados para manter as máquinas em execução. O registro é executado em um diário de estoque.
-   **Registro em projetos** (disponível com Horário e presença) – os trabalhadores podem fazer registros, como iniciar e concluir trabalhos nos projetos ou em atividades de projeto que aparecem em sua lista de trabalho.
-   **Registrar taxas do projeto e itens do projeto** (disponível com Horário e presença) – os trabalhadores podem registrar taxas (despesas) associadas a um projeto em um diário de taxas de projeto, como quilometragem e pedágio. Os trabalhadores também podem registrar o consumo de itens em projetos. Isso é feito em um diário de item do projeto.
-   **Registro como o assistente para outro trabalhador** – se dois ou mais trabalhadores trabalharem juntos em um trabalho de produção ou projeto, um trabalhador poderá se registrar como assistente para uma máquina ou outro trabalhador, que atuará como coordenador. O coordenador pode selecionar outro trabalhador como coordenador, como necessário.
-   **Registrar ausência** (disponível com Horário e presença) – os trabalhadores pode registrar horas em diversos códigos de ausência configurados. A ausência pode ser indicada se um chegar atrasado, se precisar se ausentar durante o dia de trabalho ou se sair mais cedo do que o esperado, de acordo com o perfil de horário de trabalho padrão.
-   **Registrar interrupções** (disponível com Horário e presença) – durante o dia de trabalho, os trabalhadores pode registrar que estão saindo da estação de trabalho para fazer uma interrupção. Vários tipos de interrupções podem ser configurados. Quando um trabalhador retorna e faz logon novamente, o sistema registra que o trabalhador voltou e o registro de interrupção é encerrado.
-   **Registrar atividades indiretas** (disponível com Horário e presença) – as atividades indiretas são atividades não produtivas em que os trabalhadores podem se envolver durante um dia de trabalho, como uma reunião de departamento, uma reunião de equipe ou um trabalho de manutenção executado no chão de fábrica. Os trabalhadores podem fazer registros em atividades indiretas configuradas.
-   **Registrar hora extra** (disponível com Horário e presença) – os trabalhadores que tiveram de trabalhar mais horas podem selecionar se as horas extras deverão ser registradas como horário flexível ou como horas extras.





