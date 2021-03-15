---
title: Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda
description: Este tópico fornece informações sobre o recurso que permite que as unidades de escala executem processos selecionados da carga de trabalho de gerenciamento de depósito.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 91e614889c719ae700b13e54150e5025d64e2b97
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104931"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e borda

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nem todas as funcionalidades de negócios do gerenciamento de depósito têm suporte total para depósitos que executam uma carga de trabalho em uma unidade de escala. Certifique-se de usar somente os processos descritos explicitamente por este tópico como aceitos.

## <a name="warehouse-execution-on-scale-units"></a>Execução de depósito em unidades de escala

Este recurso permite que as unidades de escala executem processos selecionados dos recursos de gerenciamento de depósito. As unidades de escala de nuvem executam cargas de trabalho na nuvem usando a capacidade de processamento dedicada na região selecionada do Microsoft Azure. Para unidades de escala de borda, você pode executar algumas cargas de trabalho de forma independente no local, mesmo enquanto as unidades de escala são temporariamente desconectadas da nuvem.

Neste tópico, as execuções de gerenciamento de depósito em um depósito definido como uma unidade de escala são conhecidas como um *sistema de execução de depósito* (*WES*).

## <a name="prerequisites"></a>Pré-requisitos

Você deve ter um hub do Dynamics 365 Supply Chain Management e uma unidade de escala que tenha sido implantada com a carga de trabalho de gerenciamento de depósito. Para obter mais informações sobre o processo de arquitetura e implantação, consulte [Unidades de escala de nuvem e de borda para cargas de trabalho de gerenciamento de fabricação e depósito](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Como a carga de trabalho de WES funciona em unidades de escala

Para os processos na carga de trabalho de gerenciamento de depósito, os dados são sincronizados entre o hub e as unidades de escala.

Uma unidade de escala pode manter somente os dados dela. O conceito de propriedade de dados para unidades de escala ajuda a evitar conflitos com vários mestres. Portanto, é importante compreender que processos pertencem ao hub e quais são de propriedade das unidades de escala.

As unidades de escala têm os seguintes dados:

- **Dados de processamento de ciclo** – os métodos de processo de ciclo selecionados são tratados como parte do processamento de ciclos da unidade de escala.
- **Dados de processamento do trabalho** – há suporte para os seguintes tipos de processamento de ordem de serviço:

  - **Movimentações de estoque** (movimentação manual e movimentação por trabalho de modelo)
  - **Ordens de compra** (armazene trabalho por meio de uma ordem de depósito quando as ordens de compra não estão associadas a cargas)
  - **Ordens de venda** (trabalho de separação e carregamento simples)
  - **Ordens de transferência** (somente saída com trabalho simples de separação e carregamento)

- **Dados de recebimento de ordem de depósito** – esses dados são usados somente para ordens de compra que são liberadas manualmente para um depósito.
- **Dados da placa de licença** – as placas de licença podem ser criadas no hub e na unidade de escala. O tratamento de conflitos dedicados foi fornecido. Observe que esses dados não são específicos de depósito.

## <a name="outbound-process-flow"></a>Fluxo do processo de saída

O hub tem os seguintes dados:

- Todos os documentos de origem, como ordens de venda e ordens de transferência
- Alocação de ordens e processamento de carga de saída
- Os processos de liberação para depósito, criação de remessa, criação de ciclo e finalização de ciclo

As unidades de escala têm o processamento de ciclos real (como alocação de trabalho, trabalho de reabastecimento e criação de trabalho por demanda) após a liberação do ciclo. Portanto, os trabalhadores de depósito podem processar o trabalho de saída usando um aplicativo de depósito conectado à unidade de escala.

![Fluxo de processamento de ciclos](./media/wes-wave-processing-ga.png "Fluxo de processamento de ciclos")

## <a name="inbound-process-flow"></a>Fluxo do processo de entrada

O hub tem os seguintes dados:

- Todos os documentos de origem, como ordens de compra e ordens de devolução de venda
- Processamento de carga de entrada
- Todas as atualizações de custo e financeiras

> [!NOTE]
> O fluxo da ordem de compra de entrada é conceitualmente diferente do fluxo de saída. Você pode operar o mesmo depósito na unidade de escala ou no hub, dependendo se a ordem de compra foi liberada para o depósito ou não. Depois de liberar uma ordem para o depósito, você só poderá trabalhar com essa ordem enquanto estiver conectado na unidade de escala.

Se você estiver usando o processo *liberar para depósito*, as [*ordens de depósito*](cloud-edge-warehouse-order.md) serão criadas e a propriedade do fluxo de recebimento relacionado será atribuída à unidade de escala. O hub não poderá registrar recebimento de entrada.

O trabalhador pode executar o processo de recebimento usando um aplicativo de depósito conectado à unidade de escala. Os dados são gravados pela unidade de escala e relatados na ordem de depósito de entrada. A criação e o processamento do armazenamento subsequente também serão tratados pela unidade de escala.

Se você não estiver usando o processo *liberar para depósito* e, portanto, não estiver usando *ordens de depósito*, o hub poderá processar o recebimento do depósito e o processamento do trabalho, independentemente das unidades de escala.

![Fluxo do processo de entrada](./media/wes-inbound-ga.png "Fluxo do processo de entrada")

## <a name="supported-processes-and-roles"></a>Processos e funções com suporte

Nem todos os processos de gerenciamento de depósito têm suporte em uma carga de trabalho de WES em uma unidade de escala. Portanto, é recomendável que você atribua funções que correspondam à funcionalidade disponível para cada usuário.

Para facilitar esse processo, uma função de exemplo denominada *Gerente de depósito na carga de trabalho* é incluída nos dados de demonstração em **Administração do sistema \> Segurança \> Configuração de segurança**. A finalidade dessa função é permitir que gerentes de depósito acessem o WES na unidade de escala. A função concede acesso às páginas que são relevantes no contexto de uma carga de trabalho hospedada em uma unidade de escala.

As funções de usuário em uma unidade de escala são atribuídas como parte da sincronização de dados inicial do hub para a unidade de escala.

Para modificar as funções atribuídas a um usuário, vá para **Administração do sistema \> Segurança \> Atribuir usuários a funções**. Os usuários que atuam como gerentes de depósito somente em unidades de escala devem receber apenas a função *Gerente de depósito na carga de trabalho*. Essa abordagem garantirá que esses usuários tenham acesso apenas à funcionalidade com suporte. Remova outras funções atribuídas a esses usuários.

Os usuários que atuam como gerentes de depósito no hub e em unidades de escala devem receber a função existente de *Trabalhador de depósito*. Lembre-se de que essa função concede aos trabalhadores de depósito acesso a recursos (como processamento de recebimento de ordem de transferência) que aparece na interface do usuário (IU), mas sem suporte atual em unidades de escala.

## <a name="supported-wes-processes"></a>Processos WES com suporte

Os seguintes processos de execução de depósito podem ser habilitados para uma carga de trabalho de WES em uma unidade de escala:

- Métodos de ciclo selecionados para ordens de venda e de transferência (alocação, reabastecimento de demanda, conteinerização, criação de trabalho e impressão de etiquetas de ciclo)
- Processar trabalho de depósito de ordens de venda e de transferência usando o aplicativo de depósito (incluindo trabalho de reabastecimento)
- Consultar o estoque disponível usando o aplicativo de depósito
- Criar e executar movimentações de estoque usando o aplicativo de depósito
- Registrar ordens de compra e realizar trabalho de armazenamento usando o aplicativo de depósito

Os seguintes tipos de ordem de serviço têm suporte no momento para cargas de trabalho WES em implantações de unidades de escala:

- Ordens de Venda
- Transferir saída
- Reabastecimento
- Movimentação de estoque
- Ordens de compra (vinculadas a ordens de depósito)

No momento, não há suporte para outros tipos de trabalho de depósito e processamento de documento de origem em unidades de escala. Por exemplo, para uma carga de trabalho de WES em uma unidade de escala, você não pode executar um processo de recebimento de ordem de transferência (recebimento de transferência) ou processar o trabalho de contagem de ciclo.

> [!NOTE]
> Os botões e itens de menu de dispositivo móvel para funcionalidades sem suporte não são mostrados no _aplicativo de depósito_ quando ele está conectado a uma implantação de unidade de escala.

> [!WARNING]
> Quando você executa uma carga de trabalho em uma unidade de escala, não pode executar processos sem suporte para o depósito específico no hub. As tabelas fornecidas posteriormente neste tópico documentam os recursos com suporte.
>
> Os tipos de trabalho de depósito selecionados podem ser criados no hub e em unidades de escala, mas só podem ser mantidos pelo hub ou pela unidade de escala titular (a implantação que criou os dados).
>
> Mesmo quando um processo específico é compatível com a unidade de escala, lembre-se de que todos os dados necessários podem não ser sincronizados entre o hub e a unidade de escala ou vice-versa, o que pode resultar em processamento inesperado do sistema. Exemplos:
> 
> - Se você usar uma consulta de diretiva de localização que ingresse em um registro de tabela de dados que existe somente na implantação do hub.
> - Se você usar as funcionalidades de status de localização e/ou carga volumétrica do local. Esses dados não serão sincronizados entre as implantações e, portanto, só funcionarão ao atualizar o estoque disponível de localização em uma das implantações.

Atualmente, não há suporte para a seguinte funcionalidade de gerenciamento de depósito para cargas de trabalho de unidade de escala:

- Processamento de entrada de linhas de ordem de compra atribuídas a uma carga
- Processamento de entrada de ordens de compra para um projeto
- Processamento de entrada e saída para itens com as dimensões de rastreamento ativas **Proprietário** e/ou **Número de série**
- Processamento de estoque com um valor de status de bloqueio
- Alterar o status de um estoque durante qualquer processo de movimentação de trabalho
- Reservas flexíveis de dimensões no nível do depósito confirmadas em uma ordem
- Uso da funcionalidade *Status de localização do depósito* (os dados não são sincronizados entre as implantações)
- Uso da funcionalidade *Posicionamento da placa de licença do local*
- Uso de *Filtros de produto* e *Grupos de filtros de produtos*, incluindo a configuração **Número de dias para combinar lotes**
- Integração com gerenciamento de qualidade
- Processar com itens de peso variável
- Processar com itens habilitados somente para gerenciamento de transporte (TMS)
- Processar com estoque disponível negativo
- Processar trabalho de depósito com tipos de trabalho personalizados
- Processar trabalho de depósito com notas de remessa
- Processar trabalho de depósito com acionamento de limite de contagem cíclica
- Processar trabalho de depósito com manuseio de material/warehouse automation
- Uso de imagem de dados de produto mestre (por exemplo, no aplicativo de depósito)

> [!WARNING]
> Algumas funcionalidades de depósito não estarão disponíveis para depósitos que executam as cargas de trabalho de gerenciamento de depósito em uma unidade de escala e também não terão suporte no hub ou na carga de trabalho da unidade de escala.
> 
> Outros recursos podem ser processados em ambos os casos, mas exigirão um uso cuidadoso em alguns cenários, por exemplo, quando o estoque disponível for atualizado para o mesmo depósito no hub e na unidade de escala devido ao processo de atualização de dados assíncronos.
> 
> Funcionalidades específicas (como *bloco de trabalho*) que têm suporte no hub e unidades de escala só terão suporte para o proprietário dos dados.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Saída (com suporte somente para ordens de venda e de transferência)

A tabela a seguir mostra quais recursos de saída têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                                      | Hub | Carga de trabalho de WES em uma unidade de escala |
|--------------------------------------------------------------|-----|------------------------------|
| Processamento de documento de origem                                   | Sim | Não |
| Processamento de gerenciamento de transporte e carga                | Sim | Não |
| Liberar para o depósito                                         | Sim | Não |
| Distribuição integrada planejada                                        | Não  | Não |
| Consolidação da remessa                                       | Sim | Não |
| Processamento de ciclo remessa                                     | Sim, mas somente a inicialização e finalização do ciclo são tratadas no hub. Isso significa que o processamento de transferência de saída e de ordem de venda só pode ser manipulado pela unidade de escala.|<p>Não, a inicialização e a finalização são manipuladas pelo hub, e não há suporte para **Criação e classificação de carga**<p><b>Observação:</b> o acesso ao hub é necessário para finalizar o status de ciclo como parte do processamento de ciclos.</p> |
| Manter remessas para o ciclo                                  | Sim | Não |
| Processamento de trabalho de depósito (incluindo a impressão da placa de licença)        | Não  | <p>Sim, mas somente para os recursos mencionados acima. |
| Separação de cluster                                              | Não  | Sim|
| Processamento manual de embalagens, incluindo o processamento do trabalho "separação de contêiner embalado"                                           | Não <P>É possível fazer processamentos parciais depois que um processo de separação inicial é manuseado por uma unidade de escala, mas não é recomendado devido às seguintes operações bloqueadas.</p>  | Não  |
| Remover o contêiner do grupo                        | Não  | Não                           |
| Processamento de classificação de saída                                  | Não  | Não |
| Impressão de documentos relacionados ao carregamento                           | Sim | Não |
| Conhecimento de embarque e geração de ASN                            | Sim | Não |
| Confirmação de remessa                    | Sim  | Não |
| Confirmação de remessa com "confirmar e transferir"                    | Não  | Não |
| Processamento de guia de remessa e faturamento                | Sim | Não |
| Separação curta (ordens de venda e de transferência)                    | Não  | Não |
| Separação em excesso (ordens de venda e de transferência)                     | Não  | Não |
| Alteração de locais de trabalho (ordens de venda e de transferência)         | Não  | Sim|
| Concluir trabalho (ordens de venda e de transferência)                    | Não  | Sim|
| Imprimir relatório de trabalho                                            | Sim | Não |
| Etiqueta da onda                                                   | Não  | Sim|
| Divisão do trabalho                                                   | Não  | Sim|
| Processamento de trabalho - Dirigido por "carregamento de transporte"            | Não  | Não |
| Reduzir quantidade separada                                       | Não  | Não |
| Reverter trabalho                                                 | Não  | Não |
| Estornar confirmação da remessa                                | Sim | Não |

### <a name="inbound"></a>Entrada

A tabela a seguir mostra quais recursos de entrada têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                                          | Hub | Carga de trabalho de WES em uma unidade de escala<BR>*(Os itens marcados como "Sim" aplicam-se somente a ordens de depósito)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Processamento&nbsp;de documento&nbsp;de origem                                       | Sim | Não |
| Processamento de gerenciamento de transporte e carga                    | Sim | Não |
| Confirmação de remessa de entrada                                            | Sim | Não |
| Liberação da ordem de compra para depósito (processamento de ordem de depósito) | Sim | Não |
| Cancelamento de linhas da ordem de depósito<p>Observe que só haverá suporte quando nenhum registro tiver ocorrido contra a linha</p>          | Sim | Não |
| Recebimento e armazenamento do item da ordem de compra                       | <p>Sim,&nbsp;quando&nbsp;não há&nbsp;uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, quando uma ordem de compra não faz parte de uma <i>carga</i></p> |
| Recebimento da linha da ordem de compra e armazenamento                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, quando uma ordem de compra não faz parte de uma <i>carga</i></p></p> |
| Recebimento e armazenamento da ordem de devolução                               | Sim | Não |
| Recebimento e armazenamento de placa de licença mista                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento do item de carga                                             | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento da placa de licença                              | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento do item da ordem de transferência                        | Sim | Não |
| Transferir recebimento e armazenamento do recebimento da linha de ordem                        | Sim | Não |
| Cancelar trabalho (entrada)                                              | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, mas somente quando opção <b>Cancelar o registro do recebimento ao cancelar o trabalho</b> (na página <b>Parâmetros de gerenciamento de depósito</b>) estiver desmarcada</p> |
| Processamento do recebimento de produtos da ordem de compra                          | Sim | Não |
| Recebimento de ordem de compra com entrega insuficiente                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não, porque você só pode cancelar as quantidades completas das linhas de ordem de depósito |
| Recebimento de ordem de compra com entrega em excesso                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Sim  |
| Recebimento com a criação de trabalho de *Distribuição integrada*                   | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Ordem de qualidade*                  | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Amostra de ordem de qualidade*          | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Qualidade na verificação de qualidade*       | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de ordem de qualidade                            | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Processamento de trabalho - Dirigido por *armazenamento de cluster*                             | Sim | Não |
| Processamento de trabalho com *separação curta*                                           | Sim | Não |
| Carregamento da placa de licença:                                           | Sim | Não |

### <a name="warehouse-operations-and-exception-handing"></a>Operações de depósito e tratamento de exceções

A tabela a seguir mostra quais recursos de operações de depósito e tratamento de exceções têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                            | Hub | Carga de trabalho de WES em uma unidade de escala |
|----------------------------------------------------|-----|------------------------------|
| Consulta de placa de licença                              | Sim | Sim                          |
| Consulta de item                                       | Sim | Sim                          |
| Consulta de localização                                   | Sim | Sim                          |
| Alterar depósito                                   | Sim | Sim                          |
| Movimentação                                           | Sim | Sim                          |
| Movimento por modelo.                               | Sim | Sim                          |
| Transferência de depósito                                 | Sim | Não                           |
| Criar ordem de transferência do aplicativo de depósito           | Sim | Não                           |
| Ajuste (entrada/saída)                                | Sim | Não                           |
| Alteração de Status do Estoque                            | Sim | Não                           |
| Processamento de contagem cíclica e discrepância de contagem | Sim | Não                           |
| Reimprimir etiqueta (impressão da placa de licença)             | Sim | Sim                          |
| Criação da placa de licença                                | Sim | Não                           |
| Interrupção da placa de licença                                | Sim | Não                           |
| Empacotar em placas de licença aninhadas                                | Sim | Não                           |
| Check-in do motorista                                    | Sim | Não                           |
| Check-out do motorista                                   | Sim | Não                           |
| Alterar código de disposição em lotes                      | Sim | Sim                          |
| Exibir lista de trabalhos abertos                             | Sim | Sim                          |
| Consolidar placas de licença                         | Sim | Não                           |
| O processamento de reabastecimento de limite mínimo e máximo e de zona| Sim <p>Recomenda-se não incluir os mesmos locais como parte das consultas</p>| Sim                          |
| Processamento de reabastecimento de slots                  | Sim  | Sim<p>Observe que a configuração deve ser feita na unidade de escala</p>                           |
| Bloquear e desbloquear trabalho                             | Sim | Sim                          |
| Alterar Usuário                                        | Sim | Sim                          |
| Alterar pool de trabalho no trabalho                           | Sim | Sim                          |
| Cancelar trabalho                                        | Sim | Sim                          |


### <a name="production"></a>Produção

No momento, os cenários de produção de gerenciamento de depósito não tem suporte em unidades de escala, conforme indicado na tabela a seguir.

| Processar | Hub | Carga de trabalho de WES em uma unidade de escala |
|---------|-----|------------------------------|
| <p>Todos os processos de gerenciamento de depósito estão relacionados à produção. Eis alguns exemplos:</p><li>Liberar para o depósito</li><li>Processamento de ciclos de produção</li><li>Separação de matéria-prima</li><li>RAF e armazenamento de mercadorias acabadas</li><li>Armazenamento de coproduto e subproduto</li><li>Armazenamento kanban</li><li>Separação kanban</li><li>Começar ordem de produção</li><li>Sucata de produção</li><li>Último palete de produção</li><li>Registrar consumo de materiais</li><li>Kanban vazio</li></ul> | Sim | Não |

## <a name="maintaining-scale-units-for-wes"></a>Manter unidades de escala para WES

Vários trabalhos em lotes são executados no hub e em unidades de escala.

Na implantação do hub, você pode manter manualmente os trabalhos em lotes. Você pode gerenciar estes trabalhos de lote em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office**:

- Processar eventos de atualização do status de trabalho
- Processador de mensagens de unidade de escala para hub
- Registrar recebimentos de ordem de origem
- Concluir ordens de depósito
- Processar respostas de atualização de quantidade para linhas da ordem de depósito

Na carga de trabalho em unidades de escala, você pode gerenciar estes trabalhos em lotes em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho**:

- Processar registros de tabela do ciclo
- Processador de mensagens da unidade de escala para o hub do depósito
- Processar solicitações de atualização de quantidade para linhas de ordem de depósito


[!INCLUDE[footer-include](../../includes/footer-banner.md)]