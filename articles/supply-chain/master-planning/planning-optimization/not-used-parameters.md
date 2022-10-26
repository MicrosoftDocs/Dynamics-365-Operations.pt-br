---
title: Parâmetros não usados pela Otimização de Planejamento
description: Este artigo lista os parâmetros que a Otimização de Planejamento atualmente não considera durante sua operação.
author: t-benebo
ms.date: 09/02/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: db8a8e929bf75c4d1dac0c1b0a7cbc848ff291a9
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682659"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Parâmetros não usados pela Otimização de Planejamento

[!include [banner](../../includes/banner.md)]

Este artigo lista os parâmetros que a Otimização de Planejamento atualmente não considera durante sua operação. O serviço de planejamento pode ignorar um parâmetro porque, por exemplo, a funcionalidade relacionada ainda não tem suporte. Outra possibilidade é que o parâmetro tenha se tornado obsoleto por causa de alterações funcionais.

As seções a seguir listam os parâmetros que a Otimização de Planejamento não usa em páginas específicas. Elas também explicam porque cada parâmetro não é usado.

## <a name="master-planning-parameters-page"></a>Página Parâmetros de planejamento mestre

A Otimização de Planejamento não usa os seguintes parâmetros ou opções na página **Parâmetros de planejamento mestre**:

- Guia **Geral**:

  - **Plano de previsão atual** – Suporte a *Previsão* pendente.
  - **Planejamento mestre estático atual** – Suporte a *Copiar plano estático para dinâmico* pendente.
  - **Planejamento mestre dinâmico atual** – Suporte a *Copiar plano estático para o dinâmico* pendente.
  - **Copiar o planejamento mestre completo e atualizado para o plano mestre dinâmico** – Suporte a *Copiar plano estático para o dinâmico* pendente.
  - **Hora de início para atrasos calculados** – Suporte a *Atrasos calculados* pendente.
  - **Usar dias negativos dinâmicos** – A Otimização de Planejamento sempre usa a abordagem *Dias negativos dinâmicos*.
  - **Calendário da data de hoje** – Suporte a *Agendamento* pendente.
  - **Uso do cache** – A configuração da assinatura do Microsoft Azure lida com pontos de desempenho.
  - **Número de tarefas no pacote de tarefas do assistente** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Pré-processando: filtrar automaticamente por itens com demanda direta** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Pós-processando: filtrar automaticamente por itens com demanda direta** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Número de ordens no pacote de confirmação** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Número de threads** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Tempo limite em minutos do processo de planejamento** – A configuração da assinatura do Azure lida com pontos de desempenho.
  - **Hora de início do agendamento** – Suporte a *Agendamento* pendente.

- Guia **Ordens planejadas**:

  - **Hora de recebimento** – Suporte a *Agendamento* pendente.
  - **Produção** – Suporte a *Agendamento* pendente.
  - Campos da seção **Projeto** – Suporte a *Agendamento* pendente.

## <a name="coverage-groups-page"></a>Página Grupos de cobertura

A Otimização de Planejamento não usa os seguintes parâmetros ou opções na página **Grupos de cobertura**:

- Guia Rápida **Geral**:

  - **Dias positivos** – o valor *Dias positivos* não é usado. Com a Otimização de Planejamento, os dias positivos são considerados infinitos.
  - **Consumir estoque disponível** – Suporte a *Consumo do estoque disponível* pendente.
  - **Usar a versão da BOM ou da fórmula especificada** – Suporte a *Versões de fórmula com Coproduto/Subproduto* pendente.
  - **Usar a versão de roteiro especificada** – Suporte a *Demanda pendente com requisitos específicos de BOM ou de roteiro definidos*.


- Guia Rápida **Outro**:

  - **Congelar limite de tempo (dias)** – O suporte à função *Congelar limite de tempo* não é planejada na Otimização de Planejamento.
  - **Limite de tempo de detalhamento da BOM (dias)** – Suporte a *Agendamento* pendente.
  - **Limite de tempo do agendamento de capacidade (dias)** – Suporte a *Agendamento* pendente.
  - **Limite de tempo da requisição aprovada (dias)** – Suporte a *Requisição* pendente.
  - **Limite de tempo do planejamento de previsões** – Suporte a *Previsão* pendente.

- Guia Rápida **Atrasos**:

  - **Atrasos calculados** – Suporte a *Atrasos calculados* pendente.
  - **Limite de tempo de atrasos calculados (dias)** – Suporte a *Atrasos calculados* pendente.

## <a name="item-coverage-page"></a>Página Cobertura de item

A Otimização de Planejamento não usa os seguintes parâmetros ou opções na página **Cobertura de item**:

- Guia **Geral**:

  - **Tipo de ordem planejada** – A Otimização de Planejamento não oferece suporte à opção *Kanban*, suporte a *Kanban* pendente.
  - **Congelar limite de tempo (dias)** – O suporte à função *Congelar limite de tempo* não é planejada na Otimização de Planejamento.
  - **Limite de tempo de detalhamento da BOM (dias)** – Suporte a *Agendamento* pendente.
  - **Limite de tempo do agendamento de capacidade (dias)** – Suporte a *Agendamento* pendente.
  - **Limite de tempo da requisição aprovada (dias)** – Suporte a *Requisição* pendente.
  - **Fornecimento mínimo** – A Otimização de Planejamento não oferece suporte às opções *Data de hoje*, *Primeira emissão* e *Limite de tempo de cobertura*. Ela sempre usa a opção *Data de hoje + tempo de aquisição*.
  - **Períodos mínimos** – Suporte a *Nível de estoque mínimo* pendente.
  - **Fórmula de planejamento** – Suporte a *Versões de fórmula com Coprodutos/Subprodutos* pendente.
  - **Prioridade padrão** – Suporte a *Versões de fórmula com Coprodutos/Subprodutos* pendente.
  - **Prioridade atual** – Suporte a *Versões de fórmula com Coprodutos/Subprodutos* pendente.
  - **Data alterada** – Suporte a *Versões de fórmula com Coprodutos/Subprodutos* pendente.
  - **Consumir estoque disponível** – Suporte a *Consumo do estoque disponível* pendente.

- Guia **Prazo de entrega**:

  - **Hora da compra** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.
  - **Tempo de produção** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.
  - **Tempo de transferência** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.
  - **Dias úteis** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.

## <a name="master-plans-page"></a>Página Planos mestres

A Otimização de Planejamento não usa os seguintes parâmetros ou opções na página **Planos mestres**:

- Guia Rápida **Geral**:

  - **Substituir disponível** – Suporte a *Consumo do estoque disponível* pendente.
  - **Consumir estoque disponível** – Suporte a *Consumo do estoque disponível* pendente.
  - **Incluir Cotações de venda** – Suporte a *Cotações de venda* pendente.
  - **Incluir solicitação de cotações** – Suporte a *Solicitação de cotações* pendente.
  - **Usar datas de validade** – Suporte a *Validade* pendente.
  - **Incluir plano de continuidade** – Suporte a *Agendamento de continuidade* pendente.
  - **Método de agendamento** – Suporte a *Agendamento* pendente.
  - **Propriedade finita** – Suporte a *Agendamento* pendente.
  - **Limite de tempo de capacidade de agendamento retroativa** – Suporte a *Agendamento* pendente.
  - **Capacidade finita** – Suporte a *Agendamento* pendente.
  - **Limite de tempo de capacidade finita** – Suporte a *Agendamento* pendente.
  - **Capacidade finita para recursos de afunilamento** – Suporte a *Agendamento* pendente.
  - **Limite de tempo da capacidade para recursos de afunilamento** – Suporte a *Agendamento* pendente.
  - **Ordens planejadas** – A Otimização de Planejamento usa sequências numéricas fixas.
  - **Sessão** – A Otimização de Planejamento usa sequências numéricas fixas.
  - **Planejamento de continuidade** – A Otimização de Planejamento usa sequências numéricas fixas.

- Guia Rápida **Limites de tempo em dias**:

  - **Congelar** - O suporte à função *Congelar limite de tempo* não é planejada na Otimização de Planejamento.
  - **Explosão** – Suporte a *Agendamento* pendente.
  - **Planejamento de previsões** – Suporte adicional a *Previsão* pendente.
  - **Capacidade** – Suporte a *Agendamento* pendente.
  - **Plano de continuidade** – Suporte a *Agendamento de continuidade* pendente.
  - **Atrasos calculados** – Suporte adicional a *Atrasos calculados* pendente.
  - **Sequenciamento** – Suporte a *Produção* pendente.

- Guia Rápida **Atrasos calculados**:

  - **Verifique se as ordens planejadas não foram criadas antes da data de execução do planejamento mestre** – Suporte a *Atrasos calculados* pendente.
  - **Adicionar o atraso calculado à data da necessidade** (na seção **Ordens de compra planejadas**) – Suporte a *Atrasos calculados* pendente.
  - **Adicionar o atraso calculado à data da necessidade** (na seção **Ordens de produção planejadas**) – Suporte a *Atrasos calculados* pendente.
  - **Adicionar o atraso calculado à data da necessidade** (na seção **Transferência planejada**) – Suporte a *Atrasos calculados* pendente.
  - **Adicionar o atraso calculado à data da necessidade** (na seção **Kanban planejado**) – Suporte a *Atrasos calculados* pendente.

- FastTab **Mensagem de ação**:

  - **Atualizar data adiada como data da requisição** - este parâmetro é descontinuado com Otimização de Planejamento.

- Guia rápida **Sequenciamento**:

  - **Ordens planejadas de sequência após o planejamento mestre** – Suporte a *Sequenciamento* pendente.
  - **Tipo de bucket** – Suporte a *Sequenciamento* pendente.
  - **Tipo de período** – Suporte a *Sequenciamento* pendente.
  - **Número de buckets no ciclo de campanha** – Suporte a *Sequenciamento* pendente.

## <a name="released-product-details-page"></a>Página Detalhes do produto liberado

A Otimização de Planejamento não usa o seguintes parâmetro ou opção na página **Detalhes do produto lançado**:

- Guia rápida **Engenheiro**:

  - **Tipo de produção** – Otimização de Planejamento não oferece suporte à opção *Item de planejamento*, suporte a *Itens de planejamento* pendente.

## <a name="default-order-settings-page"></a>Página Configurações padrão da Ordem

A Otimização de Planejamento não usa o seguintes parâmetro ou opção na página **Configurações padrão da ordem**:

- Guia Rápida **Ordem de compra**:

  - **Prazo de entrega da compra** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.
  - **Dias úteis** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.

- Guia rápida **Estoque**:

  - **Controle da data de entrega** – A Otimização de Planejamento não oferece suporte à opção *CTP*, suporte a *CTP* pendente.
  - **Prazo de entrega do estoque** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.
  - **Dias úteis** – Em versões do serviço Otimização de Planejamento mais antigas do que a versão de 6 de agosto de 2021, a Otimização de Planejamento usa esse parâmetro para calcular as datas de ordem e de entrega corretas, mas não salva o prazo de entrega calculado por si só na ordem planejada. Em versões posteriores, o serviço também usa o prazo de entrega calculado para definir o campo **Prazo de entrega** e a opção **Dias úteis**, conforme necessário para a ordem planejada relevante.

## <a name="batch-disposition-master-page"></a>Página Disposição em lotes principal

A Otimização de Planejamento não usa o seguinte parâmetro na página **Disposição em lotes principal**:

- Guia rápida **Configuração**:

  - **Líquido** – Suporte a *Códigos de disposição em lote* pendente.
 
