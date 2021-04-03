---
title: Como os trabalhadores usam a interface de execução de piso de produção
description: Este tópico descreve como usar a interface de execução de piso de produção do ponto de vista de um trabalhador.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProductionFloorExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 38bc07d37b5c51f143846110c87cff9952d52b0e
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500781"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Como os trabalhadores usam a interface de execução de piso de produção

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A interface de execução de piso de produção é otimizada para interação por toque. Seu design oferece um contraste visual que atende aos requisitos de acessibilidade para ambientes de chão de fábrica. Ele oferece todos os mesmos recursos funcionais do que o dispositivo de ficha de trabalho. No entanto, ele também permite que vários trabalhos sejam iniciados em paralelo de uma lista de trabalhos. (Esse recurso também é conhecido como *agrupamento de trabalhos*). Além disso, de uma lista de trabalhos, os funcionários podem abrir um guia criado no Guia do Microsoft Dynamics 365. Dessa forma, eles podem obter instruções visuais em um HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Entrar na interface de execução de piso de produção como um trabalhador

Antes que os funcionários possam começar a usar o dispositivo, um supervisor ou uma equipe técnica deverá prepará-lo e abrir a página correta no Dynamics 365 Supply Chain Management. Para obter mais informações sobre como configurar o dispositivo, consulte [Configurar um dispositivo para executar a interface de execução de piso de produção](production-floor-execution-setup.md).

Depois que o dispositivo tiver sido preparado, a página de entrada aparecerá nele. Essa página mostra informações sobre o status de trabalhos da célula de trabalho local. Essas informações são atualizadas periodicamente. Na página, os trabalhadores usam suas IDs de crachá para assinar. Embora os funcionários não precisem ter uma conta de usuário para o Supply Chain Management, eles devem ter uma conta de *trabalhador com tempo registrado* que possam usar para entrar.

![Página de entrada de interface de execução de piso de produção](media/pfei-sign-in-page.png "Página de entrada de interface de execução de piso de produção")

As seções restantes deste tópico descrevem como os funcionários interagem com a interface.

## <a name="all-jobs-tab"></a>Guia Todos os trabalhos

A guia **Todos os trabalhos** fornece uma lista de trabalhos que mostra todos os trabalhos de produção com o status *Não iniciado*, *Parado* ou *Iniciado*. (Este nome de guia é personalizável e pode ser diferente para o seu sistema.)

![Guia Todos os trabalhos](media/pfei-all-jobs-tab.png "Guia Todos os trabalhos")

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

![Guia Trabalhos ativos](media/pfei-active-jobs-tab.png "Guia Trabalhos ativos")

A lista de trabalhos ativos tem as colunas a seguir:

- **Coluna de seleção** – a coluna mais à esquerda usa marcas de seleção para indicar os trabalhos selecionados pelo trabalhador. Os trabalhadores podem selecionar vários trabalhos na lista ao mesmo tempo. Para selecionar todos os trabalhos na lista, marque a caixa de seleção no cabeçalho da coluna. Quando um único trabalho é selecionado, os detalhes desse trabalho são mostrados na parte inferior da página.
- **Ordem** – essa coluna mostra o número da ordem de produção para um trabalho.
- **Descrição** – essa coluna mostra uma descrição da operação da qual um trabalho faz parte.
- **Solicitado** – essa coluna mostra a quantidade que um trabalho está planejado para produzir.
- **Iniciado** – essa coluna mostra a quantidade que já foi iniciada para um trabalho.
- **Concluído** – essa coluna mostra a quantidade que já foi concluída para um trabalho.
- **Sucateado** – essa coluna mostra a quantidade que já foi sucateada para um trabalho.
- **Restante** – essa coluna mostra a quantidade que resta para ser concluída para um trabalho.

## <a name="my-machine-tab"></a>Guia Minha máquina

A guia **Minha máquina** permite aos trabalhadores selecionar um ativo que esteja conectado a um recurso de máquina no conjunto de filtros na guia **Todos os trabalhos**. O trabalhador então pode exibir o estado e a integridade do ativo selecionado lendo valores de até quatro contadores selecionados e listas de solicitações de manutenção recentes e tempos de inatividade registrados. O trabalhador também pode solicitar manutenção para o ativo selecionado e registrar e editar o tempo de inatividade da máquina. (Este nome de guia é personalizável e pode ser diferente para o seu sistema.)
 
![A guia Minha máquina](media/pfei-my-machine-tab.png "A guia Minha máquina")

A guia **Minha máquina** tem as colunas a seguir. Os números correspondem aos números da ilustração anterior.

1. **Ativo de máquina** – selecione o ativo de máquina que você deseja rastrear. Comece a digitar um nome para selecionar entre uma lista de ativos correspondentes ou selecione o ícone de lupa para selecionar entre uma lista de todos os ativos associados aos recursos que estão no filtro da lista de trabalhos.

    > [!NOTE]
    > Os usuários do Supply Chain Management podem atribuir um recurso a cada ativo conforme necessário usando a página **Todos os ativos** (na guia **Ativo fixo**, usando a lista suspensa **Recurso**). Para obter mais informações, consulte [Criar um ativo](../asset-management/objects/create-an-object.md).

1. **Configurações** – selecione o ícone de engrenagem para abrir uma caixa de diálogo na qual é possível escolher os contadores a serem exibidos para o ativo de máquina selecionado. Os valores desses contadores são mostrados na parte superior da guia **Gerenciamento de ativos**. O menu **Configurações** (mostrado na captura de tela a seguir) permite habilitar até quatro contadores. Para cada contador que você deseja habilitar, use o campo de pesquisa na parte superior do bloco para selecionar um contador. O campo de pesquisa lista todos os contadores associados ao ativo selecionado na parte superior da página **Gerenciamento de ativos**. Defina cada contador para monitorar o valor **Agregado** ou o valor **Real** mais recente do contador. Por exemplo, se você definir um contador que monitora há quantas horas a máquina está sendo executada, deverá defini-lo como **Agregado**. Se você definir um contador para medir a temperatura ou a pressão atualizada mais recente, deverá defini-lo como **Real**. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.

    ![A guia Minha máquina](media/pfei-my-machine-tab-settings.png "A guia Minha máquina")

1. **Solicitar manutenção** – selecione este botão para abrir uma caixa de diálogo na qual é possível criar uma solicitação de manutenção. Você poderá fornecer uma descrição e uma observação. A solicitação será encaminhada para um usuário do Supply Chain Management, que poderá então converter a solicitação de manutenção em uma ordem de serviço de manutenção.
1. **Registrar tempo de inatividade** – selecione este botão para abrir uma caixa de diálogo na qual é possível registrar o tempo de inatividade da máquina. Você poderá selecionar um código de motivo e inserir um período de data/hora para o tempo de inatividade. O registro de tempo de inatividade da máquina é usado para calcular a eficiência do ativo de máquina.
1. **Exibir ou editar** – selecione este botão para abrir uma caixa de diálogo na qual é possível editar ou exibir registros de tempo de inatividade existentes.


## <a name="starting-and-completing-production-jobs"></a>Como iniciar e concluir trabalhos de produção

Os trabalhadores iniciam um trabalho de produção selecionando um trabalho na guia **Todos os trabalhos** e selecionando **Iniciar trabalho** para abrir a caixa de diálogo **Iniciar trabalho**.

![Caixa de diálogo Iniciar trabalho](media/pfei-start-job-dialog.png "Caixa de diálogo Iniciar trabalho")

Os trabalhadores usam a caixa de diálogo **Iniciar trabalho** para confirmar a quantidade de produção e, em seguida, iniciar o trabalho. Os trabalhadores podem ajustar a quantidade selecionando o campo **Quantidade** e usando o teclado numérico que aparece. Em seguida, os trabalhadores selecionam **Iniciar** para iniciar o trabalho. A caixa de diálogo **Iniciar trabalho** é fechada e o trabalho é adicionado à guia **Trabalhos ativos**.

Os trabalhadores podem iniciar um trabalho que esteja em qualquer status. Quando um trabalhador inicia um trabalho com o status *Não iniciado*, o campo **Quantidade** na caixa de diálogo **Iniciar trabalho** inicialmente mostra a quantidade total. Quando um trabalhador inicia um trabalho com o status *Iniciado* ou *Parado*, o campo **Quantidade** mostra a quantidade restante.

## <a name="reporting-good-quantities"></a>Como relatar quantidades de mercadorias

Quando um trabalhador concluir ou concluir parcialmente um trabalho, ele poderá relatar as quantidades de mercadorias que foram produzidas selecionando um trabalho na guia **Trabalhos ativos** e selecionando **Progresso do relatório**. Em seguida, na caixa de diálogo **Progresso do relatório**, o trabalhador insere a quantidade de mercadorias usando o teclado numérico. A quantidade está em branco por padrão. Depois que uma quantidade for inserida, o trabalhador poderá atualizar o status do trabalho para *Em andamento*, *Parado* ou *Concluído*.

![Caixa de diálogo Progresso do relatório](media/pfei-report-progress-dialog.png "Caixa de diálogo Progresso do relatório")

## <a name="reporting-scrap"></a>Como relatar sucata

Quando um trabalhador concluir ou concluir parcialmente um trabalho, ele poderá relatar a sucata selecionando um trabalho na guia **Trabalhos ativos** e selecionando **Relatar sucata**. Em seguida, na caixa de diálogo **Relatar sucata**, o trabalhador insere a quantidade de sucata usando o teclado numérico. O trabalhador também seleciona um motivo (*Nenhum*, *Máquina*, *Operador* ou *Material*).

![Caixa de diálogo Relatar sucata](media/pfei-report-scrap-dialog.png "Caixa de diálogo Relatar sucata")

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

As atividades indiretas são atividades que não estão diretamente relacionadas a uma ordem de produção. As atividades indiretas podem ser definidas com flexibilidade, conforme descrito em [Configurar atividades indiretas para tempo e presença](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Por exemplo, Shannon, uma funcionária de chão de fábrica na Contoso, deseja participar de uma reunião da empresa, e as reuniões são consideradas uma atividade indireta. Um dos dois cenários a seguir se aplica:

- **Shannon está trabalhando em um ou mais trabalhos ativos.** Shannon seleciona **Atividade**, identifica a atividade (reunião) e confirma sua seleção. Será exibida uma mensagem informando que ela tem trabalhos em andamento. Após a mensagem, Shannon poderá optar por concluir ou parar os trabalhos em que ela está trabalhando antes de ir para a reunião.
- **Shannon não tem trabalhos ativos.** Shannon seleciona **Atividade**, identifica a atividade (reunião) e confirma sua seleção. Agora, ela está registrada como estando na reunião.

Em ambos os cenários, depois de Shannon confirmar a seleção, ela vai para a página de entrada ou uma página que aguardará que ela confirme que retornou de sua atividade indireta. A página mostrada dependerá da configuração da interface de execução de piso de produção. (Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md)).

## <a name="registering-breaks"></a>Registrar interrupções

Os trabalhadores podem registrar interrupções. As interrupções podem ser definidas com flexibilidade, conforme descrito em [Pagamento com base em registros](pay-based-on-registrations.md).

Um trabalhador registra uma interrupção selecionando **Interrupção** e, em seguida, selecionando o cartão que representa o tipo de interrupção (por exemplo, almoço). Depois que o trabalhador confirma a seleção, o dispositivo mostra a página de entrada ou uma página que aguardará que o trabalhador confirme que retornou da interrupção. A página mostrada dependerá da configuração da interface de execução de piso de produção. (Para obter mais informações, consulte [Configurar a interface de execução de piso de produção](production-floor-execution-configure.md)).

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