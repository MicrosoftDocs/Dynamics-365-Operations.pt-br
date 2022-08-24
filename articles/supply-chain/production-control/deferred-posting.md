---
title: Disponibilizar fisicamente as mercadorias acabadas antes de lançá-las em diários
description: Quando um item fabricado é informado como acabado, ele é registrado como disponível para processamento físico adicional, e um ou mais diários são lançados. Este artigo descreve como adiar os lançamentos do diário, permitindo que eles sejam processados por um trabalho em lotes em uma fila de mensagens.
author: johanhoffmann
ms.date: 08/02/2022
ms.topic: article
ms.search.form: ProdParameters, JmgProdParameters, InventLocation, JmgMES3PMessageProcessorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-08-02
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 7a8327552d9e6c38721fdac9ee1795e61f90f329
ms.sourcegitcommit: 8d072505f66f507aafbaae65bedf3b530eb6cb7b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9266476"
---
# <a name="make-finished-goods-physically-available-before-posting-to-journals"></a>Disponibilizar fisicamente as mercadorias acabadas antes de lançá-las em diários

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Quando um trabalhador relata um item fabricado como acabado, o sistema o registra como disponível para processamento físico adicional (como remessa ou armazenamento). Durante esse processo, um ou mais diários também são lançados (como o relatório como o diário concluído, o diário de listas de separação e o diário de cartão de roteiro). Se desejar disponibilizar os itens fisicamente antes que todos os lançamentos tenham sido processados, será possível configurar o sistema para adiar os lançamentos de diário. Os lançamentos diferidos são gerenciados por um trabalho em lotes que processará os lançamentos à medida que os recursos do sistema permitirem.

A ilustração a seguir mostra como os processos de lançamento de diários são invocados com e sem o lançamento adiado.

![O processo de relatório de conclusão com e sem lançamento de diário adiado.](media/deferred-posting-flowchart.png "O processo de relatório de conclusão com e sem lançamento de diário adiado")

## <a name="turn-on-deferred-journal-posting-for-your-system"></a>Ativar lançamento de diário diferido para o seu sistema

Para que você possa usar o lançamento de diário adiado, ele deve estar ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Controle de produção*
- **Nome do recurso:** *(Versão preliminar) Disponibilizar fisicamente as mercadorias concluídas antes de lançá-las em diários*

## <a name="set-up-journal-posting-options-for-reporting-as-finished"></a>Configurar opções de lançamento em diário para relatar como concluído

Os trabalhadores podem relatar itens como concluídos usando um dos seguintes clientes:

- Cliente web
- Aplicativo móvel Warehouse Management
- Interface de execução de piso de produção

O cliente Web usa a mesma configuração de método de lançamento que o aplicativo móvel Warehouse Management. No entanto, o método de lançamento que a interface de execução de piso de produção usa deve ser configurado separadamente.

### <a name="set-journal-posting-options-for-the-web-client-and-the-warehouse-management-mobile-app"></a>Definir opções de lançamento do diário para o cliente Web e o aplicativo móvel Warehouse Management

No aplicativo móvel, os trabalhadores relatam itens como concluídos, abrindo um item de menu de dispositivo móvel no qual o valor do **Processo de criação de trabalho** é *Relatar como concluído* ou *Relatar como concluído e armazenado*. No cliente Web, os trabalhadores relatam itens como concluídos na página de lista **Todas as ordens de produção** ou na página **Ordem de produção (detalhes)**. Você pode configurar um método padrão para toda a empresa e também configurar substituições específicas de depósito conforme necessário.

Use o procedimento a seguir para configurar o método de lançamento padrão para toda a empresa para relatar itens como concluídos no cliente Web ou no aplicativo móvel Warehouse Management.

1. Acesse **Controle de produção \> Configuração \> Parâmetros de controle de produção**.
1. Na guia **Diários**, na seção **Relatar como diário concluído**, defina o campo **Método de lançamento** como um dos seguintes valores:

    - *Imediato* – quando um item é informado como concluído, o sistema processa totalmente todos os lançamentos de diário relacionados antes de marcar o item concluído como fisicamente disponível.
    - *Adiado* – quando um item é relatado como concluído, o sistema marca o item concluído como fisicamente disponível e adiciona os lançamentos de diário a uma fila de mensagens. O sistema não espera até que os lançamentos sejam totalmente processados antes de marcar o item concluído como fisicamente disponível.

Use o procedimento a seguir para configurar substituições específicas do depósito para o método de lançamento padrão configurado na página **Parâmetros de controle da produção**.

1. Acesse **Gerenciamento de depósito \> Configuração \> Divisão do estoque \> Depósitos**.
1. Selecione o depósito que você desejar configurar.
1. No Painel de Ações, selecione **Editar**.
1. Na FastTab **Depósito**, na seção **Ordens de produção**, defina o campo **Método de lançamento** como um dos seguintes valores:

    - *Herança* – o depósito selecionado herda a configuração da página **Parâmetros do controle de produção**.
    - *Imediato* – quando um item é informado como concluído, o sistema processa totalmente todos os lançamentos de diário relacionados antes de marcar o item concluído como fisicamente disponível.
    - *Adiado* – quando um item é relatado como concluído, o sistema marca o item concluído como fisicamente disponível e adiciona os lançamentos de diário a uma fila de mensagens. O sistema não espera até que os lançamentos sejam totalmente processados antes de marcar o item concluído como fisicamente disponível.

### <a name="set-journal-posting-options-for-the-production-floor-execution-interface"></a>Defina opções de lançamento do diário para a interface de execução de piso de produção

Use o procedimento a seguir para configurar o método de lançamento usado quando os itens são relatados como concluídos na interface de execução de produção.

1. Acesse **Controle de produção \> Configuração \> Execução de fabricação \> Padrões de ordem de produção**.
1. Na guia **Relatar como concluído**, na seção **Relatar como diário concluído**, defina o campo **Método de lançamento** como um dos seguintes valores:

    - *Imediato* – quando um item é informado como concluído, o sistema processa totalmente todos os lançamentos de diário relacionados antes de marcar o item concluído como fisicamente disponível.
    - *Adiado* – quando um item é relatado como concluído, o sistema marca o item concluído como fisicamente disponível e adiciona os lançamentos de diário a uma fila de mensagens. O sistema não espera até que os lançamentos sejam totalmente processados antes de marcar o item concluído como fisicamente disponível.

## <a name="schedule-the-message-processor-batch-job-to-process-deferred-postings"></a>Agendar o trabalho em lotes do processador de mensagens para processar lançamentos adiados

O trabalho em lotes do processador de mensagens é responsável por processar os lançamentos do diário depois que eles forem enfileirados. Para garantir que os lançamentos de diário sejam processados, você deve configurar este trabalho para ser executado em um intervalo regular. Use o seguinte procedimento para configurar o trabalho em lote necessário.

1. Acesse **Administração do sistema \> Processador de mensagem \> Processador de mensagem**.
1. Na FastTab **Parâmetros**, defina o campo **Fila de mensagens** como *Produção*.
1. Na FastTab **Executar em segundo plano**, defina a opção **Processamento em lotes** como *Sim*. Configure um agendamento recorrente e defina outras configurações conforme necessário. As configurações funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Microsoft Dynamics 365 Supply Chain Management.

## <a name="track-the-progress-of-your-deferred-postings"></a>Rastrear o progresso de lançamentos adiados

Os lançamentos do diário adiados são enfileirados como *mensagens do processador de mensagens* que aguardam até serem processados pelo *processador de mensagens*. O processador de mensagens deve ser configurado para ser executado como um trabalho em lotes agendado. Para exibir as mensagens de lançamento adiadas que foram ou serão processadas pelo processador de mensagens, vá para **Controle de produção \> Ordens de produção \> Lançamento da ordem de produção adiada**.

### <a name="message-grid-columns-and-filters"></a>Colunas e filtros da grade de mensagens

Você pode usar os campos na parte superior da página **Lançamento da ordem de produção adiada** para ajudar a encontrar mensagens específicas que você está procurando.

Os filtros a seguir estão disponíveis:

- **Tipo de mensagem**: especifique o tipo de mensagem mostrado na grade.
- **Estado da mensagem**: especifique o estado das mensagens mostrado na grade. Existem os seguintes estados:

    - *Enfileirado* – a mensagem está pronta para ser processada pelo processador de mensagens.
    - *Processado* – a mensagem foi processada com sucesso pelo processador de mensagens.
    - *Cancelado*: a mensagem falhou ao ser processada durante a tentativa final e foi cancelada pelo usuário.
    - *Falha*: não foi possível processar a mensagem na última tentativa. O sistema repetirá três vezes as mensagens com falhas. Depois, ele desistirá e deixará a mensagem no estado de *Falha*. Lembre-se de que não é possível cancelar ou editar manualmente uma mensagem após a última dessas três tentativas.

- **Conteúdo da mensagem** – este filtro faz uma pesquisa de texto completo do conteúdo da mensagem. (O conteúdo da mensagem não é mostrado na grade). O filtro trata a maioria dos símbolos especiais (como hífens) como caracteres de espaço e trata todos os caracteres de espaço como operadores boolianos OR. Por exemplo, se você pesquisar um valor `journalid` específico equivalente a *USMF-123456*, o sistema localizará todas as mensagens contendo "USMF" ou "123456". Nesse caso, a lista de resultados provavelmente será longa. Portanto, seria melhor inserir apenas *123456*, pois você obterá resultados mais específicos.

Também é possível classificar e filtrar a lista, selecionando um dos cabeçalhos de coluna e inserindo critérios na caixa de diálogo suspensa.

### <a name="view-the-message-log-message-content-and-details"></a>Exibir o log de mensagens, o conteúdo da mensagem e os detalhes

Você pode encontrar informações detalhadas sobre uma mensagem, selecionando-a na grade e, depois, selecionando a guia **Log** ou **Conteúdo bruto** na grade da mensagem, na qual cada evento de processamento é mostrado.

A barra de ferramentas na guia **Log** tem os seguintes botões:

- **Log**: selecione este botão para mostrar os resultados do processamento. Este botão é especialmente útil quando as mensagens têm um **Resultado de processamento** com valor *Com Falha* e você deseja conhecer as razões da falha do processamento.
- **Pacote** – as operações de processamento de várias mensagens podem ser executadas como parte do mesmo processo em lote. Selecione este botão para exibir os dados detalhados. Por exemplo, você pode ver se existem dependências que exigem uma ordem de processamento específica para algumas mensagens.

### <a name="manually-process-or-cancel-a-message"></a>Processar ou cancelar manualmente uma mensagem

Você pode processar ou cancelar manualmente uma mensagem como desejar, dependendo do seu estado atual. Selecione a mensagem na grade e, depois, selecione **Processar** ou **Cancelar** no Painel de Ações.

### <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Configurar eventos de negócios para enviar alertas para resultados de processamento com falha

Você pode configurar [eventos de negócios](../../fin-ops-core/dev-itpro/business-events/home-page.md) que o alertam sobre resultados de processamento com falha. Vá para **Administração do sistema \> Configuração \> Eventos de negócios \> Catálogo de eventos de negócios** e ative o evento de negócios chamado *Mensagem do processador de mensagens processada*.

Como parte do processo de ativação, você será solicitado a especificar se o evento é específico de uma entidade legal ou se ele aplica-se a todas as entidades legais. Você também é solicitado a fornecer um valor de **Nome de ponto de extremidade**. Primeiro, é preciso definir este valor.

> [!NOTE]
> Se o campo **Quando um evento de negócios ocorre** for definido como *Microsoft Power Automate* (em vez de *HTTPS*, por exemplo), o valor de **Nome do ponto de extremidade** será criado automaticamente no Supply Chain Management, com base na configuração do *Microsoft Power Automate*.
