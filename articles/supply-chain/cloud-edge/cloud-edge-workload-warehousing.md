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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516726"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nem todas as funcionalidades comerciais têm suporte total na versão preliminar pública quando são usadas unidades de escala de carga de trabalho. Certifique-se de usar somente os processos descritos explicitamente por este tópico como aceitos.

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

    - Movimentações de estoque (movimentação manual e movimentação por trabalho de modelo)
    - Ordens de compra (trabalho de armazenamento por meio de uma ordem de depósito)
    - Ordens de venda (trabalho de separação e carregamento simples)

- **Dados de recebimento de ordem de depósito** – esses dados são usados somente para ordens de compra que são liberadas manualmente para um depósito.
- **Dados da placa de licença** – as placas de licença podem ser criadas no hub e na unidade de escala. O tratamento de conflitos dedicados foi fornecido. Observe que esses dados não são específicos de depósito.

## <a name="outbound-process-flow"></a>Fluxo do processo de saída

O hub tem os seguintes dados:

- Todos os documentos de origem, como ordens de venda e ordens de transferência
- Alocação de ordens e processamento de carga de saída
- Os processos de liberação para depósito, criação de remessa e criação de ciclos

As unidades de escala têm o processamento de ciclos real (como alocação de trabalho, trabalho de reabastecimento e criação de trabalho por demanda) após a liberação do ciclo. Portanto, os trabalhadores de depósito podem processar o trabalho de saída usando um aplicativo de depósito conectado à unidade de escala.

![Fluxo de processamento de ciclos](./media/wes_wave_processing_flow.png "Fluxo de processamento de ciclos")

## <a name="inbound-process-flow"></a>Fluxo do processo de entrada

O hub tem os seguintes dados:

- Todos os documentos de origem, como ordens de compra e ordens de devolução de venda
- Processamento de carga de entrada

> [!NOTE]
> O fluxo da ordem de compra de entrada é conceitualmente diferente do fluxo de saída, no qual a unidade de escala que faz o processamento depende da liberação da ordem para um depósito.

Se você estiver usando o processo *liberar para depósito*, as ordens de depósito serão criadas e a propriedade do fluxo de recebimento relacionado será atribuída à unidade de escala. O hub não poderá registrar recebimento de entrada.

O trabalhador pode executar o processo de recebimento usando um aplicativo de depósito conectado à unidade de escala. Os dados são gravados pela unidade de escala e relatados na ordem de depósito de entrada. A criação e o processamento do armazenamento subsequente também serão tratados pela unidade de escala.

Se você não estiver usando o processo *liberar para depósito* e, portanto, não estiver usando *ordens de depósito*, o hub poderá processar o recebimento do depósito e o processamento do trabalho, independentemente das unidades de escala.

![Fluxo do processo de entrada](./media/wes_Inbound_flow.png "Fluxo do processo de entrada")

## <a name="supported-processes-and-roles"></a>Processos e funções com suporte

Nem todos os processos de gerenciamento de depósito têm suporte em uma carga de trabalho de WES em uma unidade de escala. Portanto, é recomendável que você atribua funções que correspondam à funcionalidade disponível para cada usuário.

Para facilitar esse processo, uma função de exemplo denominada *Gerente de depósito na carga de trabalho* é incluída nos dados de demonstração em **Administração do sistema \> Segurança \> Configuração de segurança**. A finalidade dessa função é permitir que gerentes de depósito acessem o WES na unidade de escala. A função concede acesso às páginas que são relevantes no contexto de uma carga de trabalho hospedada em uma unidade de escala.

As funções de usuário em uma unidade de escala são atribuídas como parte da sincronização de dados inicial do hub para a unidade de escala.

Para modificar as funções atribuídas a um usuário, acesse **Administração do sistema \> Segurança \> Atribuir usuários a funções** na unidade de escala. Os usuários que atuam como gerentes de depósito somente em unidades de escala devem receber apenas a função *Gerente de depósito na carga de trabalho*. Essa abordagem garantirá que esses usuários tenham acesso apenas à funcionalidade com suporte. Remova outras funções atribuídas a esses usuários.

Os usuários que atuam como gerentes de depósito no hub e em unidades de escala devem receber a função existente de *Trabalhador de depósito*. Lembre-se de que essa função concede aos trabalhadores de depósito acesso a recursos (como processamento de ordem de transferência) que aparece na interface do usuário (IU), mas sem suporte atual em unidades de escala.

## <a name="supported-wes-processes"></a>Processos WES com suporte

Os seguintes processos de execução de depósito podem ser habilitados para uma carga de trabalho de WES em uma unidade de escala:

- Métodos de ciclo selecionados para ordens de venda e reabastecimento de demanda
- Executar ordens de trabalho a partir de ordens de venda e reabastecimento de demanda por meio do aplicativo de depósito
- Consultar o estoque disponível usando o aplicativo de depósito
- Criar e executar movimentações de estoque usando o aplicativo de depósito
- Registrar ordens de compra e realizar trabalho de armazenamento usando o aplicativo de depósito

Os seguintes tipos de ordem de serviço têm suporte no momento para cargas de trabalho WES em implantações de unidades de escala:

- Ordens de Venda
- Reabastecimento
- Movimentação de estoque
- Ordens de compra vinculadas a ordens de depósito

No momento, não há suporte ao processamento de outros documentos de origem em unidades de escala. Por exemplo, para uma carga de trabalho de WES em uma unidade de escala, você não pode executar as seguintes ações:

- Liberar uma ordem de transferência.
- Processe as operações de separação e remessa do depósito de saída.

> [!IMPORTANT]
> Se você usar uma carga de trabalho em uma unidade de escala, não poderá executar processos sem suporte para o depósito específico no hub.

Atualmente, não há suporte para a seguinte funcionalidade de gerenciamento de depósito em unidades de escala:

- Processamento de entrada e saída para itens com qualquer dimensão de controle ativa (como dimensões de número de série ou lote)
- Processamento de alterações de status de estoque
- Processamento de estoque com um valor de status de bloqueio
- Integração com gerenciamento de qualidade
- Integração com produção
- Processamento de itens de peso variável
- Processamento de entrega excedente e insuficiente
- Processamento de estoque disponível negativo

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Saída (com suporte somente para ordens de venda e reabastecimento de demanda)

A tabela a seguir mostra quais recursos de saída têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

> [!WARNING]
> Como só há suporte para o processamento da ordem de venda, o processamento do gerenciamento de depósito de saída não pode ser usado para ordens de transferência.
>
> Algumas funcionalidades de depósito não estarão disponíveis em depósitos que estejam executando as cargas de trabalho de gerenciamento de depósito em uma unidade de escala.

| Processar                                                      | Hub | Carga de trabalho de WES em uma unidade de escala |
|--------------------------------------------------------------|-----|------------------------------|
| Processamento de documento de origem                                   | Sim | Não |
| Processamento de gerenciamento de transporte e carga                | Sim | Não |
| Liberar para o depósito                                         | Sim | Não |
| Consolidação da remessa                                       | Não  | Não |
| Distribuição integrada (trabalho de separação)                                 | Não  | Não |
| Processamento de ciclo remessa                                     | Não, mas a finalização do status de ciclo é tratada no hub |<p>Sim, mas os seguintes recursos não têm suporte:</p><ul><li>Criação de trabalho paralelo</li><li>Criação e classificação de carga</li><li>Transporte em contêineres</li><li>Impressão de etiqueta do ciclo</li></li></ul><p><b>Observação:</b> o acesso ao hub é necessário para finalizar o status de ciclo como parte do processamento de ciclos.</p> |
| Processamento de trabalho de depósito (incluindo a impressão da placa de licença)     | Não  | <p>Sim, mas somente para os seguintes recursos:</p><ul><li>Separação de vendas (sem o uso de dimensões de rastreamento ativas)</li><li>Carregamento de venda (sem o uso de dimensões de rastreamento ativas)</li></ul> |
| Separação de cluster                                              | Não  | Não |
| Processamento de embalagens                                           | Não  | Não |
| Processamento de classificação de saída                                  | Não  | Não |
| Impressão de documentos relacionados ao carregamento                           | Sim | Não |
| Conhecimento de embarque e geração de ASN                            | Sim | Não |
| Processamento de confirmação de remessa e guia de remessa                | Sim | Não |
| Separação insuficiente (ordens de venda)                                 | Não  | Não |
| Cancelamento de trabalho                                            | Não  | Não |
| Alteração de locais de trabalho (ordens de venda)                      | Não  | Não |
| Concluir trabalho (ordens de venda)                                 | Não  | Não |
| Bloquear e desbloquear trabalho                                       | Não  | Não |
| Alterar Usuário                                                  | Não  | Não |
| Imprimir relatório de trabalho                                            | Não  | Não |
| Etiqueta da onda                                                   | Não  | Não |
| Reverter trabalho                                                 | Não  | Não |

### <a name="inbound"></a>Entrada

A tabela a seguir mostra quais recursos de entrada têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                                          | Hub | Carga de trabalho de WES em uma unidade de escala |
|------------------------------------------------------------------|-----|------------------------------|
| Processamento&nbsp;de documento&nbsp;de origem                                       | Sim | Não |
| Processamento de gerenciamento de transporte e carga                    | Sim | Não |
| Confirmação de remessa                                            | Sim | Não |
| Liberação da ordem de compra para depósito (processamento de ordem de depósito) | Sim | Não |
| Recebimento e armazenamento do item da ordem de compra                        | <p>Sim,&nbsp;quando&nbsp;não há&nbsp;uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, quando há uma ordem de depósito e quando uma ordem de compra não faz parte de uma <i>carga</i>. No entanto, dois itens de menu de dispositivo móvel devem ser usados, um para recebimento (<i>Recebimento de itens da ordem de compra</i>) e outro, com a opção <b>Usar trabalho existente</b> habilitada, para processar o armazenamento.</p><p>Não, quando não há uma ordem de depósito.</p> |
| Recebimento da linha da ordem de compra e armazenamento                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento da ordem de devolução                               | Sim | Não |
| Recebimento e armazenamento de placa de licença mista                        | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento do item de carga                                              | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento da placa de licença                              | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento do item da ordem de transferência                        | Sim | Não |
| Transferir recebimento e armazenamento do recebimento da linha de ordem                        | Sim | Não |
| Cancelamento de trabalho                                                | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, mas não há suporte à opção <b>Cancelar o registro do recebimento ao cancelar o trabalho</b> (na página <b>Parâmetros de gerenciamento de depósito</b>).</p> |
| Processamento do recebimento de produtos da ordem de compra                        | Sim | Não |
| Criação de trabalho de distribuição integrada como parte do recebimento                 | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |

### <a name="warehouse-operations-and-exception-handing"></a>Operações de depósito e tratamento de exceções

A tabela a seguir mostra quais recursos de operações de depósito e tratamento de exceções têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                            | Hub | Carga de trabalho de WES em uma unidade de escala |
|----------------------------------------------------|-----|------------------------------|
| Consulta de placa de licença                              | Sim | Sim                          |
| Consulta de item                                       | Sim | Sim                          |
| Consulta de localização                                   | Sim | Sim                          |
| Alterar depósito                                   | Sim | Sim                          |
| Movimentação                                           | Não  | Sim                          |
| Movimento por modelo.                               | Não  | Sim                          |
| Ajuste (entrada/saída)                                | Sim | Não                           |
| Processamento de contagem cíclica e discrepância de contagem | Sim | Não                           |
| Reimprimir etiqueta (impressão da placa de licença)             | Sim | Não                           |
| Criação da placa de licença                                | Sim | Não                           |
| Interrupção da placa de licença                                | Sim | Não                           |
| Check-in do motorista                                    | Sim | Não                           |
| Check-out do motorista                                   | Sim | Não                           |
| Alterar código de disposição em lotes                      | Sim | Não                           |
| Exibir lista de trabalhos abertos                             | Sim | Não                           |
| Consolidar placas de licença                         | Não  | Não                           |
| Remover o contêiner do grupo                        | Não  | Não                           |
| Cancelar trabalho                                        | Não  | Não                           |
| Processamento de reabastecimento mínimo/máximo                   | Não  | Não                           |
| Processamento de reabastecimento de slots                  | Não  | Não                           |

### <a name="production"></a>Produção

A integração de gerenciamento de depósito para cenários de produção não tem suporte atualmente, conforme indicado na tabela a seguir.

| Processar | Hub | Carga de trabalho de WES em uma unidade de escala |
|---------|-----|------------------------------|
| <p>Todos os processos de gerenciamento de depósito estão relacionados à produção. Eis alguns exemplos:</p><li>Liberar para o depósito</li><li>Processamento de ciclos de produção</li><li>Separação de matéria-prima</li><li>Armazenamento de mercadorias acabadas</li><li>Armazenamento de coproduto e subproduto</li><li>Armazenamento kanban</li><li>Separação kanban</li><li>Começar ordem de produção</li><li>Sucata de produção</li><li>Último palete de produção</li><li>Registrar consumo de materiais</li><li>Kanban vazio</li></ul> | Não | Não |

## <a name="maintaining-scale-units-for-wes"></a>Manter unidades de escala para WES

Vários trabalhos em lotes são executados no hub e em unidades de escala.

Na implantação do hub, você pode manter manualmente os trabalhos em lotes. Você pode gerenciar estes três trabalhos em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office**:

- Processar eventos de atualização do status de trabalho
- Processar eventos de transferência de controle de execução do ciclo
- Registrar recebimentos de ordem de origem

Na carga de trabalho em unidades de escala, você pode gerenciar estes dois trabalhos em lotes em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho**:

- Processar registros de tabela do ciclo
- Processar eventos de transferência de controle de execução do ciclo
