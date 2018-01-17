---
title: "Distribuição integrada de ordens de produção para docas de saída"
description: "Este tópico descreve como gerenciar o processo de distribuição integrada de materiais que está sendo informado como concluído de uma linha de produção para uma doca de transporte."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 178f74bba514309748c2dfd060486c49176dff3e
ms.openlocfilehash: 6afec24c76e3d56b77b1106375830285ad3bedad
ms.contentlocale: pt-br
ms.lasthandoff: 12/19/2017

---

# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Distribuição integrada de ordens de produção para docas de saída

Este tópico descreve como gerenciar o processo de distribuição integrada de materiais que está sendo informado como concluído de uma linha de produção para uma doca de transporte.

<a name="introduction"></a>Introdução
------------

A distribuição integrada de produção para uma localização de saída é relevante para fabricantes que geram alto volume e querem enviar os produtos acabados, de preferência, assim que forem relatados como concluídos das linhas de produção. O objetivo é enviar os produtos a centros de distribuição que estão fisicamente localizados próximos à demanda do cliente, em vez de acumular estoque no site de fabricação.

Quando não houver uma demanda imediata para um produto, ele deverá ser armazenado nos locais de armazenamento no site de fabricação. Esse processo também é conhecido como *distribuição integrada oportunista*, que indica que se houver uma demanda para enviar o produto, então esta oportunidade deverá ser usada, em vez de colocar o produto no armazenamento interno.

O exemplo a seguir mostra três variações de um fluxo que começa no fim da linha de produção (2).

Um produto é reportado como concluído para o local de saída de produção (3) e o motorista da empilhadeira pegará o palete na localização (3).

-   Se existir uma atividade planejada (6) para transferir os produtos de fabricação (1) a um centro de distribuição (7), o motorista do caminhão será direcionado pelo sistema a colocar o palete em um local da porta da baía (4).
-   Se um trailer já estiver atribuído à porta da baía, o motorista do caminhão será orientado a carregar o produto diretamente no trailer.
-   Se não houver nenhuma atividade planejada para transferir o produto, o motorista da empilhadeira será orientado para armazenar o produto em um local no depósito interno (5).

[![distribuição integrada oportunista](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Configurar a distribuição integrada
Você configura o processo de distribuição integrada nas **políticas de trabalho**. Uma política de trabalho tem um tipo de ordem de trabalho, localização e produto. No exemplo a seguir, a distribuição integrada é configurada para produto X e localização Y.

#### <a name="work-order-types"></a>Tipos de ordem de trabalho

-   Tipo de ordem de trabalho: Armazenamento de bens acabados
-   Método de criação de trabalho: Distribuição integrada
-   Nome da política de distribuição integrada: ordens de transferência

#### <a name="inventory-locations"></a>Localizações de estoque

-   Depósito: 51
-   Local: Y

#### <a name="products"></a>Produtos

-   Número do item: X

Atualmente a distribuição integrada, pode ser configurada para apenas dois tipos de ordem de trabalho:

-   Armazenamento de mercadorias acabadas
-   Armazenamento de coproduto e subproduto

Na **política de distribuição integrada**, você define quais tipos de documento são aplicáveis para a distribuição integrada. Atualmente, o único tipo de documento que é suportado é **Ordens de transferência**. O exemplo a seguir mostra a configuração de uma política de distribuição integrada.

### <a name="cross-docking-policy-name-transfer-order"></a>Nome da política de distribuição integrada: ordem de transferência

-   Número de sequência: 10
 -   Tipo de ordem de trabalho: Saída de transferência
-   A demanda de distribuição integrada requer localização: Falso
-   Estratégia distribuição integrada: Data e hora

### <a name="sequence-number"></a>Número de sequência

O **número de sequência** Indica a prioridade do tipo de documento. Atualmente, **Saída de transferência** é o único tipo suportado. Portanto, o número de sequência se tornará relevante somente quando mais tipos de ordem de trabalho forem suportados.

### <a name="cross-docking-policy"></a>Política de distribuição integrada

A política de distribuição integrada também define a política para priorização da demanda de ordem de transferência. Por exemplo, caso haja várias ordens de transferência para o mesmo produto, a data programada e as horas que são definidas na carga e associadas à ordem de transferência, determinam a priorização entre as ordens. A data e a hora programadas podem ser definidas diretamente na carga, ou podem ser definidas em uma **agenda de compromisso** associada à carga. A priorização é determinada por estratégia de distribuição integrada. Atualmente, há somente uma estratégia: **Data e hora**.

### <a name="cross-docking-demand-requires-location"></a>A demanda de distribuição integrada requer localização

Na política de distribuição integrada, você pode configurar um critério para exigir que as ordens de transferência tenham uma localização atribuída para que sejam qualificadas para a distribuição integrada. Esse critério é definido no campo **A demanda de distribuição integrada requer localização**. A localização na agenda de compromisso que está associada à carga é usada como localização final para os bens que estão sendo distribuídos integralmente. A localização final de bens que estão sendo distribuídos integralmente é determinada pela política local para **Saída de transferência** para o tipo de ordem de trabalho **Armazenar**. Talvez você ache útil definir o campo **A demanda de distribuição integrada requer localização** em um cenário que os bens acabados devem ter distribuídos integralmente somente se um trailer for atribuído a uma porta de baía. Neste cenário, os bens são movidos diretamente linha de produção para o trailer. Quando um trailer é atribuído à porta da baía, um usuário atribuirá o local à agenda de compromisso e, portanto, tornará o local aplicável para distribuição integrada. As seguintes seções a seguir o orientarão pelos dois exemplos.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>Cenário 1 - Distribuição integrada da produção para as ordens de transferência

Depois que um produto for relatado como concluído na linha de produção, ele será transferido para uma localização da baía onde será carregado para um caminhão e transferido para um centro de distribuição. Use a empresa USMF.

1.  Habilite uma nova sequência numérica para a distribuição integrada. Vá para a página **Numerar sequências** e selecione o botão **Gerar**. Um assistente o guiará pelo processo.
2.  Crie uma política de distribuição integrada. Vá para a página **Política de distribuição integrada** e crie uma nova política chamada de **Distribuição integrada para ordem de transferência**. Observe que o único tipo de ordem de trabalho que você pode selecionar é **Transferência de saída** e a única estratégia de distribuição integrada disponível é **Data e hora**.
3.  Crie uma política de trabalho. Vá para a página **Políticas de trabalho** e crie uma nova política de trabalho chamada **Distribuição integrada L0101**.
4.  Configure as cargas de modo que sejam criadas automaticamente para ordens de transferência. Nos parâmetros do depósito, configure as cargas para que sejam criadas automaticamente quando as ordens de transferência forem criadas. Uma carga é um pré-requisito para tornar a ordem de transferência qualificado para a distribuição integrada.
5.  Configure o mapeamento de carga do item. Vá para a página **Mapeamento de carga do item** e configure um modelo padrão de carga para o grupo de itens **CarAudio**. Esse mapeamento inserirá automaticamente o modelo de carga na carga quando a ordem de transferência for criada.
6.  Criar uma ordem de transferência. Crie a ordem de transferência para o número do item L0101. Quantidade = 20.
7.  Libere a ordem de transferência da bancada de planejamento de carga. Na guia **Remessa**, selecione o item de menu da bancada de planejamento de carga e no menu **Liberar** da linha de carga, selecione **Liberar para o depósito**. Uma linha de onda aberta do tipo **Transferência de saída** agora existe para a ordem de transferência.
8.  Criar uma ordem de produção. Vá para a página **Ordem de produção**, e crie uma ordem de produção do produto L0101. Quantidade = 20. Estime e inicie a ordem de produção. Observe que o campo **Lançar lista de separação agora** permanece definido como **Não**.
9.  Relate como concluído no dispositivo móvel. Vá para o portal do dispositivo móvel e selecione o item de menu **Relatar como concluído e armazenado**. Agora relate L0101 como acabado do dispositivo portátil. Quantidade = 10. Observe a localização de armazenamento é **BAYDOOR**. Esta localização é encontrada na diretiva de localização **Transferência de saída** para o tipo de ordem de serviço **Armazenar**. Observe também que esse trabalho do tipo **Saída de transferência** foi criado e concluído. Vá para detalhes da ordem de transferência verifique o trabalho.
10. Agora relate 10 unidades adicionais do dispositivo móvel. Observe que a localização de armazenamento é novamente **BAYDOOR**. Observe também que um novo trabalho do tipo **Saída de transferência** foi criado para as 10 unidades.
11. Agora tente iniciar mais 20 peças na ordem de produção e tente reportar 20 como concluídas, usando o dispositivo portátil. Esse horário, local **LP-001** são sugeridos como localização de armazenamento. Esta localização é encontrada na diretiva da localização para **Armazenamento de mercadorias acabadas**. Esta diretiva de localização está sendo usada, pois não existe nenhuma oportunidade para distribuição integrada. A ordem de transferência para LP-001 foi totalmente atendida pelas duas atividades de distribuição integrada nas etapas 9 e 10. Observe que o trabalho do tipo **Armazenamento de mercadorias acabadas** foi criado e processado.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>Cenário 2 - distribuição integrada de produção para ordens de transferência com uma agenda de compromisso

Após um produto ser relatado como concluído na linha de produção, ele será transferido para uma localização de baía-porta que é identificada por uma agenda de compromisso para as localizações de baía-porta. Use a empresa USMF.

1.  Altere a política de distribuição integrada. Altere a política de distribuição integrada criada no cenário 1, marcando a caixa de seleção **A demanda de distribuição integrada requer localização**.
2.  Crie uma nova ordem de transferência.
3.  Abra a **Bancada de planejamento de carga**.
4.  De bancada de planejamento de carga, vá para a seção **Cargas** e selecione **Agenda de compromisso** no menu **Transporte** para criar uma nova agenda de compromisso. Observe que a agenda de compromisso tem uma referência à ordem de transferência no campo **Número de ordem**. No campo **Data/hora inicial planejada na localização**, você pode definir a data e a hora do compromisso. Essas data e hora serão usadas quando a demanda de distribuição integrada for priorizada durante o processo de distribuição integrada. A data e hora definidas neste campo atualizará o campo **Data e a hora da remessa de carga agendada** da carga correspondente. A localização na Guia Rápida **Detalhes de remessa** determina a localização à qual a ordem de transferência será remetida.
5.  Na **Bancada de planejamento de carga** libere para o depósito.
6.  Crie uma ordem de produção para o número de item **L0101**, e defina o status **Iniciado**, com uma quantidade de 20.
7.  Relate como concluído no dispositivo móvel.
8.  Vá para o portal do dispositivo móvel e selecione o item de menu **Relatar como concluído e armazenado**.
9.  Relate o número do item **L0101** como acabado usando o dispositivo portátil. Observe a localização de armazenamento agora é **BAYDOOR 2**. Esta localização é encontrada na agenda de compromisso, em vez de na diretiva de localização **Recebimento de transferência**.

### <a name="additional-information"></a>Informações Adicionais

-   O cenário de distribuição integrada é suportado itens controlados por lote e série, com as dimensões de lote e número de série definidas na localização acima e abaixo na hierarquia de reserva. 



