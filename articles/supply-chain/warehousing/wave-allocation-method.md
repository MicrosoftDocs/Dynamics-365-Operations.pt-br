---
title: Alocação de ciclo
description: Este tópico descreve como configurar a etapa de alocação de ciclo, incluindo como habilitar o processamento paralelo para ela.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527bd24d7f2e9a05f6e617c222005186520f9968
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103779"
---
# <a name="wave-allocation"></a>Alocação de ciclo

[!include [banner](../includes/banner.md)]

O processamento do ciclo pode ser demorado e a maior parte do tempo de processamento é gasta na etapa de alocação e na etapa de criação de trabalho.

Agora é possível executar cada uma dessas etapas em paralelo, o que pode melhorar o desempenho do processamento do ciclo e permitir uma taxa de transferência maior de ciclos no mesmo depósito. Este tópico explica como configurar o método de alocação de ciclo para ser executado em paralelo. Para obter mais informações sobre como configurar a criação de trabalho para execução em paralelo, consulte [Agendar a criação de trabalho durante o ciclo](configure-wave-schedule-work-creation.md).

Anteriormente, era possível alocar apenas um ciclo em um depósito por vez. Essa restrição foi removida e substituída por uma nova restrição que só bloqueia o item e as dimensões acima da localização na hierarquia de reserva. As dimensões acima do local sempre incluem as dimensões do produto. Por exemplo, se um item for configurado usando *Cor*, as variantes para *Vermelho*, *Azul* e *Amarelo* poderiam ser processadas em paralelo.

Isso significa que, se o mesmo item com as mesmas dimensões acima da localização estiver sendo alocado por um ciclo, outros ciclos terão de esperar para adquirir um bloqueio no mesmo item e dimensões. Se o bloqueio não puder ser adquirido no momento oportuno, ocorrerá um erro e o processamento do ciclo falhará.

Para usar o processamento paralelo, o ciclo deverá ser executado em lotes.

## <a name="performance-improvements"></a>Aprimoramentos de desempenho

Os benefícios de desempenho do processamento paralelo recaem em duas categorias:

- **Taxa de transferência melhorada** – a taxa de transferência de ciclos geralmente aumenta, mesmo que o processamento paralelo não seja configurado, especialmente para cenários em que não há sobreposição de itens dentro dos ciclos.
- **Melhoria da alocação para um único ciclo** – testes em dados de clientes mostraram uma melhoria de desempenho de quase 50% depois da alternância para a alocação paralela. O processamento paralelo é feito por itens e dimensões acima da localização e, portanto, os aprimoramentos dependem de quantos itens diferentes um ciclo contém, a infraestrutura disponível e a duração da alocação versus a duração da criação do trabalho.

## <a name="configure-parallel-allocation"></a>Configurar a alocação paralela

### <a name="warehouse-management-parameters"></a>Parâmetros de gerenciamento de depósito

Para usar o processamento de alocação paralela, Acesse **Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito**, abra a guia **Processamento do ciclo** e faça as seguintes configurações:

- **Grupo de lotes de processamento do ciclo** – selecione o grupo de lotes que o processamento inicial do ciclo deve usar. O processamento subsequente da alocação pode ser feito usando diferentes grupos de lotes.
- **Processar ciclos em lotes** – defina isso como *Sim* para usar o processamento paralelo.
- **Aguardar bloqueio (ms)** – insira o tempo, em milissegundos, que uma etapa de alocação aguardará um recurso do sistema que está bloqueado por outra etapa de alocação. Quando esse tempo é excedido, a onda não é processada e uma mensagem de erro é exibida. Recomendamos que você aguarde pelo menos alguns segundos para permitir a alocação de uma unidade lógica seja concluída.

Para obter informações sobre essas e outras opções de processamento do ciclo na página **Parâmetros de gerenciamento de depósito**, consulte [Parâmetros de depósito para processamento do ciclo](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Métodos de processo de onda

Para configurar o processamento paralelo:

1. Acesse **Gerenciamento de depósito > Configuração > Ciclos > Métodos de processo do ciclo**.
1. Selecione o método `allocateWave` na grade.
1. No Painel de Ações, selecione **Configuração da tarefa**.
1. A página **Configuração da tarefa do método de lançamento de ciclos** é aberta. Essa grade lista cada depósito no qual você configurou o método `allocateWave`. O processamento paralelo só será usado para os depósitos listados. Use os botões do Painel de Ação para adicionar ou remover depósitos da grade, conforme necessário. 
1. Para cada depósito, faça as seguintes configurações:
    - **Número máximo de tarefas em lotes** – especifique o número de tarefas em lotes que devem ser usadas para a alocação do depósito selecionado. O número ideal de tarefas em lotes depende da infraestrutura disponível e de outros trabalhos em lotes que estão sendo processados no servidor. Os testes realizados em quatro ambientes principais dedicados ao processamento do ciclo demonstraram que o uso de oito tarefas produziu bons resultados.
    - **Grupos de lotes de processamento do ciclo** – grupos de lotes específicos podem ser usados para depósitos diferentes a fim de permitir que o processamento de alocação seja expandido por depósito.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Habilitar ou desabilitar a paralelização em todas as entidades legais

Recomendamos que você defina o método `allocateWave` a ser executado em paralelo em todas as entidades legais porque isso ajuda a melhorar o desempenho do processamento do ciclo. A partir do Supply Chain Management versão 10.0.17, o recurso *Paralelização de ciclo para o método Alocar Ciclo* é ativado por padrão para todas as instalações novas e atualizadas e não poderá ser desativado novamente. Depois que esse recurso for habilitado, ocorrerá o seguinte:

- O método `allocateWave` é atualizado para incluir uma configuração de tarefa que permite usar a página **Métodos do processo do ciclo** para definir o número de tarefas que serão executadas simultaneamente, equivalente ao número de processos paralelos. Como resultado, o tempo usado na etapa de ciclo de alocação (que, em geral, é de 30% a 60% do tempo de processamento total) é reduzido por um fator equivalente ao número de tarefas. Também é possível selecionar qual lote será atribuído para processar essas tarefas. É importante observar que todas as entidades legais serão configuradas para processar ciclos em lotes. Para os depósitos que já foram configurados para processar ciclos em lotes, e para os depósitos que já foram configurados para usar o método `allocateWave` em paralelo, a configuração existente será mantida.
- Por padrão, todas as novas entidades legais são configuradas para processar ciclos em lotes. Todos os novos depósitos com a opção **Processos de gerenciamento de depósito** habilitada terão o método `allocateWave` configurado para ser executado em paralelo por padrão.
- Na página **Parâmetros de gerenciamento de depósito**, **Salvamentos de processo em lotes** está definido como *Sim* e **Aguardar bloqueio (ms)** definido para um padrão de 15 segundos. Isso significa que todos os ciclos serão executados em lotes. Quando um ciclo está em execução, ele adquire um bloqueio no item e nas dimensões acima do local durante a etapa de alocação. Quando outra tarefa de processamento de ciclo tenta adquirir o mesmo bloqueio para o registro idêntico, ela é bloqueado. As configurações de **Aguardar bloqueio (ms)** estabelecem o tempo máximo que o sistema aguardará antes que o bloqueio seja liberado.

O processamento de alocação paralela exige que o processamento do ciclo seja executado em lotes. Portanto, você reduzirá o desempenho do processamento do ciclo se desativar a configuração **Salvamentos de processos em lotes**, especialmente se o processamento do ciclo estiver usando um processo paralelo, conforme definido pela configuração da tarefa para os métodos de ciclo relevantes.

Se necessário, você poderá desfazer cada uma das configurações feitas por padrão quando o recurso *Paralelização do ciclo para o método Alocar Ciclo* estiver habilitado automaticamente para sua instância. Para fazer isto:

- Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**. Na guia **Processamento do ciclo**, aplique os valores preferidos para **Processar ciclos em lotes** e **Aguardar bloqueio (ms)**.
- Acesse **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**. Selecione o método `allocateWave`. No Painel de Ações, selecione **Configuração da tarefa** para abrir uma página que liste cada depósito no qual o método está definido para ser executado em paralelo. Modifique ou exclua o número de tarefas em lotes e o grupo de ciclos atribuído a cada depósito listado, conforme necessário.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="troubleshoot-using-the-infolog"></a>Solucionar problemas usando o log de informações

Como a estrutura de lotes é usada, os erros que ocorrem durante o processamento do ciclo serão capturados como parte dos logs de informações de trabalhos em lotes. Para ler os trabalhos em lotes relacionados a um ciclo:

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione o ciclo que deseja inspecionar.
1. No Painel de Ações, abra a guia **Ciclo** e, no grupo **Ciclo**, selecione **Trabalhos em lotes**.

O processamento do ciclo é de correção automática e, portanto, qualquer erro detectado durante o processamento deverá ser informado usando o log de informações.

Um erro típico relacionado ao processamento paralelo poderia ser dois ciclos tentando alocar o mesmo item ao mesmo tempo e um não é concluído, de tal modo que o outro ciclo não pode adquirir um bloqueio no tempo especificado. Se essa situação ocorrer, o log de trabalhos em lotes conterá informações de que o bloqueio do item não pôde ser adquirido e, nesse caso, o ciclo que falhou deverá ser processado novamente.

Como o processamento está acontecendo em paralelo, os dados devem ser mantidos em tabelas diferentes para rastrear o estado do processamento. Isso significa que os logs para os trabalhos em lotes podem conter erros, como erros de chave duplicados.

Os erros das tarefas em lotes também fazem parte do log de trabalhos em lotes. As informações mais importantes normalmente estão na parte inferior.

Em casos raros, por exemplo, se a conexão SQL tiver sido encerrada, é possível que o processamento do ciclo termine em um estado inconsistente no qual o trabalho em lotes parece estar em execução, mas o processamento é interrompido. O ciclo não pode manipular erros como esse e, portanto, ocorrerá uma tentativa de limpar os ciclos que falharam quando o próximo ciclo for executado. Como alternativa, se o ciclo atual estiver em um estado inconsistente, execute as seguintes etapas:

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione o ciclo que precisa ser limpo.
1. No Painel de Ações, abra a guia **Ciclo** e, no grupo **Ciclo**, selecione **Limpar dados do ciclo**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Solucionar problemas usando o log de progresso do ciclo

Se a opção **Criar log de progresso do ciclo** estiver habilitada na página **Parâmetros de gerenciamento de depósito**, um registro de log será criado sempre que a alocação de um item e suas dimensões começar e terminar. Você só deverá habilitar esse log quando precisar dele, por exemplo, durante o teste inicial ou para solução de problemas. Quando esta opção estiver habilitada, você poderá exibir o log executando as seguintes etapas:

1. Acesse **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.
1. Selecione o ciclo que deseja inspecionar.
1. No Painel de Ação, abra a guia **Ciclo** e, no grupo **Ciclo**, selecione **Progresso**.
