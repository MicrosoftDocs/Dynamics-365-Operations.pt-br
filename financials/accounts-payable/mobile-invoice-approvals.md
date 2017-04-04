---
title: "Aprovações móveis de nota fiscal"
description: "Os recursos em móveis Microsoft Dynamics 365 para operações deixaram experiências móveis de um design de usuários comercial. Cenários para avançado, também deixar o preparo desenvolvedores estender recursos como fechamento. A maioria de modo efetivo saber alguns conceitos em novos celular é revisar o processo de criação alguns cenários. Este tópico é para fornecer uma abordagem prática criar a cenários móveis tirando aprovações da nota fiscal de fornecedor do celular como um caso de uso. Esse tópico deve ajudá-lo a criar outras variações de cenários e também pode ser aplicado a outros cenários que não são relacionados a notas fiscais de fornecedor."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Aprovações móveis de nota fiscal

Os recursos em móveis Microsoft Dynamics 365 para operações deixaram experiências móveis de um design de usuários comercial. Cenários para avançado, também deixar o preparo desenvolvedores estender recursos como fechamento. A maioria de modo efetivo saber alguns conceitos em novos celular é revisar o processo de criação alguns cenários. Este tópico é para fornecer uma abordagem prática criar a cenários móveis tirando aprovações da nota fiscal de fornecedor do celular como um caso de uso. Esse tópico deve ajudá-lo a criar outras variações de cenários e também pode ser aplicado a outros cenários que não são relacionados a notas fiscais de fornecedor.

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                                                            | descrição                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Manual móvel anteriormente leitura                                                                                |(/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform.md)                                                                                                  |
| Dynamics 365 for Operations                                                                             | Um ambiente com Microsoft Dynamics 365 para a versão 1611 de operações e o Microsoft Dynamics para atualização 3 de preparo operações (em novembro de 2016)                   |
| 3204341 KB de hotfix de instalação.                                                                              | O task recorder pode registrar erroneamente dois próximos comandos para caixas de diálogo que suspensos é incluído em dynamics 365 para atualização 3 de preparo de operação (a atualização) em novembro de 2016 |
| 3207800 KB de hotfix de instalação.                                                                              | Este hotfix habilita os anexos a serem exibidos no cliente que móvel é incluído em dynamics 365 para atualização 3 de preparo de operação (em novembro de 2016 atualização).           |
| 3208224 KB de hotfix de instalação.                                                                              | O código do aplicativo para o aplicativo móvel de aprovação de nota fiscal de fornecedor é incluído no aplicativo 7.0.1 Microsoft Dynamics AX (). em maio de 2016                          |
| Um ou Android iOS ou um dispositivo de O Windows que tem o instalaram descritivo móvel para dynamics 365 para operações | Procure descritivo no armazenamento de descritivo apropriado.                                                                                                                     |

## <a name="introduction"></a>Introdução
Aprovações móveis para faturas de fornecedor exigem os três hotfixes mencionados na seção “de pré-requisitos.” Esses hotfixes não fornecem um espaço de trabalho para as aprovações da nota fiscal. Para saber o que um espaço de trabalho no contexto de celular, ler o manual móvel que é mencionado na seção “de pré-requisitos.” O espaço de trabalho de aprovações da nota fiscal deve ser criado. 

Cada organização orquestra e define seu processo comercial para faturas de fornecedor diferente. Antes de criar uma experiência móvel para aprovações da nota fiscal de fornecedor, considere os seguintes aspectos do processo comercial. A ideia é possível usar tanto como esses pontos de dados para otimizar a experiência de usuário no dispositivo.

-   Os campos do cabeçalho de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?
-   Os campos de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?
-   Quantas linhas de nota fiscal antes em uma nota? Aplicar a regra 80-20 aqui e, otimizar-la para as 80.
-   Os usuários desejarão para consultar distribuições contábeis (codificação de nota fiscal) em dispositivo móvel durante revisões? Se a resposta à pergunta for sim, considere as seguintes perguntas:
    -   Quantas distribuições contábeis (preço bruto, impostos, encargos, separações, etc houver) para uma linha de nota fiscal? Além disso, aplique a regra 80-20.
    -   Faturas também têm distribuições contábeis no cabeçalho de nota fiscal? Em caso afirmativo, as distribuições contábeis devem estar disponíveis em dispositivo?

> [!NOTE]
> Este tópico explica como não editar distribuições contábeis, porque essa funcionalidade não está suportada para atualmente cenários móveis.

-   Os usuários desejarão para consultar todos para a fatura em dispositivo?

O design experiência móvel para aprovações da nota fiscal será diferente, dependendo das respostas para essas perguntas. O objetivo são otimizar a experiência de usuário do processo comercial do celular em uma organização. O restante deste tópico, é olharemos duas variações de cenário baseadas em diferentes respostas a perguntas acima. 

Como regra geral geral, ao trabalhar com o designer móvel, certifique-se “publicar” alterações para evitar perda de atualizações.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Criando um cenário simples de aprovação de nota fiscal para A Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de cenário</th>
<th>Resposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Os campos do cabeçalho de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?</td>
<td><ol>
<li>Nome do Fornecedor</li>
<li>Total da fatura</li>
<li>Conta de fatura</li>
<li>Número da fatura</li>
<li>Data da fatura</li>
<li>Descrição da fatura</li>
<li>Data de Vencimento</li>
<li>Moeda da fatura</li>
</ol></td>
</tr>
<tr class="even">
<td>Os campos de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?</td>
<td><ol>
<li>Categoria de compras</li>
<li>Quantidade</li>
<li>Preço unitário</li>
<li>Valor líquido da linha</li>
<li>Valor do 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quantas linhas de nota fiscal antes em uma nota? Aplicar a regra 80-20 aqui e, otimizar-la para as 80.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Os usuários desejarão para consultar distribuições contábeis (codificação de nota fiscal) em dispositivo móvel durante revisões?</td>
<td>Sim</td>
</tr>
<tr class="odd">
<td>Quantas distribuições contábeis (preço bruto, impostos, encargos, etc houver) para uma linha de nota fiscal? Além disso, aplique a regra 80-20.</td>
<td>Preço bruto: Imposto 2: Encargos 0: 0</td>
</tr>
<tr class="even">
<td>Faturas também têm distribuições contábeis no cabeçalho de nota fiscal? Em caso afirmativo, as distribuições contábeis devem estar disponíveis em dispositivo?</td>
<td>Não usado</td>
</tr>
<tr class="odd">
<td>Os usuários desejarão para consultar todos para a fatura em dispositivo?</td>
<td>Sim</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Crie o espaço de trabalho

1.  Em um navegador, o dynamics 365 aberta para operações, além conecta.
2.  Depois de anexar ** conectou, a URL &mode=mobile ** conforme mostrado de exemplo, atualização e a página: https://yoururl/?cmp=usmf&mi=DefaultDashboard**&mode=mobile**&lt;&gt;
3.  Clicar ** ** configurações () engrenagem grade superior direita da página, e em ** descritivo móvel **. O designer móvel descritivo deve aparecer apenas enquanto o task recorder é exibido.
4.  Clique ** adicionar ** novo para criar um espaço de trabalho. Por exemplo, nomear o espaço de trabalho ** minhas aprovações **.
5.  Insira uma descrição.
6.  Selecione uma cor de espaço de trabalho. A cor de espaço de trabalho será usada para o total de experiência estilo móvel do espaço de trabalho.
7.  Marque um ícone do espaço de trabalho.
8.  Clique ** feito **
9.  Clique ** publicar o espaço de trabalho ** para salvar as alterações

### <a name="vendor-invoices-assigned-to-me"></a>Faturas de fornecedor atribuídas a mim

A primeira a móvel que você deve criar pela lista de faturas atribuídas ao usuário para revisão. Para criar este móvel página, use VendMobileInvoiceAssignedToMeListPage página ** ** em dynamics 365 para as operações. Para concluir esse procedimento, certifique-se de que pelo menos uma nota fiscal de fornecedor estiverem atribuída para revisão, e que a nota fiscal tem duas distribuições. Essa configuração atendem a requisitos para esse cenário.

1.  Em dynamics 365 para a URL de operações, substituir o nome do item de menu com VendMobileInvoiceAssignedToMeListPage ** ** para abrir a versão móvel ** durante as notas fiscais de fornecedores atribuído a mim ** página de listagem ** contas a pagar ** no módulo. Dependendo do número de notas fiscais você tiver atribuído no sistema a você, esta página mostra as notas fiscais. Para localizar uma nota fiscal específica, use o filtro à esquerda. Entretanto, não é exigimos uma nota fiscal específica para este exemplo. Nós exigimos apenas qualquer nota fiscal atribuída a você o qual vai permitir que você crie o página móvel. Novas páginas disponíveis foram criados especificamente desenvolvendo cenários móveis para a nota fiscal de fornecedor. Portanto, você deve usar essas páginas. URL deve seguir a URL embora, e depois que você inserir na página, que é a ilustração publicar-se deve: https://yourURL/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile&lt;&gt;[faturas de fornecedor pendentes![atribuídas a página (i]. /media/mobile-invoice-approvals01-1024x281.png)](. /media/mobile-invoice-approvals01.png)
2.  Clica ** configurações ** o botão (de engrenagem) direita superior da página, e no ** descritivo móvel **
3.  Selecione o espaço de trabalho e clique ** edição **
4.  ** Clique em adicionar a página ** para criar a primeira a móvel.
5.  Insira um nome, como ** minhas ** faturas de fornecedor, e uma descrição, como ** as notas fiscais de fornecedores atribuído a mim para revisão **.
6.  Click **Done**.
7.  O designer, celular ** ** campos na guia, clique ** selecionar campos **. As colunas da página devem de embora lista à seguinte ilustração. [colunas do![em notas fiscais de fornecedores pendentes atribuídas a página (i]. /media/mobile-invoice-approvals02-1024x117.png)](. /media/mobile-invoice-approvals02.png)
8.  Adicionar colunas a página de listagem que deve ser exibido para usuários em página móvel. A ordem em que você adicionar na ordem em que os campos são exibidos ao usuário final. A única maneira de alterar a ordem dos campos serão novamente selecionar todos os campos. Com base nos requisitos para este cenário, estes oito campos são necessários. No entanto, alguns usuários podem ver oito campos demasiada informações para que um dispositivo móvel. Portanto, é mostraremos apenas campos as mais importantes na exibição de lista móvel. Os demais campos em parecerão exiba os detalhes que criaremos nós posteriormente. Por adicionaremos nós agora, os seguintes campos. Clique no sinal de adição (+) ** ** nessas adicionar colunas à página móvel.
    1.  Nome do Fornecedor
    2.  Total da fatura
    3.  Conta de fatura
    4.  Número da fatura
    5.  Data da fatura

    Depois dos campos adicionados, a página deve móvel embora ilustração à seguinte. [a página do![após campos é adicionado (]. /media/mobile-invoice-approvals03.png)](. /media/mobile-invoice-approvals03.png)
9.  Você também deve adicionar as seguintes colunas agora, para que possamos habilitar ações de fluxo de trabalho depois.
    1.  Tarefa completo de apresentação
    2.  Tarefa delegados de apresentação
    3.  Tarefa de recuperação de apresentação
    4.  Tarefa de rejeição de apresentação
    5.  Tarefa de conclusão de solicitação de apresentação
    6.  A apresentação da tarefa ele

10. ** Feito ** clique para sair do modo de edição.
11. Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
12. Clique ** publicar o espaço de trabalho ** para salvar seu trabalho.
13. Habilitar ** o total da nota fiscal de exibição em notas fiscais de fornecedores pendentes lista ** em parâmetros de contas a pagar formulário abaixo ** fatura **. Observe, somente que habilitar este parâmetro, os totais de nota fiscal serão calculados para ser exibido na página de listagem notas fiscais pendentes do fornecedor. Este é um novo recurso como parte da correção quente 3208224 de pré-condição.

### <a name="vendor-invoice-details"></a>Detalhes de nota fiscal de fornecedor

Para criar a página detalhes de nota fiscal do celular, use VendMobileInvoiceHeaderDetails ** ** página 365 em dynamics para operações. Observe que, dependendo do número de notas fiscais que você possui no sistema, este página a nota fiscal anteriores (a nota fiscal criada primeiro.) Para localizar uma nota fiscal específica, use o filtro à esquerda. Entretanto, não é exigimos uma nota fiscal específica para este exemplo. Nós exigimos apenas alguns dados de nota fiscal para que possamos criar a página móvel. [página de fluxo![trabalho![(]. /media/mobile-invoice-approvals04-1024x425.png)](. /media/mobile-invoice-approvals04.png)

1.  Em dynamics 365 para a URL de operações, substituir o nome do item de menu com VendMobileInvoiceHeaderDetails ** ** para abrir o formulário
2.  Abra o designer móvel ** configurações ** botão (de engrenagem).
3.  Clicar ** edição ** botão para o modo de edição no espaço de trabalho.
4.  Selecione ** minhas ** faturas de fornecedor que você criou página anterior, e clique em editar ** **.
5.  ** ** Campos na guia, clique ** grade ** o título de coluna.
6.  Clique ** propriedades ** &gt; ** adicionar ** a página. ** Observação: ** Quando você clica ** grade ** o título e adicionar uma página, a relação com a página detalhes será liquidada automaticamente.
7.  Insira um título de página, como detalhes ** ** de nota fiscal, e uma descrição, como ** cabeçalho de nota fiscal de exibição e detalhes ** linha.
8.  Clique ** selecionar campos **. Observe isso, a ordem em que você adicionar na ordem em que os campos são exibidos ao usuário final. A única maneira de alterar a ordem dos campos serão novamente selecionar todos os campos.
9.  Adicione os seguintes campos do cabeçalho, com base nos requisitos para este cenário:
    1.  Nome do Fornecedor
    2.  Total da fatura
    3.  Conta de fatura
    4.  Número da fatura
    5.  Data da fatura
    6.  Descrição da fatura
    7.  Data de Vencimento
    8.  Moeda da fatura

10. Adicione os seguintes campos das linhas da grade:
    1.  Categoria de compras
    2.  Quantidade
    3.  Preço unitário
    4.  Valor líquido da linha
    5.  Valor do 1099

11. Os campos de duas etapas anteriores foram adicionados depois, clique ** ** feito. Embora o a página precisar à seguinte ilustração. [![Page after fields are added](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. ** Feito ** clique para sair do modo de edição.
13. Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
14. Clique ** publicar o espaço de trabalho ** para salvar seu trabalho

### <a name="workflow-actions"></a>Ações de fluxo de trabalho

Para adicionar ações de fluxo de trabalho, siga ** página VendMobileInvoiceHeaderDetails ** em dynamics 365 para as operações. Para abrir essa página, substituir o nome do item de menu, URL como você fez anteriormente. Abra o designer móvel ** configurações ** botão (de engrenagem). Rastrear essas etapas para adicionar ações de fluxo de trabalho da detalhes.

1.  Clicar ** edição ** botão para o modo de edição no espaço de trabalho.
2.  Selecione ** ** detalhes de nota fiscal que você criou página anterior, e clique em editar ** **.
3.  ** Ações ** guia, clique em adicionar ** ** a ação.
4.  Insira um título da ação, como aprovar ** **, e uma descrição, como nota ** aprovar **. Observe o título da ação que você digita aqui se transforma o nome da ação que é exibida para o usuário em descritivo móvel.
5.  Click **Done**.
6.  Clique ** selecionar campos **.
7.  Examine o processo de fluxo de trabalho VendMobileInvoiceHeaderDetails ** ** na página, e execute a ação que deseje registrar. Verifique se você inserir comentários de fluxo de trabalho durante esse processo, para que um campo de comentários seja incluído também a experiência móvel.
8.  Depois que a ação de fluxo de trabalho é executada, clique ** feito ** conclua a tarefa selecione campos.
9.  ** Feito ** clique para sair do modo de edição.
10. Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
11. Clique ** publicar o espaço de trabalho ** para salvar seu trabalho
12. Repita as etapas 3 a 11 para registrar todas as ações necessárias do fluxo de trabalho. Observe isso, ele for uma requisição para que as notas fiscais atribuídas a você que estão em um estado das ações de fluxo de trabalho disponíveis para você que você vai para criar.
13. Abrir ou Bloco De Notas o Microsoft Visual Studio, e colar o código a seguir. Salve o arquivo em um arquivo de .js. Este código faz duas itens:
    1.  Oculta colunas fluxo de trabalho relacionadas nós extras que adicionamos anterior na página de listagem móvel. Nós adicionamos essas colunas de forma que o descritivo que tem informações no contexto e pode executar a próxima etapa.
    2.  Com a etapa do fluxo de trabalho está ativa, que aplica a lógica para mostrar somente as ações.

Observe isso, o nome das páginas e outros controles no código de JS devem ser iguais de espaço de trabalho.

1.  principal ou da função (metadataService, dataService, cacheService), $q {{appInit devolução: funções (appMetadata {) controla de ocultar de //necessárias estiverem presentes, mas não metadataService.configureControl visível (“Meu-fornecedor- faturas “, “ShowAccept,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowApprove,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowReject,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowDelegate,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowRequestChange,” {oculto: true});              metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowRecall,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowComplete,” {oculto: true});            metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowResubmit,” {oculto: true});            }, pageInit: funções (pageMetadata, se params {) nota (detalhes de pageMetadata.Name == de ") //{mostrar/ocultar as ações de fluxo de trabalho com base em metadataService.configureAction etapa de fluxo de trabalho (“,” {aceitar visível: true});                    metadataService.configureAction aprovar (“,” {visível: true});                    rejeita metadataService.configureAction (“,” {visível: true});                    representante metadataService.configureAction (“,” {visível: true});                    metadataService.configureAction (Solicitação- alteração “,” {visível: true});                    metadataService.configureAction recuperação (“,” {visível: true});                    concluir metadataService.configureAction (“,” {visível: true});                    metadataService.configureAction reenviar (“,” {visível: true});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  Carregar o arquivo do código do espaço de trabalho selecionando ** lógica ** a guia
3.  ** Feito ** clique para sair do modo de edição.
4.  Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
5.  Clique ** publicar o espaço de trabalho ** para salvar seu trabalho

### <a name="vendor-invoice-attachments"></a>Os anexos de nota fiscal de fornecedor

1.  Clica ** configurações ** o botão (de engrenagem) direita superior da página, e no ** descritivo móvel **
2.  Clicar ** edição ** botão para o modo de edição no espaço de trabalho.
3.  Selecione ** ** detalhes de nota fiscal que você criou página anterior, e clique em editar ** **.
4.  Definir Sim ** gerenciamento de documentos padrão ** ** ** como mostrado a seguir. ** Observação: ** Se não há necessidade mostra anexos no dispositivo móvel, pode deixar esta opção definida ** nenhuma **, que é a configuração padrão.
5.  [docmanagement![(]. /media/docmanagement-216x300.png)](. /media/docmanagement.png)
6.  ** Feito ** clique para sair do modo de edição.
7.  Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
8.  Clique ** publicar o espaço de trabalho ** para salvar seu trabalho

### <a name="vendor-invoice-line-distributions"></a>Distribuições linha de nota fiscal de fornecedor

Os requisitos para este confirmar o cenário que só terá uma distribuições de linha- nível, e que uma nota fiscal conterá sempre apenas uma linha. Como esse cenário é simples, a experiência de usuário no dispositivo móvel deve ser suficiente simples que o usuário não terá de fazer busca detalhada vários níveis para exibir as distribuições. As notas fiscais de fornecedor em dynamics 365 para operações incluem a opção de exibir as distribuições de cabeçalho de nota fiscal. Experiência esta é a precisamos nós do cenário móvel. Portanto, usaremos ** VendMobileInvoiceAllDistributionTree ** a página criar esta parte do cenário móvel. 

> [!NOTE] 
> Saber os requisitos ajuda-nos a decidir qual página específica para usar e exatamente como otimizar móvel a experiência do usuário quando é criamos o cenário. Em segundo cenário, usaremos uma página diferente para mostrar as distribuições, como necessidades para esse cenário forem diferentes.

1.  URL, substituir o nome do item de menu, como feitas antes. A página que aparece deve a ilustração embora seguir. [![qualquer página de distribuições (]. /media/mobile-invoice-approvals06.png)](. /media/mobile-invoice-approvals06.png)
2.  Abra o designer móvel ** configurações ** botão (de engrenagem).
3.  Clicar ** edição ** botão para o modo de edição no espaço de trabalho. ** Observação: ** Verá duas novas páginas que foram criadas automaticamente. O sistema cria essas páginas, pois você ativou o gerenciamento de documentos na seção anterior. Você pode ignorar esses novas páginas.
4.  Clique ** adicionar ** a página.
5.  Insira um título de página, como ** contabilidade de exibição **, e uma descrição, como ** exibição que para a fatura **.
6.  Click **Done**.
7.  ** ** Campos na guia, clique ** selecionar campos **, selecione os seguintes campos da página de distribuições, clique em: ** feito **
    1.  Valor
    2.  Moeda
    3.  Conta contábil

> [!NOTE] 
> Caso não selecionamos ** descrição ** a coluna de grade de distribuições, como os requisitos para este cenário confirmaram que o preço estendido é o único valor que haverá uma distribuições para. Portanto, o usuário não exigirá outro campo para determinar o valor do tipo a que estiver para distribuição. Entretanto, no cenário a seguir, nós ** ** usamos essas informações, como os requisitos do cenário que especificam outro valor tipos tem distribuições (por exemplo, imposto).
8.  ** Feito ** clique para sair do modo de edição.
9.  Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
10. Clique ** publicar o espaço de trabalho ** para salvar seu trabalho

** Observação: ** ** Contabilidade de exibição ** o página móvel não estiver vinculado atualmente a quaisquer páginas móveis disponíveis até criado. Como o usuário deve ser capaz navegar ** contabilidade de exibição a página ** ** detalhes de nota fiscal ** de página no dispositivo móvel, é devemos fornecer a navegação ** detalhes de nota fiscal ** de página ** contabilidade de exibição ** a página. Nós estabelecemos navegação esta usando a lógica adicional por JavaScript.

1.  Abra o arquivo de .js criado anteriormente, e adicionará linhas que são realçadas no código a seguir. Este código faz duas itens:
    1.  Ajuda a garantia que os usuários não conseguem navegar diretamente do espaço de trabalho ** contabilidade de exibição ** a página.
    2.  Liquida um controle de navegação ** detalhes de nota fiscal ** de página ** contabilidade de exibição ** a página.

> [!NOTE] 
> O nome das páginas e outros controles no código de JS deve ser o mesmo do espaço de trabalho.

1.  principal ou da função (metadataService, dataService, cacheService), $q {{appInit devolução: funções (appMetadata {) controla de ocultar de //necessárias estiverem presentes, mas não metadataService.configureControl visível (“Meu-fornecedor- faturas “, “ShowAccept,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowApprove,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowReject,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowDelegate,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowRequestChange,” {oculto: true});              metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowRecall,” {oculto: true});                metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowComplete,” {oculto: true});            metadataService.configureControl (“Meu-fornecedor- faturas “, “ShowResubmit,” {oculto: true});                Ocultar o de //pagina não aplicável para a navegação metadataService.hideNavigation raiz exibir contabilidade (“");                //Link para exibir metadataService.addLink contábeis (detalhes “a “, “exibir contabilidade”, “”, Exibição-contabilidade-NAV- controle de contabilidade “exibir verdadeiras,”);            }, pageInit: funções (pageMetadata, se params {) nota (detalhes de pageMetadata.Name == de ") //{mostrar/ocultar as ações de fluxo de trabalho com base em metadataService.configureAction etapa de fluxo de trabalho (“,” {aceitar visível: true});                    metadataService.configureAction aprovar (“,” {visível: true});                    rejeita metadataService.configureAction (“,” {visível: true});                    representante metadataService.configureAction (“,” {visível: true});                    metadataService.configureAction (Solicitação- alteração “,” {visível: true});                    metadataService.configureAction recuperação (“,” {visível: true});                    concluir metadataService.configureAction (“,” {visível: true});                    metadataService.configureAction reenviar (“,” {visível: true});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  Carregar o arquivo do código do espaço de trabalho selecionando ** lógica ** guia para substituir o código anterior
3.  ** Feito ** clique para sair do modo de edição.
4.  Clique ** retorno ** e ** feito ** para sair do espaço de trabalho
5.  Clique ** publicar o espaço de trabalho ** para salvar seu trabalho

### <a name="validation"></a>Validação

Do dispositivo móvel, abra o descritivo, e à alocação dynamics 365 para a instância de operações. Certifique-se de que se conectar à empresa em que as notas fiscais de fornecedor lhe foram atribuídas para revisão. Você deve ser capaz executar as seguintes ações:

-   Consulte ** minhas aprovações ** o espaço de trabalho.
-   Fure ** minhas aprovações ** o espaço de trabalho e consultar ** minhas faturas de fornecedor ** a página.
-   Em fure ** minhas ** faturas de fornecedor e a página consultam lista de faturas atribuídas.
-   Fure em uma das notas fiscais, consulte e os detalhes do cabeçalho de nota fiscal e os detalhes da linha.
-   Os detalhes, consulte a página um link para os anexos, e use este link para navegar até a lista de todos e exibir os anexos.
-   Os detalhes, consulte a página um link ** contabilidade de exibição ** a página, e use este link para navegar para a página de distribuições e exibir as distribuições.
-   Os detalhes, clique página ** ações ** o menu na parte inferior, e executar as ações de fluxo de trabalho que são aplicáveis à etapa de fluxo de trabalho.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Criando um cenário complexo de aprovação de nota fiscal de A Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Atributo de cenário</th>
<th>Resposta</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Os campos do cabeçalho de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?</td>
<td><ol>
<li>Nome do Fornecedor</li>
<li>Valor da fatura</li>
<li>Conta de fatura</li>
<li>Número da fatura</li>
<li>Data da fatura</li>
<li>Descrição da fatura</li>
<li>Data de Vencimento</li>
<li>Moeda da fatura</li>
</ol></td>
</tr>
<tr class="even">
<td>Os campos de nota fiscal desejará o usuário verá a experiência móvel, e em que ordem?</td>
<td><ol>
<li>Categoria de compras</li>
<li>Quantidade</li>
<li>Preço unitário</li>
<li>Valor líquido da linha</li>
<li>Valor do 1099</li>
</ol></td>
</tr>
<tr class="odd">
<td>Quantas linhas de nota fiscal antes em uma nota? Aplicar a regra 80-20 aqui e, otimizar-la para as 80.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Os usuários desejarão para consultar distribuições contábeis (codificação de nota fiscal) em dispositivo móvel durante revisões?</td>
<td>Sim</td>
</tr>
<tr class="odd">
<td>Quantas distribuições contábeis (preço bruto, impostos, encargos, etc houver) para uma linha de nota fiscal? Além disso, aplique a regra 80-20.</td>
<td>Preço bruto: Imposto 2: Encargos 2: 2</td>
</tr>
<tr class="even">
<td>Faturas também têm distribuições contábeis no cabeçalho de nota fiscal? Em caso afirmativo, as distribuições contábeis devem estar disponíveis em dispositivo?</td>
<td>Não usado</td>
</tr>
<tr class="odd">
<td>Os usuários desejarão para consultar todos para a fatura em dispositivo?</td>
<td>Sim</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Ano

Estas variações podem ser feitas para o cenário 1, com base nos requisitos do cenário. 2. Use esta seção como um ano concluir para aprender fins.

1.  Porque mais linhas de nota fiscal são esperadas no cenário 2, as seguintes alterações ao design ajudarão para otimizar a experiência de usuário no dispositivo móvel:
    1.  Em vez de linhas de nota fiscal de exibição da detalhes (como no cenário 1), os usuários podem selecionar para exibir linhas em uma página separada móvel.
    2.  Porque mais de uma linha de nota fiscal esperada está neste cenário, se VendMobileInvoiceAllDistributionTree ** ** a página é usado para criar a página de distribuições do celular (como no cenário 1), pode ser desconcertante para que o usuário correlacione linhas as distribuições. Use, portanto VendMobileInvoiceLineDistributionTree ** ** a página para criar distribuições da página.
    3.  Idealmente, distribuições devem ser mostradas no contexto de uma linha de nota fiscal neste cenário. Portanto, certifique-se de que o usuário pode furar em uma linha para exibir a página de distribuições. Use o recurso de link de página liquidar o drill-through, exatamente como você fez para cabeçalho e detalha páginas no cenário. 1.

2.  Porque mais de um tipo de valor deve em distribuições no cenário (2 impostos, encargos, etc), será útil mostrar descrição do tipo de valor. (É omitimos estas informações no cenário 1.)

## <a name="conclusion"></a>Conclusão
A plataforma celular e recursos de aplicativo permitem criar os cenários móveis que são otimizados para uma base de usuários em uma organização. Com base nos exemplos fornecidos neste tópico, poderá tentar outras variações e criar as experiências diferentes que atendem a uma necessidade específica.


