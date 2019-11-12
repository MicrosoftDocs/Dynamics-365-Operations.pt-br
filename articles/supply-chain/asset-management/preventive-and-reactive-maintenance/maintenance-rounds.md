---
title: Rounds de manutenção
description: Este tópico explica os rounds de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4c9a2fee7d43142f8bb17f4e819c9949a2a20c41
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570021"
---
# <a name="maintenance-rounds"></a>Rounds de manutenção

[!include [banner](../../includes/banner.md)]

 

No **Gerenciamento de Ativos**, você pode criar rounds de manutenção para vários ativos nos quais você precisa executar uma tarefa semelhante em intervalos regulares. Por exemplo, trabalhos de lubrificação ou trabalhos de inspeção de segurança que precisam ser realizados em várias máquinas dentro dos mesmos intervalos. A primeira etapa é criar um round de manutenção, incluindo os ativos que exigem o mesmo trabalho do formulário de manutenção. Em seguida, você agenda os rounds de manutenção. Quando tiver concluído o agendamento de rounds de manutenção, você verá todos os registros do trabalho referentes ao round em **Todos agendamentos de manutenção** e nas **Linhas de agendamento de manutenção abertas**.

>[!NOTE]
>Os rounds de manutenção também podem ser configurados em locais funcionais a serem concluídos nos ativos instalados no local funcional no momento da criação da ordem de serviço com base no round. Consulte [Criar locais funcionais](../functional-locations/create-functional-locations.md) para obter mais informações sobre a configuração de rounds de manutenção nos locais funcionais.

## <a name="set-up-a-maintenance-round"></a>Configurar um round de manutenção

1. Clique em **Gerenciamento de ativos** > **Configuração** > **Manutenção preventiva** > **Rounds de manutenção**.

2. Clique em **Novo** para criar um novo round de manutenção.

3. Insira uma ID no campo **Round de manutenção** e um nome para o round de manutenção no campo **Nome**.

4. Selecione uma data de início para o round no campo **Data de início**.

5. Nos campos **Concluir em dias** e **Concluir em horas** você pode inserir a data de término esperada em dias ou horas. A data de término esperada é calculada em relação à data de início, calculada quando linhas de agendamento de manutenção forem criadas. Por exemplo, você pode inserir "7" no campo **Concluir em dias** para indicar que o trabalho relacionado deve ser concluído dentro de uma semana da data de início.

6. Selecione "Sim" no botão de alternância **Criação automática** se as ordens de serviço tiverem que ser criadas automaticamente das linhas de agendamento de manutenção que são criados deste round de manutenção.

7. No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço a ser usado em ordens de serviço criadas deste round de manutenção.

8. No campo **Nível de serviço**, selecione o nível de serviço da ordem de serviço a ser usado nas ordens de serviço criados deste round de manutenção.

9. Na Guia Rápida **Linhas do ativo**, clique em **Adicionar** para adicionar um ativo ao round de manutenção.

10. Um número da linha é automaticamente inserido no campo **Número da linha** para indicar a sequência de ativos no round de manutenção.

11. Selecione o ativo no campo **Ativo**.

12. Selecione o tipo de trabalho de manutenção do ativo no campo **Tipo de trabalho de manutenção**.

13. Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício** relacionados ao tipo de trabalho de manutenção.

14. Selecione a recorrência (dia, semana, etc) no campo **Tipo de período**.

15. No campo **Frequência do período**, insira o número de recorrências para o round de manutenção. Exemplo: se você selecionar "Dia" no campo **Tipo de período** e você inserir o número "7" neste campo, as novas linhas do round de manutenção são criadas durante o agendamento de manutenção preventiva uma vez por semana.

16. Selecione uma data de início do ativo a ser incluído no round de manutenção no campo **Data de início**. Esta data pode ser diferente da data de início definida no round de manutenção.

17. Repita as etapas de 9 a 16 para adicionar mais ativos ao round de manutenção.

18. Na Guia Rápida **Linhas do local funcional** clique em **Adicionar** para adicionar um local funcional ao round de manutenção. Consulte a descrição dos campos relacionados acima. Os mesmos campos estão disponíveis para criar uma linha do ativo, mas você também pode selecionar **Fabricante** e **Modelo** para um local funcional, conforme necessário. Se você selecionar apenas um local funcional em uma linha, mas não fizer seleções em **Tipo de ativo**, **Fabricante**, **Modelo**, **Tipo de trabalho de manutenção**, **Grade do tipo de trabalho de manutenção** e **Ofício**, todos os ativos relacionados a esse local funcional no momento do agendamento de manutenção serão incluídos no round de manutenção.

19. Na Guia Rápida **Grupos**, clique em **Adicionar** para selecionar um grupo de ordem de serviço a ser incluído no round de manutenção. Vários grupos de ordens de serviço podem ser conectados a um round de manutenção.

20. Salve sua configuração.

>[!NOTE]
>Os campos **Ativos** e **Linhas** localizados no grupo **Detalhes** na Guia Rápida **Cabeçalho** mostram o número total de ativos e linhas relacionados ao round de manutenção selecionado.

A ilustração a seguir mostra um exemplo de um round de manutenção contendo três ativos.

![Figura 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>Agendar rounds de manutenção

Ao configurar um round de manutenção, você executa um trabalho de agendamento para agendar todos os trabalhos relacionados a ele.

1. Clique no botão **Gerenciamento de ativos** > **Periódico** > **Manutenção preventiva** > **Agendar rounds de manutenção** ou **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção** > selecione linha de agendamento de manutenção na lista > **Rounds de manutenção**.

2. No campo **Período**, selecione o tipo de período a ser usado para o trabalho de agendamento.

3. No campo **Frequência de período**, insira o número de períodos a ser incluído no trabalho de agendamento. O início do agendamento é a data atual.

4. Selecione "Sim" no botão de alternância **Criação automática**, se uma ordem de serviço tiver que ser criada automaticamente na base de um round de manutenção.

>[!NOTE]
>Se este botão de alternância for definido como "Sim" e o botão de alternância **Criação automática** também for definido como "Sim" no round de manutenção no formulário **Rounds de manutenção**, as ordens de serviço serão criadas com base nas linhas do round de manutenção e as linhas de agendamento de manutenção com o status "Ordem de serviço criada" também são criadas. Se apenas um dos botões de alternância **Criação automática** for definido como "Sim", nesta lista suspensa ou nos **Rounds de manutenção**, somente serão criadas linhas de agendamento de manutenção com status "Criado". Nesse caso, nenhuma ordem de serviço é criada.

5. Se necessário, é possível selecionar rounds específicos ou outra data de início para o trabalho da agenda. Clique em **Filtro** e adicione os rounds a serem incluídos.

6. Clique em **OK**.

7. Agora você pode ver os trabalhos dos rounds de manutenção no **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção**. Se os rounds programados forem conectados a um grupo de ordem de serviço, você também poderá ver as linhas de agendamento de manutenção em **Abrir grupos de agendamento de manutenção**. As linhas de agendamento de manutenção criadas a partir de um round têm o tipo de referência "Rounds de manutenção".

As duas ilustrações a seguir mostram um trabalho de agendamento na caixa de diálogo **Agendar rounds de manutenção** e as linhas do agendamento de manutenção criadas em **Todos os agendamentos de manutenção** com base nesse trabalho de agendamento.

![Figura 2](media/14-preventive-maintenance.png)

![Figura 3](media/15-preventive-maintenance.png)

- Quando as ordens de trabalho são criadas manualmente nos ativos que serão cobertos por uma garantia do fornecedor, uma caixa de diálogo será exibida para que o usuário fique ciente da garantia. A criação da ordem de serviço pode ser cancelada. A verificação de uma relação da garantia é omitida para as ordens de serviço que são criadas automaticamente.  
- Você pode configurar um trabalho em lotes na Guia Rápida **Executar em segundo plano** para agendar rounds em intervalos regulares.  
- Se um round for incluído em vários grupos da ordem de serviço (consulte [Grupos da ordem de serviço](../work-orders/work-order-pools.md)), um registro será mostrado para cada grupo em **Abrir grupos de agendamento de manutenção**. Isso é feito para otimizar as opções de filtragem para grupos de ordens de serviço.

