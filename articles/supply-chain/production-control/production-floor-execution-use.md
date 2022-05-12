---
title: Como os trabalhadores usam a interface de execução de piso de produção
description: Este tópico descreve como usar a interface de execução de piso de produção do ponto de vista de um trabalhador.
author: johanhoffmann
ms.date: 01/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f163b8feb906470f31a648bf09abf5647c5f1bab
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644980"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Como os trabalhadores usam a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]

A interface de execução de piso de produção é otimizada para interação por toque. Seu design oferece um contraste visual que atende aos requisitos de acessibilidade para ambientes de chão de fábrica. Ele oferece todos os mesmos recursos funcionais do que o dispositivo de ficha de trabalho. No entanto, ele também permite que vários trabalhos sejam iniciados em paralelo de uma lista de trabalhos. (Esse recurso também é conhecido como *agrupamento de trabalhos*). Além disso, de uma lista de trabalhos, os funcionários podem abrir um guia criado no Guia do Microsoft Dynamics 365. Dessa forma, eles podem obter instruções visuais em um HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Entrar na interface de execução de piso de produção como um trabalhador

Antes que os funcionários possam começar a usar o dispositivo, um supervisor ou uma equipe técnica deverá prepará-lo e abrir a página correta no Dynamics 365 Supply Chain Management. Para obter mais informações sobre como configurar o dispositivo, consulte [Configurar um dispositivo para executar a interface de execução de piso de produção](production-floor-execution-setup.md).

Depois que o dispositivo tiver sido preparado, a página de entrada aparecerá nele. Essa página mostra informações sobre o status de trabalhos da célula de trabalho local. Essas informações são atualizadas periodicamente. Na página, os trabalhadores usam suas IDs de crachá para assinar. Embora os funcionários não precisem ter uma conta de usuário para o Supply Chain Management, eles devem ter uma conta de *trabalhador com tempo registrado* que possam usar para entrar.

![Página de entrada de interface de execução de piso de produção.](media/pfei-sign-in-page.png "Página de entrada de interface de execução de piso de produção")

As seções restantes deste tópico descrevem como os funcionários interagem com a interface.

## <a name="all-jobs-tab"></a>Guia Todos os trabalhos

A guia **Todos os trabalhos** fornece uma lista de trabalhos que mostra todos os trabalhos de produção com o status *Não iniciado*, *Parado* ou *Iniciado*. (Este nome de guia é personalizável e pode ser diferente para o seu sistema.)

![Guia Todos os trabalhos.](media/pfei-all-jobs-tab.png "Guia Todos os trabalhos")

A lista de trabalhos tem as colunas a seguir. Os números correspondem aos números da ilustração anterior.

1. **Coluna de seleção** – a coluna mais à esquerda usa marcas de seleção para indicar os trabalhos selecionados pelo trabalhador. Os trabalhadores podem selecionar vários trabalhos na lista ao mesmo tempo. Para selecionar todos os trabalhos na lista, marque a caixa de seleção no cabeçalho da coluna. Quando um único trabalho é selecionado, os detalhes desse trabalho são mostrados na parte inferior da página.
1. **Coluna Status do trabalho** – essa coluna usa símbolos para indicar o status de cada trabalho. Os trabalhos sem nenhum símbolo nessa coluna têm o status *Não iniciado*. Um triângulo verde indica trabalhos com o status *Iniciado*. Duas linhas verticais amarelas indicam trabalhos com o status *Parado*.
1. **Coluna Alta prioridade** – essa coluna usa pontos de exclamação para indicar trabalhos com alta prioridade.
1. **Ordem** – essa coluna mostra o número da ordem de produção para um trabalho.
1. **Descrição** – essa coluna mostra uma descrição da operação da qual um trabalho faz parte.
1. **Solicitado** – essa coluna mostra a quantidade que um trabalho está planejado para produzir.
1. **Iniciado** – essa coluna mostra a quantidade que já foi iniciada para um trabalho.
1. **Concluído** – essa coluna mostra a quantidade que já foi concluída para um trabalho.
1. **Sucateado** – essa coluna mostra a quantidade que já foi sucateada para um trabalho.
1. **Restante** – essa coluna mostra a quantidade que resta para ser concluída para um trabalho.

## <a name="active-jobs-tab"></a>Guia Trabalhos ativos

A guia **Trabalhos ativos** mostra uma lista de todos os trabalhos que o trabalhador conectado já iniciou. (Este nome de guia é personalizável e pode ser diferente para o seu sistema.)

![Guia Trabalhos ativos.](media/pfei-active-jobs-tab.png "Guia Trabalhos ativos")

A lista de trabalhos ativos tem as colunas a seguir:

- **Coluna de seleção** – a coluna mais à esquerda usa marcas de seleção para indicar os trabalhos selecionados pelo trabalhador. Os trabalhadores podem selecionar vários trabalhos na lista ao mesmo tempo. Para selecionar todos os trabalhos na lista, marque a caixa de seleção no cabeçalho da coluna. Quando um único trabalho é selecionado, os detalhes desse trabalho são mostrados na parte inferior da página.
- **Ordem** – essa coluna mostra o número da ordem de produção para um trabalho.
- **Descrição** – essa coluna mostra uma descrição da operação da qual um trabalho faz parte.
- **Solicitado** – essa coluna mostra a quantidade que um trabalho está planejado para produzir.
- **Iniciado** – essa coluna mostra a quantidade que já foi iniciada para um trabalho.
- **Concluído** – essa coluna mostra a quantidade que já foi concluída para um trabalho.
- **Sucateado** – essa coluna mostra a quantidade que já foi sucateada para um trabalho.
- **Restante** – essa coluna mostra a quantidade que resta para ser concluída para um trabalho.

## <a name="my-jobs-tab"></a>Guia Meus trabalhos

A guia **Meus trabalhos** permite que trabalhadores exibam facilmente todos os trabalhos não iniciados e não concluídos que são atribuídos especificamente a eles. Ele é útil em empresas em que os trabalhos são às vezes ou sempre atribuídos a trabalhadores específicos (recursos humanos) em vez de outros tipos de recursos (como máquinas).

O sistema de agendamento atribui automaticamente cada trabalho de produção a um registro de recurso específico, e cada registro de recurso tem um tipo (como máquina ou humano). Ao configurar um funcionário como um trabalhador de produção, você pode associar a conta do trabalhador a um registro de recurso humano exclusivo.

A guia **Meus trabalhos** lista todos os trabalhos não iniciados e não concluídos que foram atribuídos ao registro de recursos humanos do trabalhador conectado, caso algum esteja conectado. Ele nunca lista trabalhos que foram atribuídos a uma máquina ou outro tipo de recurso, mesmo que o trabalhador conectado tenha começado a atuar nesses trabalhos.

Para exibir todos os trabalhos iniciados pelo trabalhador conectado, seja qual for o tipo de recurso atribuído a cada trabalho, use a guia **Trabalhos ativos**. Para exibir todos os trabalhos não concluídos que correspondam à configuração do filtro de trabalho local, independentemente do trabalhador ou do status de início, use a guia **Todos os trabalhos**.

![Guia Meus trabalhos.](media/pfei-my-jobs-tab.png "Guia Meus trabalhos")

## <a name="my-machine-tab"></a>Guia Minha máquina

A guia **Minha máquina** permite aos trabalhadores selecionar um ativo que esteja conectado a um recurso de máquina no conjunto de filtros na guia **Todos os trabalhos**. O trabalhador então pode exibir o estado e a integridade do ativo selecionado lendo valores de até quatro contadores selecionados e listas de solicitações de manutenção recentes e tempos de inatividade registrados. O trabalhador também pode solicitar manutenção para o ativo selecionado e registrar e editar o tempo de inatividade da máquina. (Este nome de guia é personalizável e pode ser diferente para o seu sistema.)

![A guia Minha máquina.](media/pfei-my-machine-tab.png "A guia Minha máquina")

A guia **Minha máquina** tem as colunas a seguir. Os números correspondem aos números da ilustração anterior.

1. **Ativo de máquina** – selecione o ativo de máquina que você deseja rastrear. Comece a digitar um nome para selecionar entre uma lista de ativos correspondentes ou selecione o ícone de lupa para selecionar entre uma lista de todos os ativos associados aos recursos que estão no filtro da lista de trabalhos.

    > [!NOTE]
    > Os usuários do Supply Chain Management podem atribuir um recurso a cada ativo conforme necessário usando a página **Todos os ativos** (na guia **Ativo fixo**, usando a lista suspensa **Recurso**). Para obter mais informações, consulte [Criar um ativo](../asset-management/objects/create-an-object.md).

1. **Configurações** – selecione o ícone de engrenagem para abrir uma caixa de diálogo na qual é possível escolher os contadores a serem exibidos para o ativo de máquina selecionado. Os valores desses contadores são mostrados na parte superior da guia **Gerenciamento de ativos**. O menu **Configurações** (mostrado na captura de tela a seguir) permite habilitar até quatro contadores. Para cada contador que você deseja habilitar, use o campo de pesquisa na parte superior do bloco para selecionar um contador. O campo de pesquisa lista todos os contadores associados ao ativo selecionado na parte superior da página **Gerenciamento de ativos**. Defina cada contador para monitorar o valor **Agregado** ou o valor **Real** mais recente do contador. Por exemplo, se você definir um contador que monitora há quantas horas a máquina está sendo executada, deverá defini-lo como **Agregado**. Se você definir um contador para medir a temperatura ou a pressão atualizada mais recente, deverá defini-lo como **Real**. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.

    ![As configurações da guia Minha máquina.](media/pfei-my-machine-tab-settings.png "As configurações da guia Minha máquina")

1. **Solicitar manutenção** – selecione este botão para abrir uma caixa de diálogo na qual é possível criar uma solicitação de manutenção. Você poderá fornecer uma descrição e uma observação. A solicitação será encaminhada para um usuário do Supply Chain Management, que poderá então converter a solicitação de manutenção em uma ordem de serviço de manutenção.
1. **Registrar tempo de inatividade** – selecione este botão para abrir uma caixa de diálogo na qual é possível registrar o tempo de inatividade da máquina. Você poderá selecionar um código de motivo e inserir um período de data/hora para o tempo de inatividade. O registro de tempo de inatividade da máquina é usado para calcular a eficiência do ativo de máquina.
1. **Exibir ou editar** – selecione este botão para abrir uma caixa de diálogo na qual é possível editar ou exibir registros de tempo de inatividade existentes.

## <a name="starting-and-completing-production-jobs"></a>Como iniciar e concluir trabalhos de produção

Os trabalhadores iniciam um trabalho de produção selecionando um trabalho na guia **Todos os trabalhos** e selecionando **Iniciar trabalho** para abrir a caixa de diálogo **Iniciar trabalho**.

![Caixa de diálogo Iniciar trabalho.](media/pfei-start-job-dialog.png "Caixa de diálogo Iniciar trabalho")

Os trabalhadores usam a caixa de diálogo **Iniciar trabalho** para confirmar a quantidade de produção e, em seguida, iniciar o trabalho. Os trabalhadores podem ajustar a quantidade selecionando o campo **Quantidade** e usando o teclado numérico que aparece. Em seguida, os trabalhadores selecionam **Iniciar** para iniciar o trabalho. A caixa de diálogo **Iniciar trabalho** é fechada e o trabalho é adicionado à guia **Trabalhos ativos**.

Os trabalhadores podem iniciar um trabalho que esteja em qualquer status. Quando um trabalhador inicia um trabalho com o status *Não iniciado*, o campo **Quantidade** na caixa de diálogo **Iniciar trabalho** inicialmente mostra a quantidade total. Quando um trabalhador inicia um trabalho com o status *Iniciado* ou *Parado*, o campo **Quantidade** mostra a quantidade restante.

## <a name="reporting-good-quantities"></a>Como relatar quantidades de mercadorias

Quando um trabalhador concluir ou concluir parcialmente um trabalho, ele poderá relatar as quantidades de mercadorias que foram produzidas selecionando um trabalho na guia **Trabalhos ativos** e selecionando **Progresso do relatório**. Em seguida, na caixa de diálogo **Progresso do relatório**, o trabalhador insere a quantidade de mercadorias usando o teclado numérico. A quantidade está em branco por padrão. Depois que uma quantidade for inserida, o trabalhador poderá atualizar o status do trabalho para *Em andamento*, *Parado* ou *Concluído*.

![Caixa de diálogo Progresso do relatório.](media/pfei-report-progress-dialog.png "Caixa de diálogo Progresso do relatório")

## <a name="reporting-good-quantities-on-batch-orders-that-have-co-products-and-by-products"></a>Relatar quantidades de mercadorias em ordens de lote que têm coprodutos e subprodutos

Os trabalhadores podem usar a interface de execução de piso de produção para relatar o progresso das ordens de lote. Isso inclui um relatório sobre coprodutos e subprodutos.

Alguns fabricantes, especialmente nas indústrias de processamento, usam ordens de lote para gerenciar seus processos de produção. As ordens de lote são criadas com base em fórmulas, e essas fórmulas podem ser definidas de modo que tenham coprodutos e subprodutos como saída. Quando comentários sobre essas ordens de lote forem relatados, o valor de saída deverá ser registrado no item de fórmula e também nos coprodutos e subprodutos.

Quando um trabalhador concluir ou concluir parcialmente um trabalho em uma ordem de lote, ele poderá relatar as quantidades de mercadorias ou sucatas de cada produto definido como saída para a ordem. Os produtos definidos como saída para uma ordem de lote podem ser do tipo *Fórmula*, *Coproduto* ou *Subproduto*.

Para relatar quantidades de mercadorias nos produtos, um trabalhador seleciona um trabalho na guia **Trabalhos ativos** e, em seguida, seleciona **Relatar progresso**.

Depois, na caixa de diálogo **Relatar progresso**, o trabalhador pode selecionar entre os produtos definidos como saída para a ordem de lote a ser relatada. Ele pode selecionar um ou vários produtos na lista e, em seguida, selecionar **Relatar progresso**. Para cada produto, a quantidade fica em branco por padrão e o trabalhador pode usar o teclado numérico para inserir a quantidade. Ele pode usar os botões **Anterior** e **Próximo** para mover-se entre os produtos selecionados. Depois que a quantidade for inserida para cada produto, o trabalhador poderá atualizar o status do trabalho para *Em andamento*, *Parado* ou *Concluído*.

![Relatar coprodutos e subprodutos.](media/report-co-by-products.png "Relatar coprodutos e subprodutos")

### <a name="reporting-on-batch-orders-for-planning-items"></a>Relatar ordens de lote para itens de planejamento

Quando um trabalhador concluir um trabalho em uma ordem de lote para um item de planejamento, ele relatará quantidades somente em coprodutos e subprodutos, pois os itens de planejamento não contêm um item do tipo *Fórmula*.

### <a name="reporting-co-product-variation"></a>Relatar variação de coprodutos

Se uma ordem de lote for criada com base em uma versão de fórmula em que a opção **Variações de coprodutos** estiver definida como *Sim*, o trabalhador poderá relatar coprodutos que não fazem parte da definição das ordens de lote. Essa funcionalidade é usada nos cenários em que uma saída de produto inesperada pode ocorrer no processo de produção.

Nesse caso, o trabalhador pode especificar o coproduto e a quantidade a ser relatada selecionando **Variações de coprodutos** na caixa de diálogo Relatar progresso. Em seguida, ele pode selecionar entre todos os produtos lançados definidos como coprodutos.

### <a name="reporting-catch-weight-items"></a>Relatar itens de peso variável

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Os trabalhadores podem usar a interface de execução de piso de produção para relatar o progresso de ordens de lote criadas para itens de peso variável. As ordens de lote são criadas com base em fórmulas, que podem ser definidas para ter itens de peso variável como itens de fórmula, coprodutos e subprodutos. Uma fórmula também pode ser definida para ter linhas de fórmula para ingredientes definidos para peso variável. Os itens de peso variável usam duas unidades de medida para rastrear o estoque: quantidade de peso variável e quantidade de estoque. Por exemplo, no setor de alimentos, a carne na caixa pode ser definida como um item de peso variável, em que a quantidade em peso variável é usada para controlar o número de caixas e a quantidade de estoque é usada para rastrear o peso das caixas.

## <a name="reporting-scrap"></a>Como relatar sucata

Quando um trabalhador concluir ou concluir parcialmente um trabalho, ele poderá relatar a sucata selecionando um trabalho na guia **Trabalhos ativos** e selecionando **Relatar sucata**. Em seguida, na caixa de diálogo **Relatar sucata**, o trabalhador insere a quantidade de sucata usando o teclado numérico. O trabalhador também seleciona um motivo (*Nenhum*, *Máquina*, *Operador* ou *Material*).

![Caixa de diálogo Relatar sucata.](media/pfei-report-scrap-dialog.png "Caixa de diálogo Relatar sucata")

## <a name="adjust-material-consumption-and-make-material-reservations"></a>Ajustar o consumo de material e fazer reservas de material

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Os trabalhadores podem ajustar o consumo de material para cada trabalho de produção. Essa funcionalidade é usada em cenários em que a quantidade real de materiais consumida por um trabalho de produção era maior ou menor do que a quantidade planejada. Portanto, ela deve ser ajustada para manter atualizados os níveis de estoque.

Os trabalhadores também podem fazer reservas nos números de série e de lote de materiais. Essa funcionalidade é usada em cenários em que um trabalhador deve especificar manualmente o lote de material ou os números de série que foram consumidos, a fim de atender aos requisitos de rastreamento de material.

Os trabalhadores podem especificar a quantidade a ser ajustada selecionando **Ajustar material**. Este botão não está disponível nos seguintes locais:

- Na caixa de diálogo **Relatório de sucata**
- Na caixa de diálogo **Progresso do relatório**
- Na barra de ferramentas à direita

### <a name="adjust-material-consumption-from-the-report-scrap-and-report-progress-dialog-boxes"></a>Ajustar consumo de material das caixas de diálogo Relatório de sucata e Progresso do relatório

Depois que um trabalhador insere a quantidade a ser reportada na caixa de diálogo **Progresso do relatório** ou **Relatório de sucata**, o botão **Ajustar material** fica disponível. Quando o usuário seleciona este botão, a caixa de diálogo **Ajustar material** é exibida. Esta caixa de diálogo lista os itens que estão planejados para serem consumidos quando a quantidade boa ou sucateada é relatada para o trabalho.

A lista na caixa de diálogo mostra as seguintes informações:

- **Número do produto** – O produto mestre e a grade de produto.
- **Nome do produto** — o nome do produto.
- **Proposta** – a quantidade estimada de material que será consumida quando o andamento ou a sucata for relatada para a quantidade especificada para o trabalho.
- **Consumo** – a quantidade real de material que será consumida quando o andamento ou a sucata for relatada para a quantidade especificada para o trabalho.
- **Reservada** – a quantidade de material que foi fisicamente reservada no estoque.
- **Unidade** – A unidade da lista de materiais (BOM).

O lado direito da caixa de diálogo mostra as seguintes informações:

- **Número do produto** – O produto mestre e a grade de produto.
- **Estimada** – A quantidade estimada para consumo.
- **Iniciada** – A quantidade que foi iniciada no trabalho de produção.
- **Quantidade restante** – Da quantidade estimada, a quantidade que resta ser consumida.
- **Quantidade liberada** – A quantidade que foi consumida.

As seguintes ações podem ser executadas:

- O trabalhador pode especificar a quantidade a ser ajustada para um material, selecionando **Ajustar consumo**. Depois que a quantidade é confirmada, a quantidade na coluna **Consumo** é atualizada com a quantidade ajustada.
- Quando o trabalhador seleciona **Ajustar material**, é criado um diário de lista de separação de produção. Esse diário contém os mesmos itens e quantidades que a lista **Ajustar material**.
- Quando o trabalhador ajusta uma quantidade na caixa de diálogo **Ajustar material**, o campo **Proposta** na linha do diário correspondente é atualizado com a mesma quantidade. Se o trabalhador selecionar **Cancelar** na caixa de diálogo **Ajustar material**, a lista de separação será excluída.
- Se o trabalhador selecionar **OK**, a lista de separação não será excluída. Ela será lançada quando o trabalho for informado na caixa de diálogo **Relatório de sucata** ou **Progresso do relatório**.
- Se o trabalhador selecionar **Cancelar** na caixa de diálogo **Progresso do relatório** ou **Relatório de sucata**, a lista de separação será excluída.

### <a name="adjust-material-from-the-primary-or-secondary-toolbar"></a>Ajustar o material da barra de ferramentas principal ou secundária

O botão **Ajustar material** pode ser configurado de forma que apareça na barra de ferramentas principal ou secundária. (Para obter mais informações, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).) Um trabalhador pode selecionar **Ajustar o material** para um trabalho de produção que está em andamento. Nesse caso, a caixa de diálogo **Ajustar material** é exibida, na qual o trabalhador pode fazer os ajustes desejados. Quando a caixa de diálogo é aberta, uma lista de separação de produção que contém linhas para as quantidades ajustadas é criada para a ordem de produção. Se o trabalhador selecionar **Lançar agora**, o ajuste será confirmado e a lista de separação será lançada. Se o trabalhador selecionar **Cancelar**, a lista de separação será excluída e nenhum ajuste será feito.

### <a name="adjust-material-consumption-for-catch-weight-items"></a>Ajustar consumo de material para itens de peso variável

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Os trabalhadores podem ajustar o consumo de material para itens de peso variável. Essa funcionalidade é usada em cenários em que a quantidade real de um material de peso variável consumida por um trabalho de produção era maior ou menor do que a quantidade planejada. Portanto, ela deve ser ajustada para manter atualizados os níveis de estoque. Quando um trabalhador ajusta o consumo de um item de peso variável, ele pode ajustar a quantidade de peso variável e a quantidade de estoque. Por exemplo, se um trabalho de produção estiver planejado para consumir cinco caixas com peso estimado de 2 quilogramas por caixa, o trabalhador poderá ajustar o número de caixas para consumo e o peso das caixas. O sistema verificará se o peso especificado das caixas está dentro dos limites mínimo e máximo definidos no produto liberado.

### <a name="reserve-materials"></a>Reservar materiais

Na caixa de diálogo **Ajustar material** um trabalhador pode fazer e ajustar as reservas de material selecionando **Reservar material**. A caixa de diálogo **Reservar material** que aparece mostra o estoque disponível fisicamente para o item para cada dimensão de armazenamento e rastreamento.

Se o material for habilitado para os processos de depósito avançados, a lista mostrará somente o estoque disponível fisicamente para o local de entrada de produção do material. A localização de entrada de produção é definida no recurso em que o trabalho de produção é planejado. Se o número do item for controlado por lote ou número de série, a lista completa de lotes e números de série disponíveis fisicamente será mostrada. Para especificar uma quantidade a ser reservada, o trabalhador pode selecionar **Reservar material**. Para remover uma reserva existente, o trabalhador pode selecionar **Remover reserva**.

Para obter mais informações sobre como configurar a localização de entrada de produção, consulte a seguinte postagem de blog: [Configurando a localização de entrada de produção](/archive/blogs/axmfg/deliver-picked-materials-to-the-locations-where-the-materials-are-consumed-by-operations-in-production).

> [!NOTE]
> As reservas feitas por um trabalhador na caixa de diálogo **Reservar material** permanecerão quando o trabalhador selecionar **Cancelar** na caixa de diálogo **Progresso do relatório** ou **Relatório de sucata**.
>
> Não é possível ajustar reservas para itens de peso variável.

## <a name="completing-a-job-and-starting-a-new-job"></a>Como concluir um trabalho e iniciar um novo

Normalmente, os funcionários concluem um trabalho selecionando um ou mais trabalhos atuais na guia **Trabalhos ativos** e então selecionando **Progresso do relatório**. Em seguida, eles inserem a quantidade produzida (a quantidade de mercadorias) e definem o status como *Concluído*. Se mais de um trabalho tiver sido selecionado, um trabalhador usará os botões **Anterior** e **Seguinte** para se mover entre eles. Para iniciar um novo trabalho, o trabalhador o seleciona na guia **Todos os trabalhos** e depois seleciona **Iniciar trabalho**.

Um trabalhador também pode iniciar um novo trabalho enquanto seu trabalho anterior ainda está aberto. Novamente, o trabalhador seleciona o novo trabalho na guia **Todos os trabalhos** e depois seleciona **Iniciar trabalho**. No entanto, nesse caso, a caixa de diálogo **Iniciar trabalho** informa ao trabalhador que ele já tem um trabalho no momento e que, portanto, ele deverá ser parado ou concluído antes que o novo trabalho seja iniciado.

## <a name="working-on-multiple-jobs-in-parallel"></a>Como ter vários trabalhos em paralelo

Um trabalhador pode ter vários trabalhos ao mesmo tempo (ou seja, em paralelo). Nesse caso, a coleção de trabalhos do trabalhador é chamada de *grupo de trabalho*. O trabalhador pode adicionar novos trabalhos ao grupo ou concluir um ou mais trabalhos no grupo. Os dois cenários a seguir mostram como um trabalhador pode ter trabalhos em paralelo.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Cenário 1: um trabalhador que não tem trabalhos ativos quer iniciar dois trabalhos e trabalhar neles em paralelo

O trabalhador seleciona os dois trabalhos na guia **Todos os trabalhos** e depois seleciona **Iniciar trabalho**. A caixa de diálogo **Iniciar trabalho** mostra os dois trabalhos selecionados e o trabalhador pode ajustar a quantidade para iniciar em cada trabalho. O trabalhador então confirma a caixa de diálogo e pode iniciar os dois trabalhos.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Cenário 2: um trabalhador com dois trabalhos ativos que estão em andamento quer iniciar um terceiro trabalho e trabalhar nele em paralelo com os outros dois

O trabalhador seleciona o terceiro trabalho na guia **Todos os trabalhos** e depois seleciona **Agrupar**. Na caixa de diálogo **Agrupar**, o trabalhador pode ajustar a quantidade para iniciar. O trabalhador então confirma a caixa de diálogo selecionando **Agrupar**.

## <a name="working-on-indirect-activities"></a>Como trabalhar em atividades indiretas

As atividades indiretas são atividades que não estão diretamente relacionadas a uma ordem de produção. As atividades indiretas podem ser definidas com flexibilidade, conforme descrito em [Configurar atividades indiretas para tempo e presença](/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Por exemplo, Shannon, uma funcionária de chão de fábrica na Contoso, deseja participar de uma reunião da empresa, e as reuniões são consideradas uma atividade indireta. Um dos dois cenários a seguir se aplica:

- **Shannon está trabalhando em um ou mais trabalhos ativos.** Shannon seleciona **Atividade**, identifica a atividade (reunião) e confirma sua seleção. Será exibida uma mensagem informando que ela tem trabalhos em andamento. Após a mensagem, Shannon poderá optar por concluir ou parar os trabalhos em que ela está trabalhando antes de ir para a reunião.
- **Shannon não tem trabalhos ativos.** Shannon seleciona **Atividade**, identifica a atividade (reunião) e confirma sua seleção. Agora, ela está registrada como estando na reunião.

Em ambos os cenários, depois de Shannon confirmar a seleção, ela vai para a página de entrada ou uma página que aguardará que ela confirme que retornou de sua atividade indireta. A página mostrada dependerá da configuração da interface de execução de piso de produção. (Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md)).

## <a name="registering-breaks"></a>Registrar interrupções

Os trabalhadores podem registrar interrupções. As interrupções podem ser definidas com flexibilidade, conforme descrito em [Pagamento com base em registros](pay-based-on-registrations.md).

Um trabalhador registra uma interrupção selecionando **Interrupção** e, em seguida, selecionando o cartão que representa o tipo de interrupção (por exemplo, almoço). Depois que o trabalhador confirma a seleção, o dispositivo mostra a página de entrada ou uma página que aguardará que o trabalhador confirme que retornou da interrupção. A página mostrada dependerá da configuração da interface de execução de piso de produção. (Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md)).

## <a name="view-the-my-day-dialog"></a>Visualizar a caixa de diálogo "Meu dia"

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

A caixa de diálogo **Meu dia** fornece aos trabalhadores uma visão geral dos registros e dos saldos. A caixa de diálogo é dividida nas três seções a seguir:

- A seção principal lista os registros feitos pelo trabalhador atual em uma data selecionada. Ela mostra os registros do dia atual e fornece um selecionador de data que permite ao trabalhador exibir outros dias.
- A seção **Último saldo diário calculado** mostra os saldos atuais do trabalhador para período pago, horas extras pagas, ausência e ausência paga. Esses valores se baseiam nos registros que foram calculados durante o processo de aprovação.
- A seção **Saldos** fornece uma visão geral dos saldos em um período definido para categorias selecionadas de registros (como férias, hora padrão e hora extra). Esses saldos se baseiam na forma como os saldos estatísticos são configurados no módulo de **Horário e presença**. Para obter mais informações sobre como definir uma configuração, consulte [Mostrar saldos de férias na interface de execução de piso de produção](production-floor-execution-payroll-stats.md).

Os administradores podem adicionar esse recurso à interface colocando o botão **Meu dia** em uma barra de ferramentas para cada guia relevante, conforme descrito em [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

## <a name="working-in-teams"></a>Trabalhar em equipes

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until 10.0.27 GA -->

Quando vários trabalhadores são designados para o mesmo trabalho de produção, eles podem formar uma equipe. A equipe pode designar um trabalhador como coordenador. Os trabalhadores restantes se tornarão automaticamente assistentes desse coordenador. Para a equipe resultante, somente o coordenador deve registrar o status do trabalho. Os registros de hora se aplicam a todos os membros da equipe.

### <a name="prerequisites"></a>Pré-requisitos

Para usar equipes, um administrador deve habilitar a ação de **Assistente** para a barra de ferramentas principal na guia **Todos os trabalhos** da interface de execução de piso de produção. Para obter instruções, consulte [Criar a interface de execução de piso de produção](production-floor-execution-tabs.md).

### <a name="form-a-new-team-that-has-a-pilot-and-an-assistant"></a>Formar uma nova equipe com um coordenador e um assistente

Um trabalhador pode se registrar como um assistente selecionando **Assistente** na guia **Todos os trabalhos**. Em seguida, na caixa de diálogo **Selecionar um funcionário para ajudar** que aparece, o trabalhador pode selecionar um coordenador em uma lista de trabalhadores que estão atuando em um trabalho. Depois que o trabalhador confirmar sua seleção, ele se tornará um assistente do trabalhador selecionado, que se tornará o coordenador da nova equipe.

### <a name="assign-a-new-pilot-to-an-existing-team"></a>Atribuir um novo coordenador a uma equipe existente

Quando uma equipe deseja selecionar um novo coordenador, o coordenador atual deve indicar a outro trabalhador na equipe como o novo coordenador. Para indicar um novo coordenador, o coordenador atual seleciona **Assistente** na guia **Todos os trabalhos** e, em seguida, na caixa de diálogo **Alterar coordenador**, ele pode selecionar um novo coordenador em uma lista de trabalhadores que já estão na equipe. Depois que o coordenador atual confirmar sua seleção, ele será removido completamente da equipe. No entanto, ele pode reingressar conforme necessário.

### <a name="assistant-clocks-out"></a>Saída do assistente

Quando um trabalhador que atua como assistente faz o registro de saída, ele deixa a equipe. Se as opções **Equipes permanentes** e **Reiniciar registro de entrada** estiverem definidas como *Sim*, um trabalhador que faz o registro de saída reingressará automaticamente na equipe na próxima vez em que fizer o registro de entrada. Essas opções podem ser encontradas na guia **Geral** da página **Parâmetros de horário e presença**.

## <a name="opening-instructions"></a>Instruções de abertura

Os funcionários podem abrir um documento anexado a um trabalho selecionando **Instruções**. O botão **Instruções** só estará disponível se um documento estiver associado ao trabalho nos dados mestres. Por exemplo, um documento anexado a um produto na página **Produtos liberados** no Supply Chain Management estará disponível para os trabalhadores abrirem na interface de execução de chão de fábrica.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Como abrir guias de realidade misturada para HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) podem ajudar a capacitar os trabalhadores, oferecendo um aprendizado prático que usa realidade misturada. Você pode definir processos padronizados onde instruções passo a passo orientam os trabalhadores para as ferramentas e peças necessárias e mostram como usar essas ferramentas em situações reais de trabalho. Aqui está uma visão geral do processo.

1. Sempre que um trabalhador abrir uma lista de trabalhos na interface de execução de chão de fábrica, a interface encontrará todos os guias relevantes para os trabalhos mostrados.
1. O trabalhador seleciona **Guias** para exibir a lista de guias.
1. O trabalhador seleciona um guia relevante na lista.
1. A interface de execução de chão de fábrica mostra um código QR para o guia selecionado.
1. O trabalhador coloca um HoloLens e olha para o código QR para iniciar o guia.
1. O trabalhador trabalha no guia para aprender a tarefa.

Para obter mais informações sobre como criar, atribuir e usar guias para HoloLens, consulte [Fornecer Guias de realidade misturada para trabalhadores em produção](instruction-guides-in-production-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
