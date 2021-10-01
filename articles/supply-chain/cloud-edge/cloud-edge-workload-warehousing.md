---
title: Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda
description: Este tópico fornece informações sobre o recurso que permite que as unidades de escala executem processos selecionados da carga de trabalho de gerenciamento de depósito.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c3f703e39e5e9d475dcb4f96dfb400a961ae2dcf
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500418"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e borda

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nem todas as funcionalidades de negócios do gerenciamento de depósito têm suporte total para depósitos que executam uma carga de trabalho em uma unidade de escala. Certifique-se de usar somente os processos descritos explicitamente por este tópico como aceitos.

## <a name="warehouse-execution-on-scale-units"></a>Execução de depósito em unidades de escala

Cargas de trabalho de gerenciamento de depósito habilitam unidades de escala de nuvem e borda para executar os processos selecionados dos recursos de gerenciamento de depósito.

## <a name="prerequisites"></a>Pré-requisitos

Você deve ter um hub do Dynamics 365 Supply Chain Management e uma unidade de escala que tenha sido implantada com a carga de trabalho de gerenciamento de depósito. Para obter mais informações sobre a arquitetura e o processo de implantação, consulte [Unidades de escala em uma topologia híbrida distribuída](cloud-edge-landing-page.md).

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Como a carga de trabalho de execução de depósito funciona em unidades de escala

Para os processos na carga de trabalho de gerenciamento de depósito, os dados são sincronizados entre o hub e as unidades de escala.

Uma unidade de escala pode manter somente os dados dela. O conceito de propriedade de dados para unidades de escala ajuda a evitar conflitos com vários mestres. Portanto, é importante compreender quais dados de processos pertencem ao hub e quais são de propriedade das unidades de escala.

Dependendo dos processos de negócios, o mesmo registro de dados pode alterar a propriedade entre as unidades de hub e escala. A seção a seguir mostra um exemplo desse cenário.

> [!IMPORTANT]
> Alguns dados podem ser criados tanto no hub quanto na unidade de escala. Os exemplos incluem **Placas de licença** e **Números de lote**. O tratamento de conflitos dedicado é fornecido no caso de um cenário no qual o mesmo registro exclusivo é criado no hub e em uma unidade de escala durante o mesmo ciclo de sincronização. Quando isso ocorre, há falha na próxima sincronização e é necessário acessar **Administração do sistema > Consultas > Consultas de carga de trabalho > Registros duplicados**. Lá, é possível exibir e mesclar os dados.

## <a name="outbound-process-flow"></a>Fluxo do processo de saída

O processo de propriedade dos dados de saída depende de você estar usando o processo de planejamento de carga. Em todos os casos, o hub é proprietário dos *documentos de origem*, como ordens de venda e de transferência, bem como do processo de alocação da ordem e dos dados de transação da ordem relacionados. Mas quando você usar o processo de planejamento de carga, as cargas serão criadas no hub e, portanto, inicialmente pertencerão a ele. Como parte do processo *Liberar para o depósito*, a propriedade dos dados de carga é transferida para a implantação da unidade de escala dedicada, que se tornará o proprietário do *processamento de ciclos de remessa* subsequente (como alocação de trabalho, trabalho de reabastecimento e criação de trabalho por demanda). Portanto, os operadores do depósito só podem processar vendas de saída e trabalho de ordem de transferência usando um aplicativo móvel Warehouse Management conectado à implantação que está executando a carga de trabalho da unidade de escala específica.

Assim que o processo de trabalho final colocar o estoque em um local de remessa final (Baydoor), a unidade de escala sinalizará o hub para atualizar as transações de estoque do documento de origem para *Separado*. Até que o processo seja executado e sincronizado novamente, o estoque disponível na carga da unidade de escala será fisicamente reservado no nível do depósito e você poderá processar imediatamente a confirmação de remessa de saída sem aguardar a conclusão dessa sincronização. A guia de remessa de venda subsequente e o faturamento ou a remessa da ordem de transferência para a carga serão tratados no hub.

O diagrama a seguir mostra o fluxo de saída e indica onde ocorrem os processos de negócios individuais. (Selecione o diagrama para aumentá-lo.)

[![Fluxo do processamento de saída.](media/wes_outbound_warehouse_processes-small.png "Fluxo do processamento de saída")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Processamento de saída com planejamento de carga

Quando você está usando o processo de planejamento de carga, as cargas e remessas são criadas no hub e a propriedade dos dados é transferida para as unidades de escala como parte do processo *Liberar para o depósito* , conforme ilustrado na figura a seguir.

![Processamento de saída com planejamento de carga.](./media/wes_outbound_processing_with_load_planning.png "Processamento de saída com planejamento de carga")

### <a name="outbound-processing-without-load-planning"></a>Processamento de saída sem planejamento de carga

Quando você não usa o processo de planejamento de carga, as remessas são criadas nas unidades de escala. As cargas também são criadas nas unidades de escala como parte do processo cíclico.

![Processamento de saída sem planejamento de carga.](./media/wes_outbound_processing_without_load_planning.png "Processamento de saída sem planejamento de carga")

## <a name="inbound-process-flow"></a>Fluxo do processo de entrada

O hub tem os seguintes dados:

- Todos os documentos de origem, como ordens de compra e de produção
- Processamento de carga de entrada
- Todas as atualizações de custo e financeiras

> [!NOTE]
> O fluxo da ordem de compra de entrada é conceitualmente diferente do fluxo de saída. Você pode operar o mesmo depósito na unidade de escala ou no hub, dependendo se a ordem de compra foi liberada para o depósito. Depois de liberar uma ordem para o depósito, você só poderá trabalhar com essa ordem enquanto estiver conectado na unidade de escala.
>
> Se você estiver usando o processo *Liberar para o depósito*, as [*ordens de depósito*](cloud-edge-warehouse-order.md) serão criadas e a propriedade do fluxo de recebimento relacionado será atribuída à unidade de escala. O hub não poderá registrar recebimento de entrada.

Você deve entrar no hub para usar o processo *Liberar para o depósito*. Para o processamento de ordem de compra, acesse uma das páginas a seguir para executá-lo ou agendá-lo:

- **Compras e fornecimento > Ordens de compra > Todas as ordens de compra > Depósito > Ações > Liberar para o depósito**
- **Gerenciamento de depósito > Liberar para depósito > Liberação automática de ordens de compra**

Ao usar a opção **Liberação automática de ordens de compra**, você pode selecionar linhas específicas da ordem de compra com base em uma consulta. Um cenário típico seria configurar um trabalho em lotes recorrente que libera todas as linhas da ordem de compra confirmadas que devem chegar no dia seguinte.

O trabalhador pode executar o processo de recebimento usando um aplicativo móvel do Warehouse Management conectado à unidade de escala. Os dados são gravados pela unidade de escala e relatados na ordem de depósito de entrada. A criação e o processamento do armazenamento subsequente também serão tratados pela unidade de escala.

Se você não estiver usando o processo *liberar para depósito* e, portanto, não estiver usando *ordens de depósito*, o hub poderá processar o recebimento do depósito e o processamento do trabalho, independentemente das unidades de escala.

![Fluxo do processo de entrada.](./media/wes-inbound-ga.png "Fluxo do processo de entrada")

Quando um trabalhador faz o registro de entrada usando um processo de recebimento do aplicativo móvel Warehouse Management em uma unidade de escala, um recebimento é registrado na ordem de depósito relacionada, que é armazenada na unidade de escala. A carga de trabalho da unidade de escala irá então sinalizar o hub para atualizar as transações de linha da ordem de compra relacionadas para *Registrado*. Assim que isso for concluído, você poderá executar um recebimento de produtos de ordem de compra no Hub.

O diagrama a seguir mostra o fluxo de entrada e indica onde ocorrem os processos de negócios individuais. (Selecione o diagrama para aumentá-lo.)

[![Fluxo do processamento de entrada](media/wes_inbound_warehouse_processes-small.png "Fluxo do processamento de entrada")](media/wes_inbound_warehouse_processes.png)

## <a name="supported-processes-and-roles"></a>Processos e funções com suporte

Nem todos os processos de gerenciamento de depósito têm suporte em uma carga de trabalho de execução de depósito em uma unidade de escala. Portanto, é recomendável que você atribua funções que correspondam à funcionalidade disponível para cada usuário.

Para facilitar esse processo, uma função de exemplo denominada *Gerente de depósito na carga de trabalho* é incluída nos dados de demonstração em **Administração do sistema \> Segurança \> Configuração de segurança**. A finalidade dessa função é permitir que gerentes de depósito acessem a carga de trabalho de execução de depósito na unidade de escala. A função concede acesso às páginas que são relevantes no contexto de uma carga de trabalho hospedada em uma unidade de escala.

As funções de usuário em uma unidade de escala são atribuídas como parte da sincronização de dados inicial do hub para a unidade de escala.

Para modificar as funções atribuídas a um usuário, Acesse **Administração do sistema \> Segurança \> Atribuir usuários a funções**. Os usuários que atuam como gerentes de depósito somente em unidades de escala devem receber apenas a função *Gerente de depósito na carga de trabalho*. Essa abordagem garantirá que esses usuários tenham acesso apenas à funcionalidade com suporte. Remova outras funções atribuídas a esses usuários.

Os usuários que atuam como gerentes de depósito no hub e em unidades de escala devem receber a função existente de *Trabalhador de depósito*. Lembre-se de que essa função concede aos trabalhadores de depósito acesso a recursos (como processamento de recebimento de ordem de transferência) que aparece na interface do usuário (IU), mas sem suporte atual em unidades de escala.

### <a name="supported-warehouse-execution-processes"></a>Processos de execução de depósito compatíveis

Os seguintes processos de execução de depósito podem ser habilitados para uma carga de trabalho de execução de depósito em uma unidade de escala:

- Métodos de ciclo selecionados para ordens de venda e de transferência (validação, criação de carga, alocação, reabastecimento de demanda, conteinerização, criação de trabalho e impressão de etiquetas de ciclo)

- Processar trabalho de depósito de ordens de venda e de transferência usando o aplicativo de depósito (incluindo trabalho de reabastecimento)
- Consultar o estoque disponível usando o aplicativo de depósito
- Criar e executar movimentações de estoque usando o aplicativo de depósito
- Criando e processando o trabalho de contagem de cíclica usando o aplicativo de depósito
- Fazendo ajustes de estoque usando o aplicativo de depósito
- Registrar ordens de compra e realizar trabalho de armazenamento usando o aplicativo de depósito

Os tipos de trabalho a seguir podem ser criados em uma unidade de escala e, portanto, ser processados como parte de uma carga de trabalho de gerenciamento de depósito:

- **Movimentações de estoque** – movimentação manual e movimentação por trabalho de modelo.
- **Contagem cíclica** – incluindo um processo de aprovação/rejeição de discrepâncias como parte das operações de contagem.
- **Ordens de compra** – armazene trabalho por meio de uma ordem de depósito quando as ordens de compra não estão associadas a cargas.
- **Ordens de venda** – separação e carregamento simples.
- **Transferir saída** – separação e carregamento simples.
- **Reabastecimento** – não incluindo matérias-primas para produção.
- **Armazenamento de mercadorias acabadas** – após o processo de produção do relatório de conclusão.
- **Armazenamento de coproduto e subproduto** – após o processo de produção do relatório de conclusão.

No momento, não há suporte para outros tipos de trabalho de depósito e processamento de documento de origem em unidades de escala. Por exemplo, para uma carga de trabalho de execução de depósito em uma unidade de escala, não é possível executar um processo de recebimento de ordem de transferência (recebimento de transferência). Isso precisa ser processado pela instância do hub.

> [!NOTE]
> Os botões e itens de menu de dispositivo móvel para funcionalidades sem suporte não são mostrados no _Aplicativo móvel Warehouse Management_ quando ele está conectado a uma implantação de unidade de escala.
> 
> Quando você executa uma carga de trabalho em uma unidade de escala, não pode executar processos sem suporte para o depósito específico no hub. As tabelas fornecidas posteriormente neste tópico documentam os recursos com suporte.
>
> Os tipos de trabalho de depósito selecionados podem ser criados no hub e em unidades de escala, mas só podem ser mantidos pelo hub ou pela unidade de escala titular (a implantação que criou os dados).
>
> Mesmo quando um processo específico é compatível com a unidade de escala, lembre-se de que todos os dados necessários podem não ser sincronizados entre o hub e a unidade de escala ou vice-versa, o que pode resultar em processamento inesperado do sistema. Exemplos desse cenário incluem:
> 
> - Se você usar uma consulta de diretiva de localização que ingresse em um registro de tabela de dados que existe somente na implantação do hub.
> - Se você usar as funcionalidades de status de localização e/ou carga volumétrica do local. Esses dados não serão sincronizados entre as implantações e, portanto, só funcionarão ao atualizar o estoque disponível de localização em uma das implantações.

Atualmente, não há suporte para a seguinte funcionalidade de gerenciamento de depósito para cargas de trabalho de unidade de escala:

- Processamento de entrada de linhas de ordem de compra atribuídas a uma carga.
- Processamento de entrada de ordens de compra para um projeto.
- Gerenciar o custo de entrega usando viagens e rastreando mercadorias em trânsito.
- Processamento de entrada e saída para itens com as dimensões de rastreamento ativas **Proprietário** e/ou **Número de série**.
- Processamento de estoque com um valor de status de bloqueio.
- Alterar o status de um estoque durante qualquer processo de movimentação de trabalho.
- Reservas flexíveis de dimensões no nível do depósito confirmadas em uma ordem.
- Uso da funcionalidade *Status de localização do depósito* (os dados não são sincronizados entre as implantações).
- Uso da funcionalidade *Posicionamento da placa de licença do local*.
- Uso de *Filtros de produto* e *Grupos de filtros de produtos*, incluindo a configuração **Número de dias para combinar lotes**.
- Integração com gerenciamento de qualidade.
- Processar com itens de peso variável.
- Processar com itens habilitados somente para Gerenciamento de transporte (TMS).
- Processar com estoque disponível negativo.
- Processar trabalho de depósito com notas de remessa.
- Processar trabalho de depósito com manuseio de material/automação do depósito.
- Uso de imagem de dados de produto mestre (por exemplo, no aplicativo móvel Warehouse Management).

> [!WARNING]
> Algumas funcionalidades de depósito não estarão disponíveis para depósitos que executam as cargas de trabalho de gerenciamento de depósito em uma unidade de escala e também não terão suporte no hub ou na carga de trabalho da unidade de escala.
> 
> Outros recursos podem ser processados em ambos os casos, mas exigirão um uso cuidadoso em alguns cenários, por exemplo, quando o estoque disponível for atualizado para o mesmo depósito no hub e na unidade de escala devido ao processo de atualização de dados assíncronos.
> 
> Funcionalidades específicas (como *bloco de trabalho*), que têm suporte no hub e nas unidades de escala, só terão suporte para o proprietário dos dados.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Saída (com suporte somente para ordens de venda e de transferência)

A tabela a seguir mostra quais recursos de saída têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                                      | Hub | Carga de trabalho de execução de depósito em uma unidades de escala |
|--------------------------------------------------------------|-----|------------------------------|
| Processamento de documento de origem                                   | Sim | Não |
| Processamento de gerenciamento de transporte e carga                | Sim, mas somente os processos de planejamento de carga. O processamento de gerenciamento de transporte não é compatível  | Não |
| Recebimento de custo de entrega de mercadorias em trânsito                                         | Sim | Não |
| Liberar para o depósito                                         | Sim | Não |
| Distribuição integrada planejada                                        | Não  | Não |
| Consolidação da remessa                                       | Sim, ao usar planejamento de carga | Sim |
| Processamento de ciclo remessa                                     | Não  |Sim, exceto **Criação e classificação de carga** |
| Manter remessas para o ciclo                                  | Não  | Sim|
| Processamento de trabalho de depósito (incluindo a impressão da placa de licença)        | Não  | Sim, mas somente para os recursos mencionados anteriormente |
| Separação de cluster                                              | Não  | Sim|
| Processamento manual de embalagens, incluindo o processamento do trabalho "separação de contêiner embalado" | Não <P>É possível fazer processamentos parciais depois que um processo de separação inicial é manuseado por uma unidade de escala, mas não é recomendado devido às seguintes operações bloqueadas.</p>  | Não |
| Remover o contêiner do grupo                                  | Não  | Não |
| Processamento de classificação de saída                                  | Não  | Não |
| Impressão de documentos relacionados ao carregamento                           | Sim | Sim|
| Conhecimento de embarque e geração de ASN                            | Não  | Sim|
| Confirmação de remessa                                             | Não  | Sim|
| Confirmação de remessa com "confirmar e transferir"            | Não  | Não |
| Processamento de guia de remessa e faturamento                        | Sim | Não |
| Separação curta (ordens de venda e de transferência)                    | Não  | Sim, sem remover reservas de documentos de origem|
| Separação em excesso (ordens de venda e de transferência)                     | Não  | Sim|
| Alteração de locais de trabalho (ordens de venda e de transferência)         | Não  | Sim|
| Concluir trabalho (ordens de venda e de transferência)                    | Não  | Sim|
| Imprimir relatório de trabalho                                            | Sim | Sim|
| Etiqueta da onda                                                   | Não  | Sim|
| Divisão do trabalho                                                   | Não  | Sim|
| Processamento de trabalho - Dirigido por "carregamento de transporte"            | Não  | Não |
| Reduzir quantidade separada                                       | Não  | Não |
| Reverter trabalho                                                 | Não  | Não |
| Estornar confirmação da remessa                                | Não  | Sim|

### <a name="inbound"></a>Entrada

A tabela a seguir mostra quais recursos de entrada têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                                          | Hub | Carga de trabalho de execução de depósito em uma unidades de escala<BR>*(Os itens marcados como "Sim" aplicam-se somente a ordens de depósito)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Processamento&nbsp;de documento&nbsp;de origem                             | Sim | Não |
| Processamento de gerenciamento de transporte e carga                    | Sim | Não |
| Confirmação de remessa de entrada                                    | Sim | Não |
| Liberação da ordem de compra para depósito (processamento de ordem de depósito) | Sim | Não |
| Cancelamento de linhas da ordem de depósito<p>Observe que só haverá suporte quando nenhum registro tiver ocorrido contra a linha</p> | Sim | Não |
| Recebimento e armazenamento do item da ordem de compra                       | <p>Sim,&nbsp;quando&nbsp;não há&nbsp;uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, quando uma ordem de compra não faz parte de uma <i>carga</i></p> |
| Recebimento da linha da ordem de compra e armazenamento                       | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, quando uma ordem de compra não faz parte de uma <i>carga</i></p></p> |
| Recebimento e armazenamento da ordem de devolução                              | Sim | Não |
| Recebimento e armazenamento de placa de licença mista                       | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Sim |
| Recebimento do item de carga                                              | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento da placa de licença                             | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento e armazenamento do item da ordem de transferência                       | Sim | Não |
| Transferir recebimento e armazenamento do recebimento da linha de ordem                       | Sim | Não |
| Cancelar trabalho (entrada)                                            | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | <p>Sim, mas somente quando opção <b>Cancelar o registro do recebimento ao cancelar o trabalho</b> (na página <b>Parâmetros de gerenciamento de depósito</b>) estiver desmarcada</p> |
| Processamento do recebimento de produtos da ordem de compra                        | Sim | Não |
| Recebimento de ordem de compra com entrega insuficiente                      | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Sim, mas somente fazendo uma solicitação de cancelamento no hub |
| Recebimento de ordem de compra com entrega em excesso                       | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Sim  |
| Recebimento com a criação de trabalho de *Distribuição integrada*                 | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Ordem de qualidade*                  | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Amostra de ordem de qualidade*          | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de trabalho de *Qualidade na verificação de qualidade*       | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Recebimento com a criação de ordem de qualidade                            | <p>Sim, quando não há uma ordem de depósito</p><p>Não, quando há uma ordem de depósito</p> | Não |
| Processamento de trabalho - Dirigido por *armazenamento de cluster*                 | Sim | Não |
| Processamento de trabalho com *separação curta*                               | Sim | Não |
| Carregamento da placa de licença:                                           | Sim | Sim |

### <a name="warehouse-operations-and-exception-handing"></a>Operações de depósito e tratamento de exceções

A tabela a seguir mostra quais recursos de operações de depósito e tratamento de exceções têm suporte e onde, quando as cargas de trabalho de gerenciamento de depósito são usadas em unidades de escala de nuvem e de borda.

| Processar                                            | Hub | Carga de trabalho de execução de depósito em uma unidades de escala |
|----------------------------------------------------|-----|------------------------------|
| Consulta de placa de licença                              | Sim | Sim                          |
| Consulta de item                                       | Sim | Sim                          |
| Consulta de localização                                   | Sim | Sim                          |
| Alterar depósito                                   | Sim | Sim                          |
| Movimentação                                           | Sim | Sim                          |
| Movimento por modelo.                               | Sim | Sim                          |
| Transferência de depósito                                 | Sim | Não                           |
| Criar ordem de transferência do aplicativo de depósito           | Sim | Não                           |
| Ajuste (entrada/saída)                                | Sim | Sim, mas não para o cenário de ajuste, em que a reserva de estoque deve ser removida usando a configuração **Remover reservas** nos tipos de ajuste de estoque</p>                           |
| Alteração de Status do Estoque                            | Sim | Não                           |
| Processamento de contagem cíclica e discrepância de contagem | Sim | Sim                           |
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

A seguinte tabela resume quais cenários de produção do gerenciamento de depósito são compatíveis atualmente nas cargas de trabalho da unidade de escala.

| Processar | Hub | Carga de trabalho de execução de depósito em uma unidades de escala |
|---------|-----|------------------------------|
| Relatar como finalizado e guardar mercadorias finalizadas | Sim | Sim |
| Armazenamento de coproduto e subproduto | Sim | Sim |
| <p>Todos os outros processos do gerenciamento de depósito que são relacionados à produção, incluindo:</p><li>Liberar para o depósito</li><li>Processamento de ciclos de produção</li><li>Separação de matéria-prima</li><li>Armazenamento kanban</li><li>Separação kanban</li><li>Começar ordem de produção</li><li>Sucata de produção</li><li>Último palete de produção</li><li>Registrar consumo de materiais</li><li>Kanban vazio</li></ul> | Sim | Não |
| Reabastecimento de matéria-prima | Não | Não |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Manter unidades de escala para execução de depósito

Vários trabalhos em lotes são executados no hub e em unidades de escala.

Na implantação do hub, você pode manter manualmente os trabalhos em lotes. Você pode gerenciar estes trabalhos de lote em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho back office**:

- Processador de mensagens de unidade de escala para hub
- Registrar recebimentos de ordem de origem
- Concluir ordens de depósito

Na carga de trabalho em unidades de escala, você pode gerenciar estes trabalhos em lotes em **Gerenciamento de depósito \> Tarefas periódicas \> Gerenciamento de carga de trabalho**:

- Processar registros de tabela do ciclo
- Processador de mensagens da unidade de escala para o hub do depósito
- Processar solicitações de atualização de quantidade para linhas de ordem de depósito

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
