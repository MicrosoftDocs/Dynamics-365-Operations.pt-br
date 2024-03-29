---
title: Visão geral do Assistente de otimização
description: Este artigo descreve como você pode usar o Assistente de otimização para ajudar a garantir a configuração ideal dos aplicativos de finanças e operações.
author: kamaybac
ms.date: 07/23/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.author: kamaybac
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.assetid: ''
ms.search.industry: ''
ms.search.form: SelfHealingWorkspace
ms.openlocfilehash: f24e8dfecb04f928994bb5a197d32a7279022512
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281345"
---
# <a name="optimization-advisor-overview"></a>Visão geral do Assistente de otimização

[!include [banner](../includes/banner.md)]

Este artigo descreve como você pode usar o Assistente de otimização para ajudar a garantir a configuração ideal dos aplicativos de finanças e operações.

## <a name="overview"></a>Visão geral

A definição e a configuração incorretas de um módulo podem afetar negativamente a disponibilidade de recursos de aplicativos, o desempenho do sistema e a operação suave dos processos de negócios. A qualidade dos dados corporativos (por exemplo, exatidão, integridade e limpeza de dados) também afeta o desempenho do sistema e recursos de tomada de decisão da organização, produtividade etc.

O espaço de trabalho **Orientador de otimização** é uma ferramenta que permite que os usuários avançados, analistas comerciais, consultores funcionais e funções de suporte de TI identifiquem problemas na configuração do módulo e nos dados de negócios. O orientador de otimização sugere práticas recomendadas para a configuração do módulo e identifica os dados corporativos que estão obsoletos ou são incorretos.

O orientador de otimização executa periodicamente um conjunto de regras de prática recomendada. Um conjunto padrão de regras está disponível, entretanto, os usuários também podem criar regras específicas às suas personalizações, soluções de fornecedores independentes de software (ISVs) e dados corporativos. Para obter mais informações sobre como criar regras, consulte [Criar regras para o Supervisor de otimização](./create-rules-optimization-advisor.md).

Quando for detectada uma violação de regra, uma oportunidade de otimização será gerada e aparecerá no espaço de trabalho **Orientador de otimização**. Um usuário pode executar a ação corretiva adequada diretamente do espaço de trabalho **Orientador de otimização**.

As oportunidades podem ser entre empresas ou específicas da empresa, dependendo do tipo de configuração e dos dados que estão sendo validados. A oportunidades entre empresas podem ser vistas de todas as empresas. Para exibir as oportunidades de uma empresa específica, primeiro, é necessário selecionar a empresa.

As políticas de segurança padrão se aplicam às oportunidades de otimização. Por exemplo, as oportunidades de otimização relacionadas à configuração do módulo **Gerenciamento de depósito** são visíveis somente a usuários que têm acesso ao gerenciamento de depósito e podem alterar sua configuração.

Quando você toma a ação em algumas oportunidades de otimização, o sistema calcula o impacto de oportunidade em termos de redução no tempo de execução de processos comerciais. Infelizmente, este recurso não está disponível para todas as oportunidades de otimização.

Para saber mais sobre o Assistente de otimização, assista ao vídeo curto [Assistente de otimização no Dynamics 365 Finance](https://www.youtube.com/watch?v=MRsAzgFCUSQ).

## <a name="optimization-rules"></a>Regras de otimização

Para exibir a lista completa de regras do orientador de otimização e ver com que frequência as regras são avaliadas, Acesse **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Manter regra de validação de diagnóstico**. Somente as regras que têm um status **Ativo** são avaliadas. A frequência de avaliação pode ser definida como **Diária**, **Semanal**, **Mensal** ou **Não programada**.

Para acionar a avaliação de regras não programadas ou reavaliar as regras periódicas fora de sua programação predefinida, Acesse **Administração do sistema** &gt; **Tarefas periódicas** &gt; **Agendar regra validação de diagnóstico**. Em seguida, na caixa de diálogo **Validação de regra de diagnóstico**, selecione uma frequência de avaliação. Todas as regras com a frequência especificada serão reavaliadas.

O conjunto de regras de otimização atual pode ser dividido nas seguintes categorias.

### <a name="module-configuration-and-setup"></a>Configuração e definição do módulo

A configuração de um Gerenciamento de depósito é um processo complicado. Para facilitar o processo, algumas regras foram introduzidas para ajudar a validar a exatidão da configuração. Por exemplo, uma regra valida a configuração de diretivas do local de depósito para localizações fixas de grade do produto para ordens de venda e ordens de transferência.

Além disso, algumas regras verificam se os recursos que foram habilitados são efetivamente usados. Por exemplo, uma regra determina se você está usando o módulo **Planejamento mestre**. Se a regra determinar que você não está usando o módulo, uma oportunidade de otimização é gerada para sugerir que você desative os processos de planejamento.

### <a name="system-configuration"></a>Configuração do sistema

Se a funcionalidade específica que é controlada por uma chave de configuração não for usada, uma oportunidade de otimização será gerada para sugerir que você desabilite a chave de configuração. Os exemplos de chaves de configuração incluem **Peso variável**, **Plano de orçamento**, **Projeto** e **Lista de fornecedores aprovados**.

### <a name="business-data-consistency-and-cleanup"></a>Consistência e limpeza de dados comerciais

Se os dados mestres não estiverem corretos (por exemplo, se você tiver as conversões de unidade de medida para as unidades que não foram definidas, ou se você tiver as conversões de unidade de medida com uma divisão por 0 \[zero\]), uma oportunidade de otimização será gerada para sugerir que você corrija os dados. 

Se você tiver muitas entradas do histórico de trabalho em lotes, itens obsoletos, entradas disponíveis fechadas para itens ativados por depósito etc, ou se as entradas e os itens forem muito antigos, as oportunidades de otimização serão geradas para sugerir que você limpe os dados. A manutenção da limpeza dos dados ajuda a melhorar o desempenho geral do sistema.

### <a name="best-practices"></a>Práticas Recomendadas

Se não estiver executando alguns processos de negócios, de acordo com as práticas recomendadas (por exemplo, se você executar um pré-fechamento de estoque antes do estoque ser fechado, ou se você usar um lote programado para transferência em lotes para diários-razão auxiliares), as oportunidades de otimização o informarão sobre a melhor prática e solicitarão que você a siga.

## <a name="optimization-opportunities"></a>Oportunidades de otimização

Para exibir as oportunidades de otimização geradas durante a avaliação de regras de otimização, abra o espaço de trabalho **Orientador de otimização**.

Neste espaço de trabalho, você poderá exibir mais informações sobre a oportunidade, selecionando **Mais informações**. Se quiser que o sistema execute uma ação e corrija a configuração, limpe os dados, de forma que não seja necessário abrir suas próprias páginas correspondentes, selecione **Executar ação**.

Não há fluxo de trabalho para oportunidades de otimização. Após selecionar **Executar ação** ou usar um caminho de navegação fornecido na caixa de diálogo **Mais informações**, a oportunidade de otimização desaparecerá da lista. Se a ação corretiva não resolver completamente um problema, a oportunidade será gerada novamente na próxima vez que a regra for avaliada.

Se uma oportunidade não se aplicar à sua função, será possível selecionar **Ocultar da lista**. Se a regra desta oportunidade for acionada novamente mais tarde, você não poderá ver a oportunidade na sua lista.

Para desativar a avaliação de regras específicas, selecione a oportunidade que foi gerada pela regra e depois selecione **Desativar análise**.

## <a name="additional-resources"></a>Recursos adicionais

[Criar regras para o Supervisor de otimização](./create-rules-optimization-advisor.md)

[Assistente de otimização no Dynamics 365 Finance (vídeo)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
