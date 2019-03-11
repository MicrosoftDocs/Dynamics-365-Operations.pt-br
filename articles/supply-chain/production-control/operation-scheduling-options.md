---
title: Opções de plano de operações
description: Este tópico descreve as opções para o plano de operações. Você pode usar o plano de operações para fornecer uma estimativa geral do processo de produção ao longo do tempo.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f3c9c40437d368b006b0f2b5a2ddd65d228ac87
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "317950"
---
# <a name="operations-scheduling-options"></a>Opções de plano de operações

[!include [banner](../includes/banner.md)]

Este tópico descreve as opções para o plano de operações. Você pode usar o plano de operações para fornecer uma estimativa geral do processo de produção ao longo do tempo.

O plano de operações calcula as seguintes informações de uma ordem de produção:

-   Datas iniciais e finais são definidas para a ordem de produção e para cada operação.
-   Recursos são atribuídos às operações.

Várias configurações determinam como as agendas de produção são calculadas. Você define essas configurações na página **Plano de operações**. As informações a seguir descrevem as opções de agendamento.

## <a name="operations-scheduling"></a>Plano de operações
### <a name="scheduling-direction"></a>Direção do plano

A direção do plano é fundamental para o processo de planejamento. A produção pode ser agendada para frente ou para trás a partir de qualquer data, dependendo dos requisitos de tempo e de agendamento.

-   **Planejamento antecipado**– você pode agendar uma produção para iniciar o mais rápido possível. A produção pode ser iniciada hoje, amanhã ou em qualquer data futura específica. A produção é agendada para iniciar na primeira data possível e é adiantada no tempo até a primeira data final possível.
-   **Planejamento regressivo** – você pode agendar uma produção para iniciar o mais tarde possível. A agenda é baseada na data em que a produção deve ser concluída e faz a contagem regressiva até a última data possível em que a produção pode ser iniciada sem que o prazo final seja perdido.

As opções a seguir estão disponíveis:

-   **Avançar a partir de hoje** – a agenda avança a partir da data atual. (A data atual é a data do sistema.)
-   **Avançar do início planejado** – a agenda avança a partir de uma data inicial anterior. Se não houver nenhum plano anterior, a direção do plano será avançar a partir da data atual.
-   **Avançar a partir da data do plano** – avança o planejamento a partir da data especificada no campo **Data de planejamento**. Se você não especificar a data de planejamento, a direção do plano será avançar a partir da data atual.
-   **Voltar a partir da data de entrega** – retrocede o agendamento a partir da data de entrega especificada para a ordem de produção Se você selecionar esta opção mas nenhuma data de entrega estiver especificada, ela será definida como a data atual.
-   **Retroceder do fim planejado** – retrocede o agendamento a partir de uma data de término previamente calculada. Se não houver nenhum agendamento anterior, a data final será definida como a data atual.
-   **Voltar a partir da data do plano** – retrocede o agendamento a partir da data especificada no campo **Data de planejamento**. Se você não especificar a data de agendamento, a data atual será usada. A data de retrocesso do agendamento é calculada para a ordem de produção na última vez em que uma requisição foi calculada Se nenhuma data de ação for especificada para a ordem de produção, a data atual do sistema será usada.
-   **Voltar a partir das datas futuras** – retrocede o agendamento a partir da data futura que foi calculada para a ordem de produção na última vez em que uma requisição foi calculada. Se nenhuma data futura for especificada para a ordem de produção, a data atual do sistema será usada.
-   **Como no último plano** – para o plano de operações e de trabalho, a direção e a data do plano selecionadas são salvas. Portanto, você pode selecionar esta opção para planos subsequentes. Se não houver nenhum plano anterior da ordem de produção, o plano retrocederá a partir da data atual do sistema.
-   **Avançar a partir de amanhã** – o agendamento avança a partir da data de hoje acrescida de um dia.
-   **Avançar a partir do trabalho anterior** – esta opção é relevante somente no planejamento de trabalho. Se você selecionar esta direção para o plano de operações, a ordem de produção será programada para uma data futura a partir da data atual. No planejamento de trabalho, o plano é estabelecido para um trabalho, e todos os outros trabalhos para a produção serão programados com base nesse trabalho.
-   **Voltar a partir do trabalho anterior** – esta opção é relevante somente no planejamento de trabalho. Se você selecionar esta direção para o plano de operações, as ordens planejadas retrocederão a partir da data atual. No planejamento de trabalho, o plano é estabelecido para um trabalho, e todos os outros trabalhos para a produção serão programados com base nesse trabalho.

### <a name="scheduling-date"></a>Data de planejamento

Esta data é usada para as direções de plano **Avançar a partir da data do plano** e **Voltar a partir da data do plano**. É feito um planejamento regressivo ou antecipado em relação a essa data. Para saber mais, consulte a seção anterior, "Direção do plano".

### <a name="recalculate-bom-levels"></a>Recalcular níveis de BOM

Quando você seleciona **Recalcular níveis de BOM**, os níveis selecionados (BOM) da lista de materiais serão recalculados para ajudar a garantir a ordem de agendamento correta.

## <a name="limitations"></a>Limitações
### <a name="finite-capacity"></a>Capacidade finita

O agendamento depende da disponibilidade dos recursos que são necessários para concluir a produção. Se não houver capacidade suficiente, as ordens de produção poderão atrasar ou até mesmo ser interrompidas. Se a capacidade finita for aplicada ao plano de operações, as reservas de capacidade existentes que são feitas nos recursos serão consideradas e essa capacidade será vista como indisponível. A ordem de produção será agendada com base na disponibilidade de capacidade nos recursos que são necessários. O agendamento de operações usa a sequência especificada de operações para determinar a ordem das operações no roteiro de produção. O plano de operações reserva a capacidade nos grupos de recursos com base nos tempos de operação definidos no roteiro de produção. A capacidade dos grupos de recursos é a soma da capacidade disponível em todos os recursos nos grupos de recursos.

### <a name="finite-material"></a>Material finito

O agendamento também depende da disponibilidade dos materiais necessários para a produção. A disponibilidade insuficiente de componentes também pode causar atrasos na produção. O agendamento também pode ser baseado no uso de materiais. Basta especificar os materiais que devem estar disponíveis para produção em vez dos materiais que não sejam críticos. Esse tipo de agendamento é conhecido como plano com material finito. Quando você especifica materiais finitos, a produção é agendada com base na disponibilidade dos materiais. **Observação:** ao otimizar a capacidade e os materiais, a produção será calculada de forma a atender as duas restrições. A disponibilidade de capacidade e de materiais será considerada, e as operações da ordem de produção não poderão ser agendadas para iniciar até que a capacidade e os materiais estejam disponíveis ao mesmo tempo e nas quantidades necessárias. Marque esta caixa de seleção se os materiais devem ser considerados limitados durante o agendamento. Se o material for limitado, a cobertura do material para aquela hora será considerada. Em outras palavras, o planejamento leva em consideração as datas futuras que são calculadas para os itens. O plano reserva matéria-prima e detalha a produção atual. Se o agendamento ocorrer várias vezes, somente o primeiro agendamento executará um detalhamento e fará as reservas. Se você fizer alterações no roteiro ou na BOM de produção, o próximo agendamento executará um detalhamento. Para o detalhamento, presume-se que os materiais sejam necessários no mesmo dia. Como a produção não está agendada no momento do detalhamento do planejamento mestre, a data atual é a melhor estimativa de quando os itens estarão disponíveis. O detalhamento verifica, em seguida, se os itens estão disponíveis. Se estiverem, o requisito de produção pode se cumprido. Se os itens não estiverem disponíveis até a data atual, uma ordem planejada será gerada e será feita uma seleção de compensação para a ordem planejada. Se a confirmação automática for configurada para a ordem planejada, ela será confirmada automaticamente para compra ou para produção. O status da produção será alterado automaticamente para o status especificado no campo **Status de produção solicitado**, na caixa de diálogo **Grupos de cobertura**. Se a caixa de seleção for desmarcada, os materiais serão sempre considerados como disponíveis. Portanto, o plano não considera se os materiais estão disponíveis no momento da requisição.

### <a name="finite-property"></a>Propriedade finita

Marque esta caixa de seleção se o plano de trabalho deve incluir requisições de propriedade.

### <a name="keep-production-unit"></a>Manter unidade de produção

Selecione se o mecanismo de agendamento deve agendar somente os recursos que já estão especificados na unidade de produção.

### <a name="keep-warehouse-from-resource"></a>Manter depósito do recurso

Selecione se o mecanismo de agendamento deve agendar somente os recursos associados ao depósito de entrada especificado no recurso.

## <a name="references"></a>Referências
### <a name="schedule-references"></a>Referências de plano

Quando as referências dependem das ordens de produção, elas também são conhecidas como subproduções. As subproduções pode ser agendadas como parte do agendamento de uma ordem de produção. Marque esta caixa de seleção se o agendamento de subproduções deve ser baseado no agendamento da produção principal. Em relação à produção principal, o agendamento das produções sobrejacentes será antecipado, enquanto o das produções subjacentes será regressivo. As referências das ordens de produção podem ser exibidas no campo **Nível de referência** na página **Ordens de produção**.

### <a name="synchronize-references"></a>Sincronizar referências

Você pode sincronizar as referências com a ordem de produção. Se essa opção for selecionada, as datas das subproduções serão movidas e alinhadas quando forem feitas alterações na agenda da ordem de produção. Se uma ordem de produção tiver uma ou mais subproduções, talvez você queira agendar as subproduções junto com a produção principal. Nesse caso, a produção principal não poderá ser iniciada até que as subproduções relacionadas não sejam concluídas. Portanto, marque esta caixa de seleção se o agendamento de subproduções deve ser baseado nas horas inicial e final da produção principal. Você poderá marcar esta caixa de seleção somente se a caixa de seleção**Referências de plano** também estiver marcada.

## <a name="cancellation"></a>Cancelamento
### <a name="cancel-queue-time"></a>Cancelar tempo de espera

Marque esta caixa de seleção para excluir o tempo de espera do agendamento.

### <a name="cancel-setup"></a>Cancelar configuração

Marque esta caixa de seleção para excluir o tempo de preparação do agendamento.

### <a name="cancel-process"></a>Cancelar processo

Marque esta caixa de seleção para excluir o tempo de execução do agendamento.

### <a name="cancel-overlap"></a>Cancelar sobreposição

Marque esta caixa de seleção para excluir o tempo de sobreposição do agendamento.

### <a name="cancel-transport"></a>Cancelar transporte

Marque esta caixa de seleção para excluir o tempo em trânsito do agendamento.

## <a name="set-default"></a>Configurar padrão
Você pode salvar os valores atuais como valores padrão. Há duas opções:

-   Definir como meu padrão
-   Definir como padrão para todos


<a name="additional-resources"></a>Recursos adicionais
--------

[Agendamento de operações](operations-scheduling.md)



