---
title: Subcontratação
description: Esse tópico o ajudará a criar um passo a passo da subcontratação na fabricação no Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421919"
---
# <a name="subcontracting"></a>Subcontratação

[!include [banner](../includes/banner.md)]

Esse tópico o ajudará a criar um passo a passo da subcontratação de fabricação no Microsoft Dynamics 365 Supply Chain Management. A primeira parte desse tópico descreve a configuração dos dados. A segunda parte fornece orientações sobre as etapas do passo a passo.

## <a name="target-audience"></a>Público-alvo

Neste tópico, você saberá como configurar a subcontratação de fabricação. Você usará os dados existentes na entidade legal de HQUS para fazer a configuração básica de um fluxo de atividade a subcontratação. Os dados de demonstração na entidade legal de HQUS incluem os parâmetros de configuração que foram predefinidos para oferecer suporte nas etapas do passo a passo. Embora o passo a passo aborde problemas encontrados e desafios importantes para várias funções, ele podem ser concluído pelo administrador do sistema.

## <a name="demo-scenario"></a>Cenário de demonstração

Na entidade legal de HQUS, fabrica-se alto-falantes. Durante o processo de fabricação, os alto-falantes passam pelas três operações a seguir.

- **Pré-montagem** – O gabinete do alto-falante é montado. O material para o gabinete é escolhido no depósito de material antes da operação ser iniciada.
- **Revestimento** – Após o gabinete do alto-falante ser montado, ele deve ser revestido. Essa operação é concluída por um fornecedor (subcontratado). O gabinete do alto-falante montado anteriormente é enviado para o subcontratado de revestimento com dois materiais.
- **Conclusão** – Após o gabinete do alto-falante montado anteriormente ser revestido pelo subcontratado, ele retorna à entidade legal de HQUS para que a montagem final do alto-falante possa ser concluída.

A ilustração a seguir mostra as três operações e os materiais que elas consomem.

![As operações de pré-montagem, revestimento e conclusão e os materiais que elas consomem](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>Configurar

Antes de começar o passo a passo, é necessário configurar os dados.

### <a name="set-up-the-finished-product"></a>Instalar o produto finalizado

Esse procedimento fornece orientações sobre a instalação do produto lançado D8100, “Gabinete revestido”.

1. Selecione **Gerenciamento de informações do produto \> Produtos \> Produtos liberados** para abrir a página **Detalhes do produto liberado** .
2. No campo de filtro rápido, insira **D8100** para encontrar o produto liberado existente.

    ![Para filtrar o produto liberado D8100 na página Detalhes do produto liberado](./media/subcontract02_filtering-released-products.png)

3. No Painel de Ações, na guia **Engenheiro** , selecione **Roteiro** para abrir a página **Roteiro** .

    A página **Roteiro** mostra as oito versões de roteiro para o produto liberado D8100. As oito versões de roteiro são divididas em quatro roteiros no site 1 e site 5. O roteiro 000400 é usado para avaliação de custo, o roteiro 00041 é usado quando a operação de revestimento é interna e roteiro 00042 é usado quando a operação de revestimento é externa.

    ![Oito versões de roteiro na página Roteiro](./media/subcontract03_route-page.png)

4. No painel superior, na grade **Versões** , selecione a versão de roteiro **00042** do site **5**.
5. No painel inferior, na guia **Visão geral**, selecione a operação **20** (**Cbnt CtSc**) na grade.

    ![Operação 20 da versão de roteiro 00042 do site 5 selecionada](./media/subcontract04_route-version-operation.png)

6. Selecione a guia **Geral**.

    Observe que o campo **Tipo de roteiro** está definido como **Fornecedor**. Esse valor que indica que a operação 20 (Cbnt CtSc) é uma operação subcontratada.

    ![Campo Tipo de roteiro definido como Fornecedor na guia Geral](./media/subcontract05_general-tab.png)

7. Selecione a guia **Requisitos de recursos**.

    Os recursos serão usados para encontrar um recurso aplicável durante o agendamento de produção. Para a operação 20 (Cbnt CtSc), observe que é necessário um recurso que tenha dois recursos, **Revestimento** e **Gabinetes revestidos**.

    ![Recursos de revestimento e gabinetes revestidos na guia de requisitos de recursos](./media/subcontract06_resource-requirements-tab.png)

8. Selecione **Recursos aplicáveis** para abrir a caixa de diálogo **Recursos aplicáveis**.

    Foram encontrados três recursos que correspondem aos requisitos de recursos para a operação. Observe que os recursos 8851 e 8852 são do tipo **Fornecedor**.

    ![Três recursos adequados na caixa de diálogo Recursos aplicáveis](./media/subcontract07_applicable-resources-dialog.png)

9. Selecione **OK** para fechar a caixa de diálogo **Recursos aplicáveis** e retornar à página **Roteiro**.
10. Fecha a página **Roteiro** para retornar à página **Detalhes do produto liberado** .

    ![Página Detalhes do produto liberado](./media/subcontract08_released-product-details-page.png)

11. No Painel de Ações, na guia **Engenheiro** , selecione **Versões de BOM** para abrir a página **Versões de BOM**.

    A página **Versões de BOM** mostra as quatro versões da lista de materiais (BOM) do produto liberado D8100. A BOM 000040 é usada para avaliação de custo e planejamento, a BOM 000041 é usada se a operação de revestimento é interna, e as BOMs 000042 e 000043 são usadas se a operação de revestimento é subcontratada.

    Observe que o item S8050 é um produto do tipo de item **Serviço**. Esse item representa o trabalho subcontratado.

    ![Quatro versões de BOM na página Versões de BOM](./media/subcontract09_bom-versions-page.png)

12. Na FastTab **Linhas da lista de materiais**, selecione **Editar** para abrir a caixa de diálogo **Editar linha de BOM**.

    Quando uma ordem de produção for criada e estimada para o produto liberado D8100, ordem de compra será gerada automaticamente para o item S8050. Essa ordem de compra será vinculada à ordem de produção. Para que as ordens de compra sejam geradas automaticamente, o campo **Tipo de linha** deve ser definido como **Fornecedor**, e a conta do fornecedor para o subcontratado deve ser selecionada. Nesse caso, a conta do fornecedor é US-801.

    Observe que a linha de BOM está conectada à operação de revestimento por meio do número da operação (neste caso, 20).

    ![Editar caixa de diálogo Linha de BOM](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>Criar uma senha para trabalhadores de depósito

Você deve definir uma senha para os trabalhadores de depósito que usam o dispositivo portátil.

1. Selecione **Gerenciamento de depósito \> Configuração \> Trabalhador** para abrir a página **Usuários de trabalho**.
2. Na FastTab **Usuários**, selecione a linha do usuário **51**.

    ![Página Usuários de trabalho](./media/subcontract11_work-users-page.png)

3. Selecione **Redefinir senha**.
4. Nos campos **Senha** e **Confirmar senha**, insira **1**.
5. Selecione **Definir senha**.

## <a name="step-by-step-walkthrough"></a>Orientação passo a passo

**Cenário e plano de fundo**

Uma ordem de produção de 10 peças é criada para o produto D8100, “Gabinete revestido”. O revestimento dos gabinetes é uma operação subcontratada que é feita no fornecedor US-801, Perfect Coating Solutions. A ordem de produção consiste em três operações. Na primeira operação, o gabinete passa pela pré-montagem como uma operação interna. O material para a pré-montagem é liberado para coleta no depósito de matéria-prima. Após a pré-montagem ser concluída, o gabinete pré-montado é enviado para a Perfect Coating Solutions com dois materiais necessários para a operação de revestimento. Quando o gabinete revestido é recebido de volta do fornecedor, ele passa pela montagem interna final para que possa ser relatado como finalizado.

1. Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.
2. No Painel de Ações, selecione **Nova ordem de produção** para abrir a caixa de diálogo **Criar ordem de produção**.

    ![Caixa de diálogo Criar ordem de produção](./media/subcontract12_create-production-order-dialog.png)

3. No campo **Número de item**, selecione **D8100**.
4. Depois que você selecionar o número do item, os campos das dimensões do estoque serão exibidos. No campo **Cor**, selecione **Cromado**.

    Uma caixa de mensagem é exibida para perguntar se versões ativas da BOM e do roteiro devem ser inseridas.

    ![Caixa de mensagem](./media/subcontract13_message-box.png)

5. Selecione **Sim**. 

    Na caixa de diálogo **Criar ordem de produção**, as versões ativas da BOM e do roteiro para o produto D8100 são selecionadas automaticamente nos campos **Número de BOM** e **Número de roteiro**, respectivamente. Nesse caso, a BOM **000040** e o roteiro **000040** são selecionados.
    
    > [!NOTE]
    > Para a BOM e o roteiro, a versão 000040 é usada para avaliação de custo e planejamento.

6. No campo **Local**, selecione **5**.
7. No campo **Depósito**, selecione **51**.
8. Nos campos **Número de BOM** e **Número de roteiro** , altere o valor selecionado automaticamente para **000042**.

    > [!NOTE]
    > Para a BOM e o roteiro, a versão 000042 é usada para subcontratar o revestimento do gabinete para o fornecedor US-801.

    ![Valores definidos na caixa de diálogo Criar ordem de produção](./media/subcontract14_create-production-order-dialog-set.png)

9. Selecione **Criar** para criar a ordem de produção e retornar à página **Todas as ordens de produção**.

    ![Nova ordem de produção na página Todas as ordens de produção](./media/subcontract15_new-production-order.png)

10. No Painel de Ações, na guia **Ordem de produção**, selecione **Estimativa** para abrir a caixa de diálogo **Estimativa**.

    ![Caixa de diálogo Estimativa](./media/subcontract16_estimate-dialog.png)

11. Selecione **OK** para criar a estimativa e retornar à página **Todas as ordens de produção**.

    > [!NOTE]
    > Quando a ordem de produção é estimada, a ordem de compra para o item de serviço S8050 é gerada para o fornecedor US-801.

12. No Painel de Ações, na guia **Ordem de produção** , selecione **BOM** para abrir a página **BOM** , que exibe as linhas de BOM para a ordem de produção.

    Para o item de serviço S8050, observe há uma referência à ordem de compra que foi gerada quando a ordem de produção foi estimada.

    ![Linhas de BOM da ordem de produção na página BOM](./media/subcontract17_production-order-bom-lines.png)

13. Feche a página **BOM** para retornar à página **Todas as ordens de produção**.
14. No Painel de Ações, na guia **Agenda**, selecione **Agendar trabalhos** para abrir a caixa de diálogo **Agendamento de trabalho**.
15. Especifique os seguintes valores:

    - No campo **Direção do agendamento**, selecione **Avançar a partir de amanhã**.
    - Defina a opção **Capacidade finita** como **Sim**.

    ![Caixa de diálogo Agendamento de trabalho](./media/subcontract18_job-scheduling-dialog.png)

16. Selecione **OK** para fechar a caixa de diálogo **Agendamento de trabalho** e retornar à página **Todas as ordens de produção**.
17. No Painel de Ações, na guia **Agendar** , selecione **Gantt** para abrir a página **Gráfico de Gantt - visão de recurso**.

    O gráfico de Gantt fornece uma visão geral de como os trabalhos de produção estão agendados nos recursos. Observe que a operação externa de revestimento consiste em três trabalhos: um trabalho de processo, o trabalho de transporte e um trabalho de tempo de espera.

    ![Gráfico de Gantt na página Gráfico de Gantt - visão de recurso](./media/subcontract19_gantt-chart.png)

18. Feche a página **Gráfico de Gantt - visão de recurso** para retornar à página **Todas as ordens de produção**.
19. No Painel de Ações, na guia **Ordem de produção**, selecione **Liberação** para abrir a caixa de diálogo **Liberação**.

    ![Caixa de diálogo Liberação](./media/subcontract20_release-dialog.png)

20. Selecione **OK** para fechar a caixa de diálogo **Liberação**.
21. Selecione **Controle de produção \> Tarefas periódicas \> Liberar para depósito \> Liberação automática de linhas de BOM e fórmula** para abrir a caixa de diálogo **Liberação automática de linhas de BOM e fórmula** .

    ![Caixa de diálogo Liberação automática de linhas de BOM e fórmula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. Selecione **OK** para executar a liberação automática do trabalho das linhas BOM e fórmula.

    Esse trabalho libera o trabalho de separação de matérias-primas para o depósito.

23. Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.
24. Use o campo de filtro rápido para selecionar a ordem de produção em que você trabalhou.
25. No Painel de Ações, na guia **Depósito** , selecione **Detalhes do trabalho** para abrir a página **Trabalho**.

    Observe que a página mostra dois conjuntos de trabalho para a separação de matéria-prima. O primeiro trabalho é para os materiais M8100 e M8101. Esses materiais são consumidos pela operação 10. O segundo trabalho é para os materiais M8202 e M8250. Esses materiais são consumidos pela operação 20, que é subcontratada.

    ![Dois conjuntos de trabalho para a separação de matéria-prima na página Trabalho.](./media/subcontract22_work-page.png)

26. Inicie o aplicativo de depósito para processar o trabalho de depósito para a operação 10.

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.
28. Use o campo de filtro rápido para selecionar a ordem de produção em que você trabalhou.
29. No Painel de Ações, na guia **Ordem de produção**, selecione **Início** para abrir a caixa de diálogo **Início**.
30. Na guia **Geral**, especifique os seguintes valores:

    - No campo **Da Oper. N°**, selecione **10**.
    - No campo **Para Oper. N°**, selecione **10**.

    ![Valores definidos na guia Geral](./media/subcontract23_start-dialog.png)

31. Selecione **OK** para fechar a caixa de diálogo **Início** e retornar à página **Todas as ordens de produção**.

    Observe que o status da ordem de produção agora é **Iniciado**. Os materiais para a operação 10 são consumidos por um lançamento automático do diário de listas de separação. O consumo de tempo para a operação 10 é contabilizado por um lançamento automático de um diário de cartão de roteiro.

32. Inicie o aplicativo de depósito para processar o trabalho de depósito para a operação 20.

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. No Painel de Ações, na guia **Ordem de produção**, selecione **Início** para abrir a caixa de diálogo **Início**.
34. Na guia **Geral**, especifique os seguintes valores:

    - No campo **Da Oper. N°**, selecione **20**.
    - No campo **Para Oper. N°**, selecione **20**.
    - No campo **Quantidade**, insira **10**.
    - Defina a opção **Lançar lista de separação agora** como **Não**.

    ![Valores definidos na guia Geral](./media/subcontract24_general-tab.png)

35. Selecione **OK** para fechar a caixa de diálogo **Início** e retornar à página **Todas as ordens de produção**.

    Uma lista de separação é criada para os materiais usados para a operação de revestimento e para o item de serviço. O item de serviço representa o custo da operação subcontratada.

36. No Painel de Ações, na guia **Exibir** , selecione **Lista de separação** para abrir a página **Lista de separação**.
37. Selecione a lista de separação que não foi lançada e, em seguida, selecione o número do diário para exibir as linhas do diário.

    ![Linhas do diário na página Lista de separação](./media/subcontract25_picking-list.png)

38. No Painel de Ações, selecione **Imprimir** \> **Relatório de lista de separação** para abrir a caixa de diálogo **Relatório de lista de separação** .
39. Defina a opção **Usar layout da nota de entrega** como **Sim**.

    ![Caixa de diálogo Relatório de lista de separação](./media/subcontract26_picking-list-report-dialog.png)

40. Selecione **OK** para gerar um relatório de **Lista de separação**.

    Nesse caso, uma nota de entrega do fornecedor será impressa do diário de listas de separação de produção. A nota de entrega especifica os materiais enviados para fornecedor que realizará a operação de revestimento.

    ![Relatório de lista de separação](./media/subcontract27_picking-list-report.png)

41. Feche o relatório de **Lista de separação** para retornar à **Lista de separação**.
42. No Painel de Ações, selecione **Lançar** para abrir a caixa de diálogo **Diário de lançamentos**.

    ![Caixa de diálogo Diário de lançamentos](./media/subcontract28_post-journal-dialog.png)

43. Selecione **OK** para fechar a caixa de diálogo **Diário de lançamentos**.
44. Abra a ordem de compra.

    ![Página Ordem de compra](./media/subcontract29_purchase-order-page.png)

45. No Painel de Ações, na guia **Compra**, selecione **Confirmar**.
46. Selecione **Lançar** para abrir a caixa de diálogo **Diário de lançamentos**.
47. Selecione **OK** para fechar a caixa de diálogo **Diário de lançamentos** e retornar à página **Ordem de compra**.
48. Altere o preço unitário de **33** para **40**.

    ![Preço unitário alterado na página Ordem de compra](./media/subcontract30_unit-price.png)

49. Confirme a ordem de compra novamente.
50. Recebimento de produtos.

    ![Caixa de diálogo Lançamento de recebimento de produtos](./media/subcontract31_posting-product-receipt-dialog.png)

51. Fatura de compra.
52. Atualizar o status de conciliação.

    ![Página Fatura de fornecedor](./media/subcontract32_vendor-invoice-page.png)

53. Relatar como concluído.

    ![Caixa de diálogo Relatar como concluído](./media/subcontract33_report-as-finished-dialog.png)

54. Finalizar.

    ![Caixa de diálogo Finalizar](./media/subcontract34_end-dialog.png)

55. Comparação de custo.

    ![Gráficos de comparação de custo](./media/subcontract35_cost-comparison-charts.png)

Não há configuração nos dados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]