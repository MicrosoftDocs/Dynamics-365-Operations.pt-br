---
title: Separação de cluster direcionada pelo sistema
description: Este tópico fornece uma visão geral da separação de cluster direcionada pelo sistema no Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: c3b23a5d3b77bae89e4845bdff4ab20f95c46497
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917847"
---
# <a name="system-directed-cluster-picking"></a>Separação de cluster direcionada pelo sistema

[!include [banner](../includes/banner.md)]

A separação de clusters é um processo de separação de peças que permite separar itens para várias ordens ao mesmo tempo, agrupando-os em clusters de separação. Em seguida, você terá que visitar o local de separação apenas uma vez. Normalmente, essa funcionalidade é usada com pequenas ou menores quantidades de separação de ordens que são menores que as quantidades do caso.

Quando a separação de clusters direcionados pelo sistema é configurada, você pode separar os cabeçalhos de trabalho em cluster, com base em um cluster gerado pelo sistema. As ordens de separações de cluster do sistema até o número de posições especificado no perfil do cluster. Portanto, é possível separar várias ordens ao mesmo tempo, sem a necessidade de criar um cluster manualmente.

A separação de cluster direcionada pelo sistema oferece uma alternativa para criação de cluster manual, no qual um perfil de cluster é usado para criar um cluster. Várias linhas relacionadas à configuração devem ser definidas no perfil de cluster antes de serem usadas:

- **Número de posições** corresponde ao número de ordens que serão colocadas em um cluster. Portanto, ele corresponde ao número de totes.
- **Dividir cluster** determina quando o cluster deve ser dividido.
- **Gerar ID de cluster** controla se o ID de cluster será gerado pelo sistema ou informado pelo usuário.
- **Classificar tipo de verificação** determina se a verificação de posição é necessária.

Um novo item de menu de dispositivo móvel é usado para a separação de cluster direcionada pelo sistema. A ID do perfil do cluster deve ser especificado para a opção **Direcionada por**. Além disso, a ordem de consulta direcionada pelo sistema pode agrupar ordens, com base em critérios específicos da empresa. Portanto, você pode otimizar ainda mais a atribuição de ordens de trabalho especificando critérios de classificação personalizados na ordem de consulta direcionada pelo sistema.

Quando a separação de clusters direcionados pelo sistema é realizada, os trabalhadores de depósito são apresentados com um cluster em que as ordens de separação foram atribuídas a posições de cluster. Portanto, os trabalhadores podem começar a separar um item para várias ordens de trabalho visitando o local de separação apenas uma vez. O processo de separação para a separação de clusters direcionados pelo sistema é o mesmo que o processo de separação de clusters direcionada pelo usuário.

## <a name="set-up-system-directed-cluster-picking"></a>Configurar separação de cluster direcionada pelo sistema

### <a name="create-cluster-profiles"></a>Criar perfis de cluster

Os perfis de cluster controlam como o sistema cria cada cluster. Se forem necessários diferentes clusters, um perfil de cluster diferente deverá ser criado para cada item de menu de dispositivo móvel.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.
2. Selecione **Novo**.
3. No campo **ID do perfil de cluster**, informe **2 Posições**.
4. No campo **Nome**, digite **2 Posições**.
5. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Gerar ID de cluster** : defina esta opção como **Sim**. Esta opção determina se a ID do cluster será criada automaticamente pelo sistema ou se o usuário a criará no início da separação.
    - **Ativar posições:** defina esta opção como **Sim**. Esta opção determina se os nomes de posição são gerados automaticamente com base na configuração do nome da posição. Se esta opção for definida como **Não**, será usada a ID da placa de licença para a posição.
    - **Número de posições:** Digite **2**. Este campo determina o número máximo de posições que o cluster pode ter (ou seja, o número máximo de caixas, totes, etc.).
    - **Nome da posição:** Selecione **Numérico**, para que as posições sejam nomeadas usando números contínuos. Se você selecionar **Alfabética**, as posições serão nomeadas em ordem alfabética.
    - **Dividir cluster em:** Selecione **Put**. Este campo determina quando o cluster é dividido.
    - **Classificar tipo de verificação:** Selecione **Verificação da posição**. Este campo determina se a etapa posição de colocação é verificada.

6. Na Guia Rápida **Classificação de cluster** é possível definir critérios de classificação, criando uma nova linha e definindo os seguintes campos:

    - **Número de sequência** : Este campo determina a sequência pela qual o sistema classifica. Um valor é inserido automaticamente, mas você pode alterá-lo, conforme necessário.
    - **Nome do campo:** Selecione **WMSLocationId**. Este campo determina o campo que a linha usa para critérios de classificação.
    - **Classificação:** selecione **Crescente**. Este campo define se a classificação é feita em ordem crescente ou decrescente.

### <a name="create-a-mobile-device-menu-item"></a>Criar um item de menu de dispositivo móvel

Para criar um novo item de menu de dispositivo móvel para a separação de cluster dirigida pelo sistema e vincular a ID do perfil de cluster ao item de menu do dispositivo móvel, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
2. Selecione **Novo**.
3. No campo **Nome do item de menu**, digite **Cluster SD**.
4. No campo **Título**, digite **Cluster SD**.
5. No campo **Modo**, selecione **Trabalho**.
6. Defina a opção **Usar trabalho existente** para **Sim**.
7. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Direcionado por:** Selecione **Direcionado pelo sistema**.
    - **Gerar placa de licença:** Defina esta opção como **Sim**.
    - **ID do perfil do cluster:** Selecione **2 Posições**.

8. Na Guia Rápida **Classes de trabalho**, configure a classe de trabalho válida para este item de menu do dispositivo móvel definindo os seguintes campos:

    - **ID da classe de trabalho:** Certifique-se de que **Vendas** foi informado.
    - **Tipo de ordem de trabalho:** Certifique-se de que **Ordens de venda** foi informado.

9. Siga estas etapas para especificar uma nova consulta de sequência de trabalho direcionada pelo sistema:

    1. Selecione **Novo**.
    2. No campo **Número de sequência**, insira **1**.
    3. No campo **Descrição**, selecione **Prioridade de trabalho - ID do Trabalho**.

10. No menu, selecione **Editar consulta**.
11. Na guia **Classificação**, defina os seguintes campos:

    - **Tabela:** Selecione **Trabalho**.
    - **Tabela derivada:** Selecione **Trabalho**.
    - **Campo:** Selecione **Prioridade de trabalho**.
    - **Direção da pesquisa:** Selecione **Crescente**.
    - **Tabela:** Selecione **Trabalho**.
    - **Tabela derivada:** Selecione **Trabalho**.
    - **Campo:** Selecione **ID do Trabalho**.
    - **Direção da pesquisa:** Selecione **Crescente**.

O sistema agora classificará as IDs de trabalho no cluster, primeiro por prioridade de trabalho e, em seguida, por ID de trabalho.

### <a name="set-up-a-mobile-device-menu"></a>Configura um menu de dispositivo móvel

1. Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.
2. Adicione o item de menu que você acabou de criar para o menu desejado.

## <a name="example"></a>Exemplo

### <a name="create-picking-work"></a>Criar trabalho de separação

Antes de configurar a separação de cluster direcionada pelo sistema, você deve criar algum trabalho de saída qualificado. O perfil de cluster criado anteriormente especifica duas posições de cluster. Portanto, você deve criar pelo menos duas IDs de trabalho.

1. Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.
2. Selecione **Novo** para criar uma ordem de venda.
3. No campo **Conta de cliente**, selecione qualquer cliente.
4. Na Guia Rápida **Geral**, no campo **Depósito**, selecione depósito **62**.
5. Selecione **OK**.
6. Na Guia Rápida **Linhas de ordem de venda**, selecione **Adicionar linha**.
7. No campo **Número de item**, selecione **A0001**.
8. No campo **Quantidade**, insira **1**.
9. Selecione **Adicionar linha** para adicionar uma segunda linha.
10. No campo **Número de item**, selecione **A0002**.
11. No campo **Quantidade**, insira **3**.
12. Repita as etapas de 2 a 6.
13. No campo **Número de item**, selecione **A0001**.
14. No campo **Quantidade**, insira **4**.
15. Selecione **Adicionar linha** para adicionar uma segunda linha.
16. No campo **Número de item**, selecione **A0002**.
17. No campo **Quantidade**, insira **2**.

Reserve o estoque e libere-o para o depósito. Duas IDs de trabalho diferentes serão criadas. Cada ID de trabalho tem duas linhas de separação.

### <a name="run-the-mobile-device-flow"></a>Execute o fluxo do dispositivo móvel

1. No dispositivo móvel, selecione o menu que inclui o novo item de menu do dispositivo móvel.
2. Selecione o item de menu **Cluster SD** e inicie a separação. Um cluster é criado e as duas IDs de trabalho criadas anteriormente são anexadas a ele. Se você tiver criado mais de duas IDs de trabalho, somente as duas primeiras serão adicionadas ao cluster. Observe que as IDs de trabalho são adicionadas ao cluster na ordem crescente, conforme especificado na configuração de consulta.

    > [!NOTE]
    > O novo cluster será criado automaticamente somente se IDs de trabalho adicionais forem criadas anteriormente. Caso contrário, a seguinte mensagem será exibida: "não é possível encontrar um trabalho suficiente para o cluster".

    Depois que você selecionar o menu, a primeira tela de seleção será exibida. O sistema agrega todas as linhas de separação correspondentes das duas IDs de trabalho e o orienta a visitar o local de separação uma vez, de forma que você possa atender a ambas as ordens usando uma separação. Esse processo é feito da mesma forma que o processo de separação de clusters direcionada pelo usuário.

3. Confirme a primeira separação. Em seguida, você deve inserir o nome da posição para confirmar que os itens foram colocados na posição correta.
4. Repita esse processo até que todos os itens tenham sido separados e colocados na posição correta.
5. A última etapa no dispositivo móvel é colocar o cluster na localização final. Quando esta operação Put é confirmada, o cluster é fechado e dividido, com base no valor definido para o campo **Dividir cluster em** no perfil de cluster. As IDs de trabalho também são fechadas.
6. Uma mensagem de "Cluster concluído" é exibida no dispositivo móvel.
