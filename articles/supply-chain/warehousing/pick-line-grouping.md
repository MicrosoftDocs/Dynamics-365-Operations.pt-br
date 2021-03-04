---
title: Agrupamento de linhas de separação
description: Este tópico oferece uma visão geral de agrupamento de linhas de separação.
author: Mirzaab
manager: tfehr
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: b3497d43a500898207ed5154721ee0e3a327fb93
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422517"
---
# <a name="pick-line-grouping"></a>Agrupamento de linhas de separação

[!include [banner](../includes/banner.md)]

No agrupamento de linhas de separação, várias linhas de trabalho que têm o mesmo item e local podem ser combinadas em uma única separação que é apresentada ao usuário em um dispositivo móvel. Portanto, os trabalhadores de depósito podem receber as instruções mais eficientes possíveis, mas a separação necessária de linhas de trabalho no sistema também é mantida (por exemplo, para diferentes contêineres e ordens).

## <a name="set-up-pick-line-grouping"></a>Configurar agrupamento de linhas de separação

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel** e criar um novo item de menu que é nomeado **Separação de linha do grupo de vendas – Direcionada ao usuário**.
2. Em **Itens de menu do dispositivo móvel**, defina os seguintes valores:

    - No campo **Nome do item de menu** digite **Separação de Vendas - Linha do grupo**.
    - No campo **Título**, digite **Separação de Vendas - Linha do grupo**.
    - No campo **Modo**, selecione **Trabalho**.
    - Defina a opção **Usar trabalho existente** para **Sim**.

3. Na Guia Rápida **Geral**, defina os seguintes valores:

    - No campo **Direcionado por**, selecione **Direcionado pelo usuário**.
    - Defina a opção **Gerar placa de licença** como **Sim**.
    - Defina a opção **Separação por grupo** como **Sim**.

4. Na Guia Rápida **Classes de trabalho**, siga estas etapas para configurar as classes de trabalho válidas para o item de menu do dispositivo móvel:

    1. Selecione **Novo**.
    2. No campo **ID da classe de trabalho**, selecione **Vendas** ou **Separação de OV**, dependendo do depósito que você usará.
    3. No campo **Tipo de ordem de trabalho**, selecione **Ordens de compra**.

### <a name="set-up-a-mobile-device-menu"></a>Configura um menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**. 
1. Adicione o item de menu que você acabou de criar para o menu desejado.

### <a name="set-up-a-work-template"></a>Configurar um modelo de trabalho

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.
1. Localize o modelo de trabalho que deve ser usado com essa função. Para este exemplo, selecione o modelo de trabalho **51 Estágio de separação** Contoso.
1. No menu, selecione **Editar consulta**.
1. Na guia **Classificação**, selecione **Adicionar** e, em seguida, defina os seguintes valores:

    - No campo **Tabela**, selecione **Transações de trabalho temporário**.
    - No campo **Tabela derivada**, selecione **Transações de trabalho temporário**.
    - No campo **Campo**, selecione **Número do item**.
    - No campo **Direção da pesquisa**, selecione **Crescente**.

> [!NOTE]
> Para que a funcionalidade agrupamento de linhas de separação funcione, as linhas de trabalho devem ser classificadas por ID do item. Se as linhas que têm os mesmos itens não forem sequenciadas uma após a outra, elas não serão agrupadas.

## <a name="example"></a>Exemplo

### <a name="create-picking-work"></a>Criar trabalho de separação

Antes de configurar o agrupamento de linhas de separação, você deve criar algum trabalho de saída qualificado.

1. Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione **Novo** para criar uma ordem de venda. 
3. No campo **Conta de cliente**, selecione qualquer cliente. 
4. Na Guia Rápida **Geral**, no campo **Depósito**, selecione **51**. Em seguida, selecione **OK**.
5. Nas **Linhas de ordem de venda**, adicione as seguintes seis linhas:

    - **Linha 1:** No campo **Número do item**, selecione **M9200**. No campo **Quantidade**, insira **3**.
    - **Linha 2:** No campo **Número do item**, selecione **M9201**. No campo **Quantidade**, insira **3**. 
    - **Linha 3:** No campo **Número do item**, selecione **M9202**. No campo **Quantidade**, insira **2**. 
    - **Linha 4:** No campo **Número do item**, selecione **M9200**. No campo **Quantidade**, insira **1**. 
    - **Linha 5:** No campo **Número do item**, selecione **M9200**. No campo **Quantidade**, insira **3**.
    - **Linha 6:** No campo **Número do item**, selecione **M9202**. No campo **Quantidade**, insira **7**. 

    Aqui está um resumo das quantidades totais de cada item:

    - **Item M9200:** 7 cada
    - **Item M9201:** 3 cada
    - **Item M9202:** 9 cada

6. Antes de liberar as ordens para o depósito, você deve verificar se os locais de separação têm estoque suficiente para todos os itens em todas as ordens. Revise a configuração **Diretiva de localização** para determinar quais locais de separação são usadas para separação da ordem de venda.
7. Reserve o estoque e libere-o para o depósito. Uma ID de trabalho que tem seis linhas é criada. As linhas são classificadas por número de item.

### <a name="run-the-mobile-device-flow"></a>Execute o fluxo do dispositivo móvel

1. No dispositivo móvel, selecione o menu que inclui o novo item de menu do dispositivo móvel.
1. Selecione o item de menu **Separação de Vendas – Linha do grupo** e inicie a separação.

    Depois de selecionar o menu e inserir a ID de trabalho, você verá a etapa de seleção em que todas as linhas de separação do item M9200 são agrupadas. Você recebe uma instrução para selecionar 7 a cada M9200 do item.

1. Confirme a etapa de separação. 
1. Vá para a tela do cliente do trabalho em andamento e observe que todas as três linhas de separação do item M9200 foram fechadas simultaneamente.

    A linha de trabalho 4 é apresentada.

1. Confirme a etapa de separação.

    A última etapa de separação no dispositivo móvel agrega as duas últimas linhas de separação da ordem de trabalho.

1. Conclua a etapa de separação para 9 cada um dos itens M9202.
1. Confirme a etapa Put e os pares Separar/Colocar adicionais para concluir o trabalho.

> [!NOTE]
> - As linhas de trabalho podem ser agrupadas somente se estiverem em sequência.
> - A seguinte funcionalidade não é suportada:
>
>    - Itens de peso variável. Se houver itens de peso variável no trabalho, você receberá uma mensagem de erro antes de começar a separar.
>    - Separação de peças.
>    - Linhas de trabalho que têm trabalho de reabastecimento não concluído.
>    - Separação de ordens.
>    - Separação insuficiente com realocação de item


[!INCLUDE[footer-include](../../includes/footer-banner.md)]