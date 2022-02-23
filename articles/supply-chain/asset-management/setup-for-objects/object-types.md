---
title: Tipos de ativo
description: Este tópico explica como criar tipos de ativo no Asset Management. Também mostra os elementos relacionados aos tipos de ativo.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectJobType, EntAssetObjectType, EntAssetObjectTypeDefaultSparePart, EntAssetObjectTypeDefaultSparePartApprove, EntAssetObjectTypeDefaultCreateCombinations, EntAssetObjectTypeDefault, EntAssetObjectTypeDefaultCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 295840c12f89bc6c6a4d53023985259ac761d6b2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017408"
---
# <a name="asset-types"></a>Tipos de ativo

[!include [banner](../../includes/banner.md)]



Este tópico explica como criar tipos de ativo. Também mostra os elementos relacionados aos tipos de ativo. Os tipos de ativo são usados como categorias gerais para ativos. Os exemplos incluem máquinas CNC, equipamento de medição e motores de caminhão. Os tipos de ativo são usados para gerenciar os tipos de trabalho de manutenção (tarefas de manutenção), os estados de ciclo de vida do ativo, os contadores, os atributos do ativo, os modelos de avaliação de condição e os modelos de ativos que podem ser selecionados para um ativo. Quando cria um ativo, você deve especificar o tipo de ativo.

Para cada tipo de ativo, variações do tipo de ativo podem ser criadas. Por exemplo, se tiver um tipo de ativo chamado **Caminhões**, você poderá criar variações desse tipo de ativo para fabricantes de ativos e modelos de ativo diferentes. Para cada configuração de tipo de ativo, você pode adicionar as peças sobressalentes e os planos de manutenção necessários.

Primeiro, você configura os tipos de ativo necessários. Em seguida, você cria os modelos de ativo que devem estar relacionados aos tipos de ativo. Por fim, na página **Padrões de tipo de ativo**, você cria todas as variações de tipos de ativo necessárias para o equipamento.

## <a name="create-an-asset-type"></a>Criar um tipo de ativo

1. Selecione **Gerenciamento de ativos** > **Configurar** > **Tipos de ativo** > **Tipos de ativo**.
2. Selecione **Novo** para criar um tipo de ativo.
3. No campo **Tipo de ativo**, insira uma ID do tipo de ativo.
4. No campo **Nome**, insira um nome.
5. No campo **Modelo de ciclo de vida de ativo**, selecione um modelo de ciclo de vida de ativo. Para obter mais informações sobre estados de ciclo de vida de ativo e modelos de ciclo de vida de ativo, consulte [Estados de ciclo de vida de ativo](object-stages.md).
6. Defina a opção **Total** como **Sim** se valores resumidos de KPI (indicador chave de desempenho) tiverem de ser calculados para os ativos com esse tipo de ativo.
7. Selecione **Salvar**.
8. Na Guia Rápida **Tipos de trabalho de manutenção**, selecione os tipos de trabalho de manutenção que devem ser relacionados ao tipo de ativo:

    - Para escolher um tipo de trabalho de manutenção, selecione-o no campo **Tipos de trabalho de manutenção restantes** e, em seguida, selecione o botão de seta para a direita ![Botão de seta para a direita](media/29-setup-for-objects.png) para movê-lo para a seção **Tipos de trabalho de manutenção selecionados**.
    - Para selecionar todos os tipos de trabalho de manutenção disponíveis, clique no botão ![seta Encaminhar tudo](media/30-setup-for-objects.png). Todos os tipos de trabalho de manutenção são transferidos do campo **Tipos de trabalho de manutenção restantes** para o campo **Tipos de trabalho de manutenção selecionados**.
    - Para cancelar a seleção de um tipo de trabalho de manutenção, marque-o no campo **Tipos de trabalho de manutenção selecionados** e selecione o botão de seta para a esquerda ![Botão de seta para a esquerda](media/31-setup-for-objects.png) para movê-lo para o campo **Tipos de trabalho de manutenção restantes**.

9. Você também pode selecionar os contadores que devem estar relacionadas ao tipo de ativo. Na Guia Rápida **Contadores**, faça as seleções usando os métodos descritos para tipos de trabalho de manutenção na etapa 8. Para obter mais informações sobre como configurar contadores, consulte [Contadores](counters.md).
10. Você também pode selecionar os tipos de atributo que devem estar relacionados ao tipo de ativo. Na Guia Rápida **Tipos de atributo**, faça as seleções usando os métodos descritos para tipos de trabalho de manutenção na etapa 8. Em seguida, para criar a sequência preferencial de tipos de atributo, selecione um atributo no campo **Tipos de atributo selecionados** e use os botões de seta para cima e para baixo para movê-lo. A sequência de tipos de atributo será mostrada nos ativos que usam esse tipo de ativo. Para obter mais informações sobre os atributos de ativo, consulte [Tipos de atributo de manutenção](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Quando você adicionar novos tipos de atributo à Guia Rápida **Tipos de atributo**, os ativos existentes serão automaticamente atualizados com essas informações.

11. Você também pode selecionar os modelos de avaliação de condição que devem estar relacionados ao tipo de ativo. Na Guia Rápida **Avaliações de condição**, faça as seleções usando os métodos descritos para tipos de trabalho de manutenção na etapa 8. Para obter mais informações sobre modelos e registros de avaliação de condição, consulte [Avaliação de condição](../setup-for-objects/condition-assessment.md).
12. A Guia Rápida **Modelo de ativo** mostra todas as combinações de fabricantes e modelos de ativo configurados em tipo de ativo selecionado. Para ver as combinações divididas de acordo com o fabricante, selecione **Modelo de ativo** para abrir a página **Modelo de ativo**.

    Na página **Modelo de ativo** , você pode adicionar relações de tipo de ativo e modelo de ativo. Além disso, na página **Tipos de ativo**, você pode adicionar relações entre fabricante de ativo e modelo de ativo diretamente para um tipo de ativo. Por fim, na página **Modelo de ativo** (**Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Modelo de ativo**), você pode criar novas relações entre fabricante de ativo, modelo de ativo e tipo de ativo. Consequentemente, há três maneiras de configurar e editar as relações entre fabricante de ativo, modelo de ativo e tipo de ativo. Todas as combinações disponíveis são mostradas de perspectivas diferentes, e você pode selecionar o ponto de entrada preferido quando trabalhar com a configuração.

> [!NOTE]
> - Se você selecionar contadores em um tipo de ativo, as seleções serão atualizadas automaticamente na página **Contadores** (**Gerenciamento de ativos** > **Configurar** > **Ativos** > **Tipos de ativo** > **Contadores**).
> - Os campos na seção **Detalhes** da Guia Rápida **Geral** mostram a quantidade de tipos de trabalho de manutenção, contadores, atributos, e assim por diante, configurados no tipo de ativo selecionado.

Normalmente, as ordens de trabalho criadas manualmente estão relacionadas à manutenção corretiva, enquanto as ordens de trabalho criados automaticamente estão relacionadas à manutenção preventiva. Quando você cria ordens de serviço manualmente, somente os tipos de trabalho de manutenção selecionados na Guia Rápida **Tipos de trabalho de manutenção** da página **Tipos de ativo** podem ser usados. Entretanto, as ordens de serviço criadas automaticamente podem usar todos os tipos de trabalho de manutenção que você criar na página **Tipos de trabalho de manutenção** (**Gerenciamento de ativos** \> **Configurar** \> **Trabalhos** \> **Tipos de trabalho de manutenção**).

## <a name="create-asset-type-setup-lines"></a>Criar linhas de configuração de tipo de ativo

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Tipos de ativo** \> **Configuração de tipo de ativo**. Como alternativa, selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Tipos de ativo** \> **Tipos de ativo**, selecione um tipo de ativo, e selecione **Configuração de tipo de ativo**.
2. Na primeira vez que usar a página **Configuração de tipo de ativo**, você poderá achar o botão **Criar combinações** muito útil. Você pode usar este botão para criar rapidamente todas as combinações de um modelo de ativo em um tipo de ativo. Selecione **Criar combinações**, selecione o tipo de ativo para o qual serão criadas as combinações e selecione **OK**.

    > [!NOTE]
    > Se você não usar todas as combinações de configuração de tipo de ativo criadas automaticamente, será possível excluir uma configuração selecionando-a e então selecionando **Excluir**.

3. Selecione **Novo** para criar manualmente uma configuração de tipo de ativo.
4. Dependendo do grau de especificidade da configuração do tipo de ativo, faça seleções nos campos **Tipo de ativo**, **Fabricante** e **Modelo**.
5. Se um contrato da garantia estiver relacionado ao tipo de ativo, selecione o contrato nos campos **Garantia do fornecedor** e **Garantia do cliente**. 
6. Na Guia Rápida **Partes sobressalentes**, selecione **Adicionar** para adicionar partes sobressalentes à configuração do tipo de ativo selecionado.
7. Para aprovar uma peça sobressalente, selecione a linha da peça sobressalente e selecione **Aprovar**. Você pode selecionar várias linhas para aprovação.
8. Para consultar se uma peça sobressalente será usada em outro lugar do Asset Management (por exemplo, em relação a ativos e ordens de serviço), selecione a linha da peça sobressalente e selecione **Item onde usado** para abrir a página **Item onde usado**. Para ver todas peças sobressalentes ativas na lista, marque a caixa de seleção **Ativo** . Para ver apenas as partes sobressalentes aprovadas, marque a caixa de seleção **Aprovado**.
9. Na Guia Rápida **Planos de manutenção**, selecione **Adicionar** para adicionar planos de manutenção à configuração do tipo de ativo selecionado.
10. Para copiar uma configuração do tipo de ativo para outra configuração, você poderá usar a função Copiar. Selecione o tipo de ativo para o qual deseja copiar uma configuração, selecione **Copiar configuração** e selecione a configuração de tipo de ativo da qual a configuração será copiada. As configurações das várias opções determina a quantidade de informações incluídas. Quando você terminar, selecione **OK** para copiar a configuração.

> [!NOTE]
> Se você tiver diversas linhas de peças sobressalentes e linhas de plano de manutenção que serão reutilizadas, a função Copiar permite que você configure os dados de forma fácil e rápida para muitas combinações de configuração de tipo de ativo.

## <a name="spare-parts-on-the-asset-type-setup"></a>Partes sobressalentes na configuração do tipo de ativo

Como descrito na seção "Criar linhas de configuração de tipo de ativo", as peças sobressalentes são configuradas em modelos de ativo na página **Configuração de tipo de ativo**. Portanto, quando abrir a página **Configuração de tipo de ativo**, você verá apenas as peças sobressalentes relacionadas à combinação selecionada de um tipo de ativo, fabricante de ativo e modelo de ativo. Para ver uma lista de todos os registros de peças sobressalentes, abra a página **Peças sobressalentes** (**Gerenciamento de ativos** \> **Consultas** \> **Peças sobressalentes**).

Na página **Peças sobressalentes**, você também pode criar novas peças sobressalentes para combinações existentes de um tipo de ativo, fabricante de ativo e modelo de ativo. Você pode decidir se prefere criar registros de peça sobressalente na página **Configuração de tipo de ativo** ou na página **Peças sobressalentes**. A página **Configuração de tipo de ativo** fornece uma visão geral de dados na combinação selecionada de um tipo de ativo, fabricante de ativo e modelo de ativo, enquanto **Peças sobressalentes** fornece uma visão geral de todas as linhas de configuração de tipo de ativo. Se a página **Peças sobressalentes** contiver vários registros, a página **Configuração de tipo de ativo** poderá oferecer uma visão geral melhor.

Para ver se a peça sobressalente na linha selecionada será usada em qualquer outro lugar do Asset Management (por exemplo, em relação a ativos e ordens de serviço), selecione a linha da peça sobressalente e selecione **Item onde usado** para abrir a página **Item onde usado**. 

