---
title: Configuração do projeto da ordem de serviço
description: Este tópico explica a configuração de projeto de ordem de serviço no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 031e61549474745360ac00f9a66bef7a9dbaaf96
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021545"
---
# <a name="work-order-project-setup"></a>Configuração do projeto da ordem de serviço

[!include [banner](../../includes/banner.md)]

 

No módulo **Gerenciamento de ativos**, uma relação de projeto é necessária para cada trabalho de ordem de serviço. O projeto associado a um trabalho de ordem de serviço permite que você controle os custos em diversos projetos relacionados ao Gerenciamento de Ativos, como projetos internos de manutenção, projetos de gerenciamento de serviços e projetos de investimentos. 

## <a name="project-setup-for-a-work-order-job"></a>Configuração de projeto para um trabalho de ordem de serviço

Quando você cria um trabalho de ordem de serviço em uma ordem de serviço, a configuração de projeto no módulo **Gerenciamento e contabilidade de projeto** e a configuração de projeto de ordem de serviço no módulo **Gerenciamento de ativos** determinam como os projetos podem ser usados para no controle de custo no ativo selecionado nesse trabalho de ordem de serviço. Esta seção descreve as seguintes partes da configuração de projeto usada para uma ordem de serviço: o projeto principal (ID do projeto), tipo de projeto, atividades de projeto e dimensões financeiras:

- Quando você cria um trabalho de ordem de serviço em uma ordem de serviço, uma ID do projeto exclusiva e uma atividade de projeto relacionada serão criadas automaticamente para ele. Entretanto, se vários trabalhos de ordem de serviço em uma ordem de serviço incluírem o mesmo ativo, a mesma ID do projeto será usada para eles. Ou seja, uma ID do projeto é criada para cada ativo em uma ordem de serviço.

    - O projeto principal (ID do projeto) para um trabalho de ordem de serviço é encontrado na configuração do projeto principal. (Para obter mais informações sobre a configuração do projeto principal, consulte a próxima seção). Por exemplo, se você associar um cliente ou um local funcional a um projeto principal específico, o projeto principal será usado sempre que você criar ordens de serviço para esse cliente ou esse local funcional. Se você não relacionar uma ID do projeto específica a, por exemplo, um local funcional, será usado o próximo projeto principal relevante na configuração do projeto de ordem de serviço.
    - Um tipo de projeto é necessário para cada ID do projeto. O tipo de projeto é encontrado na configuração do grupo de projetos. (Para obter mais informações sobre a configuração do grupo de projetos, consulte a próxima seção). Se nenhuma correspondência for encontrada na configuração do grupo de projetos, será usada a configuração do grupo de projetos do projeto principal.
    - A configuração para exigir atividades de projeto em previsões e diários é copiada do projeto principal para o projeto de ordem de serviço. Se as opções **Hora**, **Despesa** e **Item** forem definidas como **Sim** para o projeto usado como um projeto principal, uma atividade de projeto será obrigatória em previsões e diários. (Para acessar essas opções, selecione **Gerenciamento e contabilidade de projeto** \> **Projetos** \> **Todos os projetos** e então selecione o projeto usado como um projeto principal. As opções estão na seção **Exigir atividade em diários** na Guia Rápida **Configuração**).

- As dimensões financeiras são copiadas do ativo e mescladas com o projeto principal.

A próxima seção explica como configurar projetos pai e grupos de projetos. O projeto principal e os grupos principais são usados para controlar as ordens de serviço. Eles também são usados em relatórios sobre ordens de serviço.

## <a name="set-up-work-order-projects"></a>Configurar projetos de ordem de serviço

Antes de começar a criar ordens de serviço, você deverá configurar projetos de ordem de serviço. A página **Configuração de projeto de ordem de serviço** (**Gerenciamento de ativos** \> **Configuração** \> **Ordens de serviço** \> **Configuração de projeto**) contém duas guias: **Projeto principal** e **Grupo de projetos**.

Na guia **Projeto principal**, configure as relações de projeto que poderão ser usadas se nenhum projeto for configurado no ativo selecionado em trabalhos de ordem de serviço. Uma configuração do projeto principal não será necessária se sua empresa utilizar projetos de ativo. Só será relevante se você quiser usar projetos de ordem de serviço em vez de projetos de ativo. Nesse caso, você deve configurar pelo menos um projeto principal.

Na guia **Grupo de projetos**, você pode configurar grupos de projetos que podem ser associados a tipos de ordem de serviço, tipos de ativo e ativos.

Os grupos de projetos podem ser usados para criar categorias (grupos) específicas usadas para o controle de custos. Por exemplo, ao criar grupos de projetos para tipos de ativo ou tipos de ordem de serviço específicos, será possível fazer um controle detalhado dos custos de manutenção por tipo.

Os grupos de projetos não são obrigatórios. Se você não configurar grupos de projetos, o projeto principal será usado para determinar o grupo de projetos, e um projeto filho será criado desde o grupo de projetos do projeto principal.

A configuração permite a integração completa com o módulo **Gerenciamento e contabilidade de projeto**. Portanto, você pode controlar os custos relacionados a ordens de serviço nos projetos relacionados. O procedimento a seguir descreve a configuração para projetos de ordem de serviço.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ordens de serviço** \> **Configuração de projeto**.
2. Na guia **Projeto principal**, selecione **Adicionar**.
3. Nos campos **Tipo de ordem de serviço**, **Localização funcional**, **Tipo de ativo** e **Ativo**, selecione valores como necessário. Para cada linha adicionada, você poderá definir apenas um campo ou vários campos. O número de campos definidos determina a combinação usada quando uma ID de projeto é selecionada no Gerenciamento de Ativos. 

    Se você selecionar um local funcional, os locais filhos relacionados serão automaticamente incluídos. Se selecionar um ativo, você poderá criar mais linhas de configuração de projeto de ordem de serviço para o mesmo ativo, mas poderá selecionar diferentes projetos para esse ativo.

4. No campo **ID do projeto**, selecione o projeto a ser relatado à configuração criada na etapa 3.
5. Se a configuração do projeto tiver de ser válida somente por um período limitado, selecione uma data de término no campo **Data de término**. Caso contrário, selecione **Nenhuma**.

    Por padrão, a data de início é a data em que você adiciona o projeto de ordem de serviço à página. É controlada pelo campo **Válido a partir de**, que está oculto por padrão. Para mostrar o campo **Válido a partir de**, selecione **Exibir** \> **Tudo**. Você pode usar o campo **Válido a partir de** com o campo **Data de término** para configurar um período limitado de validade para o projeto de ordem de serviço.

    ![Página de configuração do projeto das ordens de serviço](media/17-setup-for-work-orders.png)

6. Na guia **Grupo de projetos**, selecione **Adicionar**.
7. No campo **Tipo de ordem de serviço**, selecione um tipo de ordem de serviço.
8. Se quiser que a associação do grupo de projetos seja mais específico, selecione um tipo de ativo no campo **Tipo de ativo** ou um ativo no campo **Ativo**.
9. No campo **Grupo de projetos**, selecione o grupo de projetos que deve estar relacionado ao tipo de ordem de serviço. Por exemplo, um tipo de ordem de serviço que é chamado de **Manutenção preventiva** pode ser associado a um grupo de projetos chamado **Manut Prev** ou **Interno**. Como alternativa, um tipo de ordem de serviço **Investimento** que é usado para ordens de serviço relacionadas a investimentos e ativos fixos pode ser associado a um grupo de projetos chamado **Investir** ou **Investimento**.
10. Selecione **Salvar**.

![Página de configuração do projeto das ordens de serviço, Adicionar ordem de serviço](media/18-setup-for-work-orders.png)

> [!NOTE]
> Sempre que uma linha de ordem de serviço for criada, o Gerenciamento de Ativos pesquisa um grupo de projetos que deverá ser relacionado ao projeto de trabalho de ordem de serviço. A pesquisa baseia-se na configuração descrita neste tópico. Todos os grupos de projetos têm um tipo de projeto relacionado. Os grupos de projetos com o tipo de projeto **Tempo e material** ou **Preço fixo** são válidos somente para ativos relacionados a uma conta de cliente.
>
> Para projetos principais e grupos de projetos, quando o sistema seleciona o projeto de ordem de serviço ou o grupo de projetos disponíveis, a seleção baseia-se nos registros criados usando o procedimento anterior. O Gerenciamento de Ativos repassa os registros relacionados ao projeto de ordem de serviço para verificar se há uma possível correspondência. Ele sempre verifica a combinação mais específica primeiro. Ou seja, para o projeto principal de ordem de serviço, o Gerenciamento de Ativos primeiro verifica se há uma possível correspondência para o campo **Ativo**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Tipo de ativo**. Se nenhuma correspondência for encontrada, ele verificará se há uma correspondência para o campo **Local funcional** e assim em diante. Como você pode perceber no layout da página **Configuração de projeto de ordem de serviço**, esse comportamento significa que, para encontrar a combinação mais específica, o Gerenciamento de Ativos verifica cada registro da direita para a esquerda em busca de uma correspondência. Se nenhuma correspondência for encontrada, o registro padrão onde somente uma ID do projeto está selecionada será usado. O processo para encontrar o grupo de projetos relacionado é semelhante. O Gerenciamento de Ativos primeiro verifica se há uma possível correspondência para o campo **Ativo** e, em seguida, o campo **Tipo de ativo** e depois o campo **Tipo de ordem de serviço**. Se nenhuma correspondência for encontrada, o registro padrão onde somente um grupo de projetos está selecionado será usado.
