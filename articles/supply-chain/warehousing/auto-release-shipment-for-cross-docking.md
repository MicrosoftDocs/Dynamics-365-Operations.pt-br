---
title: Remessa da versão automática para a distribuição integrada
description: Este tópico descreve uma estratégia de distribuição integrada que permite liberar automaticamente uma ordem de demanda para o depósito quando a ordem de produção que fornece a quantidade de demanda é relatado como concluído, para que a quantidade seja movido diretamente do local de saída de produção local de saída.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b86fe2f3ea4321dbe598233018934187ba0d713a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421982"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Remessa da versão automática para a distribuição integrada

[!include [banner](../includes/banner.md)]

Este tópico descreve uma estratégia de distribuição integrada que permite liberar automaticamente uma ordem de demanda para o depósito quando a ordem de produção que fornece a quantidade de demanda é relatado como concluído. Dessa forma, a quantidade necessária para o preenchimento da ordem de demanda é movida diretamente do local de saída de produção local de saída.

A distribuição integrada é um fluxo de manuseio de depósito na quantidade necessária para preencher uma ordem de saída seja direcionada para a doca de saída ou área de remessa de ordem do local onde a ordem de entrada foi recebida. A ordem de entrada pode ser uma ordem de compra, ordem de transferência ou ordem de produção. Considerando que o recurso Distribuição integrada avançada dá suporte a todas as ordens de fornecimento e demanda, e que exige que a demanda de saída seja liberada antes de a oportunidade de distribuição integrada ser identificada, o recurso Remessa de liberação automática tem estas características:

- Ele dá suporte apenas às ordens de produção como fornecimento e apenas às ordens de venda e ordens de transferência como demanda.
- A operação de distribuição integrada pode ser iniciada mesmo se a ordem da demanda não tiver sido liberada para o depósito antes do registro do recebimento do fornecimento (ou seja, antes de a produção ser relatada como concluída).

Essa funcionalidade de distribuição integrada tem duas vantagens:

- As operações de depósito poderão ignorar a etapa de guardar quantidades de bens acabados na área de armazenamento normal de depósito se essas quantidades forem selecionadas novamente somente para atender à ordem de saída. Em vez disso, as quantidades podem ser movidas uma vez, do local de saída para um local de embalagem/remessa. Assim, a funcionalidade ajuda a minimizar o número de vezes que o estoque é tratado e, por fim, ajuda a maximizar a economia de tempo e espaço no chão de fábrica do depósito.
- As operações de depósito poderão adiar a liberação de ordens de venda e ordens de transferência para o depósito até a saída de bens acabados para a ordem de produção associada ser relatada como concluída. A vantagem pode ser especialmente relevante em ambientes de produção de execução por encomenda, onde os prazos de entrega da fabricação tendem ser mais longos do que os prazos de entrega em ambientes de fabricação para armazenamento.

## <a name="prerequisites"></a>Pré-requisitos

| Pré-requisito | Descrição |
|---|---|
| Item | O item deve ser habilitado para os processos de gerenciamento de depósito.<p>**Observação:** os itens habilitados para peso variável não podem ser incluídos nos processos de distribuição integrada.</p> |
| Depósito | O depósito deve ser habilitado para os processos de gerenciamento de depósito. |
| Modelos de distribuição integrada | Pelo menos um método de distribuição integrada que use a política de liberação de demanda **No recebimento do fornecimento** deve ser configurado para um depósito específico. |
| Classe de trabalho | Uma ID da classe de trabalho de distribuição integrada deve ser criada para o tipo de ordem de serviço **Distribuição integrada**. |
| Modelos do trabalho | Os modelos de tipo de ordem de serviço **Distribuição integrada** são necessários para criar a separação de distribuição integrada e o trabalho de colocação. |
| Diretivas de localização | As diretivas da localização do tipo de ordem de serviço **Distribuição integrada** são necessárias para orientar o trabalho de colocação nos locais onde as quantidades de ordens de venda serão embaladas e enviadas. |
| Marcação entre uma ordem da demanda e uma ordem de produção | O sistema de depósito só poderá acionar a liberação automática da remessa de ordem de saída e criar o trabalho de distribuição integrada desde o local de saída na ação relatada como concluída se as ordens de venda e as ordens de transferência estiverem reservadas e marcadas em uma ordem de produção. |

## <a name="example-cross-docking-flow"></a>Fluxo de distribuição integrada de exemplo

Um fluxo típico de distribuição integrada consiste nas seguintes etapas principais.

1. Um tomador de ordem de venda cria uma ordem de venda para um produto de execução por encomenda. Normalmente, a quantidade solicitada não está disponível e deve ser gerada primeiro.
2. O tomador de ordem de venda cria uma ordem de produção diretamente da linha de ordem de venda. Assim, o tomador da ordem de venda reserva e marca a quantidade de ordens de venda em relação à quantidade de ordens de produção. 

    Como alternativa, um planejador de produção especifica que a marcação deverá ser atualizada quando as ordens planejadas estiverem sendo confirmadas.

3. A ordem de produção passa pelas seguintes etapas:

    1. Um planejador de produção estima e libera a ordem de produção. A estimativa inclui a reserva de matéria-prima e a liberação inclui a liberação para um depósito.
    2. Um trabalhador de depósito inicia e conclui a separação da matéria-prima do local de armazenamento para o local de entrada de produção, de acordo com os trabalhos de separação da produção.
    3. Um operador de chão de fábrica inicia a ordem de produção.
    4. Na última operação, um operador de computador usa o dispositivo móvel para relatar a ordem de produção como concluída.

4. O sistema usa a configuração para identificar o evento de distribuição integrada para as duas ordens vinculadas e então conclui estas tarefas:

    1. Liberar automaticamente a ordem de venda associada para um depósito criar uma remessa.
    2. Crie automaticamente os trabalhos de distribuição integrada com instruções para separar os bens acabados do local de saída e os mova para o local de saída que as diretivas de local de distribuição integrada atribuíram à ordem de venda.
    3. Solicite a um operador de computador que conclua o trabalho de distribuição integrada imediatamente após a ordem de produção ser relatada como concluída.

5. Depois que o trabalho de distribuição integrada for concluído, as quantidades serão carregadas no veículo, um planejador de saída do depósito confirmará a remessa de venda.

## <a name="example-scenario"></a>Cenário de exemplo

Para este cenário, você deve ter os dados de demonstração instalados e deve usar a empresa de dados de demonstração **USMF**.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Configurar distribuição integrada que usa o recurso de remessa de liberação automática

#### <a name="cross-docking-template"></a>Modelo de distribuição integrada

1. Vá para **Gerenciamento de depósito** \> **Configuração**  \> **Trabalho** \> **Modelos de distribuição integrada**.
2. Selecione **Novo**.
3. No campo **Número de sequência**, insira **1**.
4. No campo **ID do modelo de distribuição integrada** , insira um nome, como **XDock\_RAF**.
5. No campo **Política de liberação de demanda**, selecione **No recebimento do fornecimento**.
6. No campo **Depósito**, insira o número do depósito onde você deseja configurar o processo de distribuição integrada. Neste exemplo, selecione **51**.

    > [!NOTE]
    > Assim que você selecionar **No recebimento do fornecimento** como a política de liberação de demanda para o modelo, todos os campos restantes na página ficarão indisponíveis. Da mesma forma, não é possível definir qualquer origem de fornecimento. Esse comportamento ocorre porque a distribuição integrada que usa o recurso de remessa de liberação automática só oferece suporte a ordens de produção como origens de fornecimento e requer que exista uma marcação entre ordens de venda e ordens de produção. Se você selecionar **Antes do recebimento do fornecimento** como a política de liberação de demanda, os campos nas guias **Planejamento** e **Origens de fornecimento** estão disponíveis e podem ser editados.

#### <a name="work-classes"></a>Classes de trabalho

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Trabalho** \> **Classes de trabalho**.
2. Selecione **Novo**.
3. No campo **ID da classe de trabalho**, insira um nome, como **CrossDock**.
4. No campo **Tipo de ordem de serviço**, selecione **Distribuição integrada**.

Para limitar os tipos de local em que os bens acabados de distribuição integrada podem ser colocados, você poderá especificar um ou mais tipos válidos de localização.

#### <a name="work-templates"></a>Modelos do trabalho

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Trabalho** \> **Modelos de trabalho**.
2. No campo **Tipo de ordem de serviço**, selecione **Distribuição integrada**.
3. Selecione **Novo**.
4. No campo **Número de sequência**, insira **1**.
5. No campo **Modelo de trabalho**, insira um nome, como **CrossDock\_51**.
6. Selecione **Salvar**.
7. Na seção **Detalhes do Modelo de Trabalho**, selecione **Novo**.
8. Para a nova linha, no campo **Tipo de trabalho**, selecione **Separar**. No campo **ID da classe de trabalho**, selecione **CrossDock**.
9. Selecione **Novo**.
10. Para a nova linha, no campo **Tipo de trabalho**, selecione **Colocar**. No campo **ID da classe de trabalho**, selecione **CrossDock**.

#### <a name="location-directives"></a>Diretivas de localização

Um processo padrão de armazenamento para bens acabados exige uma diretiva de localização **Colocar** para orientar o movimento de quantidades separadas de produção para um espaço de armazenamento normal. Da mesma forma, você deve configurar uma diretiva de localização **Colocar** para distribuição integrada para instruir os trabalhos a colocar a quantidade acabada em um determinado local de saída que sirva a remessa da ordem de venda associada.

Para a distribuição integrada, assim como para o armazenamento normal de bens acabados, você não precisa criar uma diretiva de localização para a ação de trabalho de separação porque o local de saída é fornecido. Adicionalmente, esse local de saída deve ser configurado como o local de saída padrão em um dos registros relacionados ao recurso (ou seja, o recurso, a relação do grupo de recursos ou o grupo de recursos) ou como um local de bens acabados de produção padrão para um depósito.

1. Vá para **Gerenciamento de depósito** \> **Configuração** \> **Diretivas de localização**.
2. No campo **Tipo de ordem de serviço**, selecione **Distribuição integrada**.
3. Selecione **Novo**.
4. No campo **Número de sequência**, insira **1**.
5. No campo **Nome** , insira um nome, como **Porta da baía**.
6. No campo **Tipo de trabalho**, selecione **Colocar**.
7. No campo **Local**, selecione **5**.
8. No campo **Depósito**, selecione **51**.
9. Na Guia Rápida **Linhas**, selecione **Novo**.
10. No campo **Quantidade final**, insira a quantidade máxima do intervalo, como **1000000**.
11. Selecione **Salvar**.
12. Na Guia Rápida **Ações de Diretivas de Localização**, selecione **Novo**.
13. No campo **Nome** , insira um nome, como **Porta da baía**.
14. Selecione **Salvar**.
15. Você pode usar o recurso de consulta padrão para limitar locais de colocação a um ou mais locais específicos. Selecione **Editar consulta** e selecione **51** como critério para o campo **Depósito** na tabela **Locais**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Bens acabados de distribuição integrada para o local de saída

Para fazer a distribuição cruzada da quantidade de bens acabados para o local de saída da ordem de venda associada, siga estas etapas.

1. Vá para **Vendas e marketing** \> **Ordens de venda** \> **Todas as ordens de venda**.
2. Selecione **Novo**.
3. Para o cabeçalho de ordem de venda, selecione a conta do cliente **US-001** e um depósito que esteja configurado para distribuição integrada usando o recurso de remessa de liberação automática.
4. Adicione uma linha para um produto final e insira **10** como a quantidade.
5. Na seção **Linhas de ordem de venda** , selecione **Produto e fornecimento** \> **Ordem de produção**.
6. Na caixa de diálogo **Criar ordem de produção**, examine os valores padrão e selecione **Criar**. Uma nova ordem de produção é criada e vinculada à ordem de venda (isto é, é reservada e marcada).
7. Opcional: altere o campo **Quantidade** para que ele fique maior do que o valor necessário para atender à ordem de venda. Quando a quantidade de produção é relatada como concluída, o sistema cria o trabalho de distribuição integrada para a quantidade marcada e o trabalho de armazenamento para a quantidade restante de acordo com o procedimento normal de tratamento de armazenamento de bens acabados.

    Como mencionado anteriormente, deve existir uma marcação entre a ordem de venda e a ordem de produção. Caso contrário, a distribuição integrada não funcionará. Uma marcação pode ser criada de várias formas:

    - O sistema pode criar a marcação automaticamente nas seguintes situações:

        - A ordem de produção é criada de forma manual diretamente da linha de ordem de venda (consulte a etapa 6).
        - As ordens de produção planejadas são firmadas e o campo **Atualizar marcação** é definido como **Padrão**.

    - O usuário pode criar manualmente a marcação ao abrir a página **Marcação** desde a linha de ordem de demanda.

    > [!NOTE]
    > Uma marcação não pode ser criada manualmente para os itens configurados para usar a média padrão e ponderada como modelos de estoque.

8. Na página **Ordem de produção**, no Painel de Ação, na guia **Ordem de produção**, no grupo **Processar**, selecione **Previsão** e selecione **OK**. A ordem é estimada e a quantidade de matéria-prima é reservada para a produção.
9. No Painel de Ação, na guia **Ordem de produção**, no grupo **Processar**, selecione **Liberar** e selecione **OK**. O trabalho de separação de depósito é criado para as matérias-primas.
10. Abra e revise o trabalho. No Painel de Ação, na guia **Depósito**, no grupo **Geral**, selecione **Detalhes do trabalho**. Anote a ID do trabalho.
11. Entre no aplicativo de depósito para executar o trabalho no depósito 51.
12. Vá para **Produção** \> **Separação da produção**.
13. Insira a ID do trabalho para iniciar e concluir a separação de matéria-prima. 

    Depois que o trabalho for relatado como concluído, a quantidade de matérias-primas estará disponível no local de entrada de produção (**005** em dados de demonstração de USMF) e a execução da ordem de produção poderá começar.

14. Na página **Ordem de produção**, no Painel de Ação, na guia **Ordem de produção**, no grupo **Processar**, selecione **Iniciar** e selecione **OK**.
15. No aplicativo, vá para **Produção** \> **RAF e armazenamento**.
16. No campo **ID da Produção**, insira o número da ordem de produção e outros detalhes obrigatórios e selecione **OK**.

Observe que ocorrerão os seguintes eventos:

- A liberação para um depósito é acionada para a ordem de venda vinculada.
- Com base na liberação, o trabalho de remessa e distribuição integrada é criado. Esse trabalho instrui o operador de depósito a separar as quantidades necessárias para atender à linha de ordem de venda e as coloca no local de saída especificado na diretiva de localização de distribuição integrada.
- Se a quantidade de ordem de produção for superior à quantidade necessária para a ordem de venda, o trabalho de armazenamento normal será criado. Esse trabalho instrui o operador de depósito a separar a quantidade de bens acabados restantes após a distribuição integrada e a move-los para o estoque normal, de acordo com a diretiva de localização.
