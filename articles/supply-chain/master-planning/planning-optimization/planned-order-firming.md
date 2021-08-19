---
title: Confirmar ordens planejadas
description: Este tópico explica como confirmar ordens planejadas. Quando as ordens planejadas forem confirmadas, elas se tornarão ordens de compra, ordens de transferência ou ordens de produção reais.
author: ChristianRytt
ms.date: 04/22/2021
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 966a878a7e5b0a92d6d53e67bea19c50274087a4416980859175b12c6fdfbcdc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764827"
---
# <a name="firm-planned-orders"></a>Confirmar ordens planejadas

[!include [banner](../../includes/banner.md)]

As ordens planejadas devem ser *confirmadas* (ou seja, liberadas) como parte do processo de planejamento mestre. Quando as ordens planejadas forem confirmadas, elas se tornarão ordens de compra, ordens de transferência ou ordens de produção reais. Essas ordens também são conhecidas como *ordens liberadas* ou *ordens em aberto*.

Há três métodos para confirmar ordens planejadas:

- **Confirmação manual** – selecione ordens planejadas específicas em uma lista e inicie o processo manualmente.
- **Confirmação automática** – defina um limite de tempo de confirmação padrão para grupos de cobertura, itens individuais e combinações de itens e planos mestre. Em seguida, durante as execuções do planejamento mestre, as ordens planejadas serão confirmadas automaticamente se a data da ordem estiver no limite de tempo especificado para a confirmação.
- **Confirmação baseada em consulta** – defina uma consulta para selecionar ordens planejadas com base em suas propriedades. Você pode configurar um trabalho em lotes para executar a consulta e confirmar ordens correspondentes em uma agenda regular.

Este tópico descreve cada método em detalhes.

## <a name="enable-the-features-that-are-described-in-this-topic"></a><a name="enable-features"></a>Habilite os recursos descritos neste tópico

A maioria dos recursos de ordem planejada estão disponíveis em todas as instalações padrão do Microsoft Dynamics 365 Supply Chain Management que usam a Otimização do Planejamento. No entanto, alguns dos recursos descritos neste tópico devem estar habilitados no gerenciamento de recursos para que você possa usá-los.

### <a name="enable-parallelized-firming-of-planned-orders"></a>Habilitar confirmação paralelizada de ordens planejadas

A confirmação paralelizada ajuda a acelerar o processo de confirmação ao paralelizá-la em vários threads. Essa abordagem pode ser útil quando muitas ordens planejadas são confirmadas.

Para disponibilizar esta funcionalidade no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Confirmação paralela de ordens planejadas*.

### <a name="enable-planned-order-firming-with-filtering"></a>Habilitar confirmação de ordem planejada com filtragem

A confirmação de ordens planejadas com filtragem permite definir critérios lógicos para selecionar quais ordens planejadas devem ser confirmadas. Você também pode visualizar quais ordens planejadas foram selecionadas, executar o processo em segundo plano e/ou agendá-la como um trabalho em lotes.

Para disponibilizar esta funcionalidade no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Confirmação de ordem planejada com filtragem*.

### <a name="enable-auto-firming-for-planning-optimization"></a>Habilitar confirmação automática para Otimização do Planejamento

A confirmação automática permite que você confirme ordens planejadas como parte do processo de planejamento mestre durante o limite de tempo de confirmação. A confirmação automática sempre tem suporte para o mecanismo de planejamento criado no Supply Chain Management. No entanto, para também usá-la com a Otimização de Planejamento, você deve ativar o recurso.

Para disponibilizar esta funcionalidade no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Confirmação automática para Otimização de Planejamento*.

## <a name="manually-firm-planned-orders"></a>Confirmar manualmente ordens planejadas

Para confirmar manualmente ordens planejadas, você encontra e seleciona as ordens planejadas que deseja confirmar e, depois, inicia manualmente o processo de confirmação.

1. [Abrir qualquer página de listagem de ordens planejadas](approved-planned-order.md#view-planned-orders).
1. Use o campo **Filtro**, o campo **Plano** e títulos de coluna para filtrar e classificar a lista para localizar as ordens planejadas que você procura.
1. Marque a caixa de seleção para cada ordem planejada a ser confirmada. Se você desejar confirmar todas as ordens planejadas que estão listadas no momento na página (com base nos filtros aplicados), ignore esta etapa.
1. No Painel de Ações, selecione um dos seguintes botões:

    - **Confirmar** – confirma somente as ordens planejadas selecionadas.
    - **Confirmar tudo** – confirme todas as ordens planejadas que estão listadas no momento na página (com base nos filtros aplicados), independentemente das caixas de seleção selecionadas. Essa opção poderá ser útil se você estiver confirmando várias ordens planejadas.

1. Na caixa de diálogo **Confirmação**, na FastTab **Parâmetros**, defina os campos a seguir. (Muitos desses campos assumem valores padrão da guia **Atualização padrão** na página **Parâmetros do planejamento mestre**.)

    - **Atualizar marcação** – Selecione a política de marcação de estoque a ser usada quando ordens planejadas forem confirmadas.
    - **Interromper confirmação se ocorrer um erro** – defina esta opção como *Sim* para interromper a confirmação de todas as ordens planejadas selecionadas se ocorrer um erro em uma delas. Esta opção deverá ser definida como *Não* se a opção **Confirmação de paralelização** estiver definida como *Sim*.
    - **Paralelizar confirmação** – esta opção só estará disponível se o [ recurso *Confirmação paralela de ordens planejadas*](#enable-features) estiver ativado no sistema e se você tiver selecionado duas ou mais ordens planejadas para confirmação. Defina-a como *Sim* para executar os processos de confirmação em paralelo. A confirmação paralela pode ajudar a melhorar o desempenho.
    - **Número de threads** – esta opção só estará disponível se o [recurso *Confirmação paralela de ordens planejadas*](#enable-features) estiver ativado no sistema e se você tiver definido a opção **Paralelizar confirmação** como *Sim*. Insira o número de threads a serem usados para paralelizar o processo de confirmação. Para obter conselhos sobre como usar esta opção no planejamento mestre, consulte [Melhorar o desempenho do planejamento mestre](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Uma valor *0* (zero) do campo **Número de threads** aumenta o tempo de execução do planejamento mestre. Portanto, é recomendável sempre definir este campo com um valor maior que 0.

    - **Agrupar por fornecedor** – defina esta opção como *Sim* para agrupar ordens de compra planejadas e criar uma ordem de compra por fornecedor durante a confirmação. Como alternativa, você pode criar uma ordem de compra que tem uma linha para cada ordem planejada.
    - **Agrupar por grupo de compradores** – defina esta opção como *Sim* para agrupar ordens de compra planejadas e criar uma ordem de compra que combine o grupo de fornecedores e compradores. Para usar esta opção, você também deve definir a opção **Agrupar por fornecedor** como *Sim*.
    - **Agrupar por contrato de compra**: defina esta opção como *Sim* para agrupar ordens de compra planejados que têm o mesmo fornecedor dos contratos de compra existentes e criar uma ordem de compra por contrato de compra. Esta opção é ativada automaticamente quando **Agrupar por fornecedor** é ativado. Para usar **Agrupar por contrato de compra**, a opção **Localizar contratos de compra** deve ser definido como *Sim* na página **Parâmetros de planejamento mestre**.
    - **Agrupar por período** (na seção **Ordens de compra**) – Selecione o período para o qual agrupar ordens de compra planejadas. Para usar esta opção, você também deve selecionar a opção **Agrupar por fornecedor**.
    - **Agrupar por período** (na seção **Transferências**) – Selecione o período para o qual agrupar ordens de transferência planejadas. As ordens serão agrupadas com base nos valores **De depósito** e **Para depósito**.

    ![FastTab Parâmetros na caixa de diálogo Confirmação.](./media/manual-firming.png "FastTab Parâmetros na caixa de diálogo Confirmação")

1. Na FastTab **Executar em segundo plano**, configure o trabalho para que ele seja executado no modo de lotes. Mas, não faz sentido configurar uma agenda recorrente quando você confirma manualmente. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management. No entanto, para a confirmação manual, o trabalho em lotes processará apenas as ordens planejadas selecionadas no momento. Ele não processará ordens que atendam aos filtros aplicados no momento na página.
1. Selecione **OK** para aplicar suas configurações e gerar as ordens confirmadas.

## <a name="auto-firm-planned-orders"></a>Confirmação automática de ordens planejadas

A confirmação automática permite que você confirme ordens planejadas como parte do processo de planejamento mestre. Você pode definir um limite de tempo de confirmação para grupos de cobertura, itens individuais e combinações de itens e planos mestre. Em seguida, durante as execuções do planejamento mestre, as ordens planejadas serão confirmadas automaticamente se a data da ordem estiver no limite de tempo especificado para a confirmação. As ordens planejadas geradas pela otimização de planejamento e a operação de planejamento mestre interno tratam a data da ordem (ou seja, a data de início) de modo diferente.

> [!NOTE]
> A confirmação automática de ordens de compra planejada só poderá ocorrer para itens associados a um fornecedor.
> 
> As ordens derivadas (ou seja, ordens de compra do subcontratado) que forem confirmadas terão um status *Em revisão* se o controle de alterações estiver ativado.

> [!IMPORTANT]
> Para que o recurso descrito nesta seção possa ser usado com otimização de planejamento, o [recurso *Confirmação automática para otimização de planejamento*](#enable-features) deve estar ativado no sistema, conforme descrito no início deste tópico. A confirmação automática sempre pode ser usada com o mecanismo de planejamento mestre interno.

### <a name="auto-firming-with-planning-optimization-vs-the-built-in-planning-engine"></a>Confirmação automática com otimização de planejamento x o mecanismo de planejamento interno

A otimização de planejamento e o mecanismo de planejamento interno podem ser usados para ordens planejadas de confirmação automática. No entanto, há alguns diferenças importantes. Por exemplo, a otimização de planejamento usa a data da ordem (ou seja, a data de início) para determinar quais ordens planejadas devem ser confirmadas, enquanto o mecanismo de planejamento interno usa a data de requisição (ou seja, a data de término). A tabela a seguir resume as diferenças.

| Recurso | Otimização do Planejamento | Mecanismo de planejamento interno |
|---|---|---|
| **Base de data** | A confirmação automática se baseia na data da ordem (data inicial). | A confirmação automática se baseia na data de requisição (data final). |
| **Lead time** | Como a data da ordem (data inicial) dispara a confirmação, você não precisa considerar o prazo de entrega como parte do limite de tempo de confirmação. | Para ajudar a garantir que as ordens sejam confirmadas em tempo hábil, o limite de tempo de confirmação deverá ser superior ao prazo de entrega. |
| **Ordens da semana atual** | Para confirmar todas as ordens que devam começar na semana atual, o limite de tempo de confirmação deverá ser de uma semana. | Para confirmar todas as ordens que devam começar na semana atual, o limite de tempo de confirmação deverá ser o prazo de entrega mais uma semana. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Configurar confirmação automática e o limite de tempo de confirmação

Ative a confirmação automática atribuindo um limite de tempo de confirmação automatizado à configuração de cobertura relevante, conforme descrito mais adiante nesta seção. Se a confirmação automática não estiver ativada para uma configuração de cobertura ou se o planejamento for iniciado em uma página específica, como a página **Requisitos líquidos** para um produto liberado, o processo de confirmação automática será ignorado.

As opções de agrupamento e marcação para confirmação automática obtêm valores da guia **Atualização padrão** na página **Parâmetros de planejamento mestre**.

O limite de tempo de confirmação automática é definido pelo número de dias que você insere para a configuração de cobertura relevante. Você pode ativar a confirmação automática e controlar o limite de tempo de confirmação das seguintes maneiras:

- Para definir o limite de tempo de confirmação padrão para um grupo de cobertura, acesse **Planejamento mestre \> Configuração \> Cobertura \> Grupos de cobertura** e selecione um grupo de cobertura. Em seguida, na Guia Rápida **Outro**, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.
- Para substituir o limite de tempo de confirmação definido para o grupo de cobertura de um item específico, acesse **Gerenciamento de informações do produto \> Produtos liberados**. No Painel de Ações, selecione **Plano** e, depois, **Cobertura de item**. Na guia **Geral**, selecione **Limite de tempo de substituição** e, no campo **Limite de tempo de confirmação automática (dias)**, insira o número de dias.
- Para substituir o limite de tempo de confirmação definido para o grupo de cobertura e a cobertura de item para um plano mestre específico, acesse **Planejamento mestre \> Configuração \> Planos mestres** e selecione um plano mestre. Em seguida, na FastTab **Limite de tempo em dias**, defina a opção **Confirmação** como *Sim* e insira o número de dias.

Se você definir todos os limites de tempo mencionados anteriormente como *0* (zero), a confirmação automática será efetivamente desabilitada para os itens cobertos relevantes.

## <a name="firm-planned-orders-by-using-a-query"></a>Confirmar ordens planejadas usando uma consulta

A confirmação baseada em consulta permite planejar a confirmação com base em critérios definidos com antecedência. Diferente da confirmação automática, a confirmação baseada em consulta permite a confirmação automatizada de diferentes subconjuntos de ordens em diferentes pontos no tempo. Além disso, você pode usar operações manuais ou automatizadas para confirmar diferentes tipos de ordens planejadas. Você também pode visualizar quais ordens confirmadas são selecionadas com base em suas configurações. Portanto, você pode confirmar que a seleção atende às suas expectativas.

Você pode combinar a confirmação automática com a confirmação baseada em consulta. Por exemplo, um trabalho de confirmação baseado em consulta tem um limite de tempo de avanço maior do que o limite de tempo para uma configuração de cobertura de confirmação automática correspondente. Portanto, o trabalho de confirmação baseado em consulta processará as ordens planejadas antes do disparo da confirmação automática. Você pode aproveitar esse comportamento para agendar ordens para fornecedores específicos de forma diferente das ordens de produtos semelhantes de outros fornecedores.

> [!IMPORTANT]
> Para que o recurso descrito nesta seção possa ser usado, o [recurso *Confirmação de ordem planejada com filtragem*](#enable-features) deve ser ativado no sistema, conforme descrito no início deste tópico.

Para confirmar uma ordem planejada usando o processo de confirmação baseado em consulta, siga estas etapas.

1. Acesse **Planejamento mestre \> Planejamento mestre \> Executar \> Confirmação de ordem planejada**.
1. Na caixa de diálogo **Confirmação de ordem planejada**, na FastTab **Parâmetros**, defina as opções básicas de processamento, marcação e agrupamento. Essas opções funcionam da mesma forma que na caixa de diálogo **Confirmação**. (Consulte a seção anterior para obter descrições.) Em seguida, na seção **Plano**, defina os seguintes campos exclusivos da caixa de diálogo **Confirmação de ordem planejada**:

    - **Plano** – Selecione o planejo mestre que deve ser aplicado durante a confirmação das ordens planejadas localizadas por esta consulta.
    - **Limite de tempo de confirmação em dias à frente** – Selecione até que ponto, no futuro, os diversos requisitos e outras considerações devem ser calculados pelo planejamento mestre.
    - **Limite de tempo de confirmação em dias anteriores** – Selecione até que ponto, no passado, os diversos requisitos e outras considerações devem ser calculados pelo planejamento mestre.

    ![FastTab Parâmetros na caixa de diálogo Confirmação de ordem planejada.](./media/planned-order-firming-main-1.png "FastTab Parâmetros na caixa de diálogo Confirmação de ordem planejada")

1. Para especificar quais registros devem ser incluídos na ordem, selecione o botão **Filtrar** na FastTab **Registros a serem incluídos**. Uma caixa de diálogo de consulta padrão é exibida, na qual você pode definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Supply Chain Management. Os campos aqui são somente leitura e mostram os valores relacionados à sua consulta.

    ![FastTab Registros a serem incluídos na caixa de diálogo Confirmação de ordem planejada.](./media/planned-order-firming-main-2.png "FastTab Registros a serem incluídos na caixa de diálogo Confirmação de ordem planejada")

1. Selecione **Visualizar** para visualizar o conteúdo da ordem confirmada, com base nas suas configurações até o momento. A lista de ordens planejadas que será confirmada aparece como uma mensagem. Em seguida, você pode ajustar as configurações conforme necessário até que a versão prévia mostre a ordem confirmada pretendida.

    ![Exemplo de uma versão prévia de ordem confirmada.](./media/planned-order-firming-preview.png "Exemplo de uma versão prévia de ordem confirmada")

    > [!WARNING]
    > Este recurso confirmará todas as ordens planejadas que correspondem aos critérios de filtro. A confirmação indiscriminada de ordens planejadas pode levar à criação de muitas ordens de produção, transferência e compra indesejadas. Antes de continuar, use sempre o botão **Visualizar** para validar os registros que serão incluídos.

1. Na FastTab **Executar em segundo plano**, configure o trabalho para que ele seja executado no modo de lotes e/ou configure uma agenda recorrente. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e gerar as ordens confirmadas.

## <a name="track-firmed-orders"></a>Rastrear ordens confirmadas

Para rastrear uma ordem planejada que foi confirmada, siga estas etapas.

1. [Abrir qualquer página de listagem de ordens planejadas](approved-planned-order.md#view-planned-orders).
1. Abra ou selecione a ordem planejada a ser rastreada.
1. No Painel de Ações, na guia **Exibir**, no grupo **exibir**, selecione **Histórico de confirmação**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
